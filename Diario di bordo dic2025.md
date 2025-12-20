# Diario attivita dic 2025

* e2e e deploy app fiori da BAS cliente a S4P
  * concetto di comunicaiton system SAML e USER based. Attenzione alle mail di cross autenticazione
  * esposizione servizi Z solo da dev tennant
  * gerarchia pacchetti e SW component e collegamento transport
  * creazione destination con SAML e certificati
  * legame Buisienss catalog, IAM app, ruolo e visualizzazione app in tile S4
* connessione da BAS regesta centrale
  * nonostante si possibile creare destination con autenticazioen Uer e PWD pare non funzionare. Andrebbe aperto incident o appfondito lato logging in ADT o tennant dev

* Ricerca in S4P punti di estensione modifica
  * usando ADT e ordinado tree DEV per oggetti rilasciati e SC e area app si trovano RAP BO e relativa documentazione per usare EML per CRUD
  * nell'ADT CUST impostare
  <img width="484" height="414" alt="image" src="https://github.com/user-attachments/assets/61d51353-b4d0-4759-8bac-7db2e25ba6b6" />
  * ricerca di BADI o EnSpot attraveso search tool. La parte gerarchica filtri permette di ricercare solo oggetti rilasciati e quindi CLAS o INTF, ma dev avere gia in canna il package. Pertanto usando il <img width="68" height="35" alt="image" src="https://github.com/user-attachments/assets/ae562775-50fc-46ba-9c12-3a9b0f1d262f" /> e impostando dei fitri e colonne di raggruppamento posso cercare per area applicativa come fosse il menu della SAP GUI eventuali BADI o EnhSpto
  <img width="663" height="302" alt="image" src="https://github.com/user-attachments/assets/4d2992d1-641c-46d4-9435-ad3e9b8f3400" />
  <img width="790" height="355" alt="image" src="https://github.com/user-attachments/assets/e004d4f2-e298-4270-8f68-25fd49342ac1" />
  avvia la ricerca
  poi selezionando <img width="39" height="33" alt="image" src="https://github.com/user-attachments/assets/b3903442-34fa-4219-8fa9-7275bac82ef4" /> si aggiunge la colonna application component e si imposta il raggruppamento via <img width="32" height="27" alt="image" src="https://github.com/user-attachments/assets/77452ad5-cd64-4db6-b1a2-9517704cde5c" /> e si ottiene quindi il risultato collassato se si imposta subito <img width="31" height="34" alt="image" src="https://github.com/user-attachments/assets/07278e4a-161c-41c7-8373-5c7a96e695dd" />
  

  






