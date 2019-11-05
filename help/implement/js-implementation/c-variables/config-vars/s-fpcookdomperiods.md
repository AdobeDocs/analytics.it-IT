---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Implementazione di Analytics
seo-description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
solution: null
title: Variabili dinamiche
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# s.fpCookieDomainPeriods

La variabile si riferisce ai cookie impostati da JavaScript (s_sq, s_cc, plug-in) che sono intrinsecamente cookie di prime parti anche se la vostra implementazione utilizza i domini di terze parti 2o7.net o omtrdc.net.

La *`fpCookieDomainPeriods`* variabile non deve mai essere impostata dinamicamente. Se si utilizza *`cookieDomainPeriods`*, è buona norma specificare *`fpCookieDomainPeriods`* anche un valore. *`fpCookieDomainPeriods`* eredita il *`cookieDomainPeriods`* valore. Tieni presente che *`fpCookieDomainPeriods`* non influisce sul dominio in cui è impostato il cookie dell’ID visitatore, anche se l’implementazione lo tratta come cookie di prime parti.

Il nome " *`fpCookieDomainPeriods`*" si riferisce al numero di punti (".") nel dominio quando il dominio inizia con "www." Ad esempio, `www.mysite.com` contiene due periodi, mentre `www.mysite.co.jp` contiene tre periodi. Un altro modo per descrivere la variabile è il numero di sezioni nel dominio principale del sito (due per `mysite.com` e tre per `mysite.co.jp`).

Il file [!DNL AppMeasurement] per JavaScript utilizza la *`fpCookieDomainPeriods`* variabile per determinare il dominio con cui impostare cookie di prime parti diversi dal cookie [!UICONTROL visitor ID] (s_vi). Questa variabile interessa almeno due cookie, inclusi `s_sq` e `s_cc` (utilizzati rispettivamente per il controllo delle mappe dei clic dei visitatori e dei cookie). Anche i cookie utilizzati da plug-in come [!UICONTROL getValOnce] vengono modificati.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | N/D | cookieDomainPeriods |

## Codice di esempio per l'impostazione delle variabili di dominio del cookie

```js
s.fpCookieDomainPeriods="2" 
var d=window.location.hostname 
if(d.indexOf('.co.uk')>-1||d.indexOf('.com.au')>-1) 
  s.fpCookieDomainPeriods="3" 
```

## Sintassi e valori possibili

La *`cookieDomainPeriods`* variabile deve essere una stringa, come illustrato di seguito.

```js
s.fpCookieDomainPeriods="3"
```

## Esempi

```js
s.fpCookieDomainPeriods="3"
```

```js
s.fpCookieDomainPeriods="2"
```

## Impostazioni di configurazione

Nessuno
