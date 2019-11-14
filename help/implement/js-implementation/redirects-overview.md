---
description: Reindirizza il browser a una nuova posizione senza l'interazione dell'utente. Vengono eseguite nel browser Web (reindirizzamento lato client) o nel server Web (reindirizzamento lato server).
keywords: Analytics Implementation
solution: Analytics
subtopic: Redirects
title: Reindirizzamenti e alias
topic: Developer and implementation
uuid: 11f9ad7a-5c45-410f-86dd-b7d2cec2aae3
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Reindirizzamenti e alias

Reindirizza il browser a una nuova posizione senza l'interazione dell'utente. Vengono eseguite nel browser Web (reindirizzamento lato client) o nel server Web (reindirizzamento lato server).

## Reindirizzamenti e alias {#concept_F4F1D53D473947FE8554897332545763}

Reindirizza il browser a una nuova posizione senza l'interazione dell'utente. Vengono eseguite nel browser Web (reindirizzamento lato client) o nel server Web (reindirizzamento lato server).

Poiché i reindirizzamenti non richiedono alcuna interazione con l'utente, i reindirizzamenti vengono spesso eseguiti senza che l'utente se ne accorga. L'unica cosa che indica che si è verificato un reindirizzamento è la barra degli indirizzi del browser. La barra degli indirizzi presenta un URL diverso dal collegamento inizialmente richiesto dal browser.

Anche se esistono solo due tipi di reindirizzamenti, possono essere implementati in diversi modi. Ad esempio, i reindirizzamenti sul lato client possono verificarsi perché la pagina Web a cui un utente ha puntato il proprio browser contiene script o codice HTML speciale che reindirizzano il browser a un altro URL. I reindirizzamenti sul lato server possono verificarsi perché la pagina contiene script sul lato server o perché il server Web è stato configurato per indirizzare l'utente a un altro URL.

## Analisi e reindirizzamenti {#concept_F9132879D0CB4AC1BE7AF45E388A47F7}

[!DNL Analytics] raccoglie alcuni dei dati dal browser e si basa su alcune proprietà del browser. Due di queste proprietà, "URL di riferimento" (o "referente") e "URL corrente" possono essere modificate mediante un reindirizzamento sul lato server. Poiché il browser è consapevole che è stato richiesto un URL, ma è stato restituito un URL diverso, cancella l’URL di riferimento. Il risultato è che l'URL di provenienza è vuoto e [!DNL Analytics] potrebbe indicare che non esiste alcun referente per la pagina.

<!-- 

redirects_sc.xml

 -->

Gli esempi seguenti illustrano come la navigazione viene influenzata senza e con i reindirizzamenti:

