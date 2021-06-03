---
title: trackingServerSecure
description: Determina la posizione in cui le richieste di immagini vengono inviate sulle pagine HTTPS.
exl-id: d5b112f9-f3f6-43ac-8ee5-d9ad8062e380
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 2%

---

# trackingServerSecure

Adobe raccoglie i dati sul sito ricevendo una richiesta di immagine generata dal visitatore. La variabile `trackingServerSecure` determina la posizione in cui viene inviata una richiesta di immagine tramite HTTPS. Inoltre, determina la posizione in cui vengono memorizzati i cookie dei visitatori. Se questa variabile non è definita correttamente, l’implementazione può subire una perdita di dati.

>[!IMPORTANT]
>
>Modificando questo valore AppMeasurement cerca i cookie in una posizione diversa. Il conteggio di visitatori univoci può causare un picco temporaneo nel reporting quando i cookie dei visitatori sono impostati nella nuova posizione.

## Server di tracciamento SSL in Adobe Experience Platform Launch

[!UICONTROL SSL Tracking Server] è un campo a  [!UICONTROL General] soffietto durante la configurazione dell’estensione Adobe Analytics.

1. Accedi a [launch.adobe.com](https://launch.adobe.com) utilizzando le tue credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai alla scheda [!UICONTROL Extensions] , quindi fai clic sul pulsante [!UICONTROL Configure] in Adobe Analytics.
4. Espandi il [!UICONTROL General] pannello a soffietto, che mostra il campo [!UICONTROL SSL Tracking Server] .

Se questo campo viene lasciato vuoto, viene impostato automaticamente il valore nella variabile [`trackingServer`](trackingserver.md) .

## s.trackingServerSecure nell&#39;editor di codice personalizzato AppMeasurement e Launch

La variabile `s.trackingServerSecure` è una stringa che contiene la posizione in cui inviare le richieste di immagini. È quasi sempre un sottodominio del sito. Le moderne pratiche di privacy nei browser di solito rendono i cookie di terze parti inaffidabili. Se questa variabile è vuota, utilizza il valore nella variabile `s.trackingServer` .

Il valore di questa variabile è quasi sempre un dominio di prime parti, ad esempio `data.example.com`. Per ulteriori informazioni sul processo dei cookie di prime parti, consulta [Cookie di prime parti nell&#39;Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html) nella guida utente dei servizi core .

L’utente che inizialmente configura l’implementazione dei cookie di prima parte definisce anche il dominio e il sottodominio utilizzati. Ad esempio:

```js
s.trackingServerSecure = "data.example.com";
```

I record CNAME in genere puntano a un sottodominio su `data.adobedc.net`, `sc.adobedc.net` o `2o7.net`.
