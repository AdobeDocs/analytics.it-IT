---
title: trackingServerSecure
description: Dominio utilizzato per inviare dati ad Adobe tramite HTTPS.
feature: Appmeasurement Implementation
exl-id: d5b112f9-f3f6-43ac-8ee5-d9ad8062e380
role: Admin, Developer
TQID: https://experienceleague.adobe.com/8-M-5apvXuUfQyxdd4Es8Lr5LkgXPK2UNHrhpTzT8xE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
  - id: df312454-73c4-43f6-a90e-18f5043f074c
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 9e2c89f4188c723b4623a6e7859b74ede15e155b
workflow-type: tm+mt
source-wordcount: 794
ht-degree: 7%

---

# trackingServerSecure

La variabile `trackingServerSecure` determina il dominio utilizzato da AppMeasurement per inviare dati ad Adobe tramite HTTPS. Se questa variabile non è definita correttamente, l’implementazione può causare la perdita di dati.

Prima del [servizio Adobe Experience Cloud Identity](https://experienceleague.adobe.com/it/docs/id-service/using/home), questa variabile determinava anche dove erano impostati i cookie di terze parti. Adobe consiglia vivamente di utilizzare il servizio ID in tutte le implementazioni, laddove possibile.

## Dominio Edge tramite l’estensione Web SDK

Web SDK utilizza [!UICONTROL Edge domain] per gestire sia il server di tracciamento che il server di tracciamento protetto. È possibile impostare il valore [!UICONTROL Edge domain] desiderato durante la configurazione dell&#39;estensione Web SDK.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Seleziona la proprietà tag desiderata.
1. Passa alla scheda [!UICONTROL Extensions], quindi seleziona il pulsante **[!UICONTROL Configure]** in [!UICONTROL Adobe Experience Platform Web SDK].
1. Imposta il campo di testo **[!UICONTROL Edge domain]** desiderato.

Per ulteriori informazioni, vedere [Configurare l&#39;estensione Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html?lang=it) nella documentazione di Web SDK.

>[!TIP]
>
>Se l&#39;organizzazione passa al Web SDK da un&#39;implementazione di AppMeasurement o Analytics, questo campo può utilizzare lo stesso valore contenuto in `trackingServerSecure` (o `trackingServer`).

## Dominio Edge con implementazione manuale del Web SDK

Configurare SDK utilizzando [`edgeDomain`](https://experienceleague.adobe.com/it/docs/experience-platform/web-sdk/commands/configure/edgedomain). Il campo è una stringa che determina il dominio a cui inviare i dati.

```json
alloy("configure", {
  "edgeDomain": "data.example.com"
});
```

## Server di tracciamento SSL tramite l’estensione Adobe Analytics

[!UICONTROL SSL Tracking Server] è un campo nel pannello a soffietto [!UICONTROL General] durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Seleziona la proprietà tag desiderata.
1. Vai alla scheda [!UICONTROL Extensions], quindi seleziona il pulsante **[!UICONTROL Configure]** in Adobe Analytics.
1. Espandi il pannello a soffietto [!UICONTROL General], che mostra il campo [!UICONTROL SSL Tracking Server].

Se questo campo viene lasciato vuoto, il valore predefinito sarà [!UICONTROL Tracking Server]. Se [!UICONTROL SSL Tracking Server] e [!UICONTROL Tracking Server] sono entrambi vuoti, il valore predefinito è `[rsid].data.adobedc.net`.

## s.trackingServerSecure in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La variabile `s.trackingServerSecure` è una stringa che contiene il dominio da inviare ad Adobe. È solo dominio; ometti protocollo, percorso, porta e barre. Se questa variabile è vuota, verrà utilizzato il valore della variabile `s.trackingServer`. Se `s.trackingServerSecure` e `s.trackingServer` sono entrambi vuoti, il valore predefinito è `[rsid].2o7.net`.

```js
// Example value when participating in the Adobe-managed certificate program
s.trackingServerSecure = "data.example.com";

// Example value sending data directly to Adobe
s.trackingServerSecure = "example.data.adobedc.net";
```

## Considerazioni sulla determinazione del valore per `trackingServerSecure`

Il valore utilizzato per `trackingServerSecure` (o `edgeDomain`) dipende da diversi fattori:

* La tua partecipazione al [programma di certificazione gestito da Adobe](https://experienceleague.adobe.com/it/docs/core-services/interface/data-collection/adobe-managed-cert)
* Se il servizio [Adobe Experience Cloud Identity](https://experienceleague.adobe.com/it/docs/id-service/using/home) è stato implementato e configurato correttamente

**Se la tua organizzazione partecipa al programma di certificazione gestito da Adobe**, imposta il valore sul dominio di prime parti selezionato durante la configurazione del certificato. In genere questo valore è un sottodominio di proprietà dell’organizzazione. Ad esempio, `data.example.com`. I record CNAME nella tua organizzazione reindirizzano tali dati ad Adobe.

**Se non partecipi al programma di certificazione**, imposta il valore su un sottodominio di `data.adobedc.net`. Adobe consiglia di utilizzare per coerenza l’ID azienda della tua organizzazione. Ad esempio, `example.data.adobedc.net`. Per determinare l&#39;ID società, effettua le seguenti operazioni:

1. Accedi a [Adobe CX Enterprise](https://experience.adobe.com) utilizzando le credenziali Adobe ID.
1. In qualsiasi punto dell&#39;interfaccia di CX Enterprise, premere `[Cmd]` + `[I]` (iOS) o `[Ctrl]` + `[I]` (Windows).
1. Verrà visualizzato **[!UICONTROL User data debugger]**. Seleziona la scheda **[!UICONTROL Assigned orgs]**.
1. Espandi l’organizzazione IMS desiderata.
1. Individua il campo **[!UICONTROL Tenant]**. Questo valore è il sottodominio consigliato di `data.adobedc.net` da utilizzare.

>[!NOTE]
>
>Non utilizzare sottodomini più profondi di `example.data.adobedc.net`. `custom.example.data.adobedc.net` ad esempio non è un server di tracciamento valido.

Le implementazioni meno recenti potrebbero avere valori come `sc.omtrdc.net` o `2o7.net`. Questi sono stati utilizzati principalmente nelle versioni precedenti di Adobe Analytics e sono ancora validi.

Adobe consiglia vivamente di mantenere queste informazioni in un [documento di progettazione della soluzione](../../prepare/solution-design.md) per coerenza a livello di organizzazione.

## Ramificazioni per il mancato utilizzo del servizio ID visitatore

Adobe consiglia vivamente di utilizzare il servizio [Adobe Experience Cloud Identity](https://experienceleague.adobe.com/it/docs/id-service/using/home) in tutte le implementazioni. Il servizio ID può essere implementato in diversi modi:

* Le implementazioni manuali di AppMeasurement utilizzano `VisitorAPI.js` e chiamano il metodo `getInstance`. Per ulteriori informazioni, vedere [Implementazione del servizio Experience Cloud Identity per Analytics](https://experienceleague.adobe.com/it/docs/id-service/using/implementation/setup-analytics).
* Le implementazioni che utilizzano l&#39;estensione tag Adobe Analytics utilizzano l&#39;estensione tag del servizio [Adobe Experience Cloud ID](https://experienceleague.adobe.com/it/docs/experience-platform/tags/extensions/client/id-service/overview). Una volta aggiunta, non è necessaria alcuna configurazione aggiuntiva.
* Le implementazioni che utilizzano qualsiasi forma di Web SDK (`alloy.js` o l&#39;estensione tag Web SDK) dispongono già del servizio ID in modalità nativa. Non è richiesta alcuna configurazione oltre all&#39;impostazione del valore `edgeDomain`.

**Se la tua implementazione non utilizza il servizio Identity**, considera i seguenti impatti sulla tua implementazione:

* Se non si utilizza il servizio Identity, `trackingServerSecure` determina la posizione del cookie. Se si imposta questa variabile su un dominio di terze parti, AppMeasurement utilizza un cookie di fallback, in quanto la maggior parte dei browser moderni rifiuta i cookie di terze parti.
* Il tracciamento dei collegamenti interni e Activity Map potrebbero essere meno affidabili.
