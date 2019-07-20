---
description: Visualizza il numero di visite effettuate all'intero sito Web nel corso di un periodo di tempo specificato.
seo-description: Visualizza il numero di visite effettuate all'intero sito Web nel corso di un periodo di tempo specificato.
seo-title: Visite
solution: Analytics
title: Visite
topic: Rapporti
uuid: ff 65 bddf-fb 65-4 cf 0-8 aae -4 ab 59 c 2 bb 0 a 7
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Visite

Visualizza il numero di visite effettuate all'intero sito Web nel corso di un periodo di tempo specificato.

**Proprietà rapporto**

* Una visita viene definita come sequenza di visualizzazioni di pagina consecutive senza un'interruzione di 30 minuti o un'attività continua per 12 ore.
* Dopo la scadenza di una visita, viene avviata una nuova visita su qualsiasi richiesta di immagine successiva.
* In genere, un visitatore contiene almeno una visita (ma probabilmente più di una).
* L'inizio di una visita è la prima richiesta di immagine proveniente da un nuovo visitatore, o dopo la scadenza di una visita dell'utente esistente. Può essere identificato come Pagina di entrata.
* La fine di una visita è l'ultima richiesta dell'immagine prima della scadenza di una visita. Può essere identificato come Pagina di uscita.

   See [Entries and Exits Reports](../../../components/c-variables/dimensionslist/reports-entries-exits.md#concept_C4AED2C1D62E43A48ACAA837327FCCF2).
* Le suddivisioni orarie si basano sul fuso orario della suite di rapporti.
* Questo rapporto non contiene elementi della riga. La puoi visualizzare solo nel formato con tendenze.
* È possibile applicare un mese, un giorno, una settimana, un mese, un trimestre e un anno. Queste impostazioni di granularità sono disponibili a seconda dell'intervallo di date del rapporto.

See [Visit Metric](../../../components/c-variables/c-metrics/metrics-visit.md#concept_9DA4D9EF8B964755BAC57378AD37911E) for more information about how the Experience Cloud processes this metric.

**Informazioni sui report specifici del prodotto**

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
   <td colname="col2"> <p> <span class="uicontrol"> Metriche del sito</span> &gt; <span class="uicontrol"> Visite</span> </p> <p>You can run a <span class="wintitle"> Visits Report</span> on a selected page. Le visite su mezzanotte vengono conteggiate nel giorno in cui la visita è iniziata e terminata. Tuttavia, il totale dell'intervallo di date specificato viene deduplicato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Ad Hoc Analysis </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Rapporti</span> &gt; <span class="uicontrol"> Metriche del sito</span> &gt; <span class="uicontrol"> Visite</span> </p> 
    <ul id="ul_73FEE02C129041D6A63F2DB07676960F"> 
     <li id="li_CC3BB22DE97941EB8032BE4421FFC173"> Puoi suddividere ogni elemento del rapporto in base a quasi tutti gli altri report e variabili, per visualizzare le suddivisioni in base a qualsiasi granularità. </li> 
     <li id="li_D53D480D73264D47945C9E1202B7BD4F">Le visite su mezzanotte vengono conteggiate nel giorno in cui la visita è iniziata e terminata. Tuttavia, il totale dell'intervallo di date specificato viene duplicato. </li> 
     <li id="li_B8BCC584F95B407DB87F5EA57CC88F62">In questo rapporto puoi utilizzare tutte le metriche di conversione e traffico e utilizzare allocazione diversa per tutte le metriche di conversione. </li> 
     <li id="li_0F342D3DCFF44ABAB79BD0F9E7F43E1E">Questo rapporto può utilizzare più segmenti altamente avanzati. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

