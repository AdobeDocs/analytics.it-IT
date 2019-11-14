---
description: La partecipazione del visitatore è una serie di metriche che consente di visualizzare la partecipazione tra le sessioni del visitatore nei canali di marketing, nelle campagne, nelle entrate e così via. Ad esempio, il credito per acquisti e ricavi può essere attribuito ad altri punti di contatto marketing che si verificavano prima della visita in cui ha avuto luogo l'ordine. L'analisi ad hoc fornisce la partecipazione dei visitatori attraverso le visite.
solution: Analytics
title: 'Partecipazione visitatore: Ad Hoc Analysis'
topic: Metrics
uuid: 567d627c-a2a8-4fbf-b3fd-abb1341e57a0
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Partecipazione visitatore: Ad Hoc Analysis

La partecipazione del visitatore è una serie di metriche che consente di visualizzare la partecipazione tra le sessioni del visitatore nei canali di marketing, nelle campagne, nelle entrate e così via. Ad esempio, il credito per acquisti e ricavi può essere attribuito ad altri punti di contatto marketing che si verificavano prima della visita in cui ha avuto luogo l'ordine. L'analisi ad hoc fornisce la partecipazione dei visitatori attraverso le visite.

**Entrate (Partecipazione)**: Distribuisce il credito di conversione tra tutte le pagine in un'unica visita che ha portato alla conversione, fino alla pagina di conversione.

**Entrate (Partecipazione Visitatore)**: Distribuisce il credito di conversione tra tutte le pagine e tra le visite, in base a un intervallo di tempo specificato.

**Esempio - Partecipazione alle entrate per più visite**

Un visitatore ha due visite al sito. L'evento di conversione si verifica durante la seconda visita, a pagina D, per $60 di ricavi:

![](assets/VisitorPaticipation.png)

Nel reporting, l'allocazione di conversione è la seguente:

* **Entrate**: Allocazione alla pagina.
* **Entrate (Partecipazione)**: Allocazione alla seconda visita.
* **Entrate (Partecipazione Visitatore)**: Allocate tra entrambe le visite.

<table id="table_91A7244E77854838A8392B49366FB445"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pagina </th> 
   <th colname="col2" class="entry"> Ricavi </th> 
   <th colname="col3" class="entry"> Entrate (Partecipazione) </th> 
   <th colname="col4" class="entry"> Entrate (Partecipazione Visitatore) </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Una  </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
   <td colname="col3"> <p>$60 </p> </td> 
   <td colname="col4"> <p>$60 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>B </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
   <td colname="col3"> <p>$60 </p> </td> 
   <td colname="col4"> <p>$60 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
   <td colname="col3"> <p>0 </p> </td> 
   <td colname="col4"> <p>$60 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D </p> </td> 
   <td colname="col2"> <p>$60 </p> </td> 
   <td colname="col3"> <p>$60 </p> </td> 
   <td colname="col4"> <p>$60 </p> </td> 
  </tr> 
 </tbody> 
</table>

