---
title: trackingServerSecure
description: Dominio utilizzato per inviare dati ad Adobe tramite HTTPS.
feature: Appmeasurement Implementation
exl-id: d5b112f9-f3f6-43ac-8ee5-d9ad8062e380
role: Admin, Developer
TQID: https://experienceleague.adobe.com/8-M-5apvXuUfQyxdd4Es8Lr5LkgXPK2UNHrhpTzT8xE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
    internal-label: Appmeasurement implementation
  - id: df312454-73c4-43f6-a90e-18f5043f074c
    internal-label: Tags
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 832a3752ab758d573e5b15b2dc38dad120fe8300
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 7%
---
# trackingServerSecure

La variabile `trackingServerSecure` determina il dominio utilizzato da AppMeasurement per inviare dati ad Adobe tramite HTTPS. Se questa variabile non è definita correttamente, l’implementazione può causare la perdita di dati.

>[!NOTE]
>
>[`trackingServer`](configuration-variables.md#retired-configuration-variables) è una variante ritirata di questa variabile. È stato specificato il dominio per i dati inviati tramite HTTP. Con la prevalenza di HTTPS, utilizzare invece `trackingServerSecure`. Se `s.trackingServerSecure` è vuoto, AppMeasurement tornerà al valore `s.trackingServer`.

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

Configurare SDK utilizzando [`edgeDomain`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/edgedomain). Il campo è una stringa che determina il dominio a cui inviare i dati.

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
// Example value when using a first-party domain
s.trackingServerSecure = "data.example.com";

// Example value when using a third-party domain
s.trackingServerSecure = "example.data.adobedc.net";
```

## Considerazioni per la determinazione del valore per `trackingServerSecure`

Il valore utilizzato per `trackingServerSecure` (o `edgeDomain`) dipende dal modo in cui l&#39;organizzazione invia i dati ad Adobe:

* **Se l&#39;organizzazione utilizza un dominio di prime parti**, ad esempio tramite il [programma di certificazione gestito da Adobe](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/adobe-managed-cert), un [certificato gestito dal cliente](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/customer-managed-cert) o una [rete di distribuzione di contenuti (CDN)](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cdn), impostare il valore su tale dominio. Ad esempio, `data.example.com`.
* **Se l&#39;organizzazione utilizza un dominio di terze parti**, impostare il valore sul sottodominio dell&#39;ID tenant di `data.adobedc.net`. Ad esempio, `example.data.adobedc.net`.

Per informazioni dettagliate su ciascuna opzione, inclusa la modalità di ricerca dell&#39;ID tenant, vedere [Scegliere un dominio di raccolta dati](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/collection-domain) nella Guida all&#39;amministrazione e all&#39;interfaccia di CX Enterprise.

Adobe consiglia vivamente di mantenere queste informazioni in un [documento di progettazione della soluzione](../../prepare/solution-design.md) per coerenza a livello di organizzazione.

## Ramificazioni per non aver utilizzato il servizio ID visitatore o Experience Platform Identity

Adobe consiglia vivamente di utilizzare ECID come forma principale di identità del visitatore in tutte le implementazioni. La raccolta degli ECID può essere implementata in diversi modi, a seconda del tipo di implementazione:

* Le implementazioni manuali di AppMeasurement utilizzano `VisitorAPI.js` e chiamano il metodo `getInstance`. Per ulteriori informazioni, consulta [Implementazione del servizio ID visitatori per Analytics](https://experienceleague.adobe.com/en/docs/id-service/using/implementation/setup-analytics).
* Le implementazioni che utilizzano l&#39;estensione tag di Adobe Analytics utilizzano l&#39;estensione tag [[!UICONTROL Experience Cloud ID Service]](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/id-service/overview), che implementa il servizio ID visitatori. Una volta aggiunta, non è necessaria alcuna configurazione aggiuntiva.
* Le implementazioni che utilizzano qualsiasi tipo di Web SDK (`alloy.js` o l&#39;estensione tag Web SDK) includono automaticamente il servizio Experience Platform Identity. Non è richiesta alcuna configurazione oltre all&#39;impostazione del valore `edgeDomain`.

**Se la tua implementazione non utilizza gli ECID**, considera i seguenti impatti sulla tua implementazione:

* Se non utilizzi il servizio ID visitatore o il servizio Experience Platform Identity, `trackingServerSecure` determina la posizione dei cookie. Se si imposta questa variabile su un dominio di terze parti, AppMeasurement utilizza un cookie di fallback, in quanto la maggior parte dei browser moderni rifiuta i cookie di terze parti.
* Il tracciamento dei collegamenti interni e Activity Map potrebbero essere meno affidabili.
