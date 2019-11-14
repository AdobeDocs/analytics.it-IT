---
description: Visualizza il numero di visite effettuate all’intero sito Web durante un periodo di tempo specificato.
solution: Analytics
title: Visite
topic: Reports
uuid: ff65bddf-fb65-4cf0-8aae-4ab59c2bb0a7
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Visite

Visualizza il numero di visite effettuate all’intero sito Web durante un periodo di tempo specificato.

**Proprietà report**

* Una visita è definita come una sequenza di visualizzazioni di pagina consecutive senza un'interruzione di 30 minuti, o un'attività continua per 12 ore.
* Dopo la scadenza di una visita, viene avviata una nuova visita su qualsiasi richiesta di immagine successiva.
* Un visitatore in genere contiene almeno una (ma probabilmente più di una) visita.
* L’inizio di una visita è la prima richiesta di immagine proveniente da un nuovo visitatore, o dopo che la visita di un utente esistente è scaduta. Questo può essere identificato come pagina di immissione.
* La fine di una visita è l’ultima richiesta di immagine prima della scadenza di una visita. Questo può essere identificato come pagina di uscita.

   Consulta Rapporti [di entrata ed uscita](/help/components/c-variables/dimensionslist/reports-entries-exits.md).
* Le suddivisioni orari si basano sul fuso orario della suite di rapporti.
* Questo rapporto non contiene elementi di riga. La visualizzate solo nel formato con tendenze.
* È possibile applicare la granularità di ora, giorno, settimana, mese, trimestre e anno. Queste impostazioni di granularità sono disponibili a seconda dell’intervallo di date del rapporto.

Per ulteriori informazioni sull’elaborazione di questa metrica da parte di Experience Cloud, vedi [Metrica](/help/components/c-variables/c-metrics/metrics-visit.md) .

**Informazioni specifiche del prodotto**

<table id="table_3138CA443CAC4F55838216E8B8786EE2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Prodotto </th> 
   <th colname="col2" class="entry"> Navigazione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Reporting e analisi </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Metriche</span> del sito &gt; <span class="uicontrol"> Visite</span> </p> <p>Puoi eseguire un rapporto <span class="wintitle"> sulle</span> visite su una pagina selezionata. Le visite che si estendono su tutta la mezzanotte sono conteggiate sia nel giorno in cui la visita ha avuto inizio che in cui è terminata. Tuttavia, il totale per l'intervallo di date specificato viene deduplicato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Ad Hoc Analysis </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Rapporti</span> &gt; <span class="uicontrol"> Metriche</span> del sito &gt; <span class="uicontrol"> Visite</span> </p> 
    <ul id="ul_73FEE02C129041D6A63F2DB07676960F"> 
     <li id="li_CC3BB22DE97941EB8032BE4421FFC173"> È possibile suddividere ciascun elemento in questo rapporto per quasi tutti gli altri rapporti e variabili, consentendo di visualizzare le suddivisioni per ogni granularità. </li> 
     <li id="li_D53D480D73264D47945C9E1202B7BD4F">Le visite che si estendono su tutta la mezzanotte sono conteggiate sia nel giorno in cui la visita ha avuto inizio che in cui è terminata. Tuttavia, il totale per l'intervallo di date specificato è deduplicato. </li> 
     <li id="li_B8BCC584F95B407DB87F5EA57CC88F62">Puoi utilizzare tutte le metriche di conversione e traffico in questo rapporto, nonché utilizzare un'allocazione diversa per tutte le metriche di conversione. </li> 
     <li id="li_0F342D3DCFF44ABAB79BD0F9E7F43E1E">Questo rapporto può utilizzare più segmenti altamente avanzati. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

