---
title: trackingServer
description: Consente di determinare la posizione in cui vengono inviate le richieste di immagini.
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# trackingServer

Adobe raccoglie i dati sul sito ricevendo una richiesta di immagine generata dal visitatore. La `trackingServer` variabile determina la posizione in cui viene inviata una richiesta di immagine. Se questa variabile non è definita correttamente, l&#39;implementazione potrebbe causare la perdita di dati.

> [!IMPORTANT] Modificando questo valore, AppMeasurement cerca i cookie in una posizione diversa. Il conteggio univoco dei visitatori può aumentare temporaneamente il picco nel reporting quando i cookie dei visitatori sono impostati nella nuova posizione.

## Server di monitoraggio in Adobe Experience Platform Launch

Tracking Server è un campo situato sotto la struttura di [!UICONTROL General] navigazione durante la configurazione dell’estensione Adobe Analytics.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Vai alla [!UICONTROL Extensions] scheda, quindi fai clic sul [!UICONTROL Configure] pulsante in Adobe Analytics.
4. Espandere la [!UICONTROL General] struttura a soffietto, che mostra il [!UICONTROL Tracking Server] campo.

Se il campo viene lasciato vuoto, per impostazione predefinita viene impostato su `[rsid].112.2o7.net`.

## s.trackingServer nell’editor di codice personalizzato AppMeasurement e Launch

La `s.trackingServer` variabile è una stringa che contiene la posizione in cui inviare i dati.

> [!TIP] Alcune implementazioni puntano i dati a `2o7.net`. Anche se si tratta di un dominio di raccolta dati valido, non utilizza la raccolta dati regionale. Le implementazioni effettuate tramite `2o7.net` la visualizzazione di tempi di risposta delle richieste di immagini leggermente più elevati.

## Determinare il valore per trackingServer

Il valore di questa variabile dipende da se si utilizzano cookie di prime parti o cookie di terze parti. Adobe consiglia vivamente di utilizzare i cookie di prime parti nella vostra implementazione.

### Cookie di prime parti

Se utilizzate un&#39;implementazione di cookie di prime parti, è probabile che qualcuno all&#39;interno dell&#39;organizzazione abbia già completato il processo di cookie di prime parti. Consulta Cookie di [prime parti in Experience Cloud](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-first-party.html) nella guida utente dei servizi di base per ulteriori informazioni sul processo dei cookie di prime parti.

L’utente che configura inizialmente l’implementazione dei cookie di prime parti definisce anche il dominio e il sottodominio utilizzati. Ad esempio:

```js
s.trackingServer = "data.example.com";
```

In genere i record CNAME sono già configurati e puntano a `sc.omtrdc.net`. Il dominio `2o7.net` è anche una destinazione CNAME valida, utilizzata principalmente nelle versioni precedenti di Adobe Analytics.

### Cookie di terze parti

> [!TIP] L&#39;aumento delle pratiche di privacy nei browser moderni rende meno affidabili i cookie di terze parti. Adobe consiglia di seguire il flusso di lavoro dei cookie di prime parti.

Se utilizzate un&#39;implementazione di cookie di terze parti, il valore per `trackingServer` è un sottodominio di `sc.omtrdc.net`. Ad esempio:

```js
s.trackingServer = "example.sc.omtrdc.net";
```

Scegli un sottodominio univoco per la tua organizzazione, probabilmente scelto da un&#39;altra organizzazione che utilizza Adobe Analytics. Accertati che tutte le implementazioni dell’organizzazione utilizzino lo stesso server di tracciamento. Può essere utile mantenere queste informazioni in un documento [di progettazione di una](../../prepare/solution-design.md)soluzione.
