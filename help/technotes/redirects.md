---
description: I reindirizzamenti indicano il browser a una nuova posizione senza l’interazione dell’utente. Vengono eseguite nel browser web (reindirizzamento lato client) o nel server web (reindirizzamento lato server).
keywords: Implementazione di Analytics
subtopic: Redirects
title: Reindirizzamenti e alias
topic-fix: Developer and implementation
uuid: 11f9ad7a-5c45-410f-86dd-b7d2cec2aae3
exl-id: 0ed2aa9b-ab42-415d-985b-2ce782b6ab51
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '1104'
ht-degree: 1%

---

# Reindirizzamenti e alias

I reindirizzamenti indicano il browser a una nuova posizione senza l’interazione dell’utente. Vengono eseguite nel browser web (reindirizzamento lato client) o nel server web (reindirizzamento lato server).

## Reindirizzamenti e alias {#concept_F4F1D53D473947FE8554897332545763}

I reindirizzamenti indicano il browser a una nuova posizione senza l’interazione dell’utente. Vengono eseguite nel browser web (reindirizzamento lato client) o nel server web (reindirizzamento lato server).

Poiché i reindirizzamenti non richiedono alcuna interazione con l’utente, i reindirizzamenti vengono spesso eseguiti senza che l’utente se ne accorga. L’unica cosa che indica che si è verificato un reindirizzamento è la barra degli indirizzi del browser. La barra degli indirizzi visualizza un URL diverso dal collegamento inizialmente richiesto dal browser.

Sebbene esistano solo due tipi di reindirizzamenti, questi possono essere implementati in diversi modi. Ad esempio, i reindirizzamenti lato client possono verificarsi perché la pagina web a cui un utente ha puntato il proprio browser contiene script o codice HTML speciale che reindirizzano il browser a un altro URL. I reindirizzamenti lato server possono verificarsi perché la pagina contiene script sul lato server o perché il server Web è stato configurato per indirizzare l&#39;utente a un altro URL.

## Analytics e reindirizzamenti {#concept_F9132879D0CB4AC1BE7AF45E388A47F7}

[!DNL Analytics] raccoglie alcuni dei suoi dati dal browser e si basa su alcune proprietà del browser. Due di queste proprietà, l’&quot;URL di riferimento&quot; (o &quot;referrer&quot;) e l’&quot;URL corrente&quot; possono essere modificate da un reindirizzamento lato server. Poiché il browser è consapevole che è stato richiesto un URL, ma è stato restituito un URL diverso, cancella l’URL di riferimento. Il risultato è che l’URL di riferimento è vuoto e [!DNL Analytics] potrebbe indicare che non esiste alcun referente per la pagina.

## Esempio: Navigazione senza reindirizzamenti {#section_5C835A4D665A4625A23333C2C21F152D}

Considera il seguente scenario ipotetico in cui l’utente non trova un reindirizzamento:

