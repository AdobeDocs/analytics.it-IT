---
description: I reindirizzamenti puntano il browser a una nuova posizione senza l’interazione dell’utente. Vengono eseguiti nel browser web (reindirizzamento lato client) o nel server web (reindirizzamento lato server).
keywords: Implementazione di Analytics
title: Reindirizzamenti e alias
feature: Implementation Basics
exl-id: 0ed2aa9b-ab42-415d-985b-2ce782b6ab51
source-git-commit: fcc165536d77284e002cb2ba6b7856be1fdb3e14
workflow-type: tm+mt
source-wordcount: '1086'
ht-degree: 1%

---

# Reindirizzamenti e alias

I reindirizzamenti puntano il browser a una nuova posizione senza l’interazione dell’utente. Vengono eseguiti nel browser web (reindirizzamento lato client) o nel server web (reindirizzamento lato server).

## Reindirizzamenti e alias {#aliases}

I reindirizzamenti puntano il browser a una nuova posizione senza l’interazione dell’utente. Vengono eseguiti nel browser web (reindirizzamento lato client) o nel server web (reindirizzamento lato server).

Poiché i reindirizzamenti non richiedono alcuna interazione da parte dell’utente, spesso vengono eseguiti senza che l’utente se ne accorga. L’unica cosa che indica che si è verificato un reindirizzamento è la barra degli indirizzi del browser. Nella barra degli indirizzi viene visualizzato un URL diverso dal collegamento richiesto inizialmente dal browser.

Anche se esistono solo due tipi di reindirizzamenti, possono essere implementati in numerosi modi. Ad esempio, i reindirizzamenti lato client possono verificarsi perché la pagina web a cui un utente ha puntato il browser contiene script o codice HTML speciale che reindirizza il browser a un altro URL. È possibile che si verifichino reindirizzamenti lato server perché la pagina contiene script lato server o perché il server web è stato configurato per indirizzare l’utente a un altro URL.

## Analytics e reindirizzamenti {#aa-redirects}

[!DNL Analytics] raccoglie alcuni dati dal browser e si basa su determinate proprietà del browser. Due di queste proprietà, &quot;URL di riferimento&quot; (o &quot;referrer&quot;) e &quot;URL corrente&quot; possono essere modificate da un reindirizzamento lato server. Poiché il browser è a conoscenza del fatto che è stato richiesto un URL, ma è stato restituito un URL diverso, cancella l’URL di riferimento. Il risultato è che l&#39;URL di riferimento è vuoto e [!DNL Analytics] potrebbe segnalare che non esiste alcun referente per la pagina.

## Esempio: esplorazione senza reindirizzamenti {#browse-without}

Considera il seguente scenario ipotetico in cui l’utente non incontra un reindirizzamento:

