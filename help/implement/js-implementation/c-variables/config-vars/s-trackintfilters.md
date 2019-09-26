---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Implementazione di Analytics
seo-description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
solution: null
title: Variabili dinamiche
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---



# s.linkInternalFilters

La variabile viene utilizzata per determinare quali collegamenti sul sito sono collegamenti di uscita.

It is a comma-separated list of filters that represent the links that are part of the site.

| Max Size | Debugger Parameter | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | Paths &gt; Entries &amp; Exits &gt; Exit Links |  |

>[!NOTE]
>
>We had previously suggested setting the linkInternalFilters to javascript:. Tuttavia, ciò ha comportato la visualizzazione di tutti i domini esterni, compreso il dominio corrente su cui risiede il tag. If you want several domains to be considered internal, you can add those, as shown in the examples below.

La *`linkInternalFilters`* variabile viene utilizzata per determinare se un collegamento è un collegamento di uscita, definito come qualsiasi collegamento che allontani un visitatore dal sito. Se la finestra di destinazione di un collegamento di uscita è una finestra a comparsa o una finestra esistente, il collegamento non influisce sulla visualizzazione del collegamento nel rapporto dei collegamenti di uscita. I collegamenti di uscita vengono tracciati solo se *`trackExternalLinks`* è impostata su `"true"`. (Per informazioni su come Gestione dinamica dei tag gestisce i collegamenti di uscita, consulta [Tracciamento](https://marketing.adobe.com/resources/help/en_US/dtm/link_tracking.html) dei collegamenti nella documentazione di Gestione dinamica dei tag.) I filtri non *`linkInternalFilters`* fanno distinzione tra maiuscole e minuscole.

Per impostazione predefinita, l’elenco dei filtri *`linkInternalFilters`* si applica al dominio e al percorso di qualsiasi collegamento. Se *`linkLeaveQueryString`* è impostato su `"true"`, i filtri si applicano all’intero URL (dominio, percorso e stringa di query). I filtri vengono sempre applicati al percorso assoluto dell'URL, anche se come valore href viene utilizzato un percorso relativo.

Fai attenzione a includere tutti i domini del tuo sito (e tutti i partner che utilizzano il file JavaScript) in *`linkInternalFilters`*. Se non hai tutti i domini inclusi nell'elenco, tutti i collegamenti a tali domini vengono considerati collegamenti di uscita, aumentando le chiamate al server inviate. Se si desidera che più domini o società utilizzino un singolo [!DNL AppMeasurement] per il file JavaScript, è consigliabile compilare *`linkInternalFilters`* la pagina, ignorando il valore specificato nel file JavaScript. Se hai domini vanità che si reindirizzano immediatamente al tuo dominio principale, quei domini vanità non devono essere inclusi nell'elenco.

L’esempio seguente illustra come viene utilizzata questa variabile. In questo esempio, l’URL della pagina è `https://www.mysite.com/index.html`.

```js
s.trackExternalLinks=true 
s.linkInternalFilters="mysite.com" 
s.linkExternalFilters="" 
s.linkLeaveQueryString=false 
... 
<a href="https://www.mysite.com">Not an Exit Link</a> 
<a href="/careers/job_list.html">Not an Exit Link</a> 
<a href="https://www2.site3.com">Exit Link</a> 
<a href="https://www2.site1.com/partners/">Exit Link</a> 
```

## Sintassi e valori possibili

La *`linkInternalFilters`* variabile è un elenco separato da virgole di caratteri ASCII. Non sono consentiti spazi.

```js
s.linkInternalFilters="site1.com[,site2.com[,site3.net[...]]]"
```

## Esempi

```js
s.linkInternalFilters="mysite.com"
```

```js
s.linkInternalFilters="mysite.com,mysite.net,vanity1.com"
```

## Impostazioni di configurazione

Nessuno

## Insidie, domande e suggerimenti

* Includete tutti i domini in cui può essere servito il file [!DNL AppMeasurement] per JavaScript nell'elenco dei filtri.
* Controllate periodicamente il rapporto [!UICONTROL Paths] &gt; [!UICONTROL Entries & Exits] &gt; [!UICONTROL Exit] Collegamenti per verificare che nessuna delle voci del rapporto sia corretta.

* Rivedete periodicamente i contratti dei partner per determinare se contengono restrizioni al tracciamento dei collegamenti. Ad esempio, potrebbe essere vietato tenere traccia dei collegamenti visualizzati negli annunci visualizzati dai partner. Filtra i collegamenti dei partner aggiungendo il dominio a *`linkInternalFilters`*:

```js
s.linkInternalFilters="mysite.com,mysite.net,mypartner.net/adclick"
```
