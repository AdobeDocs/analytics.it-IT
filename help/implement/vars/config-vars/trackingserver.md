---
title: trackingServer
description: Determina la posizione in cui vengono inviate le richieste di immagini.
exl-id: bcc23286-4dd5-45ac-ac6f-7b60e95cb798
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 2%

---

# trackingServer

Adobe raccoglie i dati sul sito ricevendo una richiesta di immagine generata dal visitatore. La variabile `trackingServer` determina la posizione in cui viene inviata una richiesta di immagine. Se questa variabile non è definita correttamente, l’implementazione può subire una perdita di dati.

>[!IMPORTANT]
>
>Modificando questo valore AppMeasurement cerca i cookie in una posizione diversa. Il conteggio di visitatori univoci può causare un picco temporaneo nel reporting quando i cookie dei visitatori sono impostati nella nuova posizione.

## Server di tracciamento in Adobe Experience Platform Launch

Tracking Server è un campo sotto il pannello a soffietto [!UICONTROL General] durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi a [launch.adobe.com](https://launch.adobe.com) utilizzando le tue credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai alla scheda [!UICONTROL Extensions] , quindi fai clic sul pulsante [!UICONTROL Configure] in Adobe Analytics.
4. Espandi il [!UICONTROL General] pannello a soffietto, che mostra il campo [!UICONTROL Tracking Server] .

Se questo campo viene lasciato vuoto, viene impostato automaticamente su `[rsid].data.adobedc.net`.

## s.trackingServer nell&#39;editor di codice personalizzato AppMeasurement e Launch

La variabile `s.trackingServer` è una stringa che contiene la posizione in cui inviare i dati.

## Determinare il valore per trackingServer

Il valore di questa variabile dipende dall’utilizzo di cookie di prime parti o di cookie di terze parti. Adobe consiglia vivamente di utilizzare i cookie di prime parti nell’implementazione.

### Cookie di prime parti

Se utilizzi un’implementazione di cookie di prime parti, è probabile che un utente dell’organizzazione abbia già completato il processo di cookie di prime parti. Per ulteriori informazioni sul processo dei cookie di prime parti, consulta [Cookie di prime parti nell&#39;Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html) nella guida utente dei servizi core .

L’utente che inizialmente configura l’implementazione dei cookie di prima parte definisce anche il dominio e il sottodominio utilizzati. Ad esempio:

```js
s.trackingServer = "data.example.com";
```

### Cookie di terze parti

>[!TIP]
>
>L’aumento delle pratiche di privacy nei browser moderni rende i cookie di terze parti meno affidabili. Adobe consiglia di seguire il flusso di lavoro dei cookie di prime parti.

Se utilizzi un’implementazione di cookie di terze parti, il valore per `trackingServer` è un sottodominio di `data.adobedc.net`. Ad esempio:

```js
s.trackingServer = "example.data.adobedc.net";
```

Scegli un sottodominio univoco per la tua organizzazione, probabilmente scelto da un’altra organizzazione che utilizza Adobe Analytics.  Si consiglia di assegnare lo spazio dei nomi visitatore all’organizzazione.  Assicurati che tutte le implementazioni nell&#39;organizzazione utilizzino lo stesso server di tracciamento. Può essere utile mantenere queste informazioni in un [documento di progettazione della soluzione](../../prepare/solution-design.md).

La tua organizzazione potrebbe già utilizzare un server di tracciamento di terze parti nei domini `sc.omtrdc.net` o `2o7.net` .  Questi sono stati utilizzati principalmente nelle versioni precedenti di Adobe Analytics e sono ancora validi.

>[!NOTE]
>
>Non utilizzare sottodomini più profondi di `example.data.adobedc.net`. Ad esempio, `custom.example.data.adobedc.net` non è un server di tracciamento valido.
