# RAB
* bash package: yq, jq (brew install)
CAP Project by CF CLI
* accesso API 
ricercare API esposte dalla BTP (ex Destination Service)
https://api.sap.com/api/SAP_CP_CF_Connectivity_Destination/overview

* node ➜ /workspaces/regScale $ cf login
`API endpoint: https://api.cf.eu10.hana.ondemand.com/`
`Email: valentino.paderni@regestaitalia.it`
`Password: ****`

Select an org:
1. ClarexSrl_regestaprd
2. ClarexSrl_regestatest
3. Clarex Srl_SVILUPPO
...

Org (enter to skip): 3
Targeted org Clarex Srl_SVILUPPO.

Targeted space DEV.

* node ➜ /workspaces/regScale $ cf target

API endpoint:   https://api.cf.eu10.hana.ondemand.com
API version:    3.113.0
user:           valentino.paderni@regestaitalia.it
org:            Clarex Srl_SVILUPPO
space:          DEV

* node ➜ /workspaces/regScale $ cf s
Getting services in org Clarex Srl_SVILUPPO / space DEV as valentino.paderni@regestaitalia.it...

* Creao servizio destination
* node ➜ /workspaces/regScale $ cf cs destination lite vscode-vp00-destination
Creating service instance vscode-vp00-destination in org Clarex Srl_SVILUPPO / space DEV as valentino.paderni@regestaitalia.it...
OK
* Esistono Service Key nell'istanza del servizion interrogata?
* node ➜ /workspaces/regScale $ cf sk vscode-vp00-destination
Getting keys for service instance vscode-vp00-destination as valentino.paderni@regestaitalia.it...
No service key for service instance vscode-vp00-destination

* Creo una service KEY per l'istanza del servizio
* node ➜ /workspaces/regScale $ cf csk vscode-vp00-destination sk-vscode-vp00
Creating service key sk-vscode-vp00 for service instance vscode-vp00-destination as valentino.paderni@regestaitalia.it...
OK

* Ottengo il contenuto della service KEY creata per l'istanza
* node ➜ /workspaces/regScale $ cf service-key vscode-vp00-destination sk-vscode-vp00
Getting key sk-vscode-vp00 for service instance vscode-vp00-destination as valentino.paderni@regestaitalia.it...

{
 "clientid": "sb-clone9050d10b954b49b58b710455af983850!b43598|destination-xsappname!b404",

* Salvo il contenuto in un file locale 
> Elimina intestazioni non json nel file con editor
* node ➜ /workspaces/regScale $ cf service-key vscode-vp00-destination sk-vscode-vp00 > key.json

* Lettura tramite destination API delle destination
> curl -H "Authorization: Bearer $(skgat < key.json)" --verbose "$(skv uri)/destination-configuration/v1/subaccountDestinations"

* Creao una destination e come body uso sintassi yaml to read convertito in jason e std input [ $(yq r -j -) ]
> curl --data $(yq r - -o=json) -H "Authorization: Bearer $(skgat < key.json)" --verbose "$(skv uri)/destination-configuration/v1/subaccountDestinations"
