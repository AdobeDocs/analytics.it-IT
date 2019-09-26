---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Implementazione di Analytics
seo-description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
solution: null
title: Variabili dinamiche
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.linkDownloadFileTypes

La variabile è un elenco separato da virgole di estensioni di file.

Se il sito contiene collegamenti a file con una di queste estensioni, gli URL di questi collegamenti verranno visualizzati nel [!UICONTROL File Downloads] rapporto.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|--- |--- |--- |--- |
| N/D | N/D | Traffico &gt; Traffico sito &gt; Download file | "exe,zip,wav,mp3,mov,mpg,avi,wmv, doc,pdf,xls" |

La *`linkDownloadFileTypes`* variabile è pertinente solo se *`trackDownloadLinks`* è impostata su "True".

Only left-mouse-clicks on a link are counted in the  report. [!UICONTROL File Downloads] All file downloads that start automatically when a page loads, or that are only downloaded after a redirect, are not counted in the [!UICONTROL File Downloads] report. When you right-click a file and select the "Save Target As..." option, it is not counted in the [!UICONTROL File Downloads] report.

La *`linkDownloadFileTypes`* variabile può essere utilizzata per monitorare i clic sui feed RSS. Se disponete di collegamenti ai feed RSS con un .xml o un'altra estensione, aggiungendo ",xml" all' *`linkDownloadFileTypes`* elenco potete vedere la frequenza con cui viene fatto clic su ogni collegamento RSS.

## Sintassi e valori possibili

Only include file extensions (no spaces).

```js
s.linkDownloadFileTypes="type1[,type2[,type3[...]]]"
```

Qualsiasi estensione di file può essere inclusa nell'elenco. Be careful not to include a common file extension, such as htm or aspx, in *`linkDownloadFileTypes`*. In questo modo viene inviata una richiesta immagine aggiuntiva per ogni clic, che verrà fatturata come chiamata server principale.

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