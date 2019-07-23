---
description: Per iniziare a utilizzare Analytics, i dati devono essere inviati a una suite di rapporti per essere visualizzati nei rapporti.
keywords: Implementazione di Analytics; javascript; implementazione javascript; appmeasurement; appmeasurement del download; Servizio identità; visitorapi. js; memorizzazione nella cache; compressione delle app
seo-description: Per iniziare a utilizzare Analytics, i dati devono essere inviati a una suite di rapporti per essere visualizzati nei rapporti.
seo-title: Panoramica sull'implementazione javascript
solution: Analytics
title: Panoramica sull'implementazione javascript
topic: Sviluppatore e implementazione
uuid: bb 661 d 8 c-faf 9-4454-ac 3 c -0 c 1 a 4 c 0 a 9336
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Panoramica sull'implementazione javascript

Per iniziare a utilizzare Analytics, i dati devono essere inviati a una suite di rapporti per essere visualizzati nei rapporti.

The easiest and recommended way to send data to [!DNL Analytics] is by using [Dynamic Tag Management](../../implement/c-implement-with-dtm/dtm-implementation-overview.md). Tuttavia, in alcuni casi, potrebbe essere utile implementare Analytics utilizzando il metodo javascript precedente.

>[!NOTE]
>
>Questa sezione descrive il metodo legacy di implementazione di Analytics. All Analytics customers have access to [Dynamic Tag Management](https://marketing.adobe.com/resources/help/en_US/dtm/) which is the standard method to deploy Experience Cloud tags.

## Passaggi di implementazione {#section_73961BAD5BB4430A95E073DE5C026277}

Per implementare correttamente una pagina con codice per la raccolta di dati, è necessario disporre dell'accesso ai server host per caricare nuovi contenuti nel sito Web. È inoltre utile disporre di un sito esistente per implementare il codice.

La procedura seguente illustra l'implementazione di base di Analytics.

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
   <td colname="col1"> Scarica appmeasurement per javascript e il servizio ID visitatori. </td> 
   <td colname="col2"> <p>The download is available in <a href="https://marketing.adobe.com/resources/help/en_US/reference/?f=code_manager_admin" format="http" scope="external"> Code Manager </a>. </p> <p>Questo file ZIP di download contiene diversi file. <code> Appmeasurement. js </code> e <code> visitorapi. js </code> sono i file pertinenti durante l'implementazione di Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step2_icon.png" id="image_02CFDC007BF1486AA312698EBFFA79F7" /> </td> 
   <td colname="col1"> Configurare il servizio identità. </td> 
   <td colname="col2"> <p>(Formerly <span class="term"> Visitor ID service </span>.) See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-setup-analytics.html" format="https" scope="external"> Set Up the Identity Service for Analytics </a>. </p> 
    <draft-comment> 
     <p>In <code> VisitorAPI.js </code>, add the following visitor ID initialization code at the beginning of the file: </p> 
     <code class="syntax javascript">var visitor = Visitor. getinstance ("INSERT-MCORG-ID-HERE"); visitor. trackingserver = "INSERT-TRACKING-SERVER-HERE"; // same as s. trackingserver visitor. trackingserversecure = "INSERT-SECURE-TRACKING-SERVER-HERE"; //same as s. trackingserversecure/* = = DO NOT ALTER ANYTHING BELOW THIS LINE = = </code>
      <ul id="ul_769BA118CC244308A805079C2CBECC12"> 
      <li id="li_D366EBDE24CB433EA523DB228CB2FAF1"> <code> " INSERT-MCORG-ID-HERE " </code> - (obbligatorio) questo ID organizzazione Adobe Experience Cloud viene inviato all'amministratore quando viene eseguito il provisioning della tua società per Adobe Experience Cloud. </li> 
      <li id="li_4F9704A6A6EA4334A3758F99B8D67C9D"> <code> " INSERT-TRACKING-SERVER-HERE " </code> - (obbligatorio) il server di tracciamento Analytics. </li> 
      <li id="li_C578420458D649228E54D9809AF62627"> <code> " INSERT-SECURE-TRACKING-SERVER-HERE " </code> - (Obbligatorio se ssl è abilitato) Il server di tracciamento protetto di Analytics. </li> 
     </ul> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step3_icon.png" id="image_76B61DEABE3849CCB39135FDD7399EAA" /> </td> 
   <td colname="col1"> Update <code> AppMeasurement.js </code>. </td> 
   <td colname="col2"> <p>Copy the <a href="../../implement/js-implementation/appmeasure-mjs-pagecode.md#section_4351543F2D6049218E18B48769D471E2" format="dita" scope="local"> Example AppMeasurement.js Code </a> and paste it at the beginning of your <code> AppMeasurement.js </code> file. Come minimo, aggiorna le seguenti variabili: </p> 
    <ul id="ul_62FA640BD2604E589650A92158272615"> 
     <li id="li_54E56B483B3A416EA27D7B540D60E39F"> <code> s. account = "INSERT-RSID-HERE" </code> </li> 
     <li id="li_00A958289BB045379B436F13287E03D5"> <code> s. trackingserver = "INSERT-TRACKING-SERVER-HERE" </code> </li> 
     <li id="li_C0779ADF780440ED876236AEB1FB5DCC"> <code> s. visitornamespace = "INSERT-NAMESPACE-HERE" </code> </li> 
     <li id="li_93072B656C134D8C89195B7F2D7D8F05"> <code> s. visitor = Visitor. getinstance ("INSERT-MCORG-ID-HERE") </code> </li> 
    </ul> <p> See <a href="https://helpx.adobe.com/analytics/kb/determining-data-center.html" format="https" scope="external"> Correctly populate the trackingServer and trackingServerSecure variable </a> or contact Client Care if you are unsure about any of these values. Se non vengono impostati correttamente, i dati non saranno raccolti dalla tua implementazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step4_icon.png" id="image_B255E5EAE7BB43FC946D0E9DFCA83003" /> </td> 
   <td colname="col1"> Host <code> AppMeasurement.js </code> and <code> VisitorAPI.js </code>. </td> 
   <td colname="col2"> <p>Questi file javascript di base devono essere ospitati su un server Web accessibile a tutte le pagine del sito. È necessario definire il percorso di questi file nella fase successiva. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step5_icon.png" id="image_844E896941E2489A943BE10AD710ED36" /> </td> 
   <td colname="col1"> Reference <code> AppMeasurement.js </code> and <code> VisitorAPI.js </code> on all site pages. </td> 
   <td colname="col2"> <p> Include the Visitor ID Service by adding the following line of code in the <code> &lt;head&gt; </code> or &lt;body&gt; tag on each page. <code> Visitorapi. js </code> deve essere incluso prima di <code> appmeasurement. js </code>: </p> 
    <code class="syntax html">&lt; script language = "javascript" type = "text/javascript" src = "https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/VisitorAPI.js" &gt; &lt;/script &gt; </code>
  <p> Include AppMeasurement for JavaScript by adding the following line of code in the <code> &lt;head&gt; </code> or <code> &lt;body&gt; </code> tag on each page: </p> 
    <code class="syntax html">&lt; script language = "javascript" type = "text/javascript" src = "https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/AppMeasurement.js" &gt; &lt;/script &gt; </code>
  </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step6_icon.png" id="image_1C4293CA98F04EE2ADA69EAB95BDE8B1" /> </td> 
   <td colname="col1"> Aggiornate e distribuite il codice della pagina. </td> 
   <td colname="col2"> <p>Copy the <a href="../../implement/js-implementation/appmeasure-mjs-pagecode.md#section_042412C29CC249E298F19B2BC2F43CE7" format="dita" scope="local"> Example Page Code </a> and paste it just after the opening <code> &lt;body&gt; </code> tag on each page you want to track. Come minimo, aggiorna le seguenti variabili: </p> 
    <ul id="ul_29200A6E8DA14386BDA242AD8B270FEB"> 
     <li id="li_FB24D2CB9241401A83BD13EE342A7810"> <code> var s = s_ gi ("INSERT-RSID-HERE") </code> </li> 
     <li id="li_463A35BA06CC4618B4AF17CD7E83AED5"> <code> s. pagename = "INSERT-NAME-HERE" //, ad esempio, s. pagename = document. title </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step7_icon.png" id="image_A423CBF386AF4E5986E8CBB6E31CD3E5" /> </td> 
   <td colname="col1"> Utilizzate digitalpulse Debugger per verificare che i dati siano in fase di invio. </td> 
   <td colname="col2"> <p>Install the <a href="../../implement/impl-testing/debugger.md#concept_B26FFE005EDD4E0FACB3117AE3E95AA2" format="dita" scope="local"> Adobe Debugger </a> bookmarklet. Dopo essere stato installato, caricate una pagina in cui avete distribuito il codice della pagina e aprite il debugger. Il debugger visualizza i dettagli relativi ai dati della raccolta inviati. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Caching {#section_4E2D1D962DF046418134C43CFC49AD4A}

Il file javascript viene memorizzato nella cache del browser del visitatore dopo averlo caricato inizialmente, e in genere viene scaricato non più di una volta per sessione. Il file non viene scaricato su ogni pagina, anche se viene utilizzato da ogni pagina del sito. Nella maggior parte dei siti Web, gli utenti possono media più di un paio di visualizzazioni di pagina per sessione, quindi il trasferimento di javascript utilizzato più volte in questo file può comportare meno dati scaricati.

## JavaScript for AppMeasurement Compression {#section_C10BBC84C81C414088F97363D29E021B}

Se siete preoccupati dello spessore della pagina (dimensione) di Codice H (appmeasurement per javascript 1.0), Adobe consiglia di considerare la compressione del file mediante GZIP. GZIP is supported by all major browsers and offers better performance than JavaScript compression to compress and decompress the core [!DNL s_code.js] JavaScript file.

The following links help explain how you can use GZIP functionality on your site to handle compression of the [!DNL s_code.js] JavaScript code:

[Apache Module mod_ deflate](https://httpd.apache.org/docs/2.0/mod/mod_deflate.html)

[Abilitazione della compressione gzip con Tomcat e Flex](https://www.cubicleman.com/2007/04/06/enabling-gzip-compression-with-tomcat-and-flex/)
