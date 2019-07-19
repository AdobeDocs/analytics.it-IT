---
description: Determina se un visitatore è un nuovo visitatore o un visitatore ripetuto e acquisisce tali informazioni in una variabile Analytics.
keywords: Implementazione di Analytics
seo-description: Determina se un visitatore è un nuovo visitatore o un visitatore ripetuto e acquisisce tali informazioni in una variabile Analytics.
seo-title: Getnewrepeat
solution: Analytics
subtopic: Plug-in
title: Getnewrepeat
topic: Sviluppatore e implementazione
uuid: e 3 e 9 f 362-e 0 b 1-4 a 2 b-bb 5 b -98 eddaa 0 a 7 f 4
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# Getnewrepeat

Determina se un visitatore è un nuovo visitatore o un visitatore ripetuto e acquisisce tali informazioni in una variabile Analytics.

Utilizzate questo plug-in per rispondere alle seguenti domande:

* Che percentuale dei miei visitatori sono nuovi (rispetto ai visitatori ripetuti)?
* I visitatori restituiscono una conversione più elevata rispetto ai nuovi visitatori? Cos'è il rapporto?
* Le mie campagne di marketing causano persistenze nelle visite? Ad esempio, gli utenti che fanno clic sulle mie campagne torneranno successivamente?

>[!NOTE]
>
>Le istruzioni seguenti richiedono di modificare il codice della raccolta dati sul sito. This can affect data collection on your site, and should only be done by a developer with experience using and implementing [!DNL Analytics].

## Plug-in Code and Implementation {#section_92E94A96A4764113B5588F1B83E3DE2C}

**SEZIONE CONFIG**: Nessuna modifica necessaria per questa sezione.

**Configurazione plug-in**

Place the following code within the *`s_doPlugins()`* function, which is located in the area of the *`s_code.js`* file labeled *Plugin Config*. Scegliete una variabile Traffico personalizzato (s. prop) o una variabile Conversione personalizzata (s. evar) per l'acquisizione di dati di valore persistenti. Deve trattarsi di una variabile abilitata tramite Admin Console, ma non attualmente utilizzata per nessun altro scopo. Potete utilizzare l'esempio seguente e aggiornarlo in base alle vostre esigenze.

`s.prop1=s.getNewRepeat(30,'s_getNewRepeat');`

*`s.getNewRepeat`* hanno due argomenti facoltativi:

1. Il primo argomento opzionale è il numero di giorni per cui il cookie deve durare. Il valore predefinito se questo argomento viene omesso è 30 giorni.
1. Il secondo argomento opzionale è il nome del cookie. Se questo argomento viene omesso, viene utilizzato un valore predefinito.

**SEZIONE PLUGINS**: Aggiungete il codice seguente all'area del [!DNL s_code.js] file etichettata in PLUGINS SECTION. Non apportate modifiche a questa parte del codice plug-in.

```js
/* 
 * Plugin: getNewRepeat 1.2 - Returns whether user is new or repeat 
 */ 
s.getNewRepeat=new Function("d","cn","" 
+"var s=this,e=new Date(),cval,sval,ct=e.getTime();d=d?d:30;cn=cn?cn:" 
+"'s_nr';e.setTime(ct+d*24*60*60*1000);cval=s.c_r(cn);if(cval.length=" 
+"=0){s.c_w(cn,ct+'-New',e);return'New';}sval=s.split(cval,'-');if(ct" 
+"-sval[0]<30*60*1000&&sval[1]=='New'){s.c_w(cn,ct+'-New',e);return'N" 
+"ew';}else{s.c_w(cn,ct+'-Repeat',e);return'Repeat';}"); 
/* 
* Utility Function: split v1.5 (JS 1.0 compatible) 
*/ 
s.split=new Function("l","d","" 
+"var i,x=0,a=new Array;while(l){i=l.indexOf(d);i=i>-1?i:l.length;a[x" 
+"++]=l.substring(0,i);l=l.substring(i+d.length);}return a");
```

Verifica sempre in modo esteso le installazioni dei plug-in per garantire che la raccolta dati sia come previsto prima della distribuzione in un ambiente di produzione.
