---
description: I reindirizzamenti puntano il browser a una nuova posizione senza l’interazione dell’utente. Vengono eseguiti nel browser web (reindirizzamento lato client) o nel server web (reindirizzamento lato server).
keywords: Implementazione di Analytics
title: Reindirizzamenti e alias
feature: Implementation Basics
exl-id: 0ed2aa9b-ab42-415d-985b-2ce782b6ab51
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: tm+mt
source-wordcount: '1104'
ht-degree: 1%

---

# Reindirizzamenti e alias

I reindirizzamenti puntano il browser a una nuova posizione senza l’interazione dell’utente. Vengono eseguiti nel browser web (reindirizzamento lato client) o nel server web (reindirizzamento lato server).

## Reindirizzamenti e alias {#concept_F4F1D53D473947FE8554897332545763}

I reindirizzamenti puntano il browser a una nuova posizione senza l’interazione dell’utente. Vengono eseguiti nel browser web (reindirizzamento lato client) o nel server web (reindirizzamento lato server).

Poiché i reindirizzamenti non richiedono alcuna interazione da parte dell’utente, spesso vengono eseguiti senza che l’utente se ne accorga. L’unica cosa che indica che si è verificato un reindirizzamento è la barra degli indirizzi del browser. Nella barra degli indirizzi viene visualizzato un URL diverso dal collegamento richiesto inizialmente dal browser.

Anche se esistono solo due tipi di reindirizzamenti, possono essere implementati in numerosi modi. Ad esempio, i reindirizzamenti lato client possono verificarsi perché la pagina web a cui un utente ha puntato il browser contiene script o uno speciale codice HTML che reindirizza il browser a un altro URL. È possibile che si verifichino reindirizzamenti lato server perché la pagina contiene script lato server o perché il server web è stato configurato per indirizzare l’utente a un altro URL.

## Analytics e reindirizzamenti {#concept_F9132879D0CB4AC1BE7AF45E388A47F7}

[!DNL Analytics] raccoglie alcuni dei suoi dati dal browser e si basa su determinate proprietà del browser. Due di queste proprietà, &quot;URL di riferimento&quot; (o &quot;referrer&quot;) e &quot;URL corrente&quot; possono essere modificate da un reindirizzamento lato server. Poiché il browser è a conoscenza del fatto che è stato richiesto un URL, ma è stato restituito un URL diverso, cancella l’URL di riferimento. Il risultato è che l’URL di riferimento è vuoto e [!DNL Analytics] potrebbe indicare che non esiste alcun referente per la pagina.

## Esempio: esplorazione senza reindirizzamenti {#section_5C835A4D665A4625A23333C2C21F152D}

Considera il seguente scenario ipotetico in cui l’utente non incontra un reindirizzamento:

