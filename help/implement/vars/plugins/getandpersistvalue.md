---
title: getAndPersistValue
description: Memorizzare un valore che può essere recuperato in un secondo momento.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '909'
ht-degree: 1%

---


# Plug-in Adobe: getAndPersistValue

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarvi a ottenere più valore da Adobe  Analytics. L&#39;Assistenza clienti Adobe non fornisce supporto per questo plug-in, inclusa l&#39;installazione o la risoluzione dei problemi. Se avete bisogno di aiuto con questo plug-in, contattate l&#39;Account Manager della vostra azienda. Possono organizzare una riunione con un consulente per assistenza.

Il `getAndPersistValue` plug-in consente di memorizzare un valore in un cookie che sarà possibile recuperare in seguito durante una visita. Assegna un ruolo simile alla [!UICONTROL Storage duration] funzione in  lancio Adobe Experience Platform. Adobe consiglia di utilizzare questo plug-in se desiderate mantenere automaticamente una variabile Analytics  allo stesso valore negli hit successivi dopo l’impostazione della variabile. Questo plug-in non è necessario se la funzione di Launch [!UICONTROL Storage duration] è sufficiente o se non è necessario impostare e mantenere le variabili sullo stesso valore negli hit successivi. La persistenza incorporata delle eVar non richiede l&#39;utilizzo di questo plug-in, in quanto queste variabili persistono sul lato server da parte di Adobe.

## Installare il plug-in utilizzando l&#39;estensione Lancio del Adobe Experience Platform 

Adobe offre un’estensione che consente di utilizzare la maggior parte dei plug-in usati comunemente.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
1. Fate clic sulla proprietà desiderata.
1. Vai alla [!UICONTROL Extensions] scheda, quindi fai clic sul [!UICONTROL Catalog] pulsante
1. Installare e pubblicare l’ [!UICONTROL Common Analytics Plugins] estensione
1. Se non lo avete già fatto, create una regola con l&#39;etichetta &quot;Inizializza plug-in&quot; con la seguente configurazione:
   * Condizione: nessuna
   * Evento: Core - Libreria caricata (Page Top)
1. Aggiungete un&#39;azione alla regola precedente con la seguente configurazione:
   * Estensione: Plug-in Analytics  comuni
   * Tipo azione: Initialize getAndPersistValue
1. Salvate e pubblicate le modifiche alla regola.

## Installare il plug-in utilizzando l&#39;editor di codice personalizzato Launch

Se non desiderate utilizzare l&#39;estensione del plug-in, potete utilizzare l&#39;editor di codice personalizzato.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
1. Fate clic sulla proprietà desiderata.
1. Vai alla [!UICONTROL Extensions] scheda, quindi fai clic sul [!UICONTROL Configure] pulsante sotto l&#39;estensione Adobe  Analytics.
1. Espandere la struttura [!UICONTROL Configure tracking using custom code] a soffietto, che mostra il [!UICONTROL Open Editor] pulsante.
1. Aprite l’editor di codice personalizzato e incollate il codice plug-in fornito di seguito nella finestra di modifica.
1. Salvate e pubblicate le modifiche nell’estensione Analytics .

## Installare il plug-in utilizzando AppMeasurement

Copiate e incollate il seguente codice in qualsiasi punto del file AppMeasurement dopo che è stata creata un&#39;istanza dell&#39;oggetto di tracciamento Analytics  (utilizzando [`s_gi`](../functions/s-gi.md)). La conservazione di commenti e numeri di versione del codice nell’implementazione consente ad Adobe di risolvere eventuali problemi.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getAndPersistValue v2.0 */
s.getAndPersistValue=function(vtp,cn,ex){var b=new Date;cn=cn?cn:"s_gapv";(ex=ex?ex:0)?b.setTime(b.getTime()+864E5*ex): b.setTime(b.getTime()+18E5);vtp||(vtp=this.c_r(cn));this.c_w(cn,vtp,b);return vtp};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

Il `getAndPersist` metodo utilizza i seguenti argomenti:

