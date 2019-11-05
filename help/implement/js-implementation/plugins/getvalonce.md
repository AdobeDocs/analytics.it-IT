---
description: Il plug-in getValOnce impedisce che una determinata variabile venga impostata sul valore definito in precedenza. Utilizza un cookie per determinare l'ultimo valore visualizzato di una variabile. Se il valore corrente corrisponde al valore del cookie, la variabile viene sovrascritta con una stringa vuota prima di essere inviata ai server di elaborazione di Adobe. Questo plug-in è utile per evitare l’inflazione variabile di conversione causata dall’aggiornamento della pagina da parte degli utenti o facendo clic sul pulsante Indietro.
keywords: Implementazione di Analytics
seo-description: Il plug-in getValOnce impedisce che una determinata variabile venga impostata sul valore definito in precedenza. Utilizza un cookie per determinare l'ultimo valore visualizzato di una variabile. Se il valore corrente corrisponde al valore del cookie, la variabile viene sovrascritta con una stringa vuota prima di essere inviata ai server di elaborazione di Adobe. Questo plug-in è utile per evitare l’inflazione variabile di conversione causata dall’aggiornamento della pagina da parte degli utenti o facendo clic sul pulsante Indietro.
seo-title: getValOnce
solution: Analytics
subtopic: Plug-in
title: getValOnce
topic: Sviluppatore e implementazione
uuid: 82fe0da5-3bc4-4632-8c62-7b5683f6b587
translation-type: tm+mt
source-git-commit: 57fe1f6d613b9f54a5191ac8684d36bccfebf4e5

---


# getValOnce

Il plug-in getValOnce impedisce che una determinata variabile venga impostata sul valore definito in precedenza. Utilizza un cookie per determinare l'ultimo valore visualizzato di una variabile. Se il valore corrente corrisponde al valore del cookie, la variabile viene sovrascritta con una stringa vuota prima di essere inviata ai server di elaborazione di Adobe. Questo plug-in è utile per evitare l’inflazione variabile di conversione causata dall’aggiornamento della pagina da parte degli utenti o facendo clic sul pulsante Indietro.

>[!IMPORTANT]
>
>Il plug-in non è stato convalidato per compatibilità con [AppMeasurement per JavaScript](/help/implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md). See [AppMeasurement Plug-in Support](/help/implement/js-implementation/c-appmeasurement-js/plugins-support.md).

**Parametri**

```js
s.eVar1=s.getValOnce(variable,cookie,expiration,minute);
```

* **** Variabile: Variabile da verificare. In genere corrisponde alla variabile definita.
* **** Cookie: Nome del cookie in cui viene memorizzato il valore precedente da confrontare. Il cookie può essere di qualsiasi valore.
* **(Facoltativo)** Scadenza: Il numero di giorni in cui il cookie scade. Se non è impostato o impostato su 0, la scadenza predefinita è la sessione del browser.
* **(Facoltativo)** Minuto: Se si imposta questo valore sulla stringa *`m`*, il valore di scadenza è definito in minuti anziché in giorni. Se non è impostato, *`days`* è la scadenza predefinita.

**Proprietà**

* Questo plug-in è comunemente utilizzato sulle variabili di conversione. Tuttavia, potete utilizzarlo su qualsiasi [!DNL Analytics] variabile.
* Quando Javascript incontra questa funzione, confronta il valore definito con quello memorizzato nel cookie. Se il valore definito è diverso dal valore del cookie, viene impostato il valore definito. Se il valore definito è lo stesso del valore del cookie, viene restituita una stringa vuota.
* Il cookie può contenere un solo valore, il che significa che il plug-in è solo l'ultimo valore definito.
* Il plug-in non impedisce a tutti i valori di definire la variabile dopo che questa è stata definita. Il plug-in impedisce solo l'impostazione dell'ultimo valore più volte consecutiva.
* Se l'utente finale blocca o rifiuta i cookie, viene sempre restituito il valore originale.
* La sessione del plug-in è diversa da quella [!DNL Analytics] definita come sessione (o visita). [!DNL Analytics] termina una sessione dopo 12 ore di attività o 30 minuti di inattività. Poiché il plug-in utilizza la definizione di sessione del browser, viene terminato solo dopo che l'utente chiude la scheda o esce dal browser.

   * Se un utente chiude la pagina, apre una scheda diversa e torna al sito entro 30 minuti, il plug-in crea una nuova sessione mantenendo aperta la [!DNL Analytics] visita.
   * Se un utente tiene aperta la finestra del browser senza fare clic su un collegamento per più di 30 minuti, la [!DNL Analytics] visita scade mantenendo aperta la sessione del browser.

> [!NOTE] Le istruzioni seguenti richiedono di modificare il codice di raccolta dei dati sul sito. Questo può influenzare la raccolta di dati sul sito e dovrebbe essere eseguito solo da uno sviluppatore con esperienza di utilizzo e implementazione [!DNL Analytics].

## Implementazione {#section_177FF7F425B64FFB83CDE15A6ACC8D21}

> [!NOTE] Se la vostra azienda utilizza Marketing Channels e dispone di regole configurate in base a `s.campaign`, si consiglia di non utilizzare il plug-in getValOnce quando impostate il `s.campaign`valore. In questo modo si potrebbe determinare l'assegnazione di un canale errato in un click-through di una campagna secondaria.

Per implementare questo plug-in, inserite il seguente codice nel [!DNL s_code.js] file

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

Una volta implementato il codice, definite la variabile desiderata utilizzando la *`getValOnce`* funzione. Di seguito sono riportati diversi esempi di come può essere implementato:

****`s.campaign=s.getValOnce(s.campaign,'s_cmp',30);`**Impedire la definizione dello stesso valore della campagna se viene rilevato un valore duplicato entro 30 giorni dall’impostazione del cookie:
Impedisce** `s.eVar1=s.getValOnce(s.eVar1,'s_ev1',30,'m');`la definizione dello stesso valore eVar1 se viene rilevato un valore duplicato entro 30 minuti dall’impostazione del cookie:
Impedisce****che lo stesso valore eVar2 venga definito più volte nella stessa sessione del browser:
`s.eVar2=s.getValOnce(s.eVar2,'s_ev2');` **Note**

* Verificate sempre in modo esteso le installazioni dei plug-in per garantire che la raccolta dei dati avvenga come previsto prima della distribuzione in un ambiente di produzione.
* Accertatevi di eliminare il cookie o utilizzare nuovi valori univoci durante il test o che le variabili non vengano inviate.

