---
title: trackingServer
description: Determina la posizione in cui vengono inviate le richieste di immagini.
feature: Appmeasurement Implementation
exl-id: bcc23286-4dd5-45ac-ac6f-7b60e95cb798
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '683'
ht-degree: 9%

---

# trackingServer

Adobe raccoglie dati sul sito ricevendo una richiesta di immagine generata dal visitatore. La variabile `trackingServer` determina la posizione in cui viene inviata una richiesta di immagine. Se questa variabile non è definita correttamente, l’implementazione può causare la perdita di dati.

>[!WARNING]
>
>La modifica di questo valore fa sì che AppMeasurement cerchi i cookie in una posizione diversa. Il conteggio dei visitatori univoci può aumentare temporaneamente nei rapporti in quanto i cookie dei visitatori vengono impostati nella nuova posizione.

## Dominio Edge tramite l’estensione Web SDK

Web SDK utilizza [!UICONTROL Edge domain] per gestire sia il server di tracciamento che il server di tracciamento protetto. È possibile impostare il valore [!UICONTROL Edge domain] desiderato durante la configurazione dell&#39;estensione Web SDK.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Passa alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in [!UICONTROL Adobe Experience Platform Web SDK].
1. Imposta il campo di testo **[!UICONTROL Edge domain]** desiderato.

Per ulteriori informazioni, vedere [Configurare l&#39;estensione Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html?lang=it) nella documentazione di Web SDK.

>[!TIP]
>
>Se l&#39;organizzazione passa al Web SDK da un&#39;implementazione di AppMeasurement o Analytics, questo campo può utilizzare lo stesso valore contenuto in `trackingServerSecure` (o `trackingServer`).

## Dominio Edge con implementazione manuale del Web SDK

Configurare SDK utilizzando [`edgeDomain`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=it). Il campo è una stringa che determina il dominio a cui inviare i dati.

```json
alloy("configure", {
  "edgeDomain": "data.example.com"
});
```

## Tracciamento del server tramite l’estensione Adobe Analytics

Il server di tracciamento è un campo nel pannello a soffietto [!UICONTROL General] durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in Adobe Analytics.
4. Espandi il pannello a soffietto [!UICONTROL General], che mostra il campo [!UICONTROL Tracking Server].

Se questo campo viene lasciato vuoto, il valore predefinito è `[rsid].data.adobedc.net`.

## s.trackingServer in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La variabile `s.trackingServer` è una stringa che contiene la posizione in cui inviare i dati.

## Considerazioni per la determinazione del valore per `trackingServer`

È possibile scegliere di utilizzare i domini del server di tracciamento di Adobe (ad esempio `adobedc.net`) oppure eseguire un processo speciale per configurare un server di tracciamento che corrisponda al dominio dei siti (ad esempio `data.mydomain.com`), noto anche come implementazione CNAME. Disporre di un server di tracciamento che corrisponde al dominio del sito può avere alcuni vantaggi a seconda di altri aspetti dell’implementazione. Se il server di tracciamento non corrisponde al dominio della pagina corrente, i cookie impostati da AppMeasurement devono essere impostati come di terze parti. Se il browser non supporta i cookie di terze parti, questa mancata corrispondenza può interferire con alcune funzionalità di Analytics:

- Identificatori di impostazione: se utilizzi il servizio Experience Cloud Identity, il server di tracciamento non influisce sul modo in cui vengono impostati i cookie. Tuttavia, se utilizzi gli identificatori legacy di Analytics (ovvero il cookie `s_vi`) e il server di raccolta non corrisponde al dominio corrente, i cookie devono essere impostati come di terze parti. In questo caso, se i cookie di terze parti sono bloccati dal browser, Analytics imposta un ID di fallback (`s_fid`) di prime parti invece del cookie standard `s_vi`.
- Il tracciamento dei collegamenti non funzionerà per i collegamenti interni.
- Activity Map non funzionerà per i collegamenti interni.
- Controllo cookie.

### Cookie di prime parti

Se utilizzi un’implementazione di cookie di prima parte, è probabile che qualcuno nella tua organizzazione abbia già completato il processo di cookie di prima parte. Per ulteriori informazioni sul processo dei cookie di prime parti, consulta [Cookie di prime parti in Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=it) nella guida utente dei servizi core.

L’utente che configura inizialmente l’implementazione dei cookie di prime parti definisce anche il dominio e il sottodominio utilizzati. Ad esempio:

```js
s.trackingServer = "data.example.com";
```

### Server di tracciamento di terze parti

>[!TIP]
>
>L’aumento delle pratiche di privacy nei browser moderni rende i cookie di terze parti meno affidabili. Adobe consiglia di seguire il flusso di lavoro dei cookie di prime parti.

Se utilizzi un&#39;implementazione di cookie di terze parti, il valore per `trackingServer` è un sottodominio di `data.adobedc.net`. Ad esempio:

```js
s.trackingServer = "example.data.adobedc.net";
```

Scegli un sottodominio specifico per la tua organizzazione, che probabilmente non verrà scelto da un’altra organizzazione che utilizza Adobe Analytics.  Si consiglia di assegnare al visitatore lo spazio dei nomi assegnato alla tua organizzazione.  Assicurati che tutte le implementazioni nell’organizzazione utilizzino lo stesso server di tracciamento. Può essere utile conservare queste informazioni in un [documento di progettazione della soluzione](../../prepare/solution-design.md).

È possibile che la tua organizzazione stia già utilizzando un server di tracciamento di terze parti nei domini `sc.omtrdc.net` o `2o7.net`.  Questi sono stati utilizzati principalmente nelle versioni precedenti di Adobe Analytics e sono ancora validi.

>[!NOTE]
>
>Non utilizzare sottodomini più profondi di `example.data.adobedc.net`. `custom.example.data.adobedc.net` ad esempio non è un server di tracciamento valido.
