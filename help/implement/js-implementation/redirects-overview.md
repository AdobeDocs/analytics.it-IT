---
description: Reindirizza il browser a una nuova posizione senza interazione con l'utente. Vengono eseguiti sul browser Web (reindirizzamento lato client) o sul server Web (reindirizzamento lato server).
keywords: Implementazione di Analytics
seo-description: Reindirizza il browser a una nuova posizione senza interazione con l'utente. Vengono eseguiti sul browser Web (reindirizzamento lato client) o sul server Web (reindirizzamento lato server).
seo-title: Reindirizzamenti e alias
solution: Analytics
subtopic: Reindirizza
title: Reindirizzamenti e alias
topic: Sviluppatore e implementazione
uuid: 11 f 9 ad 7 a -5 c 45-410 f -86 dd-b 7 d 2 cec 2 aae 3
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# Reindirizzamenti e alias

Reindirizza il browser a una nuova posizione senza interazione con l'utente. Vengono eseguiti sul browser Web (reindirizzamento lato client) o sul server Web (reindirizzamento lato server).

## Redirects and aliases {#concept_F4F1D53D473947FE8554897332545763}

Reindirizza il browser a una nuova posizione senza interazione con l'utente. Vengono eseguiti sul browser Web (reindirizzamento lato client) o sul server Web (reindirizzamento lato server).

Poiché i reindirizzamenti non richiedono alcuna interazione con l'utente, i reindirizzamenti vengono spesso eseguiti senza che l'utente abbia mai notato. L'unica cosa che indica che si è verificato un reindirizzamento è la barra degli indirizzi del browser. Nella barra degli indirizzi viene visualizzato un URL diverso dal collegamento inizialmente richiesto dal browser.

Sebbene siano disponibili solo due tipi di reindirizzamenti, possono essere implementati in vari modi. Ad esempio, i reindirizzamenti lato client possono verificarsi perché la pagina Web a cui un utente ha puntato il browser contiene script o codice HTML speciale che reindirizza il browser a un altro URL. I reindirizzamenti lato server possono verificarsi perché la pagina contiene script sul lato server o perché il server Web è stato configurato per indirizzare l'utente a un altro URL.

## Analytics and redirects {#concept_F9132879D0CB4AC1BE7AF45E388A47F7}

[!DNL Analytics] raccoglie alcuni dati dal browser e si basa su determinate proprietà del browser. Due di queste proprietà, «URL di riferimento» (o «referrer») e «URL corrente» possono essere modificate da un reindirizzamento lato server. Poiché il browser è consapevole che è stato richiesto un URL, ma è stato restituito un URL diverso, cancella l'URL di provenienza. The result is the referring URL is blank, and [!DNL Analytics] might report that no referrer existed for the page.

<!-- 

redirects_sc.xml

 -->

Gli esempi seguenti illustrano come la navigazione è interessata da e con reindirizzamenti:

