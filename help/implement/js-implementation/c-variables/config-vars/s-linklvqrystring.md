---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Analytics Implementation
solution: null
title: Variabili dinamiche
translation-type: tm+mt
source-git-commit: f1ebe5e89f62957c8bcc829be4b1a97463210f93

---


# s.linkLeftQueryString

Per impostazione predefinita, le stringhe di query sono escluse da tutti i rapporti.

Per alcuni collegamenti di uscita e di download, la parte importante dell’URL può trovarsi nella stringa di query, come illustrato nell’URL di esempio seguente.

```js
https://www.mycompany.com/download.asp?filename=myfile.exe
```

Il nome del file di download può essere definito nella stringa di query e, di conseguenza, la stringa di query è necessaria per rendere il [!UICONTROL File Downloads] rapporto più accurato.

La *`linkLeaveQueryString`* variabile determina se la stringa di query deve essere inclusa nei [!UICONTROL Exit Links] report e [!UICONTROL File Download] .

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|--- |--- |--- |--- |
| N/D | N/D | Esci dai download dei file dei collegamenti | false |

*Nota:L'impostazione`linkLeaveQueryString=true`include tutti i parametri della stringa di query per tutti i collegamenti di uscita e i collegamenti di download.*

## Sintassi

```js
s.linkLeaveQueryString=[false/true]
```

## Esempi

```js
s.linkLeaveQueryString=false
```

## Valori possibili

```js
s.linkLeaveQueryString=false
```

```js
s.linkLeaveQueryString=true
```

## Impostazioni di configurazione

Per questa variabile non è necessaria alcuna configurazione.

## Insidie, domande e suggerimenti

* L'impostazione `s.linkLeaveQueryString=true` include tutti i parametri della stringa di query per tutti i collegamenti di uscita e i collegamenti di download.
* La `linkLeaveQueryString` variabile non influisce sugli URL delle pagine registrati, sulla mappa clic del visitatore o sui [!UICONTROL Path] rapporti.

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