* **`vtp`** (obbligatorio): Il valore da mantenere da una pagina all’altra
* **`cn`** (facoltativo): Nome del cookie in cui memorizzare il valore. Se questo argomento non è impostato, il cookie viene denominato `"s_gapv"`
* **`ex`** (facoltativo): Il numero di giorni prima della scadenza del cookie. Se questo argomento è `0` o non è impostato, il cookie scade alla fine della visita (30 minuti di inattività).

Se la variabile nell&#39; `vtp` argomento è impostata, il plug-in imposta il cookie e quindi restituisce il valore del cookie. Se la variabile nell&#39; `vtp` argomento non è impostata, il plug-in restituisce solo il valore del cookie.

## Esempi

### Esempio n. 1

Il codice seguente imposta eVar21 uguale al valore &quot;hello&quot;.  Il codice imposta quindi il cookie ev21gapv, che scade tra 28 giorni, pari al valore di eVar21 (ovvero &quot;hello&quot;).  Il codice imposta quindi (ri)eVar21 come valore del cookie ev21gapv.

```js
s.eVar21 = "hello";
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Esempio n. 2

Si supponga che eVar21 non sia ancora stato impostato sulla pagina corrente ma sia stato impostato come &quot;hello&quot; in una pagina precedente negli ultimi 28 giorni.   Il codice seguente imposta eVar21 solo uguale al valore del cookie ev21gapv (ovvero &quot;hello&quot;).  Non reimposta il cookie ev21gapv perché eVar21 non è stato impostato sulla pagina corrente prima della chiamata della funzione.

```js
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Esempio n. 3

Si supponga che eVar21 non sia ancora stato impostato sulla pagina corrente ma sia stato impostato come &quot;hello&quot; in una pagina precedente negli ultimi 28 giorni.  Il codice seguente imposta solo prop35 uguale al valore del cookie ev21gapv (es. &quot;hello&quot;).  Non imposta eVar21.

```js
s.prop35 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Esempio n. 4

Il codice seguente imposta eVar21 come valore &quot;howdy&quot;.  Il codice imposta (o reimposta) il cookie ev21gapv, che scade tra 28 giorni, pari al valore di eVar21 (cioè &quot;howdy&quot;).  Il codice imposta quindi prop35 uguale al valore del cookie ev21gapv (es. &quot;howdy&quot;).

```js
s.eVar21 = "howdy";
s.prop35 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Esempio n. 5

Si supponga che s.eVar21 non sia stato impostato su alcuna pagina negli ultimi 28 giorni.  Il codice seguente imposta s.eVar21 uguale a zero, poiché il cookie ev21gapv sarebbe scaduto 28 giorni dopo l’ultima impostazione.

```js
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Esempio n. 6

Il codice seguente imposta eVar30 su &quot;shopping&quot;.  Quindi imposta il cookie s_gapv, che scade alla fine della sessione del browser, pari al valore di s.eVar30 (ovvero &quot;shopping&quot;).  Quindi, imposta s.eVar30 uguale al valore del cookie s_gapv (ovvero, la chiamata getAndPersistValue restituisce il valore del cookie s_gapv, che in questo caso è &quot;shopping&quot;).

```js
s.eVar30 = "shopping";
s.eVar30 = s.getAndPersistValue(s.eVar30);
```

Se s.eVar30 non è impostato su un valore esplicito su alcuna pagina aggiuntiva visualizzata durante la sessione, ma è impostato (in doPlugins) tramite il seguente codice...

```js
s.eVar30 = s.getAndPersistValue(s.eVar30);
```

...s.eVar30 verrà impostato su &quot;shopping&quot; (ovvero il valore persistente del cookie s_gapv)

## Cronologia versioni

### 2.0 (16 aprile 2018)

* Rilascio punto (dimensioni del codice più piccole)
* Se si passa 0 all&#39; `ex` argomento ora la scadenza viene forzata dopo 30 minuti di inattività anziché alla scadenza alla fine della sessione del browser.

### 1.0 (18 gennaio 2016)

* Versione iniziale.
