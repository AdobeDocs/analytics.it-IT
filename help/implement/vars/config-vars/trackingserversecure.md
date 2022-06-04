---
title: trackingServerSecure
description: Determina la posizione in cui le richieste di immagini vengono inviate sulle pagine HTTPS.
feature: Variables
exl-id: d5b112f9-f3f6-43ac-8ee5-d9ad8062e380
source-git-commit: 3f4d8df911c076a5ea41e7295038c0625a4d7c85
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 3%

---

# trackingServerSecure

Adobe raccoglie i dati sul sito ricevendo una richiesta di immagine generata dal visitatore. La `trackingServerSecure` determina la posizione in cui viene inviata una richiesta di immagine tramite HTTPS. Inoltre, determina la posizione in cui vengono memorizzati i cookie dei visitatori. Se questa variabile non è definita correttamente, l’implementazione può subire una perdita di dati.

>[!WARNING]
>
>La modifica di questo valore fa sì che AppMeasurement cerchi i cookie in una posizione diversa. Il conteggio di visitatori univoci può causare un picco temporaneo nel reporting quando i cookie dei visitatori sono impostati nella nuova posizione.

## Server di tracciamento SSL tramite tag in Adobe Experience Platform

[!UICONTROL SSL Tracking Server] è un campo sotto [!UICONTROL General] pannello a soffietto durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi a [Interfaccia utente per la raccolta dati](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai a [!UICONTROL Extensions] , quindi fai clic sul pulsante [!UICONTROL Configure] sotto Adobe Analytics.
4. Espandi la [!UICONTROL General] fisarmonica, che rivela [!UICONTROL SSL Tracking Server] campo .

Se questo campo viene lasciato vuoto, viene impostato automaticamente sul valore nel [`trackingServer`](trackingserver.md) variabile.

## s.trackingServerSecure in AppMeasurement e nell&#39;editor di codice personalizzato

La `s.trackingServerSecure` è una stringa che contiene la posizione in cui inviare le richieste di immagini. È quasi sempre un sottodominio del sito. Le moderne pratiche di privacy nei browser di solito rendono i cookie di terze parti inaffidabili. Se questa variabile è vuota, utilizza il valore nel `s.trackingServer` variabile.

Il valore di questa variabile è quasi sempre un dominio di prima parte, ad esempio `data.example.com`. Vedi [Cookie di prime parti nell’Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=it) nella guida utente dei servizi core per ulteriori informazioni sul processo dei cookie di prime parti.

L’utente che inizialmente configura l’implementazione dei cookie di prima parte definisce anche il dominio e il sottodominio utilizzati. Ad esempio:

```js
s.trackingServerSecure = "data.example.com";
```

I record CNAME in genere puntano a un sottodominio su `data.adobedc.net`, `sc.adobedc.net` o `2o7.net`.
