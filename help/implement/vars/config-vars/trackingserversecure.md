---
title: trackingServerSecure
description: Consente di determinare la posizione in cui le richieste di immagini vengono inviate sulle pagine HTTPS.
translation-type: tm+mt
source-git-commit: d9fa9fa6afb6b76ae37a92c86d9ca21a9c3fb22e
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 5%

---


# trackingServerSecure

 Adobe raccoglie i dati sul sito ricevendo una richiesta di immagine generata dal visitatore. La `trackingServerSecure` variabile determina il percorso in cui una richiesta di immagine viene inviata tramite HTTPS. Determina inoltre la posizione in cui vengono memorizzati i cookie dei visitatori. Se questa variabile non è definita correttamente, l&#39;implementazione potrebbe causare la perdita di dati.

>[!IMPORTANT]
>
>Modificando questo valore, AppMeasurement cerca i cookie in una posizione diversa. Il conteggio univoco dei visitatori può aumentare temporaneamente il picco nel reporting quando i cookie dei visitatori sono impostati nella nuova posizione.

## Server di tracciamento SSL in  Adobe Experience Platform Launch

[!UICONTROL SSL Tracking Server] è un campo situato sotto la [!UICONTROL General] struttura di navigazione durante la configurazione dell&#39;estensione Adobe Analytics .

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Vai alla [!UICONTROL Extensions] scheda, quindi fai clic sul [!UICONTROL Configure] pulsante sotto  Adobe Analytics.
4. Espandere la [!UICONTROL General] struttura a soffietto, che mostra il [!UICONTROL SSL Tracking Server] campo.

Se questo campo viene lasciato vuoto, per impostazione predefinita viene utilizzato il valore nella [`trackingServer`](trackingserver.md) variabile.

## s.trackingServerSecure in AppMeasurement e Launch editor di codice personalizzato

La `s.trackingServerSecure` variabile è una stringa che contiene la posizione in cui inviare le richieste di immagini. È quasi sempre un sottodominio del sito. Le pratiche di privacy moderne nei browser rendono generalmente inaffidabili i cookie di terze parti. Se questa variabile è vuota, utilizza il valore nella `s.trackingServer` variabile.

Il valore di questa variabile è quasi sempre un dominio di prime parti, ad esempio `data.example.com`. Per ulteriori informazioni sul processo dei cookie di prime parti, consulta Cookie di [prime parti nel Experience Cloud](https://docs.adobe.com/content/help/it-IT/core-services/interface/ec-cookies/cookies-first-party.html)  nella guida utente di Servizi di base.

L’utente che configura inizialmente l’implementazione dei cookie di prime parti definisce anche il dominio e il sottodominio utilizzati. Ad esempio:

```js
s.trackingServerSecure = "data.example.com";
```

I record CNAME in genere puntano a un sottodominio su `data.adobedc.net`, `sc.omtrdc.net` o `2o7.net`.
