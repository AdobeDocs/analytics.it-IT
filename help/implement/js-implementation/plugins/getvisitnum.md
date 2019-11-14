---
description: Il plug-in getVisitNum determina il numero di visite effettuate da un utente al sito e acquisisce tale numero in una variabile di Analytics.
keywords: Analytics Implementation
solution: Analytics
subtopic: Plug-ins
title: getVisitNum
topic: Developer and implementation
uuid: 27d57f92-fffb-44d0-b9ca-9da93323f64c
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# getVisitNum

Il plug-in getVisitNum determina il numero di visite effettuate da un utente al sito e acquisisce tale numero in una variabile di Analytics.

## Codice plug-in e implementazione {#section_92E94A96A4764113B5588F1B83E3DE2C}

**SEZIONE** CONFIGURAZIONE: Nessuna modifica richiesta per questa sezione.

**Configurazione plug-in**

Inserire il codice seguente all'interno della *`s_doPlugins()`* funzione, che si trova nell'area del *`s_code.js`* file denominato *Plugin Config*. Scegliete una variabile Traffico personalizzato (s.prop) o Conversione personalizzata (s.eVar) da usare per l’acquisizione dei dati del numero di visita. Deve trattarsi di una variabile abilitata tramite Admin Console, ma attualmente non utilizzata per altri scopi. Potete utilizzare l'esempio seguente e aggiornarlo in base alle vostre esigenze.

`s.prop1=s.getVisitNum();`

> [!NOTE] Le istruzioni seguenti richiedono di modificare il codice di raccolta dei dati sul sito. Questo può influenzare la raccolta di dati sul sito e dovrebbe essere eseguito solo da uno sviluppatore con esperienza di utilizzo e implementazione [!DNL Analytics].

**SEZIONE** PLUG-IN: Aggiungere il codice seguente all'area del [!DNL s_code.js] file con etichetta PLUGINS SECTION. Non apportare modifiche a questa parte del codice plug-in.

```js
/* 
* Plugin: getVisitNum - version 3.0 
*/ 
s.getVisitNum=new Function("tp","c","c2","" 
+"var s=this,e=new Date,cval,cvisit,ct=e.getTime(),d;if(!tp){tp='m';}" 
+"if(tp=='m'||tp=='w'||tp=='d'){eo=s.endof(tp),y=eo.getTime();e.setTi" 
+"me(y);}else {d=tp*86400000;e.setTime(ct+d);}if(!c){c='s_vnum';}if(!" 
+"c2){c2='s_invisit';}cval=s.c_r(c);if(cval){var i=cval.indexOf('&vn=" 
+"'),str=cval.substring(i+4,cval.length),k;}cvisit=s.c_r(c2);if(cvisi" 
+"t){if(str){e.setTime(ct+1800000);s.c_w(c2,'true',e);return str;}els" 
+"e {return 'unknown visit number';}}else {if(str){str++;k=cval.substri" 
+"ng(0,i);e.setTime(k);s.c_w(c,k+'&vn='+str,e);e.setTime(ct+1800000);" 
+"s.c_w(c2,'true',e);return str;}else {s.c_w(c,e.getTime()+'&vn=1',e)" 
+";e.setTime(ct+1800000);s.c_w(c2,'true',e);return 1;}}"); 
s.dimo=new Function("m","y","" 
+"var d=new Date(y,m+1,0);return d.getDate();"); 
s.endof=new Function("x","" 
+"var t=new Date;t.setHours(0);t.setMinutes(0);t.setSeconds(0);if(x==" 
+"'m'){d=s.dimo(t.getMonth(),t.getFullYear())-t.getDate()+1;}else if(" 
+"x=='w'){d=7-t.getDay();}else {d=1;}t.setDate(t.getDate()+d);return " 
+"t;");
```

**Parametri**

* tp = (stringa, facoltativo) periodo di tracciamento. utilizzate "d" per il giorno, "w" per la settimana, "m" per il mese o un numero per un numero personalizzato di giorni.

   * Se è selezionato giorno, settimana o mese, il numero della visita verrà reimpostato alla fine del giorno/settimana/mese.
   * Se viene selezionato un numero personalizzato di giorni, il numero della visita verrà reimpostato dopo tale numero di giorni.
   * Se non viene fornito alcun valore, verrà utilizzato "m".

* c = (stringa, facoltativo) Specificare il nome del cookie persistente. Il valore predefinito è 's_vnum'.
* c2 = (stringa, facoltativo) Specificate il nome del cookie di sessione. Il valore predefinito è 's_invisit'

**Restituisce**

* restituisce il numero della visita (1,2,3, ecc.). Questo numero viene incrementato solo nella prima pagina di ogni visita.
* restituisce "numero di visita sconosciuto" se il plug-in non è in grado di identificare il numero di visita (i cookie sono bloccati).

**Esempi**

```js
s.prop1=s.getVisitNum(365); //custom length, 365 days. Default cookie names 
s.prop1=s.getVisitNum('w'); //resets weekly 
s.prop1=s.getVisitNum('m','s_vmonthnum','s_monthinvisit'); //resets montly, custom cookie names 
s.prop1=s.getVisitNum('d'); //resets daily
```

**Note**

* Verificate sempre in modo esteso le installazioni dei plug-in per garantire che la raccolta dei dati avvenga come previsto prima della distribuzione in un ambiente di produzione.
* Questo plug-in si basa sulla capacità di impostare i cookie nel browser Web dell'utente. Se l'utente non accetta i cookie, tutte le visite risulteranno essere le prime visite.

