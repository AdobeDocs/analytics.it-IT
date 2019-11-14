---
description: Determina il numero di giorni dall'ultima visita di un utente al sito e acquisisce tali informazioni in una variabile di Analytics.
keywords: Analytics Implementation
solution: Analytics
subtopic: Plug-ins
title: getDaysSinceLastVisit
topic: Developer and implementation
uuid: cad95882-3bd0-4f94-a0c3-4e7b6058d246
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# getDaysSinceLastVisit

Determina il numero di giorni dall'ultima visita di un utente al sito e acquisisce tali informazioni in una variabile di Analytics.

>[!IMPORTANT]
>
>[Analysis Workspace](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/) ora include una **[!UICONTROL Days since last visit]** dimensione out-of-the-box, eliminando così la necessità di questo plug-in.

Questi dati sulla frequenza di ritorno possono essere utilizzati per rispondere alle seguenti domande:

* Con quale frequenza gli utenti rivisitano il sito?
* In che modo la frequenza di ritorno è correlata con la conversione? Gli acquirenti ripetuti visitano spesso o raramente?
* Gli utenti che fanno clic tra le campagne e tornano spesso?

Il plug-in può inoltre generare valori utilizzati per la segmentazione. Ad esempio, puoi creare un segmento per visualizzare tutti i dati relativi solo alle visite precedute da 30 o più giorni di non visita da parte dell'utente.

> [!NOTE] Le istruzioni seguenti richiedono di modificare il codice di raccolta dei dati sul sito. Questo può influenzare la raccolta di dati sul sito e dovrebbe essere eseguito solo da uno sviluppatore con esperienza di utilizzo e implementazione [!DNL Analytics].

## Codice plug-in e implementazione {#section_5600DBB819F143D59527A73BD94418DE}

**SEZIONE CONFIGURAZIONE**

Nessuna modifica richiesta.

**Configurazione plug-in**

Inserire il codice seguente all'interno della `s_doPlugins()` funzione, che si trova nell'area del [!DNL s_code.js] file denominato *Plugin Config*. Scegliete una variabile Traffico personalizzato (s.prop) e/o una variabile Conversione personalizzata (s.eVar) da usare per acquisire i dati della frequenza di ritorno. Questa selezione deve essere una variabile abilitata tramite Admin Console ma attualmente non utilizzata per altri scopi. Di seguito viene fornito un esempio e deve essere aggiornato in base alle proprie esigenze.

```js
s.prop1=s.getDaysSinceLastVisit(Cookie_Name);
```

**SEZIONE** PLUGINS Aggiungere il seguente codice all'area del [!DNL s_code.js] file etichettato *PLUGINS SECTION*. Non apportare modifiche a questa parte del codice plug-in.

```js
/* 
 * Plugin: Days since last Visit 1.1 - capture time from last visit 
 */ 
s.getDaysSinceLastVisit=new Function("c","" 
+"var s=this,e=new Date(),es=new Date(),cval,cval_s,cval_ss,ct=e.getT" 
+"ime(),day=24*60*60*1000,f1,f2,f3,f4,f5;e.setTime(ct+3*365*day);es.s" 
+"etTime(ct+30*60*1000);f0='Cookies Not Supported';f1='First Visit';f" 
+"2='More than 30 days';f3='More than 7 days';f4='Less than 7 days';f" 
+"5='Less than 1 day';cval=s.c_r(c);if(cval.length==0){s.c_w(c,ct,e);" 
+"s.c_w(c+'_s',f1,es);}else{var d=ct-cval;if(d>30*60*1000){if(d>30*da" 
+"y){s.c_w(c,ct,e);s.c_w(c+'_s',f2,es);}else if(d<30*day+1 && d>7*day" 
+"){s.c_w(c,ct,e);s.c_w(c+'_s',f3,es);}else if(d<7*day+1 && d>day){s." 
+"c_w(c,ct,e);s.c_w(c+'_s',f4,es);}else if(d<day+1){s.c_w(c,ct,e);s.c" 
+"_w(c+'_s',f5,es);}}else{s.c_w(c,ct,e);cval_ss=s.c_r(c+'_s');s.c_w(c" 
+"+'_s',cval_ss,es);}}cval_s=s.c_r(c+'_s');if(cval_s.length==0) retur" 
+"n f0;else if(cval_s!=f1&&cval_s!=f2&&cval_s!=f3&&cval_s!=f4&&cval_s" 
+"!=f5) return '';else return cval_s;");
```

**Note**

* Verificate sempre in modo esteso le installazioni dei plug-in per garantire che la raccolta dei dati avvenga come previsto prima della distribuzione in un ambiente di produzione.
* Il plug-in classifica gli utenti in base alla frequenza di ritorno nei seguenti gruppi:

   * Prima visita
   * Meno di 1 giorno
   * Meno di 7 giorni
   * Oltre 7 giorni
   * Oltre 30 giorni

* Questo plug-in si basa sui cookie per segnalare che un utente ha visitato in precedenza. Se il browser non accetta i cookie, il plug-in restituisce il valore *Cookie non supportati*.

