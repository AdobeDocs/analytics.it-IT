---
description: 'null'
title: Implementazione roadmap
uuid: 988bcca5-67ae-4e3f-97e6-6a42030b1962
translation-type: tm+mt
source-git-commit: 9d0b8e1e9bc2d92fb949ceed7bcfaa31818d02b8

---


# Implementazione roadmap

## Nuovi utenti {#section_77433E4FC5ED4C6BAFC1E72EB61C4503}

Se non hai mai utilizzato Adobe Analytics, puoi creare rapidamente la tua prima suite di rapporti Analytics (archivio dati) utilizzando la guida [Guida introduttiva ad Adobe Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/getting-started/) . Quindi, puoi distribuire il codice Analytics utilizzando [Experience Platform Launch](https://docs.adobelaunch.com/).

## Implementation Roadmap {#section_E3DD8D199B744FFB9E9B386A44220206}

<table id="table_1683413EA0E34DBC9291832647B68E96"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> Passaggio </th> 
   <th colname="col1" class="entry"> Attività </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <img  src="assets/step1_icon.png" id="image_21F30BBFC0A249F8B0E1A50EBBEED77D" /> </td> 
   <td colname="col1"> Scegliere un metodo di implementazione. </td> 
   <td colname="col2"> <p>I metodi comuni per implementare Analytics includono: </p> <p> 
     <ul id="ul_A7475867861540EFBD77AEE8C6DAD418"> 
      <li id="li_035E2619670F4D04A7F708625A9C01EF"> <a href="https://docs.adobelaunch.com/"> Lancio della piattaforma Experience </a> (consigliato) <p>Questa guida descrive tutto ciò che è necessario sapere sull’utilizzo delle funzionalità di gestione dei tag del sito Web e dell’SDK per dispositivi mobili di Adobe e su come implementarle. </p> </li> 
      <li id="li_996FA2F5B0E149399CED391AB5235D8A"> <a href="/help/implement/c-implement-with-dtm/dtm-implementation-overview.md"> Dynamic Tag Management </a> <p>Questa guida contiene informazioni specifiche di Analytics per guidarti attraverso un’implementazione di Gestione tag dinamica. </p> </li> 
      <li id="li_18E6AD6D864246D0BA26DAA1D91DD811"> <a href="/help/implement/js-implementation/javascript-implementation-overview.md"> JavaScript </a> <p>Questa guida contiene una descrizione delle variabili di raccolta dati e informazioni dettagliate sull'implementazione del codice di raccolta dati in JavaScript, incluso <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/video/video_js.html"> il video </a>. </p> </li> 
      <li id="li_85EC7A0AC5E04EE6981ED72A88C5D1FD"> <a href="https://marketing.adobe.com/resources/help/en_US/reference/developer.html"> SDK di Analytics </a> <p>Usa gli SDK di Analytics per gestire: </p> <p> 
        <ul id="ul_F67F2E1964724800A84445A36DFB8E86"> 
         <li id="li_9C43F051EB5B4EA7A4C14EC1513DB824"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/analytics_main.html"> App mobili su iOS </a> </li> 
         <li id="li_4354E44EB8B3494A88578C1621EF5BAC"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/analytics_main.html"> App mobili su Android </a> </li> 
        </ul> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step2_icon.png" id="image_02CFDC007BF1486AA312698EBFFA79F7" /> </td> 
   <td colname="col1"> Configurare il servizio identità. </td> 
   <td colname="col2"> <p>(Formerly <span class="term"> Visitor ID service </span>.) Consultate <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-setup-analytics.html"> Configurare il servizio identità per Analytics </a>. </p> 
    <draft-comment> 
     <p>In <code> VisitorAPI.js </code>, aggiungi il seguente codice di inizializzazione ID visitatore all’inizio del file: </p> 
     <code class="syntax javascript">
       var&nbsp;visitor&nbsp;=&nbsp;Visitor.getInstance("INSERT-MCORG-ID-HERE"); 
      visitor.trackingServer&nbsp;=&nbsp;"INSERT-TRACKING-SERVER-HERE";&nbsp;//&nbsp;same&nbsp;as&nbsp;s.trackingServer 
      visitor.trackingServerSecure&nbsp;=&nbsp;"INSERT-SECURE-TRACKING-SERVER-HERE";&nbsp;//same&nbsp;as&nbsp;s.trackingServerSecure 
      /* 
      &nbsp;==============&nbsp;DO&nbsp;NOT&nbsp;ALTER&nbsp;ANYTHING&nbsp;BELOW&nbsp;THIS&nbsp;LINE&nbsp;!&nbsp;============
     </code> 
     <ul id="ul_769BA118CC244308A805079C2CBECC12"> 
      <li id="li_D366EBDE24CB433EA523DB228CB2FAF1"> <code> "INSERT-MCORG-ID-HERE" </code> - (Obbligatorio) Questo ID organizzazione Adobe Experience Cloud viene inviato all'amministratore quando la società effettua il provisioning per Adobe Experience Cloud. </li> 
      <li id="li_4F9704A6A6EA4334A3758F99B8D67C9D"> <code> "INSERT-TRACKING-SERVER-HERE" </code> - (Obbligatorio) Il server di tracciamento di Analytics. </li> 
      <li id="li_C578420458D649228E54D9809AF62627"> <code> "INSERT-SECURE-TRACKING-SERVER-HERE" </code> - (Obbligatorio se ssl è abilitato) Il server di tracciamento protetto di Analytics. </li> 
     </ul> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step3_icon.png" id="image_76B61DEABE3849CCB39135FDD7399EAA" /> </td> 
   <td colname="col1"> Utilizza il metodo di implementazione scelto per aggiornare e distribuire il codice della pagina. </td> 
   <td colname="col2"> <p>Posizionare il codice della pagina subito dopo il <code> &lt;body&gt; </code> tag di apertura su ogni pagina da monitorare. Come minimo, aggiorna le seguenti variabili: </p> 
    <ul id="ul_29200A6E8DA14386BDA242AD8B270FEB"> 
     <li id="li_FB24D2CB9241401A83BD13EE342A7810"> <code> var s=s_gi("INSERT-RSID-HERE") </code> </li> 
     <li id="li_463A35BA06CC4618B4AF17CD7E83AED5"> <code> s.pageName="INSERT-NAME-HERE" // for example, s.pageName=document.title </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step4_icon.png" id="image_844E896941E2489A943BE10AD710ED36" /> </td> 
   <td colname="col1"> Usa Adobe Experience Cloud Debugger per verificare che i dati vengano inviati. </td> 
   <td colname="col2"> <p>Install the <a href="/help/implement/impl-testing/debugger.md"> Experience Cloud Debugger </a>. Una volta installato, carica una pagina in cui hai distribuito il codice della pagina e apri il debugger. Il debugger visualizza i dettagli relativi ai dati di raccolta inviati. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ulteriori informazioni {#section_64B6A948DF4A4B5E9E1D22549F8C508B}

Per informazioni sulle differenze tra metodi [!UICONTROL Experience Platform Launch], [!UICONTROL Dynamic Tag Management]e JavaScript, vedere [Scegliere un metodo](/help/implement/c-implementation-methods/choose-implementation-method.md)di implementazione.

Per una breve panoramica del processo iniziale e per assistenza sulla configurazione rapida della prima suite di rapporti di Analytics, consulta [Guida introduttiva all’implementazione](https://marketing.adobe.com/resources/help/en_US/dtm/get_started.html) di Analytics nella guida introduttiva ad Analytics.