1. L’utente punta il browser a `www.google.com`, e digita &quot;sconto biglietti aerei&quot; nel campo di ricerca, quindi fa clic sul pulsante **[!UICONTROL Search]** pulsante.
1. Il browser visualizza i risultati della ricerca, incluso un collegamento al sito, [!DNL https://www.example.com/]. Dopo aver visualizzato i risultati della ricerca, nella barra degli indirizzi del browser vengono visualizzati i termini di ricerca immessi dall&#39;utente nel campo di ricerca ( `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`). I termini di ricerca sono inclusi nei parametri della stringa di query URL che seguono `https://www.google.com/search?`.
1. L’utente fa clic sul collegamento al tuo ipotetico sito [!DNL https://www.example.com/]. Quando l’utente fa clic su questo collegamento e arriva al [!DNL example.com] sito web, [!DNL Analytics] utilizza JavaScript per raccogliere l’URL di riferimento ( `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`) e l&#39;URL corrente ( `https://www.example.com/`).
1. [!DNL Analytics] segnala le informazioni raccolte durante questa interazione in vari rapporti, ad esempio [!UICONTROL Referring Domains], [!UICONTROL Search Engines], e [!DNL Search Keywords].

## Esempio: Esplorazione Con Reindirizzamenti {#section_921DDD32932847848C4A901ACEF06248}

I reindirizzamenti possono causare la rimozione del browser dall’URL di riferimento effettivo. Considera lo scenario seguente:

1. L’utente punta il browser a `https://www.google.com`, e tipi, *biglietti aerei scontati* nel campo di ricerca e quindi fa clic sul pulsante **[!UICONTROL Search]** pulsante.
1. Nella barra degli indirizzi della finestra del browser vengono visualizzati i termini di ricerca digitati dall&#39;utente nel campo di ricerca `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`. I termini di ricerca sono inclusi nei parametri della stringa di query URL che seguono `https://www.google.com/search?`. Nel browser viene inoltre visualizzata una pagina contenente i risultati della ricerca, con un collegamento a uno dei tuoi nomi di dominio: [!DNL https://www.flytohawaiiforfree.com/]. Questo *vanità* è configurato per reindirizzare l’utente a `https://www.example.com/`.
1. L’utente fa clic sul collegamento `https://www.flytohawaiiforfree.com/` e viene reindirizzato dal server al sito principale, `https://www.example.com`. Quando si verifica il reindirizzamento, i dati importanti per [!DNL Analytics] La raccolta dei dati viene persa perché il browser cancella l’URL di riferimento. Pertanto, le informazioni di ricerca originali utilizzate nel [!DNL Analytics] rapporti (ad esempio, [!UICONTROL Referring Domains], [!UICONTROL Search Engines], [!UICONTROL Search Keywords]) è persa.

## Implementare reindirizzamenti {#concept_5EC2EE9677A44CC5B90A38ECF28152E7}

Per acquisire [!DNL Analytics] dati dei reindirizzamenti, è necessario apportare quattro modifiche minori al codice che crea il reindirizzamento e al [!DNL AppMeasurement] per il file JavaScript.

<!-- 

redirects_implement.xml

 -->

Il completamento dei seguenti passaggi conserverà le informazioni che il referente originale (ad esempio, `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets` nello scenario precedente) passa al sito:

## Configurare l’override del codice JavaScript del referente {#section_87BB1D47D9C345C18339078824645CC4}

<!-- 

redirects_js_override.xml

 -->

Il frammento di codice seguente mostra due variabili JavaScript: *`s_referrer`* e *`s_pageURL`*. Questo codice viene inserito nella pagina di destinazione finale del reindirizzamento.

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
>Imposta *`s.referrer`* una sola volta sulla pagina. Impostandolo più di una volta con ogni chiamata di tracciamento o con ogni clic di collegamento tracciato si verifica un doppio conteggio del referente e delle dimensioni correlate, come motori di ricerca e parole chiave.

## Reindirizzamenti tramite getQueryParam {#section_EE924E399F7A431C8FC8E8A2BEF84DEC}

Mentre il [!UICONTROL getQueryParam] è un modo semplice per popolare [!DNL Analytics] variabili con valori di stringa di query, deve essere implementato in connessione a una variabile temporanea in modo che i referenti legittimi non vengano sovrascritti quando la stringa di query è vuota. Il modo migliore per utilizzare [!UICONTROL getQueryParam] è in relazione con [!UICONTROL getValue] plug-in come descritto con lo pseudo-codice seguente.

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

Poiché il browser elimina l’URL di riferimento, devi configurare il meccanismo che gestisce il reindirizzamento (ad esempio, il server web, il codice lato server e il codice lato client) in modo che trasmetta le informazioni originali sul referente. Se desideri registrare anche l’URL del collegamento di alias, questo deve essere trasmesso anche alla pagina di destinazione finale. Utilizza il *`s_pageURL`* per sostituire l&#39;URL corrente.

Poiché esistono diversi modi per implementare un reindirizzamento, è necessario rivolgersi al gruppo operativo Web o al partner pubblicitario online per identificare i meccanismi specifici che eseguono i reindirizzamenti sul sito Web.

## Acquisire il referente originale {#section_7F1A77F447CF485385B456A64B174050}

<!-- 

redirects_referrer.xml

 -->

Normalmente, [!DNL Analytics] otterrà l’URL di riferimento dal [!UICONTROL document.referrer] e l&#39;URL corrente da [!UICONTROL document.location] proprietà. Trasmettendo i valori al *`referrer`* e *`pageURL`* variabili, puoi ignorare l’elaborazione predefinita. Trasmettendo un valore alla variabile referrer, stai dicendo [!DNL Analytics] per ignorare le informazioni sul referente in [!UICONTROL document.referrer] e per utilizzare un valore alternativo definito dall&#39;utente.

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

Esegui un test per verificare che l’URL di origine del referente ( *`s_server`*) e le variabili della campagna vengono acquisite.

Queste variabili saranno rappresentate come i seguenti parametri nella [Experience Cloud Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=it).

<table id="table_5F3B987D4D514CA283F7B9F52EBC2301"> 
 <thead> 
  <tr> 
   <th class="entry"> </th> 
   <th class="entry"> <b>Valore stringa di query o URL</b> </th> 
   <th class="entry"> <b>Valore mostrato nel debugger DigitalPulse</b> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>Referente originale </p> </td> 
   <td> <p> <span class="filepath"> https://www.google.com/search%3F hl%3Den %26ie%3DUTF826q%3 Dsconto%2Bairline%2Bticket </span> </p> </td> 
   <td> <p> <span class="filepath"> r=https:/ref=www.google.com/search?hl=en&amp;ie=UTF -8&amp;q=sconto+compagnia aerea+biglietti </span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p>URL della pagina </p> </td> 
   <td> <p> <span class="filepath"> https://www.flytohawaiiforfree.com </span> </p> </td> 
   <td> <p> <span class="filepath"> g=https://www.flytohawaiiforfree.com </span> </p> <p>Questo valore verrà visualizzato nel debugger DigitalPulse se <span class="varname"> pageURL </span> viene utilizzata la variabile. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>URL della pagina di destinazione finale </p> </td> 
   <td> <p> <span class="filepath"> https://www.example.com </span> </p> </td> 
   <td> <p>Questo valore NON viene visualizzato in DigitalPulse Debugger se <span class="varname"> pageURL </span> viene utilizzata la variabile. </p> </td> 
  </tr> 
 </tbody> 
</table>

Il testo visualizzato nel debugger deve corrispondere al seguente esempio:

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

Dopo aver verificato che l’Adobe [!UICONTROL Debugger] mostra queste variabili, è sempre utile confermare che i termini di ricerca e il dominio di riferimento originale (prima del reindirizzamento) registrano il traffico nei rapporti.
