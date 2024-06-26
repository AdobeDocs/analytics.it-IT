---
title: trackingServer
description: Determina la posizione in cui vengono inviate le richieste di immagini.
feature: Variables
exl-id: bcc23286-4dd5-45ac-ac6f-7b60e95cb798
role: Admin, Developer
source-git-commit: 284f121428ce9d682b42309dd85cfd117285a7e5
workflow-type: tm+mt
source-wordcount: '683'
ht-degree: 9%

---

# trackingServer

Adobe raccoglie dati sul sito ricevendo una richiesta di immagine generata dal visitatore. Il `trackingServer` determina la posizione in cui viene inviata una richiesta di immagine. Se questa variabile non è definita correttamente, l’implementazione può causare la perdita di dati.

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

## Tracciamento del server tramite l’estensione Adobe Analytics

Il tracking server è un campo sotto [!UICONTROL General] Pannello a soffietto durante la configurazione dell’estensione Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in Adobe Analytics.
4. Espandi il pannello a soffietto [!UICONTROL General], che mostra il campo [!UICONTROL Tracking Server].

Se questo campo viene lasciato vuoto, il valore predefinito è `[rsid].data.adobedc.net`.

## s.trackingServer in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Il `s.trackingServer` variabile è una stringa che contiene la posizione in cui inviare i dati.

## Considerazioni per la determinazione del valore per `trackingServer`

Puoi scegliere di utilizzare i domini del server di tracciamento di Adobe (ad es. `adobedc.net`) oppure puoi seguire un processo speciale per configurare un server di tracciamento che corrisponda al dominio dei siti (ad es. `data.mydomain.com`), nota anche come implementazione CNAME. Disporre di un server di tracciamento che corrisponde al dominio del sito può avere alcuni vantaggi a seconda di altri aspetti dell’implementazione. Se il server di tracciamento non corrisponde al dominio della pagina corrente, i cookie impostati dall’AppMeasurement devono essere impostati come di terze parti. Se il browser non supporta i cookie di terze parti, questa mancata corrispondenza può interferire con alcune funzionalità di Analytics:

- Identificatori di impostazione: se utilizzi il servizio Experience Cloud Identity, il server di tracciamento non ha alcun impatto sull’impostazione dei cookie. Tuttavia, se utilizzi gli identificatori legacy di Analytics (o `s_vi` cookie) e il server di raccolta non corrisponde al dominio corrente, quindi i cookie devono essere impostati come di terze parti. In questo caso, se i cookie di terze parti sono bloccati dal browser, Analytics imposta un ID di fallback di prime parti (`s_fid`) invece dello standard `s_vi` cookie.
- Il tracciamento dei collegamenti non funzionerà per i collegamenti interni.
- L’Activity Map non funzionerà per i collegamenti interni.
- Controllo cookie.

### Cookie di prime parti

Se utilizzi un’implementazione di cookie di prima parte, è probabile che qualcuno nella tua organizzazione abbia già completato il processo di cookie di prima parte. Consulta [Cookie di prime parti nell’Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=it) nella guida utente dei servizi core per ulteriori informazioni sul processo dei cookie di prime parti.

L’utente che configura inizialmente l’implementazione dei cookie di prime parti definisce anche il dominio e il sottodominio utilizzati. Ad esempio:

```js
s.trackingServer = "data.example.com";
```

### Server di tracciamento di terze parti

>[!TIP]
>
>L’aumento delle pratiche di privacy nei browser moderni rende i cookie di terze parti meno affidabili. L’Adobe consiglia di seguire il flusso di lavoro dei cookie di prime parti.

Se utilizzi un’implementazione di cookie di terze parti, il valore per `trackingServer` è un sottodominio di `data.adobedc.net`. Ad esempio:

```js
s.trackingServer = "example.data.adobedc.net";
```

Scegli un sottodominio specifico per la tua organizzazione, che probabilmente non verrà scelto da un’altra organizzazione che utilizza Adobe Analytics.  Si consiglia di assegnare al visitatore lo spazio dei nomi assegnato alla tua organizzazione.  Assicurati che tutte le implementazioni nell’organizzazione utilizzino lo stesso server di tracciamento. Può essere utile conservare queste informazioni in un [documento di progettazione della soluzione](../../prepare/solution-design.md).

La tua organizzazione potrebbe già utilizzare un server di tracciamento di terze parti in `sc.omtrdc.net` o `2o7.net` domini.  Questi sono stati utilizzati principalmente nelle versioni precedenti di Adobe Analytics e sono ancora validi.

>[!NOTE]
>
>Non utilizzare sottodomini più profondi di `example.data.adobedc.net`. Ad esempio: `custom.example.data.adobedc.net` non è un server di tracciamento valido.
