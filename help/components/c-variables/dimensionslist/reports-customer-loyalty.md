---
description: La fedeltà dei clienti rivela i pattern di acquisto dei clienti.
seo-description: La fedeltà dei clienti rivela i pattern di acquisto dei clienti.
seo-title: Fedeltà cliente
solution: Analytics
title: Fedeltà cliente
topic: Rapporti
uuid: 7 dc 30 b 57-7 b 18-4228-a 6 ab -6 eb 66 b 3 d 9402
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Fedeltà cliente

La fedeltà dei clienti rivela i pattern di acquisto dei clienti.

Il rapporto mostra i pattern di acquisto dei clienti in base a quattro categorie di fedeltà:

* Non è un cliente
* Nuovo cliente
* Ritorno a capo
* Cliente leale

Sebbene in questo rapporto siano visualizzabili metriche non di acquisto (come eventi personalizzati, eventi del carrello acquisti e così via), le categorie sono sempre in base al numero di ordini inseriti. Ad esempio, un visitatore potrebbe aggiungere al rapporto un evento personalizzato denominato Ricerca interna. The [!UICONTROL Return Customer] line item would show the number of internal searches performed by visitors who have made two purchases previously, not the number of visitors who have made two internal searches.

**Elaborazione della fedeltà dei clienti**

Le tabelle seguenti definiscono come Analysis Workspace, Reporting e analisi, Analisi ad hoc e Data Warehouse elaborano la fedeltà cliente:

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
   <td colname="col1"> <p>Non è un cliente </p> </td> 
   <td colname="col2"> <p>Visitatori che non hanno mai acquistato </p> </td> 
   <td colname="col3"> <p>Visitatori che hanno effettuato 0 acquisti fino alla fine di una visita. </p> </td> 
   <td colname="col4"> <p>Non disponibile. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nuovo cliente </p> </td> 
   <td colname="col2"> <p>Visitatori che hanno effettuato un acquisto unico </p> </td> 
   <td colname="col3"> <p>Visitatori che hanno effettuato il 1 acquisto fino alla fine della visita. </p> <p>(Se si è verificato un acquisto, lo stato del cliente è stato aggiornato nella visita successiva dopo tale acquisto.) </p> </td> 
   <td colname="col4"> <p>Visitatori che hanno effettuato 0 acquisti fino alla fine della visita. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ritorno a capo </p> </td> 
   <td colname="col2"> <p>Visitatori che hanno effettuato 2 acquisti </p> </td> 
   <td colname="col3"> <p>Visitatori che hanno effettuato 2 acquisti fino alla fine della visita in cui hanno effettuato un acquisto a 2 nd. </p> <p>(Se si è verificato un acquisto, lo stato del cliente è stato aggiornato nella visita successiva dopo tale acquisto.) </p> </td> 
   <td colname="col4"> <p>Visitatori che hanno effettuato il 1 acquisto fino alla fine della visita in cui hanno effettuato l'acquisto. </p> <p>(Se si è verificato un acquisto, lo stato del cliente è stato aggiornato nella visita successiva dopo tale acquisto.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cliente leale </p> </td> 
   <td colname="col2"> <p>Visitatori che hanno effettuato acquisti 3 + </p> </td> 
   <td colname="col3"> <p>Visitatori che hanno effettuato 3 acquisti fino alla fine della visita in cui hanno effettuato acquisti più recenti. </p> <p>(Se si è verificato un acquisto, lo stato del cliente è stato aggiornato nella visita successiva dopo tale acquisto.) </p> </td> 
   <td colname="col4"> <p>Visitatori che hanno effettuato 2 acquisti fino alla fine della visita in cui hanno effettuato acquisti più recenti. </p> <p>(Se si è verificato un acquisto, lo stato del cliente è stato aggiornato nella visita successiva dopo tale acquisto.) </p> </td> 
  </tr> 
 </tbody> 
</table>

| versione 14 - Fedeltà cliente (corrente) |
|---|
| Nuovo cliente | 1 visite e 1 acquisto |
| Ritorno a capo | Più di 1 visite e 2 acquisti |
| Cliente leale | Più di 1 visite e 3 acquisti |

Lo stato di fedeltà cambia subito dopo l'evento di acquisto nella stessa visita. Ad esempio, un nuovo cliente (acquisto 1) effettua un acquisto e si registra per una newsletter dopo l'acquisto nella stessa visita. L'evento di registrazione newsletter è considerato un'interazione di ritorno cliente, in quanto lo stato di fedeltà cliente del visitatore è stato modificato immediatamente dopo l'acquisto.