* [Esempio: Navigazione senza reindirizzamenti](../../implement/js-implementation/redirects-overview.md#section_5C835A4D665A4625A23333C2C21F152D)
* [Esempio: Navigazione con i reindirizzamenti](../../implement/js-implementation/redirects-overview.md#section_921DDD32932847848C4A901ACEF06248)

## Example: Browsing Without Redirects {#section_5C835A4D665A4625A23333C2C21F152D}

Considerate il seguente scenario ipotetico in cui l'utente non partecipa a un reindirizzamento:

1. User points his or her browser to `www.google.com`, and types, "discount airline tickets" into the search field, and then clicks the **[!UICONTROL Search]** button.
1. The browser displays the search results including a link to your site, [!DNL https://www.flywithus.com/]. After displaying the search results, the browser's address bar displays the search terms that the user entered in the search field ( `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`). Notice that the search terms are included in the URL query string parameters that follow `https://www.google.com/search?`.
1. The user clicks the link to your hypothetical site [!DNL https://www.flywithus.com/]. When the user clicks this link and lands on the [!DNL flywithus.com] website, [!DNL Analytics] uses JavaScript to collect the referring URL ( `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`) as well as the current URL ( `https://www.flywithus.com/`).
1. [!DNL Analytics] segnala le informazioni raccolte durante questa interazione in vari report, ad esempio [!UICONTROL Referring Domains], [!UICONTROL Search Engines]e [!DNL Search Keywords].

## Example: Browsing With Redirects {#section_921DDD32932847848C4A901ACEF06248}

I reindirizzamenti possono causare la perdita dell'URL di provenienza effettivo dal browser. Considerate lo scenario seguente:

1. User points his or her browser to `https://www.google.com`, and types, *discount airline tickets* into the search field, and then clicks the **[!UICONTROL Search]** button.
1. The browser window's address bar displays the search terms that the user typed into the search field `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`. Notice that the search terms are included in the URL query string parameters that follow `https://www.google.com/search?`. The browser also displays a page that contains the search results including a link to one of your domain names: [!DNL https://www.flytohawaiiforfree.com/]. This *vanity* domain is configured to redirect the user to `https://www.flywithus.com/`.
1. The user clicks on the link `https://www.flytohawaiiforfree.com/` and is redirected by the server to your main site, `https://www.flywithus.com`. When the redirection occurs, the data that is important to [!DNL Analytics] data collection is lost because the browser clears the referring URL. Thus, the original search information used in the [!DNL Analytics] reports (for example, [!UICONTROL Referring Domains], [!UICONTROL Search Engines], [!UICONTROL Search Keywords]) is lost.

[L'implementazione dei reindirizzamenti](../../implement/js-implementation/redirects-overview.md#concept_5EC2EE9677A44CC5B90A38ECF28152E7) illustra come sfruttare [!DNL Analytics] le variabili per acquisire i dati persi nel reindirizzamento. In particolare, la sezione illustra come correggere la situazione "biglietti aerei" descritta in precedenza.

## Implement redirects {#concept_5EC2EE9677A44CC5B90A38ECF28152E7}

In order to capture [!DNL Analytics] data from redirects, four minor alterations need to be made to the code that creates the redirect and the [!DNL AppMeasurement] for JavaScript file.

<!-- 

redirects_implement.xml

 -->

Completing the following steps will retain the information that the original referrer (for example, `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets` in the scenario above) passes to your site:

## Configure referrer override JavaScript code {#section_87BB1D47D9C345C18339078824645CC4}

<!-- 

redirects_js_override.xml

 -->

The code snippet below shows two JavaScript variables, *`s_referrer`* and *`s_pageURL`*. Questo codice viene inserito nella pagina di destinazione più aggiornata del reindirizzamento.

```js
<script language="JavaScript" src="//INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/AppMeasurement.js"></script> 
<script language="JavaScript"><!-- 
/* You may give each page an identifying name, server, and channel on 
the next lines. */ 
s.pageName="" 
s.server="" 
s.campaign="" 
s.referrer="" 
s.pageURL=""
```

>[!IMPORTANT]
>
>Set *`s.referrer`* only once on the page. Impostandolo più volte con ogni chiamata di tracciamento o con ogni clic di collegamento tracciato causa un doppio conteggio del referente e delle dimensioni correlate, ad esempio motori di ricerca e parole chiave.

## Redirects using getQueryParam {#section_EE924E399F7A431C8FC8E8A2BEF84DEC}

While the [!UICONTROL getQueryParam] is an easy way to populate [!DNL Analytics] variables with query string values, it must be implemented in connection with a temporary variable so that legitimate referrers are not overwritten when the query string is empty. The best way to use [!UICONTROL getQueryParam] is in connection with the [!UICONTROL getValue] plug in as outlined with the following pseudo-code.

```js
// AppMeasurement 1.x 
var tempVar=s.Util.getQueryParam('origref') 
if(tempVar) 
  s.referrer=tempVar;
```

```js
// H Code 
var tempVar=s.getQueryParam('origref') 
if(tempVar) 
  s.referrer=tempVar;
```

## Modify the redirect mechanism {#section_2FF9921E8FCA4440B6FF90F15386E548}

<!-- 

redirects_modify_mechanism.xml

 -->

Poiché l'URL di riferimento per le strisce del browser, è necessario configurare il meccanismo che gestisce il reindirizzamento (ad esempio, il server Web, il codice lato server, il codice lato client) da trasmettere lungo le informazioni del referente originale. Se desiderate registrare anche l'URL del collegamento alias, questo deve essere trasmesso anche alla pagina di destinazione finale. Use the *`s_pageURL`* variable to override the current URL.

Poiché esistono molti modi per implementare un reindirizzamento, rivolgetevi al vostro gruppo di operazioni Web o al vostro partner pubblicitario online per identificare i meccanismi specifici che eseguono reindirizzamenti sul vostro sito Web.

## Capture the original referrer {#section_7F1A77F447CF485385B456A64B174050}

<!-- 

redirects_referrer.xml

 -->

Normally, [!DNL Analytics] will obtain the referring URL from the browser's [!UICONTROL document.referrer] property, and the current URL from the [!UICONTROL document.location] property. By passing values to the *`referrer`* and *`pageURL`* variables, you can override the default processing. By passing a value to the referrer variable, you are telling [!DNL Analytics] to ignore the referrer information in the [!UICONTROL document.referrer] property and to use an alternative value that you define.

Pertanto, la versione finale della pagina di destinazione deve contenere il seguente codice per correggere i problemi introdotti nello scenario «sconto dei biglietti aerei».

```js
<script language="JavaScript" src="https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/AppMeasurement.js"></script> 
<script language="JavaScript"><!-- 
/* You may give each page an identifying name, server, and channel on 
the next lines. */ 
s.pageName="" 
s.server="" 
s.campaign="" 
s.referrer="https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets" 
// Setting the s.pageURL variable is optional. 
s.pageURL="https://www.flytohawaiiforfree.com"
```

## Verify the referrer with the Adobe Debugger {#section_B3E85941982E4E1698B271375AD669B9}

<!-- 

redirects_verify_referrer.xml

 -->

Run a test to verify that the referrer, originating URL ( *`s_server`*) and campaign variables are being captured.

These variables will be represented as the following parameters in the [Experience Cloud Debugger](https://marketing.adobe.com/resources/help/en_US/experience-cloud-debugger/).

<table id="table_5F3B987D4D514CA283F7B9F52EBC2301"> 
 <thead> 
  <tr> 
   <th class="entry"> </th> 
   <th class="entry"> <b>URL o valore stringa query</b> </th> 
   <th class="entry"> <b>Valore come mostrato nel debugger digitalpulse</b> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>Referrer originale </p> </td> 
   <td> <p> <span class="filepath"> https://www.google.com/search%3F hl % 3 Den % 26 ie % 3 DUTF 826 q % 3 Dsconto % 2 Bairline % 2 Biss </span> </p> </td> 
   <td> <p> <span class="filepath"> r = https:/ref=www.google.com/search?hl=en&amp;ie=UTF -8 &amp; q = sconto + airline + biglietti </span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p>URL della pagina </p> </td> 
   <td> <p> <span class="filepath"> https://www.flytohawaiiforfree.com </span> </p> </td> 
   <td> <p> <span class="filepath"> g = https://www.flytohawaiiforfree.com </span> </p> <p>This value will appear in the DigitalPulse Debugger if the <span class="varname"> pageURL </span> variable is used. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>URL pagina di destinazione finale </p> </td> 
   <td> <p> <span class="filepath"> https://www.flywithus.com </span> </p> </td> 
   <td> <p>This value will NOT appear in the DigitalPulse Debugger if the <span class="varname"> pageURL </span> variable is used. </p> </td> 
  </tr> 
 </tbody> 
</table>

Il testo visualizzato dal debugger corrisponde al seguente esempio:

```
Image 
 
https://flywithuscom.112.2o7.net/b/ss/flywithuscom/1/JS-1.4/s61944015791667?[AQB] 
ndh=1 
t=4/8/2014 13:34:28 4 360 
pageName=Welcome to FlyWithUs.com 
r=https://ref=www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets 
cc=USD 
g=https://www.flytohawaiiforfree.com 
s=1280x1024 
c=32 
j=1.3 
v=Y 
k=Y 
bw=1029 
bh=716 
ct=lan 
hp=N 
[AQE]
```

After verifying that the Adobe [!UICONTROL Debugger] displays these variables, it is always helpful to confirm that the search terms and the original referring domain (prior to the redirect) are registering traffic in reports.
