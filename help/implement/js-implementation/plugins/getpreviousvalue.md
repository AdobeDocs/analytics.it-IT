---
description: Acquisisce il valore di una variabile Analytics nella visualizzazione pagina successiva. Ad esempio, è possibile utilizzare il plug-in per acquisire il valore s. pagename dalla visualizzazione pagina precedente in una variabile Traffico personalizzato. Inoltre, dispone di un'opzione per acquisire un valore precedente solo quando sono impostati eventi di successo.
keywords: Implementazione di Analytics
seo-description: Acquisisce il valore di una variabile Analytics nella visualizzazione pagina successiva. Ad esempio, è possibile utilizzare il plug-in per acquisire il valore s. pagename dalla visualizzazione pagina precedente in una variabile Traffico personalizzato. Inoltre, dispone di un'opzione per acquisire un valore precedente solo quando sono impostati eventi di successo.
seo-title: Getpreviousvalue
solution: Analytics
subtopic: Plug-in
title: Getpreviousvalue
topic: Sviluppatore e implementazione
uuid: 20 da 7 b 4 a -9820-4690-a 1 cc-d 10 b 6 dd 627 a 7
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# Getpreviousvalue

Acquisisce il valore di una variabile Analytics nella visualizzazione pagina successiva. Ad esempio, è possibile utilizzare il plug-in per acquisire il valore s. pagename dalla visualizzazione pagina precedente in una variabile Traffico personalizzato. Inoltre, dispone di un'opzione per acquisire un valore precedente solo quando sono impostati eventi di successo.

>[!NOTE]
>
>Le istruzioni seguenti richiedono di modificare il codice della raccolta dati sul sito. This can affect data collection on your site, and should only be done by a developer with experience using and implementing [!DNL Analytics].

## Plug-in Code and Implementation {#section_92E94A96A4764113B5588F1B83E3DE2C}

**SEZIONE CONFIG**: Nessuna modifica necessaria per questa sezione.

**Configurazione plug-in**

Place the following code within the *`s_doPlugins()`* function, which is located in the area of the *`s_code.js`* file labeled *Plugin Config*. Scegliete una variabile Traffico personalizzato (s. prop) o una variabile Conversione personalizzata (s. evar) per l'acquisizione di dati di valore persistenti. Deve trattarsi di una variabile abilitata tramite Admin Console, ma non attualmente utilizzata per nessun altro scopo. Potete utilizzare l'esempio seguente e aggiornarlo in base alle vostre esigenze.

`s.prop1=s.getPreviousValue(s.pageName,'gpv_pn','event1');`

*`s.getPreviousValue`* sono dotati di tre argomenti:

1. The variable to be captured from the previous page ( *`s.pageName`* above).
1. The cookie name for use in storing the value for retrieval ( *`gpv_pn`* above).
1. The events that must be set on the page view in order to trigger the retrieval of the previous value ( *`event1`* above). Se lasciato vuoto o omesso, il plug-in acquisisce il valore precedente in tutte le visualizzazioni pagina.

**SEZIONE PLUGINS**: Aggiungete il codice seguente all'area del [!DNL s_code.js] file etichettata in PLUGINS SECTION. Non apportate modifiche a questa parte del codice plug-in.

```js
/* 
 * Plugin: getPreviousValue_v1.0 - return previous value of designated 
 * variable (requires split utility) 
 */ 
s.getPreviousValue=new Function("v","c","el","" 
+"var s=this,t=new Date,i,j,r='';t.setTime(t.getTime()+1800000);if(el" 
+"){if(s.events){i=s.split(el,',');j=s.split(s.events,',');for(x in i" 
+"){for(y in j){if(i[x]==j[y]){if(s.c_r(c)) r=s.c_r(c);v?s.c_w(c,v,t)" 
+":s.c_w(c,'no value',t);return r}}}}}else{if(s.c_r(c)) r=s.c_r(c);v?" 
+"s.c_w(c,v,t):s.c_w(c,'no value',t);return r}"); 
/* 
 * Utility Function: split v1.5 - split a string (JS 1.0 compatible) 
 */ 
s.split=new Function("l","d","" 
+"var i,x=0,a=new Array;while(l){i=l.indexOf(d);i=i>-1?i:l.length;a[x" 
+"++]=l.substring(0,i);l=l.substring(i+d.length);}return a"); 
```

**Note**

* Verifica sempre in modo esteso le installazioni dei plug-in per garantire che la raccolta dati sia come previsto prima della distribuzione in un ambiente di produzione.
* If no value is present for the selected variable on any given page, the text *no value* will be set in the cookie.
* È stata impostata una scadenza del cookie fisso di 30 minuti per ogni cookie, e aggiornata con ogni caricamento di pagina. Il plug-in funziona per la durata di una visita.
* Because the function must be called as part of the plug-ins section of code, the code runs each time *`s.t()`* or *`s.tl()`* is called.

* The chosen variable should be populated with a value prior to the call to *`s.getPreviousValue`*. Because the *`s_doPlugins()`* function is executed after the variables on the page are populated, this issue rarely occurs. It should only be a matter of concern if the variable used with this plug-in is populated within the *`s_doPlugins()`* function and after the call to *`s.getPreviousValue`*.

