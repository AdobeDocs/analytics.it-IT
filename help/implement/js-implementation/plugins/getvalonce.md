---
description: Il plug-in getvalonce impedisce che una determinata variabile venga impostata sul valore definito in precedenza. Utilizza un cookie per determinare l'ultimo valore visualizzato di una variabile. Se il valore corrente corrisponde al valore del cookie, la variabile viene sovrascritta con una stringa vuota prima che venga inviata ai server di elaborazione di Adobe. Questo plug-in è utile per impedire l'inflazione di istanza variabile di conversione causata dall'aggiornamento della pagina o dal pulsante Indietro.
keywords: Implementazione di Analytics
seo-description: Il plug-in getvalonce impedisce che una determinata variabile venga impostata sul valore definito in precedenza. Utilizza un cookie per determinare l'ultimo valore visualizzato di una variabile. Se il valore corrente corrisponde al valore del cookie, la variabile viene sovrascritta con una stringa vuota prima che venga inviata ai server di elaborazione di Adobe. Questo plug-in è utile per impedire l'inflazione di istanza variabile di conversione causata dall'aggiornamento della pagina o dal pulsante Indietro.
seo-title: Getvalonce
solution: Analytics
subtopic: Plug-in
title: Getvalonce
topic: Sviluppatore e implementazione
uuid: 82 fe 0 da 5-3 bc 4-4632-8 c 62-7 b 5683 f 6 b 587
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# Getvalonce

Il plug-in getvalonce impedisce che una determinata variabile venga impostata sul valore definito in precedenza. Utilizza un cookie per determinare l'ultimo valore visualizzato di una variabile. Se il valore corrente corrisponde al valore del cookie, la variabile viene sovrascritta con una stringa vuota prima che venga inviata ai server di elaborazione di Adobe. Questo plug-in è utile per impedire l'inflazione di istanza variabile di conversione causata dall'aggiornamento della pagina o dal pulsante Indietro.

>[!IMPORTANT]
>
>This plug-in has not been validated to be compatible with [AppMeasurement for JavaScript](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8). See [AppMeasurement Plug-in Support](../../../implement/js-implementation/c-appmeasurement-js/plugins-support.md#concept_E31A189BC8A547738666EB5E00D2252A).

**Parametri**

```js
s.eVar1=s.getValOnce(variable,cookie,expiration,minute);
```

* **Variabile:** La variabile che verrà selezionata. In genere corrisponde alla stessa variabile definita.
* **Cookie:** Il nome del cookie che memorizza il valore precedente da confrontare. Il cookie può essere un qualsiasi valore.
* (Optional) **Expiration:** The number of days the cookie will expire. Se non viene impostata o impostata su 0, la scadenza predefinita è la sessione del browser.
* (Optional) **Minute:** If you set this to the string value *`m`*, the expiration value is defined in minutes instead of days. If not set, *`days`* is the default expiration.

**Proprietà**

* Questo plug-in viene comunemente utilizzato nelle variabili di conversione. However, you can use it on any [!DNL Analytics] variable.
* Quando Javascript rileva questa funzione, confronta il valore definito con quello memorizzato nel cookie. Se il valore definito è diverso dal valore del cookie, viene impostato il valore definito. Se il valore definito è uguale al valore del cookie, viene restituita una stringa vuota.
* Il cookie può memorizzare solo un singolo valore, il che significa che il plug-in avrà l'aspetto solo dell'ultimo valore definito.
* Il plug-in non impedisce a tutti i valori di definire la variabile dopo che è stata definita. Il plug-in impedisce che l'ultimo valore venga impostato più volte consecutivamente.
* Se l'utente finale blocca o rifiuta i cookie, il valore originale viene sempre restituito.
* The plug-in's session is different from what [!DNL Analytics] defines as a session (or visit). [!DNL Analytics] termina una sessione dopo 12 ore di attività o 30 minuti di inattività. Poiché il plug-in utilizza la definizione sessione del browser, viene terminata solo dopo che l'utente chiude la scheda o esce dal browser.

   * If a user closes your page, opens a different tab and navigates back to your site within 30 minutes, the plug-in creates a new session while keeping the [!DNL Analytics] visit open.
   * If a user keeps the browser window open without clicking on a link for more than 30 minutes, the [!DNL Analytics] visit expires while keeping the browser session open.

>[!NOTE]
>
>Le istruzioni seguenti richiedono di modificare il codice della raccolta dati sul sito. This can affect data collection on your site, and should only be done by a developer with experience using and implementing [!DNL Analytics].

## Implementazione {#section_177FF7F425B64FFB83CDE15A6ACC8D21}

>[!NOTE]
>
>If your organization uses Marketing Channels and has rules set up based on `s.campaign`, it is recommended that you not use the getValOnce plugin when setting the `s.campaign`value. Ciò potrebbe portare a un canale errato assegnato a un click-through della campagna secondaria.

To implement this plug-in, place the following code within your [!DNL s_code.js] file

```js
/******************************************************************** 
 * 
 * Main Plug-in code (should be in Plug-ins section) 
 * 
 *******************************************************************/ 
/* 
 * Plugin: getValOnce_v1.11 
 */ 
s.getValOnce=new Function("v","c","e","t","" 
+"var s=this,a=new Date,v=v?v:'',c=c?c:'s_gvo',e=e?e:0,i=t=='m'?6000" 
+"0:86400000,k=s.c_r(c);if(v){a.setTime(a.getTime()+e*i);s.c_w(c,v,e" 
+"==0?0:a);}return v==k?'':v");
```

Once the above code is implemented, define the desired variable using the *`getValOnce`* function. Di seguito sono riportati alcuni esempi su come implementarlo:

**Non viene definito lo stesso valore della campagna se viene rilevato un valore duplicato entro 30 giorni dal cookie impostato:**`s.campaign=s.getValOnce(s.campaign,'s_cmp',30);`**Impedisce che venga definito lo stesso valore evar 1 se viene rilevato un valore duplicato entro 30 minuti dal cookie impostato:**`s.eVar1=s.getValOnce(s.eVar1,'s_ev1',30,'m');`**Impedisce che lo stesso valore evar 2 venga definito più volte nella stessa sessione del browser:**`s.eVar2=s.getValOnce(s.eVar2,'s_ev2');`**Note**

* Verifica sempre in modo esteso le installazioni dei plug-in per garantire che la raccolta dati sia come previsto prima della distribuzione in un ambiente di produzione.
* Assicurati di eliminare il cookie o utilizzare nuovi valori univoci durante il test o le variabili non verranno inviate.

