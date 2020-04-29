---
description: Puoi distribuire Gestione tag dinamica utilizzando una o più delle opzioni di hosting disponibili.
keywords: Analytics Implementation;implementation method;dynamic tag management;dtm;hosting;hosting options;akamai;self hosting;self-hosting;ftp delivery;ftp hosting;library download
title: Configurare le opzioni di hosting
topic: Developer and implementation
uuid: 04268f2d-e76f-4fe4-8fcc-f0db3a016502
translation-type: tm+mt
source-git-commit: 3fe3442eae1bdd8b90acffc9c25d184714613c16

---


# Configurare le opzioni di hosting

Potete eseguire la distribuzione [!UICONTROL Dynamic Tag Management] utilizzando una o più delle opzioni di hosting disponibili.

[!UICONTROL Dynamic Tag Management] fornisce una serie di opzioni per ospitare i file JavaScript richiesti.

Per informazioni dettagliate sull&#39;hosting, consultate [Incorpora codice e opzioni](https://docs.adobe.com/content/help/it-IT/dtm/using/client-side/client-side-information.html) di hosting nella documentazione del [!UICONTROL Dynamic Tag Management] prodotto.

Nella scheda Incorpora, selezionate un&#39;opzione di hosting.

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
   <td colname="col2"> <p> L'opzione di hosting più semplice da implementare. </p> <p>Rete di distribuzione globale. </p> <p>Aggiunge ulteriori dipendenze dell'infrastruttura di terze parti (ricerca DNS, disponibilità Akamai). </p> <p>Per ulteriori informazioni, consulta <a href="https://docs.adobe.com/content/help/en/dtm/using/client-side/deployment.html#concept_722B01555D0441ACBB052BC34DC5B67D"> Akamai</a> nella Documentazione prodotto Gestione tag dinamica. </p> </td> 
   <td colname="col3"> 
    <ol id="ol_EF148EF091A645B3962B084963B3C0B0"> 
     <li id="li_7ECE0C331EEE4907A563D581DF1DFEFE">Gestione tag dinamica genera librerie JavaScript personalizzate. </li> 
     <li id="li_8E2C858290EF4665B2F45ACAFA121CB3">Gestione tag dinamica esporta le librerie JavaScript personalizzate in Akamai. </li> 
     <li id="li_CE88B10B6E844A56BBB8C575A9363BA9">Il sito Web di destinazione fa riferimento alle librerie Gestione tag dinamica ospitate da Akamai direttamente a livello di pagina. </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Self-hosting: Distribuzione FTP </td> 
   <td colname="col2"> <p>Un approccio <span class="term"> push</span> , mediante il quale Gestione tag dinamica esporta librerie JavaScript personalizzate direttamente nell'host del server dei contenuti Web tramite il protocollo FTP. </p> <p>Questa soluzione richiede un server FTP e le credenziali per essere disponibili sul server di contenuti Web per pubblicare le modifiche alle librerie di gestione tag dinamica personalizzate. </p> <p>Per ulteriori informazioni, consulta <a href="https://docs.adobe.com/help/en/dtm/using/client-side/deployment.html#task_A7B37CB2C89941A4A4D1F9AF06FC493D"> FTP</a> nella Documentazione prodotto Gestione tag dinamica. </p> </td> 
   <td colname="col3"> 
    <ol id="ol_60348F9C991D4F2B9457006B0F98C834"> 
     <li id="li_24A141C3C7074BF9897C022A22CAE78C">Gestione tag dinamica genera librerie JavaScript personalizzate. </li> 
     <li id="li_E1E0843060F7447E853EA416A0B033BE">Gestione tag dinamica esporta le librerie JavaScript personalizzate nel server host tramite FTP. </li> 
     <li id="li_EAF5D2ABD03B4911A0CFA464AD8791CE">Il sito Web di destinazione fa riferimento localmente alle librerie di gestione tag dinamica. </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Self-hosting: Download libreria </td> 
   <td colname="col2"> <p>Un approccio <span class="term"> pull</span> , mediante il quale l'applicazione esporta librerie JavaScript personalizzate <!-- to Amazon S3-->. In questo caso, l'accesso alle librerie è possibile tramite un processo lato server ospitato. </p> <p>Inoltre, le librerie sono disponibili tramite download Web direttamente dall'interfaccia Gestione tag dinamica. </p> <p>Questa soluzione richiede il recupero e la pubblicazione manuali delle librerie Gestione tag dinamica o la creazione di un processo automatizzato che estrae le librerie da Akamai sul server dei contenuti Web. </p> <p>Questo approccio richiede il massimo tempo per la configurazione, ma è anche l'opzione più sicura e flessibile. </p> <p>Per verificare se esiste un riferimento alla versione più recente del file libreria, utilizza il comando </p> <p>Per ulteriori informazioni, consulta<a href="https://docs.adobe.com/content/help/en/dtm/using/client-side/deployment.html#task_B7A42F3B1D3E4B71B0BADD17C181F22A"> Library Download</a> nella Documentazione prodotto Gestione tag dinamica. </p> </td> 
   <td colname="col3"> 
    <ol id="ol_F40B721306FE473496BD657262DFD585"> 
     <li id="li_4EA4D6B555CE4E9CA476C7550C18C061">Gestione tag dinamica genera librerie JavaScript personalizzate. </li> 
     <li id="li_BA40EBD7AD1546F29D8A209034D06477">Gestione tag dinamica esporta le librerie JavaScript personalizzate in Akamai. </li> 
     <li id="li_E107E69E386A40F3B067F9991C2979AF">Le librerie Gestione tag dinamica personalizzata vengono spostate manualmente o a livello di programmazione nel server del contenuto Web. </li> 
     <li id="li_0809038453B544168A20CE09D7E5AC59">Il sito Web di destinazione fa riferimento localmente alle librerie di gestione tag dinamica. </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

Potete utilizzare più di un&#39;opzione di hosting. Ad esempio, potete ospitare i file sullo stage utilizzando Akamai, ma potete ospitare autonomamente il sito di produzione. Ogni tipo di host dispone di un proprio codice da incorporare e a una pagina è possibile aggiungere un solo codice da incorporare.
