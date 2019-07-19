---
description: nulle
seo-description: nulle
seo-title: Domande frequenti su Attribution IQ
title: Domande frequenti su Attribution IQ
uuid: 90961172-869 d -4 ed 3-aba 5-52374 e 53 b 603
translation-type: tm+mt
source-git-commit: ab2cda6d10bfeee13262581578bcdb4746112296

---


# Domande frequenti su Attribution IQ

<table id="table_590341C2F0DA4511ADEFDC1DB49CD248"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Domanda </th> 
   <th colname="col2" class="entry"> Risposta </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>D: Perché a volte, quando si usano i nuovi modelli di attribuzione, l’elemento “Nessuno” riceve più valore del previsto?</b> </p> </td> 
   <td colname="col2"> <p>R: Questo è probabilmente dovuto all’intervallo di reporting selezionato come descritto <a href="../../../analyze/analysis-workspace/attribution-iq/attribution.md#section_BC71DA030E45487AA3C3F6ED247A3C4A" format="dita" scope="local">qui </a>. Si verifica soprattutto quando l’intervallo di reporting inizia il primo giorno del mese e si utilizza un lookback (finestra di reporting) per visitatore. Per acquisire ulteriori lookback di attribuzione (e ridurre l’elemento “Nessuno”), prova a impostare l’intervallo di reporting su un lasso di tempo più lungo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>D: A volte nel rapporto vengono visualizzate date al di fuori dell’intervallo di reporting durante l’utilizzo di modelli di attribuzione. Perché?</b> </p> </td> 
   <td colname="col2"> <p>R: Queste date aggiuntive vengono aggiunte dall’intervallo di lookback per il reporting dei visitatori descritto <a href="../../../analyze/analysis-workspace/attribution-iq/attribution.md" format="dita" scope="local">qui </a>. Nell’articolo <a href="https://helpx.adobe.com/analytics/kb/data-appearing-outside-reporting-window.html" format="html" scope="external">Visualizzazione di dati al di fuori dell’intervallo di reporting</a> viene spiegato perché al momento si verifica questa situazione. Adobe Analytics escluderà queste righe aggiuntive in una delle prossime versioni. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>D: È possibile utilizzare un intervallo di lookback personalizzato con i modelli di attribuzione?</b> </p> </td> 
   <td colname="col2"> <p>A: Currently, attribution models rely on either a visitor or visit lookback window - but either of these lookback windows are adjustable by either changing the reporting date range (for visitor lookback) or by using a custom visit definition as part of Virtual Report Suites and <a href="https://marketing.adobe.com/resources/help/en_US/reference/vrs-mobile-visit-processing.html" format="html" scope="external"> Context-Aware Sessions </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>D: Quando si deve utilizzare un lookback di attribuzione per “visita” rispetto a un lookback di attribuzione per “visitatore”?</b> </p> </td> 
   <td colname="col2"> <p>R: La scelta del lookback di attribuzione dipende dal caso di utilizzo. Se la conversione tipicamente ha un ciclo di considerazione più lungo (qualcosa che impiega più di una singola visita), è consigliato l’utilizzo di un lookback relativo ai visitatori, oppure la creazione di un VRS con una visita più lunga che rifletta più accuratamente il ciclo di considerazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>D: I modelli di attribuzione sono disponibili nei feed di dati o in Data Warehouse?</b> </p> </td> 
   <td colname="col2"> <p>R: No. Poiché i modelli di attribuzione vengono calcolati sul momento grazie all’<a href="https://marketing.adobe.com/resources/help/en_US/reference/vrs-report-time-processing.html" format="html" scope="external">elaborazione al momento della generazione del rapporto</a>, non è possibile riportarli nei feed di dati o in Data Warehouse. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>D: I modelli di attribuzione sono disponibili solo se si utilizza una suite di rapporti virtuali ed è abilitata l’elaborazione al momento della generazione del rapporto?</b> </p> </td> 
   <td colname="col2"> <p>R: No, anche se i modelli di attribuzione sfruttano l’<a href="https://marketing.adobe.com/resources/help/en_US/reference/vrs-report-time-processing.html" format="html" scope="external">elaborazione al momento della generazione del rapporto</a> nel back-end, sono anche disponibili per comodità sia per le suite di rapporti virtuali, sia per quelle di base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>D: Attribution IQ in Analysis Workspace supporta un modello di attribuzione basato sui dati o algoritmico?</b> </p> </td> 
   <td colname="col2"> <p>A: Questa funzione non è ancora disponibile in Analysis Workspace, ma è qualcosa su cui si sta lavorando attivamente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>D: Ci sono delle dimensioni o metriche non supportate da Attribution IQ?</b> </p> </td> 
   <td colname="col2"> <p>A: L'IQ attribuzione è supportato su tutte le dimensioni.</p> 
    <p>Le metriche <u>non</u> supportate (principalmente perché non avrebbero senso) includono: </p> 
    <ul id="ul_B12A1291DEEF41FDBAD110C4A9265234"> 
     <li id="li_245571C5377C45ADBAE6F735B91FCD1F"> Visitatori univoci </li> 
     <li id="li_000CA7680A0745D9860CA7D5F62288D4">Visite </li> 
     <li id="li_53CAD3ECAE54451BBB0750FB62AF1243">Occorrenze </li> 
     <li id="li_C589008CA92E4C69866E85EEEC88EF90"> Visualizzazioni pagina </li> 
     <li id="li_ACF8D24E3AC746E280DB0F71D4B772A3">Metriche A4T </li> 
     <li id="li_78BFE0A4F8024301A218C0415537F632">Metriche Tempo trascorso </li> 
     <li id="li_29774EEFE9A04759B7929EA35AA9BEAD">Non recapitate </li> 
     <li id="li_B163C6F24240465F85AB5C9792F0F013">Percentuale non recapitate </li> 
     <li id="li_CF065E227A634C77BC2C48C2A6EC849A">Ingressi </li> 
     <li id="li_ED962C5063B047F185EFC58EB43C661F">Uscite </li> 
     <li id="li_029F6D09433F48A38303E5C96E77480B">Pagine non trovate </li> 
     <li id="li_8410AF29208247B5B3E49F72208913BA">Ricerche </li> 
     <li id="li_8421F1D5F58148D98B1AB5C04FCCA9CF">Visite a pagina singola </li> 
     <li id="li_50D4EA0FF2E6438C8DD2A1B2EAD7B9D7">Accesso singolo </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>D: In che modo Attribution IQ è diverso dall’attribuzione in Data Workbench?</b> </p> </td> 
   <td colname="col2"> <p>R: Data Workbench offre in modo incrementale: </p> 
    <ul id="ul_5A8C979CDCD04FF5B9625C84B2678CC7"> 
     <li id="li_115DC58D4BDF40A4A0036E76F6E64158">La capacità di assegnare l’attribuzione per più sorgenti dati per visitatore, ad esempio impression di annunci e punto vendita. </li> 
     <li id="li_C31891A4D5594D93AF97340F6D3A2E3E">Modellazione algoritmica (<a href="https://marketing.adobe.com/resources/help/en_US/insight/client/c_attrib_algorithmic.html" format="html" scope="external">più adatta</a>). Attribution IQ include solo modelli basati su regole. </li> 
     <li id="li_749D5D11B34E40E9AB53908A38979CAA">Visualizzazioni aggiuntive, come ad esempio <a href="https://marketing.adobe.com/resources/help/en_US/insight/client/c_lat_tbls.html" format="html" scope="external">tabelle di latenza </a>. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>D: Attribution IQ funziona con origini di dati?</b> </p> </td> 
   <td colname="col2"> <p>R: Al momento Attribution IQ funziona con le origini di dati diverse da quelle a livello di riepilogo. </p> <p> Poiché le origini di dati a livello di riepilogo non sono associate a un identificatore visitatore di Analytics, non è possibile eseguire l’attribuzione avanzata. Sono supportate anche le origini di dati per ID transazione, a meno che sia utilizzata una suite di rapporti virtuali e che sia selezionata l’<a href="https://marketing.adobe.com/resources/help/en_US/reference/vrs-report-time-processing.html" format="html" scope="external">elaborazione al momento del rapporto</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>D: Attribution IQ funziona con l’integrazione <a href="https://marketing.adobe.com/resources/help/en_US/analytics/advertising/overview.html" format="html" scope="external">Advertising Analytics</a>?</b> </p> </td> 
   <td colname="col2"> <p>R: Le metriche integrate, che comprendono impression, costo, click, posizione media e punteggio medio, sono origini di dati a livello di riepilogo e quindi non sono compatibili con Attribution IQ. Tuttavia le dimensioni di tipo metadati (come tipo e parola chiave) funzionano con l’attribuzione se utilizzati con eventi o metriche standard di Analytics. </p> </td> 
  </tr> 
 </tbody> 
</table>

