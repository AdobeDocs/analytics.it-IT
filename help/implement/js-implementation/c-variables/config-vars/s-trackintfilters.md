---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Implementazione di Analytics
seo-description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
solution: null
title: Variabili dinamiche
translation-type: tm+mt
source-git-commit: 8c06a54ccd652f3f915af3af040e9cc69f01d0c1

---



# s.linkInternalFilters

La variabile viene utilizzata per determinare quali collegamenti sul sito sono collegamenti di uscita.

Si tratta di un elenco di filtri separati da virgole che rappresentano i collegamenti che fanno parte del sito.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | Percorsi &gt; Voci ed uscite &gt; Esci dai collegamenti |  |

> [!NOTE] In precedenza avevamo suggerito di impostare linkInternalFilters su javascript:. Tuttavia, ciò ha comportato la visualizzazione di tutti i domini esterni, compreso il dominio corrente su cui risiede il tag. Se desiderate che più domini siano considerati interni, potete aggiungerli, come mostrato negli esempi seguenti.

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

## Tracciamento automatico dei collegamenti di uscita e dei download dei file

Il file JavaScript può essere configurato per tenere traccia automaticamente dei download dei file e dei collegamenti di uscita, in base ai parametri che definiscono i tipi di file di download e i collegamenti di uscita.

I parametri che controllano il tracciamento automatico sono i seguenti:

```
s.trackDownloadLinks=true 
s.trackExternalLinks=true 
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,doc,pdf,xls" 
s.linkInternalFilters="javascript:,mysite.com,[more filters here]" 
s.linkLeaveQueryString=false 
```

I parametri `trackDownloadLinks` e `trackExternalLinks` determinare se sono abilitati il download automatico dei file e il tracciamento dei collegamenti di uscita. Quando attivato, qualsiasi collegamento con un tipo di file che corrisponda a uno dei valori in `linkDownloadFileTypes` viene tracciato automaticamente come download di file. Qualsiasi collegamento con un URL che non contiene uno dei valori in `linkInternalFilters` viene tracciato automaticamente come collegamento di uscita.

In JavaScript H.25.4 (rilasciato a febbraio 2013), il tracciamento automatico dei collegamenti di uscita è stato aggiornato per ignorare sempre i collegamenti con `HREF` gli attributi che iniziano con `#`, `about:`, o `javascript:`.

### Esempio 1

I tipi di file `.jpg` e `.aspx` non sono inclusi in `linkDownloadFileTypes` precedenza, pertanto nessun clic su di essi viene tracciato automaticamente e segnalato come download di file.

Il parametro `linkLeaveQueryString` modifica la logica utilizzata per determinare i collegamenti di uscita. Se `linkLeaveQueryString`=false, i collegamenti di uscita sono determinati utilizzando solo il dominio, il percorso e la parte file dell’URL del collegamento. Se `linkLeaveQueryString`=true, per determinare un collegamento di uscita viene utilizzata anche la porzione stringa della query dell’URL del collegamento.

### Esempio 2

Con le seguenti impostazioni, l'esempio seguente verrà conteggiato come collegamento di uscita:

```
//JS file  
s.linkInternalFilters="javascript:,mysite.com" 
s.linkLeaveQueryString=false 
 
//HTML file 
<a href='https://othersite.com/index.html?r=mysite.com'>Visit Other Site!</a> 
```

### Esempio 3

Con le seguenti impostazioni, il collegamento seguente non viene conteggiato come collegamento di uscita:

```
//JS file  
s.linkInternalFilters="javascript:,mysite.com" 
s.linkLeaveQueryString=true 
 
//HTML  
<a href='https://othersite.com/index.html?r=mysite.com'>Visit Other Site</a> 
```

*Nota: È possibile tenere traccia di un singolo collegamento solo come collegamento di download o uscita del file, con il download prioritario. Se un collegamento è un collegamento di uscita e un download di file basato sui parametri`linkDownloadFileTypes`e`linkInternalFilters`, viene tracciato e segnalato come download di file e non come collegamento di uscita.*
