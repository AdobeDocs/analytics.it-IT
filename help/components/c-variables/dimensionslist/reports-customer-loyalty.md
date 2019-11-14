---
description: La fedeltà dei clienti rivela i modelli di acquisto dei clienti.
solution: Analytics
title: Fedeltà cliente
topic: Reports
uuid: 7dc30b57-7b18-4228-a6ab-6eb66b3d9402
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Fedeltà cliente

La fedeltà dei clienti rivela i modelli di acquisto dei clienti.

Il rapporto mostra i pattern di acquisto dei clienti in base a quattro categorie di fedeltà:

* Not a Customer
* Nuovo cliente
* Return Customer
* Cliente fedele

Anche se le metriche non di acquisto sono visibili in questo rapporto (come eventi personalizzati, eventi del carrello e così via), le categorie sono sempre basate sul numero di ordini inseriti. Ad esempio, un visitatore potrebbe aggiungere al rapporto un evento personalizzato denominato Internal Searches (Ricerche interne). L'elemento di [!UICONTROL Return Customer] riga mostra il numero di ricerche interne eseguite dai visitatori che hanno effettuato due acquisti in precedenza, non il numero di visitatori che hanno effettuato due ricerche interne.

**Elaborazione fedeltà cliente**

Le tabelle seguenti definiscono il modo in cui Analysis Workspace, Reporting e analisi, Analisi ad hoc e Data Warehouse elaborano attualmente la fedeltà dei clienti:

<table id="table_E6A5CA96BE5C47F29F09688A4D41BC60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> <p>Dopo il 19 maggio 2016 </p> </th> 
   <th colname="col3" class="entry"> <p>Tra il 21 aprile e il 19 maggio 2016 </p> <p>(non applicabile a Data Warehouse) </p> </th> 
   <th colname="col4" class="entry"> <p>Prima del 21 aprile 2016 </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Not a Customer </p> </td> 
   <td colname="col2"> <p>Visitatori che non hanno mai acquistato </p> </td> 
   <td colname="col3"> <p>Visitatori che hanno effettuato 0 acquisti fino alla fine di una visita. </p> </td> 
   <td colname="col4"> <p>Non disponibile. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nuovo cliente </p> </td> 
   <td colname="col2"> <p>Visitatori che hanno effettuato un singolo acquisto </p> </td> 
   <td colname="col3"> <p>Visitatori che hanno effettuato 1 acquisto fino alla fine della visita. </p> <p>(Se si è verificato un acquisto, lo stato del cliente è stato aggiornato alla visita successiva dopo tale acquisto). </p> </td> 
   <td colname="col4"> <p>Visitatori che hanno effettuato 0 acquisti fino alla fine della visita. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Return Customer </p> </td> 
   <td colname="col2"> <p>Visitatori che hanno effettuato 2 acquisti </p> </td> 
   <td colname="col3"> <p>Visitatori che hanno effettuato 2 acquisti fino alla fine della visita dove hanno effettuato il secondo acquisto. </p> <p>(Se si è verificato un acquisto, lo stato del cliente è stato aggiornato alla visita successiva dopo tale acquisto). </p> </td> 
   <td colname="col4"> <p>Visitatori che hanno effettuato 1 acquisto fino alla fine della visita in cui hanno effettuato tale acquisto. </p> <p>(Se si è verificato un acquisto, lo stato del cliente è stato aggiornato alla visita successiva dopo tale acquisto). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cliente fedele </p> </td> 
   <td colname="col2"> <p>Visitatori che hanno effettuato 3+ acquisti </p> </td> 
   <td colname="col3"> <p>Visitatori che hanno effettuato 3+ acquisti fino alla fine della visita dove hanno effettuato l'acquisto più recente. </p> <p>(Se si è verificato un acquisto, lo stato del cliente è stato aggiornato alla visita successiva dopo tale acquisto). </p> </td> 
   <td colname="col4"> <p>Visitatori che hanno effettuato 2+ acquisti fino alla fine della visita dove hanno effettuato l'acquisto più recente. </p> <p>(Se si è verificato un acquisto, lo stato del cliente è stato aggiornato alla visita successiva dopo tale acquisto). </p> </td> 
  </tr> 
 </tbody> 
</table>

| versione 14 Fedeltà cliente (corrente) |
|---|
| Nuovo cliente | 1 visita e 1 acquisto |
| Return Customer | Più di 1 visita e 2 acquisti |
| Cliente fedele | Più di 1 visita e 3+ acquisti |

Lo stato di fedeltà cambia subito dopo l’evento di acquisto all’interno della stessa visita. Ad esempio, un nuovo cliente (1 acquisto) effettua un acquisto e quindi si registra per una newsletter dopo tale acquisto all’interno della stessa visita. L’evento di registrazione della newsletter viene considerato un’interazione con il cliente a seguito della modifica dello stato di fedeltà del cliente subito dopo l’acquisto.
