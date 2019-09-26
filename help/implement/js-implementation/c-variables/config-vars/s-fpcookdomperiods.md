---
description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
keywords: Implementazione di Analytics
seo-description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
solution: null
title: Variabili dinamiche
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.fpCookieDomainPeriods

La variabile si riferisce ai cookie impostati da JavaScript (s_sq, s_cc, plug-in) che sono intrinsecamente cookie di prime parti anche se la vostra implementazione utilizza i domini di terze parti 2o7.net o omtrdc.net.

La *`fpCookieDomainPeriods`* variabile non deve mai essere impostata dinamicamente. If you use *`cookieDomainPeriods`*, it is good practice to specify a value for *`fpCookieDomainPeriods`* as well. *`fpCookieDomainPeriods`* eredita il *`cookieDomainPeriods`* valore. Note that  does not affect the domain on which the visitor ID cookie is set, even if your implementation treats this as a first-party cookie.*`fpCookieDomainPeriods`*

The name " " refers to the number of periods (".") *`fpCookieDomainPeriods`* nel dominio quando il dominio inizia con "www." For example, `www.mysite.com` contains two periods, while `www.mysite.co.jp` contains three periods. Un altro modo per descrivere la variabile è il numero di sezioni nel dominio principale del sito (due per `mysite.com` e tre per `mysite.co.jp`).

Il file [!DNL AppMeasurement] per JavaScript utilizza la *`fpCookieDomainPeriods`* variabile per determinare il dominio con cui impostare cookie di prime parti diversi dal cookie [!UICONTROL visitor ID] (s_vi). There are at least two cookies affected by this variable, including  and  (used for visitor click map and cookie checking respectively). `s_sq``s_cc` Cookies used by plug-ins such as [!UICONTROL getValOnce] are also affected.

| Max Size | Debugger Parameter | Reports Populated | Valore predefinito |
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

## Configuration Settings

Nessuno