---
title: trackingServer
description: Determina la posizione in cui vengono inviate le richieste di immagini.
feature: Variables
exl-id: bcc23286-4dd5-45ac-ac6f-7b60e95cb798
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '543'
ht-degree: 2%

---

# trackingServer

Adobe raccoglie i dati sul sito ricevendo una richiesta di immagine generata dal visitatore. La `trackingServer` determina la posizione in cui viene inviata una richiesta di immagine. Se questa variabile non è definita correttamente, l’implementazione può subire una perdita di dati.

>[!WARNING]
>
>La modifica di questo valore fa sì che AppMeasurement cerchi i cookie in una posizione diversa. Il conteggio di visitatori univoci può causare un picco temporaneo nel reporting quando i cookie dei visitatori sono impostati nella nuova posizione.

## Dominio Edge che utilizza l’estensione SDK per web

L&#39;SDK per web utilizza [!UICONTROL Edge domain] per gestire sia il server di tracciamento che il server di tracciamento protetto. Puoi impostare il [!UICONTROL Edge domain] durante la configurazione dell&#39;estensione SDK per web.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
1. Fai clic sulla proprietà tag desiderata.
1. Vai a [!UICONTROL Extensions] , quindi fai clic sul pulsante **[!UICONTROL Configure]** pulsante sotto [!UICONTROL Adobe Experience Platform Web SDK].
1. Imposta il valore desiderato **[!UICONTROL Edge domain]** campo di testo.

Vedi [Configurare l’estensione Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html) per ulteriori informazioni, consulta la documentazione SDK per web .

>[!TIP]
>
>Se l&#39;organizzazione passa all&#39;SDK web da un&#39;implementazione di un&#39;estensione AppMeasurement o Analytics, questo campo può utilizzare lo stesso valore contenuto in `trackingServerSecure` o `trackingServer`).

## Dominio Edge che implementa manualmente l’SDK per web

Configurare l&#39;SDK utilizzando [`edgeDomain`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html). Il campo è una stringa che determina il dominio a cui inviare i dati.

```json
alloy("configure", {
  "edgeDomain": "data.example.com"
});
```

## Server di tracciamento tramite l’estensione Adobe Analytics

Tracking Server è un campo sotto [!UICONTROL General] pannello a soffietto durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
2. Fai clic sulla proprietà tag desiderata.
3. Vai a [!UICONTROL Extensions] , quindi fai clic sul pulsante **[!UICONTROL Configure]** sotto Adobe Analytics.
4. Espandi la [!UICONTROL General] fisarmonica, che rivela [!UICONTROL Tracking Server] campo .

Se questo campo viene lasciato vuoto, viene impostato automaticamente su `[rsid].data.adobedc.net`.

## s.trackingServer in AppMeasurement e nell&#39;editor di codice personalizzato dell&#39;estensione Analytics

La `s.trackingServer` è una stringa che contiene la posizione in cui inviare i dati.

## Determinare il valore per `trackingServer`

Il valore di questa variabile dipende dall’utilizzo di cookie di prime parti o di cookie di terze parti. Adobe consiglia vivamente di utilizzare i cookie di prime parti nell’implementazione.

### Cookie di prime parti

Se utilizzi un’implementazione di cookie di prime parti, è probabile che un utente dell’organizzazione abbia già completato il processo di cookie di prime parti. Vedi [Cookie di prime parti nell’Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=it) nella guida utente dei servizi core per ulteriori informazioni sul processo dei cookie di prime parti.

L’utente che inizialmente configura l’implementazione dei cookie di prima parte definisce anche il dominio e il sottodominio utilizzati. Ad esempio:

```js
s.trackingServer = "data.example.com";
```

### Cookie di terze parti

>[!TIP]
>
>L’aumento delle pratiche di privacy nei browser moderni rende i cookie di terze parti meno affidabili. Adobe consiglia di seguire il flusso di lavoro dei cookie di prime parti.

Se utilizzi un’implementazione di cookie di terze parti, il valore di `trackingServer` è un sottodominio di `data.adobedc.net`. Ad esempio:

```js
s.trackingServer = "example.data.adobedc.net";
```

Scegli un sottodominio univoco per la tua organizzazione, probabilmente scelto da un’altra organizzazione che utilizza Adobe Analytics.  Si consiglia di assegnare lo spazio dei nomi visitatore all’organizzazione.  Assicurati che tutte le implementazioni nell&#39;organizzazione utilizzino lo stesso server di tracciamento. Può essere utile mantenere queste informazioni in un [documento di progettazione della soluzione](../../prepare/solution-design.md).

La tua organizzazione potrebbe già utilizzare un server di tracciamento di terze parti nel `sc.omtrdc.net` o `2o7.net` domini.  Questi sono stati utilizzati principalmente nelle versioni precedenti di Adobe Analytics e sono ancora validi.

>[!NOTE]
>
>Non utilizzare sottodomini più profondi di `example.data.adobedc.net`. Ad esempio: `custom.example.data.adobedc.net` non è un server di tracciamento valido.
