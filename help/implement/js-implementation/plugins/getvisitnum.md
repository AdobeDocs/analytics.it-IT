---
description: Il plug-in getvisitnum determina il numero di visite effettuate da un utente al sito e acquisisce il numero in una variabile Analytics.
keywords: Implementazione di Analytics
seo-description: Il plug-in getvisitnum determina il numero di visite effettuate da un utente al sito e acquisisce il numero in una variabile Analytics.
seo-title: Getvisitnum
solution: Analytics
subtopic: Plug-in
title: Getvisitnum
topic: Sviluppatore e implementazione
uuid: 27 d 57 f 92-fffb -44 d 0-b 9 ca -9 da 93323 f 64 c
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# Getvisitnum

Il plug-in getvisitnum determina il numero di visite effettuate da un utente al sito e acquisisce il numero in una variabile Analytics.

## Plug-in Code and Implementation {#section_92E94A96A4764113B5588F1B83E3DE2C}

**SEZIONE CONFIG**: Nessuna modifica necessaria per questa sezione.

**Configurazione plug-in**

Place the following code within the *`s_doPlugins()`* function, which is located in the area of the *`s_code.js`* file labeled *Plugin Config*. Scegliete una variabile Traffico personalizzato (s. prop) o una variabile Conversione personalizzata (s. evar) per l'acquisizione dei dati del numero di visite. Deve trattarsi di una variabile abilitata tramite Admin Console, ma non attualmente utilizzata per un altro scopo. Potete utilizzare l'esempio seguente e aggiornarlo in base alle vostre esigenze.

`s.prop1=s.getVisitNum();`

>[!NOTE]
>
>Le istruzioni seguenti richiedono di modificare il codice della raccolta dati sul sito. This can affect data collection on your site, and should only be done by a developer with experience using and implementing [!DNL Analytics].

**SEZIONE PLUGINS**: Aggiungete il codice seguente all'area del [!DNL s_code.js] file etichettata in PLUGINS SECTION. Non apportate modifiche a questa parte del codice plug-in.

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

* tp = (stringa, facoltativo) Periodo di tracciamento. use "d" for day, "w" for week, "m" for month, or a number for a custom number of days.

   * Se è selezionato giorno, settimana o mese, il numero di visita viene reimpostato alla fine del giorno/settimana/mese.
   * Se è selezionato un numero personalizzato di giorni, il numero di visite viene reimpostato dopo quel numero di giorni.
   * Se non viene fornito alcun valore, verrà utilizzato "m".

* c = (stringa, facoltativo) Specificate il nome del cookie persistente. Il valore predefinito è's_ vnum '.
* c 2 = (stringa, facoltativo) Specificate il nome del cookie della sessione. Il valore predefinito è_ invisit '

**Restituisce**

* restituisce il numero di visita (1,2,3, ecc.) della visita. Questo numero viene incrementato solo nella prima pagina di ogni visita.
* restituisce "numero visita sconosciuto" se il plug-in non è in grado di identificare il numero di visite (i cookie sono bloccati).

**Esempi**

```js
s.prop1=s.getVisitNum(365); //custom length, 365 days. Default cookie names 
s.prop1=s.getVisitNum('w'); //resets weekly 
s.prop1=s.getVisitNum('m','s_vmonthnum','s_monthinvisit'); //resets montly, custom cookie names 
s.prop1=s.getVisitNum('d'); //resets daily
```

**Note**

* Verifica sempre in modo esteso le installazioni dei plug-in per garantire che la raccolta dati sia come previsto prima della distribuzione in un ambiente di produzione.
* Questo plug-in si basa sulla capacità di impostare cookie nel browser Web dell'utente. Se l'utente non accetta i cookie, tutte le visite diventeranno visite.

