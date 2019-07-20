---
description: Ottiene il tempo di caricamento della pagina in incrementi di un secondo e consente di memorizzare il valore in una prop, evar e/o in un evento numerico.
keywords: Implementazione di Analytics
seo-description: Ottiene il tempo di caricamento della pagina in incrementi di un secondo e consente di memorizzare il valore in una prop, evar e/o in un evento numerico.
seo-title: Getloadtime
solution: Analytics
title: Getloadtime
topic: Sviluppatore e implementazione
uuid: 5 d 26 a 69 b-cbde -4 be 1-bac 1-5 ee 8 a 4 e 55 ca 3
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# Getloadtime

Ottiene il tempo di caricamento della pagina in incrementi di un secondo e consente di memorizzare il valore in una prop, evar e/o in un evento numerico.

To use this plugin, you insert the function code, then call the function twice in your [!DNL s_code.js] file. Once at the beginning of the file, and then again in the `doPlugins` section. Questo plug-in viene intenzionalmente non definito come metodo dell'oggetto s. Ciò sarebbe stato aggiunto al tempo di caricamento delle pagine calcolato.

>[!NOTE]
>
>Le istruzioni seguenti richiedono di modificare il codice della raccolta dati sul sito. This can affect data collection on your site, and should only be done by a developer with experience using and implementing [!DNL Analytics].

## Plug-in Code and Implementation {#section_968AC379C3004C359A85AFED5A48D5AE}

**Aggiungere la funzione**

Add the following definition of the `s_getLoadTime` function in [!DNL s_code.js], anywhere before the "DO NOT ALTER ANYTHING BELOW THIS LINE" section:

```js
function s_getLoadTime(){if(!window.s_loadT){var b=new Date().getTime(),o=window.performance?performance.timing:0,a=o?o.requestStart:window.inHeadTS||0;s_loadT=a?Math.round((b-a)/100):''}return s_loadT}
```

**Chiamata della funzione iniziale**

Add a call to `s_getLoadTime()` near the beginning of [!DNL s_code.js], outside of any function.

**Chiamata alla funzione finale**

Add another call to `s_getLoadTime()` in the `s_doPlugins()` function, saving the returned value in a prop, eVar, and/or a numeric event.

Esempio utilizzo 1 - Salva il tempo di caricamento della pagina in prop 10 e evar 20:

```js
s.eVar20=s.prop10=s_getLoadTime();
```

Esempio utilizzo 2 - Salva il tempo di caricamento della pagina nell'evento numerico 99:

```js
if(s_getLoadTime())s.events=s.apl(s.events,'event90='+s_getLoadTime(),',',1);
```

**(Facoltativo) Aggiunta di supporto per browser meno recenti**

To support older browsers that don't provide the [window.performance.timing](https://www.html5rocks.com/en/tutorials/webperformance/basics/) property, include the following line in the HEAD section of the page's HTML near the beginning and prior to invoking .js, .css, or other files:

```
<script type="text/javascript">var inHeadTS=(new Date()).getTime();</script>
```