1. L&#39;utente indirizza il proprio browser a `www.google.com` e digita &quot;biglietti aerei scontati&quot; nel campo di ricerca, quindi fai clic sul pulsante **[!UICONTROL Search]** .
1. Il browser visualizza i risultati della ricerca, compreso un collegamento al sito, [!DNL https://www.example.com/]. Dopo aver visualizzato i risultati della ricerca, nella barra degli indirizzi del browser vengono visualizzati i termini di ricerca immessi dall’utente nel campo di ricerca ( `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`). Tieni presente che i termini di ricerca sono inclusi nei parametri della stringa di query URL che seguono `https://www.google.com/search?`.
1. L&#39;utente fa clic sul collegamento al sito ipotetico [!DNL https://www.example.com/]. Quando l&#39;utente fa clic su questo collegamento e arriva sul sito web [!DNL example.com], [!DNL Analytics] utilizza JavaScript per raccogliere l&#39;URL di riferimento ( `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`) e l&#39;URL corrente ( `https://www.example.com/`).
1. [!DNL Analytics] riporta le informazioni raccolte durante questa interazione in vari rapporti, ad esempio  [!UICONTROL Referring Domains],  [!UICONTROL Search Engines] e  [!DNL Search Keywords].

## Esempio: Navigazione Con I Reindirizzamenti {#section_921DDD32932847848C4A901ACEF06248}

I reindirizzamenti possono causare la visualizzazione del vero URL di riferimento da parte del browser. Considera lo scenario seguente:

1. L&#39;utente indirizza il proprio browser a `https://www.google.com` e digita *biglietti aerei scontati* nel campo di ricerca, quindi fai clic sul pulsante **[!UICONTROL Search]** .
1. La barra degli indirizzi della finestra del browser visualizza i termini di ricerca digitati dall&#39;utente nel campo di ricerca `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`. Tieni presente che i termini di ricerca sono inclusi nei parametri della stringa di query URL che seguono `https://www.google.com/search?`. Il browser visualizza inoltre una pagina contenente i risultati della ricerca, compreso un collegamento a uno dei tuoi nomi di dominio: [!DNL https://www.flytohawaiiforfree.com/]. Questo dominio *vanity* è configurato per reindirizzare l&#39;utente a `https://www.example.com/`.
1. L&#39;utente fa clic sul collegamento `https://www.flytohawaiiforfree.com/` e viene reindirizzato dal server al sito principale `https://www.example.com`. Quando si verifica il reindirizzamento, i dati importanti per la raccolta dati [!DNL Analytics] vengono persi perché il browser cancella l&#39;URL di riferimento. Pertanto, le informazioni di ricerca originali utilizzate nei rapporti [!DNL Analytics] (ad esempio, [!UICONTROL Referring Domains], [!UICONTROL Search Engines], [!UICONTROL Search Keywords]) vengono perse.

## Implementare i reindirizzamenti {#concept_5EC2EE9677A44CC5B90A38ECF28152E7}

Per acquisire dati [!DNL Analytics] dai reindirizzamenti, è necessario apportare quattro modifiche minori al codice che crea il reindirizzamento e al [!DNL AppMeasurement] per il file JavaScript.

<!-- 

redirects_implement.xml

 -->

Il completamento dei passaggi seguenti manterrà le informazioni trasmesse al sito dal referente originale (ad esempio, `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets` nello scenario precedente):

## Configurare l’override del referrer per il codice JavaScript {#section_87BB1D47D9C345C18339078824645CC4}

<!-- 

redirects_js_override.xml

 -->

Lo snippet di codice riportato di seguito mostra due variabili JavaScript, *`s_referrer`* e *`s_pageURL`*. Questo codice viene inserito nella pagina di destinazione finale del reindirizzamento.

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
>Imposta *`s.referrer`* una sola volta sulla pagina. Impostarlo più di una volta con ogni chiamata di tracciamento o con ogni clic di collegamento tracciato causa un doppio conteggio del referente e delle dimensioni correlate, come motori di ricerca e parole chiave.

## Reindirizza utilizzando getQueryParam {#section_EE924E399F7A431C8FC8E8A2BEF84DEC}

Anche se il [!UICONTROL getQueryParam] è un modo semplice per popolare le variabili [!DNL Analytics] con valori di stringa di query, deve essere implementato in connessione con una variabile temporanea in modo che i referenti legittimi non vengano sovrascritti quando la stringa di query è vuota. Il modo migliore per utilizzare [!UICONTROL getQueryParam] è collegato al plug-in [!UICONTROL getValue] come descritto con il seguente pseudo-codice.

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

## Modificare il meccanismo di reindirizzamento {#section_2FF9921E8FCA4440B6FF90F15386E548}

<!-- 

redirects_modify_mechanism.xml

 -->

Poiché il browser elimina l’URL di riferimento, è necessario configurare il meccanismo che gestisce il reindirizzamento (ad esempio, il server web, il codice lato server e il codice lato client) per passare le informazioni di riferimento originali. Se desideri anche registrare l’URL del collegamento di alias, devi anche trasmetterlo alla pagina di destinazione finale. Utilizza la variabile *`s_pageURL`* per sovrascrivere l’URL corrente.

Poiché sono disponibili diversi modi per implementare un reindirizzamento, è necessario consultare il gruppo di operazioni web o il partner di pubblicità online per identificare i meccanismi specifici che eseguono i reindirizzamenti sul sito web.

## Cattura il referente originale {#section_7F1A77F447CF485385B456A64B174050}

<!-- 

redirects_referrer.xml

 -->

Normalmente, [!DNL Analytics] ottiene l&#39;URL di riferimento dalla proprietà [!UICONTROL document.referrer] del browser e l&#39;URL corrente dalla proprietà [!UICONTROL document.location]. Passando i valori alle variabili *`referrer`* e *`pageURL`*, puoi sovrascrivere l’elaborazione predefinita. Passando un valore alla variabile referente, viene indicato a [!DNL Analytics] di ignorare le informazioni sul referente nella proprietà [!UICONTROL document.referrer] e di utilizzare un valore alternativo definito dall&#39;utente.

Pertanto, la versione finale della pagina di destinazione dovrebbe contenere il seguente codice per correggere i problemi introdotti nello scenario &quot;biglietti aerei scontati&quot;.

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

## Verificare il referente con Adobe Debugger {#section_B3E85941982E4E1698B271375AD669B9}

<!-- 

redirects_verify_referrer.xml

 -->

Esegui un test per verificare che il referente, l’URL di origine ( *`s_server`*) e le variabili della campagna siano acquisiti.

Queste variabili saranno rappresentate come i seguenti parametri nel [Experience Cloud Debugger](https://docs.adobe.com/content/help/it-IT/experience-cloud/user-guides/home.translate.html).

<table id="table_5F3B987D4D514CA283F7B9F52EBC2301"> 
 <thead> 
  <tr> 
   <th class="entry"> </th> 
   <th class="entry"> <b>Valore stringa URL o query</b> </th> 
   <th class="entry"> <b>Valore mostrato nel debugger DigitalPulse</b> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>Referrer originale </p> </td> 
   <td> <p> <span class="filepath"> https://www.google.com/search%3F hl%3Den %26ie%3DUTF826q%3 Ddiscount%2Bair%2Bticket  </span> </p> </td> 
   <td> <p> <span class="filepath"> r=https:/ref=www.google.com/search?hl=en&amp;ie=UTF -8&amp;q=sconto+biglietti aerei  </span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p>URL della pagina </p> </td> 
   <td> <p> <span class="filepath"> https://www.flytohawaiiforfree.com  </span> </p> </td> 
   <td> <p> <span class="filepath"> g=https://www.flytohawaiiforfree.com  </span> </p> <p>Questo valore verrà visualizzato in DigitalPulse Debugger se viene utilizzata la variabile <span class="varname"> pageURL </span> . </p> </td> 
  </tr> 
  <tr> 
   <td> <p>URL della pagina di destinazione finale </p> </td> 
   <td> <p> <span class="filepath"> https://www.example.com  </span> </p> </td> 
   <td> <p>Questo valore NON verrà visualizzato nel debugger di DigitalPulse se viene utilizzata la variabile <span class="varname"> pageURL </span> . </p> </td> 
  </tr> 
 </tbody> 
</table>

Il testo visualizzato dal debugger deve corrispondere al seguente esempio:

```
Image 
 
https://examplecom.112.2o7.net/b/ss/examplecom/1/JS-1.4/s61944015791667?[AQB] 
ndh=1 
t=4/8/2014 13:34:28 4 360 
pageName=Welcome to example.com 
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

Dopo aver verificato che l’Adobe [!UICONTROL Debugger] visualizzi queste variabili, è sempre utile confermare che i termini di ricerca e il dominio di riferimento originale (prima del reindirizzamento) registrano il traffico nei rapporti.
