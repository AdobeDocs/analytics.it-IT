---
description: Puoi implementare Gestione tag dinamica utilizzando una o più opzioni di hosting disponibili.
keywords: Implementazione di Analytics; metodo di implementazione; gestione tag dinamica; dtm; hosting; opzioni di hosting; akamai; hosting autonomo; self-hosting; ftp delivery; host ftp; download della libreria
seo-description: Puoi implementare Gestione tag dinamica utilizzando una o più opzioni di hosting disponibili.
seo-title: Configurare le opzioni di hosting
solution: Analytics
title: Configurare le opzioni di hosting
topic: Sviluppatore e implementazione
uuid: 04268 f 2 d-e 76 f -4 fe 4-8 fcc-f 0 db 3 a 016502
translation-type: tm+mt
source-git-commit: 6250335d05c8e7799802fce26192896a7a6598fe

---


# Configurare le opzioni di hosting

You can deploy [!UICONTROL Dynamic Tag Management] using one or more of the available hosting options.

[!UICONTROL Dynamic Tag Management] fornisce una serie di opzioni per ospitare i file javascript richiesti.

For detailed information about hosting, see [Embed Code and Hosting Options](https://marketing.adobe.com/resources/help/en_US/dtm/deployment.html) in the [!UICONTROL Dynamic Tag Management] Product Documentation.

Nella scheda Incorpora, selezionate un'opzione di hosting.

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
   <td colname="col2"> <p> L'opzione di hosting più semplice da implementare. </p> <p>Rete di consegna distribuita a livello globale. </p> <p>Aggiunge ulteriori dipendenze infraparte di terze parti (ricerca DNS, disponibilità Akamai). </p> <p>For more detailed information, see <a href="https://marketing.adobe.com/resources/help/en_US/dtm/akamai.html" format="html" scope="external"> Akamai</a> in the Dynamic Tag Management Product Documentation. </p> </td> 
   <td colname="col3"> 
    <ol id="ol_EF148EF091A645B3962B084963B3C0B0"> 
     <li id="li_7ECE0C331EEE4907A563D581DF1DFEFE">Gestione tag dinamica genera librerie javascript personalizzate. </li> 
     <li id="li_8E2C858290EF4665B2F45ACAFA121CB3">Gestione tag dinamica esporta le librerie javascript personalizzate in Akamai. </li> 
     <li id="li_CE88B10B6E844A56BBB8C575A9363BA9">Il sito Web di destinazione fa riferimento alle librerie di Gestione tag dinamica di Akamai direttamente a livello di pagina. </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hosting autonomo: Consegna FTP </td> 
   <td colname="col2"> <p>A <span class="term"> push</span> approach, whereby Dynamic Tag Management exports custom JavaScript libraries directly to the web content server host via the FTP protocol. </p> <p>Per pubblicare le modifiche alle librerie di gestione tag dinamica personalizzate, questa soluzione richiede un server FTP e le credenziali che devono essere disponibili sul server del contenuto Web. </p> <p>For more detailed information, see <a href="https://marketing.adobe.com/resources/help/en_US/dtm/deployment_ftp.html" format="html" scope="external"> FTP</a> in the Dynamic Tag Management Product Documentation. </p> </td> 
   <td colname="col3"> 
    <ol id="ol_60348F9C991D4F2B9457006B0F98C834"> 
     <li id="li_24A141C3C7074BF9897C022A22CAE78C">Gestione tag dinamica genera librerie javascript personalizzate. </li> 
     <li id="li_E1E0843060F7447E853EA416A0B033BE">Gestione tag dinamica esporta le librerie javascript personalizzate sul server host tramite FTP. </li> 
     <li id="li_EAF5D2ABD03B4911A0CFA464AD8791CE">Il sito Web di destinazione fa riferimento a librerie dinamiche di Gestione tag dinamica. </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hosting autonomo: Download libreria </td> 
   <td colname="col2"> <p>A <span class="term"> pull</span> approach, whereby the application exports custom JavaScript libraries
     <!-- to Amazon S3-->. In tal caso, è possibile accedere alle librerie mediante un processo sul lato server. </p> <p>Inoltre, le librerie sono disponibili tramite il download Web direttamente dall'interfaccia di Gestione tag dinamica. </p> <p>Questa soluzione richiede un recupero manuale e una pubblicazione delle librerie di Gestione tag dinamica o la creazione di un processo automatizzato che estrae le librerie da Akamai sul server del contenuto Web. </p> <p>Questo approccio richiede più tempo, ma è anche l'opzione più sicura e flessibile. </p> <p>Per verificare se viene fatto riferimento alla versione più recente del file libreria, utilizzate il comando </p> <p>For more detailed information, see<a href="https://marketing.adobe.com/resources/help/en_US/dtm/deployment_download.html" format="html" scope="external"> Library Download</a> in the Dynamic Tag Management Product Documentation. </p> </td> 
   <td colname="col3"> 
    <ol id="ol_F40B721306FE473496BD657262DFD585"> 
     <li id="li_4EA4D6B555CE4E9CA476C7550C18C061">Gestione tag dinamica genera librerie javascript personalizzate. </li> 
     <li id="li_BA40EBD7AD1546F29D8A209034D06477">Gestione tag dinamica esporta le librerie javascript personalizzate in Akamai. </li> 
     <li id="li_E107E69E386A40F3B067F9991C2979AF">Le librerie di gestione tag dinamica personalizzate vengono spostate manualmente o spostate a livello di programmazione sul server Web. </li> 
     <li id="li_0809038453B544168A20CE09D7E5AC59">Il sito Web di destinazione fa riferimento a librerie dinamiche di Gestione tag dinamica. </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

Potete utilizzare più di un'opzione di hosting. Ad esempio, potete ospitare i file staging utilizzando Akamai, ma potete ospitare autonomamente il sito di produzione. Ogni tipo di host ha un proprio codice da incorporare e un solo codice da incorporare può essere aggiunto a una pagina.
