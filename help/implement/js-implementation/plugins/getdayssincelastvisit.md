---
description: Determina il numero di giorni trascorsi dal quale un utente ha visitato il sito e acquisisce queste informazioni in una variabile Analytics.
keywords: Implementazione di Analytics
seo-description: Determina il numero di giorni trascorsi dal quale un utente ha visitato il sito e acquisisce queste informazioni in una variabile Analytics.
seo-title: Getdayssincelastvisit
solution: Analytics
subtopic: Plug-in
title: Getdayssincelastvisit
topic: Sviluppatore e implementazione
uuid: cad 95882-3 bd 0-4 f 94-a 0 c 3-4 e 7 b 6058 d 246
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# Getdayssincelastvisit

Determina il numero di giorni trascorsi dal quale un utente ha visitato il sito e acquisisce queste informazioni in una variabile Analytics.

>[!IMPORTANT]
>
>[Analysis Workspace](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/) ora include una **[!UICONTROL Days since last visit]** dimensione dalla casella, con conseguente nullizzazione della necessità di questo plug-plugin.

I dati di frequenza restituiti possono essere utilizzati per rispondere alle seguenti domande:

* Con quale frequenza gli utenti riprendono il mio sito?
* How does return frequency related with conversion? Gli acquirenti ripetono la visita frequente o raramente?
* Gli utenti che fanno clic sulle mie campagne torneranno spesso?

Il plug-in può anche generare valori utilizzati per la segmentazione. Ad esempio, puoi creare un segmento per visualizzare tutti i dati per solo quelle visite che sono precedute da almeno 30 giorni di non visite da parte dell'utente.

>[!NOTE]
>
>Le istruzioni seguenti richiedono di modificare il codice della raccolta dati sul sito. This can affect data collection on your site, and should only be done by a developer with experience using and implementing [!DNL Analytics].

## Plug-in Code and Implementation {#section_5600DBB819F143D59527A73BD94418DE}

**SEZIONE DI CONFIG**

Nessuna modifica richiesta.

**Configurazione plug-in**

Place the following code within the `s_doPlugins()` function, which is located in the area of the [!DNL s_code.js] file labeled *Plugin Config*. Scegli una variabile Traffico personalizzato (s. prop) e/o una variabile Conversione personalizzata (s. evar) da utilizzare per acquisire i dati di frequenza restituiti. Questa selezione deve essere una variabile abilitata tramite Admin Console ma non è attualmente utilizzata per nessun altro scopo. L'esempio seguente viene fornito come esempio e deve essere aggiornato in modo appropriato in base alle esigenze.

```js
s.prop1=s.getDaysSinceLastVisit(Cookie_Name);
```

**PLUGINS SECTION**
Aggiungete il codice seguente all'area del [!DNL s_code.js] file etichettata in *PLUGINS SECTION*. Non apportate modifiche a questa parte del codice plug-in.

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

* Verifica sempre in modo esteso le installazioni dei plug-in per garantire che la raccolta dati sia come previsto prima della distribuzione in un ambiente di produzione.
* Il plug-in classifica gli utenti di una frequenza di ritorno nei seguenti gruppi:

   * Prima visita
   * Meno di 1 giorno
   * Meno di 7 giorni
   * Più di 7 giorni
   * Più di 30 giorni

* Questo plug-in si basa sui cookie che l'utente ha visitato in precedenza. If the browser does not accept cookies, the plug-in returns a value of *Cookies Not Supported*.

