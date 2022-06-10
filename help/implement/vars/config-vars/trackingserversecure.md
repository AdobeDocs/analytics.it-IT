---
title: trackingServerSecure
description: Determina la posizione in cui le richieste di immagini vengono inviate sulle pagine HTTPS.
feature: Variables
exl-id: d5b112f9-f3f6-43ac-8ee5-d9ad8062e380
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 2%

---

# trackingServerSecure

Adobe raccoglie i dati sul sito ricevendo una richiesta di immagine generata dal visitatore. La `trackingServerSecure` determina la posizione in cui viene inviata una richiesta di immagine tramite HTTPS. Inoltre, determina la posizione in cui vengono memorizzati i cookie dei visitatori. Se questa variabile non è definita correttamente, l’implementazione può subire una perdita di dati.

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

## Server di tracciamento SSL utilizzando l’estensione Adobe Analytics

[!UICONTROL SSL Tracking Server] è un campo sotto [!UICONTROL General] pannello a soffietto durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
2. Fai clic sulla proprietà tag desiderata.
3. Vai a [!UICONTROL Extensions] , quindi fai clic sul pulsante **[!UICONTROL Configure]** sotto Adobe Analytics.
4. Espandi la [!UICONTROL General] fisarmonica, che rivela [!UICONTROL SSL Tracking Server] campo .

Se questo campo viene lasciato vuoto, viene impostato automaticamente sul valore nel [`trackingServer`](trackingserver.md) variabile.

## s.trackingServerSecure in AppMeasurement e nell&#39;editor di codice personalizzato dell&#39;estensione Analytics

La `s.trackingServerSecure` è una stringa che contiene la posizione in cui inviare le richieste di immagini. È quasi sempre un sottodominio del sito. Le moderne pratiche di privacy nei browser di solito rendono i cookie di terze parti inaffidabili. Se questa variabile è vuota, utilizza il valore nel `s.trackingServer` variabile.

Il valore di questa variabile è quasi sempre un dominio di prima parte, ad esempio `data.example.com`. Vedi [Cookie di prime parti nell’Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=it) nella guida utente dei servizi core per ulteriori informazioni sul processo dei cookie di prime parti.

L’utente che inizialmente configura l’implementazione dei cookie di prima parte definisce anche il dominio e il sottodominio utilizzati. Ad esempio:

```js
s.trackingServerSecure = "data.example.com";
```

I record CNAME in genere puntano a un sottodominio su `data.adobedc.net`, `sc.adobedc.net` o `2o7.net`.