* [Esempio: Navigazione senza reindirizzamenti](/help/implement/js-implementation/redirects-overview.md#section_5C835A4D665A4625A23333C2C21F152D)
* [Esempio: Navigazione Con I Reindirizzamenti](/help/implement/js-implementation/redirects-overview.md#section_921DDD32932847848C4A901ACEF06248)

## Esempio: Navigazione senza reindirizzamenti {#section_5C835A4D665A4625A23333C2C21F152D}

Considerate il seguente scenario ipotetico in cui l'utente non riscontra un reindirizzamento:

1. L'utente punta il browser a `www.google.com`e digita "biglietti aerei scontati" nel campo di ricerca, quindi fa clic sul **[!UICONTROL Search]** pulsante.
1. Il browser visualizza i risultati della ricerca, compreso un collegamento al sito, [!DNL https://www.flywithus.com/]. Dopo aver visualizzato i risultati della ricerca, nella barra degli indirizzi del browser vengono visualizzati i termini di ricerca immessi dall'utente nel campo di ricerca ( `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`). I termini di ricerca sono inclusi nei parametri di stringa della query URL che seguono `https://www.google.com/search?`.
1. L'utente fa clic sul collegamento al sito ipotetico [!DNL https://www.flywithus.com/]. Quando l'utente fa clic su questo collegamento e accede al [!DNL flywithus.com] sito Web, [!DNL Analytics] utilizza JavaScript per raccogliere l'URL di provenienza ( `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`) e l'URL corrente ( `https://www.flywithus.com/`).
1. [!DNL Analytics] segnala le informazioni raccolte durante questa interazione in vari rapporti, quali [!UICONTROL Referring Domains], [!UICONTROL Search Engines]e [!DNL Search Keywords].

## Esempio: Navigazione Con I Reindirizzamenti {#section_921DDD32932847848C4A901ACEF06248}

I reindirizzamenti possono causare la visualizzazione dell'URL di provenienza effettivo nel browser. Considerate il seguente scenario:

1. L'utente punta il browser a `https://www.google.com`e digita biglietti aerei *scontati* nel campo di ricerca, quindi fa clic sul **[!UICONTROL Search]** pulsante.
1. Nella barra degli indirizzi della finestra del browser sono visualizzati i termini di ricerca digitati dall'utente nel campo di ricerca `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`. I termini di ricerca sono inclusi nei parametri di stringa della query URL che seguono `https://www.google.com/search?`. Il browser visualizza anche una pagina contenente i risultati della ricerca, compreso un collegamento a uno dei nomi di dominio: [!DNL https://www.flytohawaiiforfree.com/]. Questo dominio *personalizzato* è configurato per reindirizzare l'utente a `https://www.flywithus.com/`.
1. L'utente fa clic sul collegamento `https://www.flytohawaiiforfree.com/` e viene reindirizzato dal server al sito principale, `https://www.flywithus.com`. Quando si verifica il reindirizzamento, i dati importanti per la raccolta di [!DNL Analytics] dati vengono persi perché il browser cancella l'URL di provenienza. Pertanto, le informazioni di ricerca originali utilizzate nei [!DNL Analytics] report (ad esempio, [!UICONTROL Referring Domains], [!UICONTROL Search Engines], [!UICONTROL Search Keywords]) vengono perse.

[Implementazione dei reindirizzamenti](/help/implement/js-implementation/redirects-overview.md#concept_5EC2EE9677A44CC5B90A38ECF28152E7) spiega come sfruttare [!DNL Analytics] le variabili per acquisire i dati persi nel reindirizzamento. In particolare, la sezione descrive come risolvere la situazione dei "biglietti aerei scontati" descritta sopra.

## Implementare i reindirizzamenti {#concept_5EC2EE9677A44CC5B90A38ECF28152E7}

Per acquisire [!DNL Analytics] i dati dai reindirizzamenti, è necessario apportare quattro modifiche minori al codice che crea il reindirizzamento e al file [!DNL AppMeasurement] per JavaScript.

<!-- 

redirects_implement.xml

 -->

Completando i seguenti passaggi, le informazioni trasmesse dal referente originale (ad esempio, `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets` nello scenario precedente) verranno mantenute nel sito:

## Configurare l'override del codice JavaScript per il referente {#section_87BB1D47D9C345C18339078824645CC4}

<!-- 

redirects_js_override.xml

 -->

Lo snippet di codice riportato di seguito mostra due variabili JavaScript *`s_referrer`* e *`s_pageURL`*. Questo codice viene inserito nella pagina di destinazione finale del reindirizzamento.

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
>Impostato *`s.referrer`* una sola volta sulla pagina. Impostandolo più volte con ogni chiamata di tracciamento o con ogni clic di collegamento tracciato, si verifica un doppio conteggio del referente e delle dimensioni correlate, come motori di ricerca e parole chiave.

## Reindirizza utilizzando getQueryParam {#section_EE924E399F7A431C8FC8E8A2BEF84DEC}

Anche se [!UICONTROL getQueryParam] è un modo semplice per compilare [!DNL Analytics] le variabili con i valori stringa di query, è necessario implementarle in relazione a una variabile temporanea in modo che i riferimenti legittimi non vengano sovrascritti quando la stringa di query è vuota. Il modo migliore per utilizzare [!UICONTROL getQueryParam] è in connessione con il [!UICONTROL getValue] plug-in come descritto con lo pseudo-codice seguente.

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

Poiché il browser elimina l’URL di provenienza, è necessario configurare il meccanismo che gestisce il reindirizzamento (ad esempio, il server Web, il codice lato server e il codice lato client) per passare le informazioni originali sul referente. Se desideri anche registrare l’URL del collegamento alias, questo deve essere trasmesso anche alla pagina di destinazione finale. Utilizzate la *`s_pageURL`* variabile per sovrascrivere l’URL corrente.

Poiché esistono molti modi per implementare un reindirizzamento, è necessario consultare il gruppo di operazioni Web o il partner pubblicitario online per identificare i meccanismi specifici che eseguono i reindirizzamenti sul sito Web.

## Acquisisci il referente originale {#section_7F1A77F447CF485385B456A64B174050}

<!-- 

redirects_referrer.xml

 -->

In genere [!DNL Analytics] , l'URL di provenienza viene ottenuto dalla [!UICONTROL document.referrer] proprietà del browser e l'URL corrente dalla [!UICONTROL document.location] proprietà. Passando valori alle *`referrer`* variabili e alle *`pageURL`* variabili, potete ignorare l'elaborazione predefinita. Passando un valore alla variabile referrer, si consiglia [!DNL Analytics] di ignorare le informazioni sul referente nella [!UICONTROL document.referrer] proprietà e di utilizzare un valore alternativo definito dall'utente.

Pertanto, la versione finale della pagina di destinazione dovrebbe contenere il seguente codice per correggere i problemi introdotti nello scenario "biglietti aerei scontati".

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

Eseguite un test per verificare che il referente, l'URL di origine ( *`s_server`*) e le variabili della campagna vengano acquisite.

Queste variabili saranno rappresentate come i seguenti parametri in [Experience Cloud Debugger](https://marketing.adobe.com/resources/help/en_US/experience-cloud-debugger/).

<table id="table_5F3B987D4D514CA283F7B9F52EBC2301"> 
 <thead> 
  <tr> 
   <th class="entry"> </th> 
   <th class="entry"> <b>Valore stringa URL o query</b> </th> 
   <th class="entry"> <b>Valore come mostrato nel debugger DigitalPulse</b> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>Referente originale </p> </td> 
   <td> <p> <span class="filepath"> https://www.google.com/search%3F hl%3Den %26ie%3DUTF826q%3 Dsconto%2Bair%2Bticket </span> </p> </td> 
   <td> <p> <span class="filepath"> r=https:/ref=www.google.com/search?hl=en&amp;ie=UTF -8&amp;q=sconto+biglietti aerei </span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p>URL della pagina </p> </td> 
   <td> <p> <span class="filepath"> https://www.flytohawaiiforfree.com </span> </p> </td> 
   <td> <p> <span class="filepath"> g=https://www.flytohawaiiforfree.com </span> </p> <p>Questo valore verrà visualizzato in DigitalPulse Debugger se viene utilizzata la variabile <span class="varname"> URL </span> pagina. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>URL pagina di destinazione finale </p> </td> 
   <td> <p> <span class="filepath"> https://www.flywithus.com </span> </p> </td> 
   <td> <p>Questo valore NON verrà visualizzato in DigitalPulse Debugger se viene utilizzata la variabile <span class="varname"> URL pagina </span> . </p> </td> 
  </tr> 
 </tbody> 
</table>

Il testo visualizzato dal debugger deve corrispondere al seguente esempio:

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

Dopo aver verificato che Adobe [!UICONTROL Debugger] visualizzi queste variabili, è sempre utile confermare che i termini di ricerca e il dominio di riferimento originale (prima del reindirizzamento) stanno registrando il traffico nei rapporti.
