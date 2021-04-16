---
description: Puoi distribuire Dynamic Tag Management utilizzando una o più delle opzioni di hosting disponibili.
keywords: Implementazione di Analytics;metodo di implementazione;gestione tag dinamica;dtm;hosting;opzioni di hosting;akamai;self hosting;self hosting;consegna ftp;hosting ftp;download libreria
title: Configurare le opzioni di hosting
topic-fix: Developer and implementation
uuid: 04268f2d-e76f-4fe4-8fcc-f0db3a016502
exl-id: cef5205e-bb21-4d8d-862b-33dc800e1118
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 3%

---

# Configurare le opzioni di hosting

Puoi distribuire [!UICONTROL Dynamic Tag Management] utilizzando una o più delle opzioni di hosting disponibili.

[!UICONTROL Dynamic Tag Management] fornisce una serie di opzioni per ospitare i file JavaScript richiesti.

Per informazioni dettagliate sull&#39;hosting, consulta [Opzioni di hosting e codice di incorporamento](https://docs.adobe.com/content/help/it-IT/dtm/using/client-side/client-side-information.html) nella [!UICONTROL Dynamic Tag Management] documentazione del prodotto.

Nella scheda Incorpora , seleziona un’opzione di hosting.

<table id="table_229298207DB64838B6F2477DFFAE073F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opzione di hosting </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
   <th colname="col3" class="entry"> Implementazione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Akamai </p> </td> 
   <td colname="col2"> <p> L'opzione di hosting più semplice da implementare. </p> <p>Rete di distribuzione globale. </p> <p>Aggiunge dipendenze aggiuntive dell’infrastruttura di terze parti (ricerca DNS, disponibilità Akamai). </p> <p>Per informazioni più dettagliate, consulta <a href="https://docs.adobe.com/content/help/en/dtm/using/client-side/deployment.html#concept_722B01555D0441ACBB052BC34DC5B67D"> Akamai</a> nella Documentazione del prodotto Dynamic Tag Management. </p> </td> 
   <td colname="col3"> 
    <ol id="ol_EF148EF091A645B3962B084963B3C0B0"> 
     <li id="li_7ECE0C331EEE4907A563D581DF1DFEFE">Dynamic Tag Management genera librerie JavaScript personalizzate. </li> 
     <li id="li_8E2C858290EF4665B2F45ACAFA121CB3">Dynamic Tag Management esporta le librerie JavaScript personalizzate in Akamai. </li> 
     <li id="li_CE88B10B6E844A56BBB8C575A9363BA9">Il sito web di destinazione fa riferimento alle librerie Dynamic Tag Management ospitate da Akamai direttamente a livello di pagina. </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hosting autonomo: Consegna FTP </td> 
   <td colname="col2"> <p>Un approccio <span class="term"> push</span>, grazie al quale Dynamic Tag Management esporta librerie JavaScript personalizzate direttamente all’host del server dei contenuti web tramite il protocollo FTP. </p> <p>Questa soluzione richiede un server FTP e le credenziali per essere disponibili sul server dei contenuti web per pubblicare le modifiche alle librerie di Dynamic Tag Management personalizzate. </p> <p>Per informazioni più dettagliate, consulta <a href="https://docs.adobe.com/help/en/dtm/using/client-side/deployment.html#task_A7B37CB2C89941A4A4D1F9AF06FC493D"> FTP</a> nella Documentazione del prodotto Dynamic Tag Management . </p> </td> 
   <td colname="col3"> 
    <ol id="ol_60348F9C991D4F2B9457006B0F98C834"> 
     <li id="li_24A141C3C7074BF9897C022A22CAE78C">Dynamic Tag Management genera librerie JavaScript personalizzate. </li> 
     <li id="li_E1E0843060F7447E853EA416A0B033BE">Dynamic Tag Management esporta le librerie JavaScript personalizzate al server host tramite FTP. </li> 
     <li id="li_EAF5D2ABD03B4911A0CFA464AD8791CE">Il sito web di destinazione fa riferimento localmente alle librerie di Dynamic Tag Management personalizzate. </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hosting autonomo: Download libreria </td> 
   <td colname="col2"> <p>Un approccio <span class="term"> pull</span>, in base al quale l’applicazione esporta librerie JavaScript personalizzate
     <!-- to Amazon S3-->. In questo caso, è possibile accedere alle librerie tramite un processo ospitato lato server. </p> <p>Inoltre, le librerie sono disponibili tramite download web direttamente dall’interfaccia Dynamic Tag Management. </p> <p>Questa soluzione richiede un recupero e una pubblicazione manuali delle librerie Dynamic Tag Management o la creazione di un processo automatizzato che estrae le librerie da Akamai sul server dei contenuti web. </p> <p>Questo approccio richiede il massimo tempo per la configurazione, ma è anche l'opzione più sicura e flessibile. </p> <p>Per verificare che venga fatto riferimento alla versione più recente del file di libreria, utilizza il comando </p> <p>Per informazioni più dettagliate, consulta<a href="https://docs.adobe.com/content/help/en/dtm/using/client-side/deployment.html#task_B7A42F3B1D3E4B71B0BADD17C181F22A"> Library Download</a> nella Documentazione del prodotto Dynamic Tag Management. </p> </td> 
   <td colname="col3"> 
    <ol id="ol_F40B721306FE473496BD657262DFD585"> 
     <li id="li_4EA4D6B555CE4E9CA476C7550C18C061">Dynamic Tag Management genera librerie JavaScript personalizzate. </li> 
     <li id="li_BA40EBD7AD1546F29D8A209034D06477">Dynamic Tag Management esporta le librerie JavaScript personalizzate in Akamai. </li> 
     <li id="li_E107E69E386A40F3B067F9991C2979AF">Le librerie Dynamic Tag Management personalizzate vengono spostate manualmente o programmaticamente nel server dei contenuti web. </li> 
     <li id="li_0809038453B544168A20CE09D7E5AC59">Il sito web di destinazione fa riferimento localmente alle librerie di Dynamic Tag Management personalizzate. </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

Puoi utilizzare più di un&#39;opzione di hosting. Ad esempio, puoi ospitare i file di staging utilizzando Akamai, ma self-host del sito di produzione. Tieni presente che ogni tipo di hosting dispone di un proprio codice di incorporamento e che è possibile aggiungere a una pagina un solo codice di incorporamento.
