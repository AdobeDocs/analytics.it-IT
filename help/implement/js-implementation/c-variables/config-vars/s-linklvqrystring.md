---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Implementazione di Analytics
seo-description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
solution: null
title: Variabili dinamiche
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

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

> [!NOTE] L'impostazione `linkLeaveQueryString=true` include tutti i parametri della stringa di query per tutti i collegamenti di uscita e i collegamenti di download.

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
