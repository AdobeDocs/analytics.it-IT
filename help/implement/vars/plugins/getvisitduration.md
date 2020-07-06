---
title: getVisitDuration
description: Tieni traccia del tempo trascorso sul sito da un visitatore.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 1%

---


# Plug-in Adobe: getVisitDuration

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarvi a ottenere più valore da Adobe  Analytics. L&#39;Assistenza clienti Adobe non fornisce supporto per questo plug-in, inclusa l&#39;installazione o la risoluzione dei problemi. Se avete bisogno di aiuto con questo plug-in, contattate l&#39;Account Manager della vostra azienda. Possono organizzare una riunione con un consulente per assistenza.

Il `getVisitDuration` plug-in tiene traccia della quantità di tempo in minuti che il visitatore ha trascorso sul sito fino a quel momento. Adobe consiglia di utilizzare questo plug-in se desiderate tenere traccia del tempo cumulativo sul sito fino a quel momento, o per tenere traccia del tempo necessario per eseguire un&#39;attività. Questo plug-in non tiene traccia del tempo intercorso tra gli eventi; se questa funzionalità è desiderata, utilizzate il [`getTimeBetweenEvents`](gettimebetweenevents.md) plug-in.

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
   * Tipo azione: Initialize getVisitDuration
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
/* Adobe Consulting Plugin: getVisitDuration v2.0 */
s.getVisitDuration=function(){var d=new Date,c=d.getTime(),b=this.c_r("s_dur");if(isNaN(b)||18E5<c-b)b=c;var a=c-b;d.setTime(c+18E5); this.c_w("s_dur",b+"",d);if(0===a)return"first hit of visit";a=Math.floor(a/6E4);return 0===a?"less than a minute":1===a?"1 minute": a+" minutes"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

Il `getVisitDuration` metodo non utilizza argomenti. Restituisce uno dei seguenti valori:

* `"first hit of visit"`
* `"less than a minute"`
* `"1 minute"`
* `"[x] minutes"` (dove `[x]` è il numero di minuti trascorsi dall&#39;arrivo del visitatore sul sito)

Questo plug-in crea un cookie di prime parti denominato `"s_dur"`, corrispondente al numero di millisecondi trascorsi dall&#39;arrivo del visitatore sul sito. Il cookie scade dopo 30 minuti di inattività.

## Chiamate di esempio

### Esempio n. 1

Codice seguente...

```js
s.eVar10 = s.getVisitDuration();
```

...eVar10 è sempre uguale al numero di minuti passati da quando il visitatore è atterrato sul sito

### Esempio n. 2

Codice seguente...

```js
if(s.inList(s.events, "purchase")) s.eVar10 = s.getVisitDuration();
```

...utilizza il plug-in inList per verificare se la variabile eventi contiene l&#39;evento acquisto.  In tal caso, eVar10 verrà impostato come numero di minuti tra l&#39;inizio della visita e l&#39;ora di acquisto del visitatore.

### Esempio n. 3

Codice seguente...

```js
s.prop10 = s.getVisitDuration();
```

...imposta sempre prop10 uguale al numero di minuti passati da quando il visitatore è atterrato sul sito.  Questo risulta utile se il percorso del prop10 è abilitato.  Aggiungendo la metrica &quot;uscite&quot; al rapporto prop10 verrà visualizzato un rapporto dettagliato &quot;spargimento&quot; sul tempo impiegato da una visita in pochi minuti prima che un visitatore lasciasse il sito.

## Cronologia versioni

### 2.0 (2 maggio 2018)

* Rilascio punto (reanalisi completa/riscrittura del plug-in).
