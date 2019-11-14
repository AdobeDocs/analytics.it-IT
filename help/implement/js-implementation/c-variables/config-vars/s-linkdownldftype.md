---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Analytics Implementation
solution: null
title: Variabili dinamiche
translation-type: tm+mt
source-git-commit: f1ebe5e89f62957c8bcc829be4b1a97463210f93

---


# s.linkDownloadFileTypes

La variabile è un elenco separato da virgole di estensioni di file.

Se il sito contiene collegamenti a file con una di queste estensioni, gli URL di questi collegamenti verranno visualizzati nel [!UICONTROL File Downloads] rapporto.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|--- |--- |--- |--- |
| N/D | N/D | Traffico &gt; Traffico sito &gt; Download file | "exe,zip,wav,mp3,mov,mpg,avi,wmv, doc,pdf,xls" |

La *`linkDownloadFileTypes`* variabile è pertinente solo se *`trackDownloadLinks`* è impostata su "True".

Nel [!UICONTROL File Downloads] rapporto vengono contati solo i clic con il pulsante sinistro del mouse su un collegamento. Tutti i download di file che iniziano automaticamente quando una pagina viene caricata, o che vengono scaricati solo dopo un reindirizzamento, non vengono conteggiati nel [!UICONTROL File Downloads] rapporto. Quando fai clic con il pulsante destro del mouse su un file e seleziona "Salva destinazione con nome..." non viene conteggiata nel [!UICONTROL File Downloads] rapporto.

La *`linkDownloadFileTypes`* variabile può essere utilizzata per monitorare i clic sui feed RSS. Se disponete di collegamenti ai feed RSS con un .xml o un'altra estensione, aggiungendo ",xml" all' *`linkDownloadFileTypes`* elenco potete vedere la frequenza con cui viene fatto clic su ogni collegamento RSS.

## Sintassi e valori possibili

Includete solo estensioni di file (senza spazi).

```js
s.linkDownloadFileTypes="type1[,type2[,type3[...]]]"
```

Qualsiasi estensione di file può essere inclusa nell'elenco. Fate attenzione a non includere un'estensione file comune, come htm o aspx, in *`linkDownloadFileTypes`*. In questo modo viene inviata una richiesta immagine aggiuntiva per ogni clic, che verrà fatturata come chiamata server principale.

## Esempi

```js
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls"
```

```js
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls,xml"
```

## Impostazioni di configurazione*

Nessuno

## Insidie, domande e suggerimenti

* Nel [!UICONTROL File Downloads] rapporto vengono visualizzati solo i clic con il pulsante sinistro del mouse sui file di download.
* L'inclusione di un'estensione di file comune in *`linkDownloadFileTypes`* potrebbe aumentare notevolmente il totale delle chiamate server inviate ai server Adobe.
* I collegamenti ai reindirizzamenti sul lato server o alle pagine HTML che iniziano automaticamente il download di un file non vengono conteggiati a meno che l'estensione del file non sia inclusa *`linkDownloadFileTypes`*.
* I collegamenti che utilizzano JavaScript (come javascript:openLink( )) non vengono conteggiati nei download dei file.

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