1. L&#39;utente punta il browser a `www.google.com` e digita &quot;biglietti aerei scontati&quot; nel campo di ricerca, quindi fa clic sul pulsante **[!UICONTROL Search]**.
1. Nel browser vengono visualizzati i risultati della ricerca, incluso un collegamento al sito, [!DNL https://www.example.com/]. Dopo aver visualizzato i risultati della ricerca, nella barra degli indirizzi del browser vengono visualizzati i termini di ricerca immessi dall&#39;utente nel campo di ricerca ( `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`). I termini di ricerca sono inclusi nei parametri della stringa di query URL che seguono `https://www.google.com/search?`.
1. L&#39;utente fa clic sul collegamento al sito ipotetico [!DNL https://www.example.com/]. Quando l&#39;utente fa clic su questo collegamento e arriva al sito Web [!DNL example.com], [!DNL Analytics] utilizza JavaScript per raccogliere l&#39;URL di riferimento ( `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`) e l&#39;URL corrente ( `https://www.example.com/`).
1. [!DNL Analytics] segnala le informazioni raccolte durante questa interazione in vari rapporti, ad esempio [!UICONTROL Referring Domains], [!UICONTROL Search Engines] e [!DNL Search Keywords].

## Esempio: Esplorazione Con Reindirizzamenti {#browse-with}

I reindirizzamenti possono causare la rimozione del browser dall’URL di riferimento effettivo. Considera lo scenario seguente:

1. L&#39;utente punta il browser a `https://www.google.com` e digita *biglietti aerei scontati* nel campo di ricerca, quindi fa clic sul pulsante **[!UICONTROL Search]**.
1. Nella barra degli indirizzi della finestra del browser vengono visualizzati i termini di ricerca digitati dall&#39;utente nel campo di ricerca `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`. I termini di ricerca sono inclusi nei parametri della stringa di query URL che seguono `https://www.google.com/search?`. Nel browser viene inoltre visualizzata una pagina contenente i risultati della ricerca, incluso un collegamento a uno dei tuoi nomi di dominio: [!DNL https://www.flytohawaii.example/]. Questo dominio *vanity* è configurato per reindirizzare l&#39;utente a `https://www.example.com/`.
1. L&#39;utente fa clic sul collegamento `https://www.flytohawaii.example/` e viene reindirizzato dal server al sito principale, `https://www.example.com`. Quando si verifica il reindirizzamento, i dati importanti per la raccolta dati [!DNL Analytics] vengono persi perché il browser cancella l&#39;URL di riferimento. Pertanto, le informazioni di ricerca originali utilizzate nei report [!DNL Analytics] (ad esempio, [!UICONTROL Referring Domains], [!UICONTROL Search Engines], [!UICONTROL Search Keywords]) andranno perse.

## Implementare reindirizzamenti {#implement}

Per acquisire i dati [!DNL Analytics] dai reindirizzamenti, è necessario apportare quattro modifiche minori al codice che crea il reindirizzamento e al file [!DNL AppMeasurement] per JavaScript.

Il completamento dei seguenti passaggi conserverà le informazioni che il referente originale (ad esempio, `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets` nello scenario precedente) trasmette al sito:

## Configurare il referente per sostituire il codice JavaScript {#override}

Il frammento di codice seguente mostra due variabili JavaScript, `s.referrer` e `s.pageURL`. Questo codice viene inserito nella pagina di destinazione finale del reindirizzamento.

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

## Reindirizzamenti tramite getQueryParam {#getqueryparam}

Anche se [!UICONTROL getQueryParam] è un modo semplice per popolare [!DNL Analytics] variabili con valori stringa di query, deve essere implementato in connessione con una variabile temporanea in modo che i referenti legittimi non vengano sovrascritti quando la stringa di query è vuota. Il modo migliore per utilizzare [!UICONTROL getQueryParam] è in connessione con il plug-in [!UICONTROL getValue] come descritto con lo pseudo-codice seguente.

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

## Modificare il meccanismo di reindirizzamento {#modify}

Poiché il browser elimina l’URL di riferimento, devi configurare il meccanismo che gestisce il reindirizzamento (ad esempio, il server web, il codice lato server e il codice lato client) in modo che trasmetta le informazioni originali sul referente. Se desideri registrare anche l’URL del collegamento di alias, questo deve essere trasmesso anche alla pagina di destinazione finale. Utilizza la variabile *`s_pageURL`* per ignorare l&#39;URL corrente.

Poiché esistono diversi modi per implementare un reindirizzamento, è necessario rivolgersi al gruppo operativo Web o al partner pubblicitario online per identificare i meccanismi specifici che eseguono i reindirizzamenti sul sito Web.

## Acquisire il referente originale {#original}

In genere, [!DNL Analytics] otterrà l&#39;URL di riferimento dalla proprietà [!UICONTROL document.referrer] del browser e l&#39;URL corrente dalla proprietà [!UICONTROL document.location]. Trasmettendo i valori alle variabili *`referrer`* e *`pageURL`*, è possibile ignorare l&#39;elaborazione predefinita. Trasmettendo un valore alla variabile referrer, si comunica a [!DNL Analytics] di ignorare le informazioni sul referente nella proprietà [!UICONTROL document.referrer] e di utilizzare un valore alternativo definito dall&#39;utente.

Pertanto, la versione finale della pagina di destinazione dovrebbe contenere il seguente codice per correggere i problemi introdotti nello scenario &quot;biglietti aerei scontati&quot;.

```js
<script language="JavaScript" src="AppMeasurement.js"></script> 
<script language="JavaScript"><!-- 
/* You may give each page an identifying name, server, and channel on 
the next lines. */ 
s.pageName="" 
s.server="" 
s.campaign="" 
s.referrer="https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets" 
// Setting the s.pageURL variable is optional.
s.pageURL="https://www.flytohawaii.example"
```

## Verificare il referente con Adobe Debugger {#verify}

Eseguire un test per verificare che il referente, l&#39;URL di origine ( *`s_server`*) e le variabili della campagna vengano acquisiti.

Queste variabili saranno rappresentate come i seguenti parametri nel [Experience Cloud Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=it).

<table id="table_5F3B987D4D514CA283F7B9F52EBC2301"> 
 <thead> 
  <tr> 
   <th class="entry"> </th> 
   <th class="entry"> <b>URL o valore stringa di query</b> </th> 
   <th class="entry"> <b>Valore mostrato nel debugger DigitalPulse</b> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>Referente originale </p> </td> 
   <td> <p> <span class="filepath"> https://www.google.com/search%3F hl%3Den %26ie%3DUTF826q%3 Ddiscount%2Bairline%2Bticket </span> </p> </td> 
   <td> <p> <span class="filepath"> r=https:/ref=www.google.com/search?hl=en&amp;ie=UTF -8&amp;q=sconto+compagnia aerea+biglietti </span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p>URL della pagina </p> </td> 
   <td> <p> <span class="filepath"> https://www.flytohawaii.example </span> </p> </td> 
   <td> <p> <span class="filepath"> g=https://www.flytohawaii.example </span> </p> <p>Questo valore verrà visualizzato nel debugger di DigitalPulse se si utilizza la variabile <span class="varname"> pageURL </span>. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>URL della pagina di destinazione di Ultimate </p> </td> 
   <td> <p> <span class="filepath"> https://www.example.com </span> </p> </td> 
   <td> <p>Questo valore NON verrà visualizzato nel debugger DigitalPulse se si utilizza la variabile <span class="varname"> pageURL </span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

Il testo visualizzato nel debugger deve corrispondere al seguente esempio:

```
Image 
 
https://examplecom.112.2o7.net/b/ss/examplecom/1/JS-1.4/s61944015791667?[AQB] 
ndh=1 
t=4/8/20XX 13:34:28 4 360 
pageName=Welcome to example.com 
r=https://ref=www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets 
cc=USD 
g=https://www.flytohawaii.example 
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

Dopo aver verificato che Adobe [!UICONTROL Debugger] visualizzi queste variabili, è sempre utile verificare che i termini di ricerca e il dominio di riferimento originale (prima del reindirizzamento) registrino il traffico nei rapporti.
