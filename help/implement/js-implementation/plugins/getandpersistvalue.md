---
description: Il plug-in getAndPersistValue ottiene un valore di scelta e lo compila in una variabile Analytics per un periodo determinato. Un utilizzo comune consiste nel vedere quante pagine vengono generate da una campagna dopo un click-through, per visualizzare facilmente le pagine più comuni per ogni campagna.
keywords: Analytics Implementation
solution: Analytics
subtopic: Plug-ins
title: getAndPersistValue
topic: Developer and implementation
uuid: ddeab80c-260e-44b6-8483-8b8b369ec19b
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# getAndPersistValue

Il plug-in getAndPersistValue ottiene un valore di scelta e lo compila in una variabile Analytics per un periodo determinato. Un utilizzo comune consiste nel vedere quante pagine vengono generate da una campagna dopo un click-through, per visualizzare facilmente le pagine più comuni per ogni campagna.

>[!IMPORTANT]
>
>Il plug-in non è stato convalidato per compatibilità con [AppMeasurement per JavaScript](/help/implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md). See [AppMeasurement Plug-in Support](/help/implement/js-implementation/c-appmeasurement-js/plugins-support.md).

Ad esempio, potete utilizzare questo plug-in per impostare un codice di tracciamento campagna dalla *`campaign`* variabile in una variabile Traffico personalizzato ( *`s.prop`*) per la visualizzazione della pagina di ogni visitatore creata per i 30 giorni successivi. Questo esempio consente di determinare quante pagine visualizzano il codice di tracciamento generato in seguito al click-through originale.

> [!NOTE] Le istruzioni seguenti richiedono di modificare il codice di raccolta dei dati sul sito. Questo può influenzare la raccolta di dati sul sito e dovrebbe essere eseguito solo da uno sviluppatore con esperienza di utilizzo e implementazione [!DNL Analytics].

## Codice plug-in e implementazione {#section_92E94A96A4764113B5588F1B83E3DE2C}

**SEZIONE** CONFIGURAZIONE: Nessuna modifica richiesta per questa sezione.

**Configurazione plug-in**

Inserire il codice seguente all'interno della *`s_doPlugins()`* funzione, che si trova nell'area del *`s_code.js`* file denominato *Plugin Config*. Scegliete una variabile Traffico personalizzato (s.prop) o Conversione personalizzata (s.eVar) da usare per l’acquisizione di dati di valore persistenti. Deve essere una variabile abilitata tramite Admin Console, ma attualmente non utilizzata per altri scopi. Potete utilizzare l'esempio seguente e aggiornarlo in base alle vostre esigenze.

`s.prop1=s.getAndPersistValue(s.campaign,'s_getval',30);`

*`s.getAndPersistValue`* presenta tre argomenti:

1. Variabile o valore attualmente popolato da mantenere ( *`s.campaign`* come mostrato sopra).
1. Nome del cookie, utilizzato per memorizzare il valore ( *`s_getval`* illustrato sopra).
1. Periodo di tempo per la persistenza, in giorni. "30", come mostrato sopra, causa il popolamento del valore nella variabile selezionata su ogni visualizzazione di pagina eseguita dall'utente per i successivi 30 giorni. Se omesso, l'impostazione predefinita è *session*.

**SEZIONE** PLUG-IN: Aggiungere il codice seguente all'area del [!DNL s_code.js] file con etichetta PLUGINS SECTION. Non apportare modifiche a questa parte del codice plug-in.

```js
/* 
 * Plugin: getAndPersistValue 0.3 - get a value on every page 
 */ 
s.getAndPersistValue=new Function("v","c","e","" 
+"var s=this,a=new Date;e=e?e:0;a.setTime(a.getTime()+e*86400000);if(" 
+"v)s.c_w(c,v,e?a:0);return s.c_r(c);");
```

Verificate sempre in modo esteso le installazioni dei plug-in per garantire che la raccolta dei dati avvenga come previsto prima della distribuzione in un ambiente di produzione.
