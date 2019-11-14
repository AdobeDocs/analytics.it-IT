---
description: Determina se un visitatore è un nuovo visitatore o un visitatore ripetuto e acquisisce queste informazioni in una variabile di Analytics.
keywords: Analytics Implementation
solution: Analytics
subtopic: Plug-ins
title: getNewRepeat
topic: Developer and implementation
uuid: e3e9f362-e0b1-4a2b-bb5b-98eddaa0a7f4
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# getNewRepeat

Determina se un visitatore è un nuovo visitatore o un visitatore ripetuto e acquisisce queste informazioni in una variabile di Analytics.

Utilizzate questo plug-in per rispondere alle seguenti domande:

* Quale percentuale dei miei visitatori è nuova (invece di ripetere)?
* I visitatori di ritorno generano una conversione pro capite più elevata rispetto ai nuovi visitatori? Qual è questo rapporto?
* Le mie campagne di marketing causano persistenza tra le visite? Ad esempio, gli utenti che fanno clic sulle mie campagne torneranno più tardi?

> [!NOTE] Le istruzioni seguenti richiedono di modificare il codice di raccolta dei dati sul sito. Questo può influenzare la raccolta di dati sul sito e dovrebbe essere eseguito solo da uno sviluppatore con esperienza di utilizzo e implementazione [!DNL Analytics].

## Codice plug-in e implementazione {#section_92E94A96A4764113B5588F1B83E3DE2C}

**SEZIONE** CONFIGURAZIONE: Nessuna modifica richiesta per questa sezione.

**Configurazione plug-in**

Inserire il codice seguente all'interno della *`s_doPlugins()`* funzione, che si trova nell'area del *`s_code.js`* file denominato *Plugin Config*. Scegliete una variabile Traffico personalizzato (s.prop) o Conversione personalizzata (s.eVar) da usare per l’acquisizione di dati di valore persistenti. Deve essere una variabile abilitata tramite Admin Console, ma attualmente non utilizzata per altri scopi. Potete utilizzare l'esempio seguente e aggiornarlo in base alle vostre esigenze.

`s.prop1=s.getNewRepeat(30,'s_getNewRepeat');`

*`s.getNewRepeat`* dispone di due argomenti facoltativi:

1. Il primo argomento facoltativo è il numero di giorni di durata del cookie. Il valore predefinito se questo argomento viene omesso è 30 giorni.
1. Il secondo argomento facoltativo è il nome del cookie. Se questo argomento viene omesso, viene utilizzato un valore predefinito.

**SEZIONE** PLUG-IN: Aggiungere il codice seguente all'area del [!DNL s_code.js] file con etichetta PLUGINS SECTION. Non apportare modifiche a questa parte del codice plug-in.

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

Verificate sempre in modo esteso le installazioni dei plug-in per garantire che la raccolta dei dati avvenga come previsto prima della distribuzione in un ambiente di produzione.
