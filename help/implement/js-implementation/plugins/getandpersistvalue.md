---
description: Il plug-in getandpersistvalue ottiene un valore da voi e lo compila in una variabile di Analytics per un periodo determinato. Un utilizzo comune consiste nel vedere quante visualizzazioni di pagina vengono generate da una campagna dopo un click-through, che consente di vedere facilmente le pagine più comuni per ogni campagna.
keywords: Implementazione di Analytics
seo-description: Il plug-in getandpersistvalue ottiene un valore da voi e lo compila in una variabile di Analytics per un periodo determinato. Un utilizzo comune consiste nel vedere quante visualizzazioni di pagina vengono generate da una campagna dopo un click-through, che consente di vedere facilmente le pagine più comuni per ogni campagna.
seo-title: Getandpersistvalue
solution: Analytics
subtopic: Plug-in
title: Getandpersistvalue
topic: Sviluppatore e implementazione
uuid: ddeab 80 c -260 e -44 b 6-8483-8 b 8 b 369 ec 19 b
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# Getandpersistvalue

Il plug-in getandpersistvalue ottiene un valore da voi e lo compila in una variabile di Analytics per un periodo determinato. Un utilizzo comune consiste nel vedere quante visualizzazioni di pagina vengono generate da una campagna dopo un click-through, che consente di vedere facilmente le pagine più comuni per ogni campagna.

>[!IMPORTANT]
>
>This plug-in has not been validated to be compatible with [AppMeasurement for JavaScript](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8). See [AppMeasurement Plug-in Support](../../../implement/js-implementation/c-appmeasurement-js/plugins-support.md#concept_E31A189BC8A547738666EB5E00D2252A).

For example, you might use this plug-in to set a campaign tracking code from the *`campaign`* variable into a Custom Traffic ( *`s.prop`*) variable on each visitor's page view made for the next 30 days. Questo esempio consente di determinare il numero di visualizzazioni del codice di tracciamento generato come risultato del click-through originale.

>[!NOTE]
>
>Le istruzioni seguenti richiedono di modificare il codice della raccolta dati sul sito. This can affect data collection on your site, and should only be done by a developer with experience using and implementing [!DNL Analytics].

## Plug-in Code and Implementation {#section_92E94A96A4764113B5588F1B83E3DE2C}

**SEZIONE CONFIG**: Nessuna modifica necessaria per questa sezione.

**Configurazione plug-in**

Place the following code within the *`s_doPlugins()`* function, which is located in the area of the *`s_code.js`* file labeled *Plugin Config*. Scegliete una variabile Traffico personalizzato (s. prop) o una variabile Conversione personalizzata (s. evar) per l'acquisizione di dati di valore persistenti. Deve trattarsi di una variabile abilitata tramite Admin Console, ma non attualmente utilizzata per nessun altro scopo. Potete utilizzare l'esempio seguente e aggiornarlo in base alle vostre esigenze.

`s.prop1=s.getAndPersistValue(s.campaign,'s_getval',30);`

*`s.getAndPersistValue`* sono dotati di tre argomenti:

1. Currently populated variable or value to persist ( *`s.campaign`* shown above).
1. Cookie name, used to store the value ( *`s_getval`* shown above).
1. Periodo di tempo per la persistenza, in giorni. " 30 "come mostrato qui sopra causa la compilazione del valore nella variabile selezionata su ogni visualizzazione di pagina effettuata dall'utente per i successivi 30 giorni. If omitted, the setting defaults to *session*.

**SEZIONE PLUGINS**: Aggiungete il codice seguente all'area del [!DNL s_code.js] file etichettata in PLUGINS SECTION. Non apportate modifiche a questa parte del codice plug-in.

```js
/* 
 * Plugin: getAndPersistValue 0.3 - get a value on every page 
 */ 
s.getAndPersistValue=new Function("v","c","e","" 
+"var s=this,a=new Date;e=e?e:0;a.setTime(a.getTime()+e*86400000);if(" 
+"v)s.c_w(c,v,e?a:0);return s.c_r(c);");
```

Verifica sempre in modo esteso le installazioni dei plug-in per garantire che la raccolta dati sia come previsto prima della distribuzione in un ambiente di produzione.
