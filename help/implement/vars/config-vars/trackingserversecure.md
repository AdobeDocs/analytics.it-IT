---
title: trackingServerSecure
description: Determina il percorso in cui le richieste di immagini vengono inviate sulle pagine HTTPS.
feature: Variables
exl-id: d5b112f9-f3f6-43ac-8ee5-d9ad8062e380
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 14%

---

# trackingServerSecure

Adobe raccoglie dati sul sito ricevendo una richiesta di immagine generata dal visitatore. Il `trackingServerSecure` determina la posizione in cui viene inviata una richiesta di immagine tramite HTTPS. Inoltre, determina la posizione in cui vengono memorizzati i cookie dei visitatori. Se questa variabile non è definita correttamente, l’implementazione può causare la perdita di dati.

>[!WARNING]
>
>La modifica di questo valore fa sì che AppMeasurement cerchi i cookie in una posizione diversa. Il conteggio dei visitatori univoci può aumentare temporaneamente nei rapporti in quanto i cookie dei visitatori vengono impostati nella nuova posizione.

## Dominio Edge tramite l’estensione Web SDK

L’SDK per web utilizza [!UICONTROL Edge domain] per gestire sia Tracking Server che Secure Tracking Server. È possibile impostare il [!UICONTROL Edge domain] valore durante la configurazione dell&#39;estensione Web SDK.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Vai a [!UICONTROL Extensions] , quindi fare clic sulla scheda **[!UICONTROL Configure]** pulsante sotto [!UICONTROL Adobe Experience Platform Web SDK].
1. Impostare il **[!UICONTROL Edge domain]** campo di testo.

Consulta [Configurare l’estensione Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html?lang=it) per ulteriori informazioni, consulta la documentazione dell’SDK per web.

>[!TIP]
>
>Se la tua organizzazione passa al Web SDK da un’implementazione di AppMeasurement o estensione Analytics, questo campo può utilizzare lo stesso valore contenuto in `trackingServerSecure` (o `trackingServer`).

## Dominio Edge che implementa manualmente Web SDK

Configurare l’SDK tramite [`edgeDomain`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=it). Il campo è una stringa che determina il dominio a cui inviare i dati.

```json
alloy("configure", {
  "edgeDomain": "data.example.com"
});
```

## Server di tracciamento SSL tramite l’estensione Adobe Analytics

[!UICONTROL SSL Tracking Server] è un campo sotto [!UICONTROL General] Pannello a soffietto durante la configurazione dell’estensione Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in Adobe Analytics.
4. Espandi il pannello a soffietto [!UICONTROL General], che mostra il campo [!UICONTROL SSL Tracking Server].

Se questo campo viene lasciato vuoto, per impostazione predefinita viene utilizzato il valore [`trackingServer`](trackingserver.md) variabile.

## s.trackingServerSecure in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Il `s.trackingServerSecure` variabile è una stringa che contiene la posizione in cui inviare le richieste di immagini. È quasi sempre un sottodominio del sito. Le moderne pratiche di privacy nei browser rendono comunemente inaffidabili i cookie di terze parti. Se questa variabile è vuota, utilizza il valore nella `s.trackingServer` variabile.

Il valore di questa variabile è quasi sempre un dominio di prime parti, ad esempio `data.example.com`. Consulta [Cookie di prime parti nell’Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=it) nella guida utente dei servizi core per ulteriori informazioni sul processo dei cookie di prime parti.

L’utente che configura inizialmente l’implementazione dei cookie di prime parti definisce anche il dominio e il sottodominio utilizzati. Ad esempio:

```js
s.trackingServerSecure = "data.example.com";
```

I record CNAME in genere puntano a un sottodominio in `data.adobedc.net`, `sc.adobedc.net` o `2o7.net`.
