---
title: Migrare da AppMeasurement a Web SDK
description: Aggiorna l’implementazione di Adobe Analytics dalla libreria JavaScript di AppMeasurement alla libreria JavaScript di Web SDK.
source-git-commit: d4c9bddf18311e13d025ed9d62c0636a33eb7b85
workflow-type: tm+mt
source-wordcount: '1323'
ht-degree: 0%

---

# Migrare da AppMeasurement a Web SDK

Questo percorso di implementazione prevede un approccio metodologico di migrazione per passare da un’implementazione AppMeasurement a un’implementazione della libreria JavaScript dell’SDK Web. Altri percorsi di implementazione sono trattati in pagine separate:

* [Estensione Analytics per estensione Web SDK](analytics-extension-to-web-sdk.md): adotta un approccio fluido e sistematico per passare dall’estensione tag Adobe Analytics all’estensione tag Web SDK. Questo approccio elimina la necessità di utilizzare XDM fino a quando l’organizzazione non è pronta a utilizzare i servizi Adobe Experience Platform, come il Customer Journey Analytics. Utilizza il `data` oggetto invece del `xdm` oggetto per inviare dati ad Adobe.
* [Libreria JavaScript dell’SDK per web](web-sdk-javascript-library.md): nuova installazione di Web SDK tramite la libreria JavaScript di Web SDK (`alloy.js`). Gestisci autonomamente l’implementazione anziché utilizzare l’interfaccia utente dei tag. Richiede il gruppo di campi ExperienceEvent di Adobe Analytics, che include le variabili Analytics tipiche da includere nello schema XDM.
* [Estensione tag Web SDK](web-sdk-tag-extension.md): nuova installazione di Web SDK in cui puoi gestire l’implementazione utilizzando i tag in Raccolta dati di Adobe Experience Platform. Richiede il gruppo di campi ExperienceEvent di Adobe Analytics, che include le variabili Analytics tipiche da includere nello schema XDM.

## Vantaggi e svantaggi di questo percorso di implementazione

L’utilizzo di questo approccio alla migrazione presenta sia vantaggi che svantaggi. Valuta attentamente ogni opzione per decidere quale approccio è meglio per la tua organizzazione.

| Vantaggi | Svantaggi |
| --- | --- |
| <ul><li>**Utilizza l’implementazione esistente**: sebbene questo approccio richieda alcune modifiche di implementazione, non richiede un’implementazione completamente nuova da zero. Puoi utilizzare il livello dati e il codice esistenti con modifiche minime alla logica di implementazione.</li><li>**Non richiede uno schema**: in questa fase della migrazione all’SDK per web non è necessario uno schema XDM. È invece possibile compilare il `data` , che invia i dati direttamente ad Adobe Analytics. Una volta completata la migrazione all’SDK per web, puoi creare uno schema per la tua organizzazione e utilizzare la mappatura dello stream di dati per popolare i campi XDM applicabili. Se in questa fase del processo di migrazione fosse necessario uno schema, l’organizzazione sarebbe costretta a utilizzare uno schema XDM di Adobe Analytics. L’utilizzo di questo schema rende più difficile per l’organizzazione utilizzare il proprio schema in futuro.</li></ul> | <ul><li>**Le modifiche all’implementazione richiedono l’intervento degli sviluppatori**: se desideri apportare modifiche all’implementazione dell’SDK web, devi collaborare con il team di sviluppo per modificare il codice sul sito. L&#39;approccio che [esegue la migrazione all’estensione tag Web SDK](analytics-extension-to-web-sdk.md) evita questo svantaggio.</li><li>**Obbligo tecnico di attuazione**: poiché questo approccio utilizza una forma modificata dell’implementazione esistente, può essere più difficile tracciare la logica di implementazione ed eseguire modifiche in futuro quando necessario.</li><li>**Richiede la mappatura per inviare dati a Platform**: quando l’organizzazione è pronta per utilizzare il Customer Journey Analytics, è necessario inviare dati a un set di dati in Adobe Experience Platform. Questa azione richiede che ogni campo nel `data` object può essere una voce nello strumento di mappatura dello stream di dati che lo assegna a un campo dello schema XDM. La mappatura deve essere eseguita una sola volta per questo flusso di lavoro e non richiede l’apporto di modifiche all’implementazione. Si tratta tuttavia di un passaggio aggiuntivo non richiesto per l’invio di dati in un oggetto XDM.</li></ul> |

L’Adobe consiglia di seguire questo percorso di implementazione nei seguenti scenari:

* È disponibile un’implementazione esistente utilizzando la libreria JavaScript di Adobe Analytics AppMeasurement. Se hai un’implementazione tramite l’estensione tag Adobe Analytics, segui [Migrare dall’estensione tag Adobe Analytics all’estensione tag Web SDK](analytics-extension-to-web-sdk.md) invece.
* Intendi utilizzare il Customer Journey Analytics in futuro, ma non desideri sostituire l’implementazione di Analytics con un’implementazione Web SDK da zero. La sostituzione dell’implementazione da zero su Web SDK richiede il massimo impegno, ma offre anche l’architettura di implementazione a lungo termine più efficiente. Se la tua organizzazione è disposta a passare attraverso l’implementazione di un SDK web pulito, consulta [Inserire dati tramite Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk) nella guida utente del Customer Journey Analytics.

## Passaggi necessari per migrare a Web SDK

Le seguenti fasi contengono obiettivi concreti da perseguire. Fai clic su ogni passaggio per istruzioni dettagliate su come eseguirlo.

+++**1. Creare e configurare uno stream di dati**

Creare uno stream di dati in Raccolta dati di Adobe Experience Platform. Quando invii dati a questo stream di dati, questi vengono inoltrati ad Adobe Analytics. In futuro, lo stesso flusso di dati inoltra i dati al Customer Journey Analytics.

1. Accedi a [experience.adobe.com](https://experience.adobe.com) e accedere utilizzando le credenziali.
1. Utilizza la home page o il selettore di prodotti in alto a destra per passare a **[!UICONTROL Data Collection]**.
1. Nel menu di navigazione a sinistra, seleziona **[!UICONTROL Datastreams]**.
1. Seleziona **[!UICONTROL New Datastream]**.
1. Immetti il nome desiderato, quindi seleziona **[!UICONTROL Save]**.
1. Una volta creato lo stream di dati, seleziona **[!UICONTROL Add Service]**.
1. Nel menu a discesa del servizio, seleziona **[!UICONTROL Adobe Analytics]**.
1. Immetti lo stesso ID suite di rapporti del sito a cui invii attualmente i dati di analisi. Fai clic su **[!UICONTROL Save]**.

![Aggiungi servizio Adobe Analytics](assets/datastream-rsid.png) {style="border:1px solid gray"}

Il flusso di dati è ora pronto per ricevere e trasmettere dati ad Adobe Analytics. Prendi nota dell’ID dello stream di dati, in quanto questo ID è richiesto durante la configurazione dell’SDK web nel codice.

+++

+++**2. Installare la libreria JavaScript dell’SDK per web**

Fai riferimento all’ultima versione di `alloy.js` in modo che possano essere utilizzate le relative chiamate di metodo. Consulta [Installare l’SDK web utilizzando la libreria JavaScript](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library) per i dettagli e i blocchi di codice da utilizzare.

+++

+++**3. Configurare l’SDK per web**

Imposta l’implementazione in modo che punti allo stream di dati creato nel passaggio precedente utilizzando l’SDK per web [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) comando. Il `configure` deve essere impostato su ogni pagina, in modo da poterlo includere insieme al codice di installazione della libreria.

Utilizza il [`edgeConfigId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/edgeconfigid) e [`orgId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/orgid) proprietà nell’SDK per web `configure` comando:

* Imposta il `edgeConfigId` all’ID dello stream di dati recuperato dal passaggio precedente.
* Imposta il `orgId` all’organizzazione IMS della tua organizzazione.

```js
alloy("configure", {
    "edgeConfigId": "ebebf826-a01f-4458-8cec-ef61de241c93",
    "orgId": "ADB3LETTERSANDNUMBERS@AdobeOrg"
});
```

Facoltativamente, puoi impostare altre proprietà nella [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) a seconda dei requisiti di implementazione della tua organizzazione.

+++

+++**4. Aggiorna la logica del codice per utilizzare un payload JSON**

Modifica l’implementazione di Analytics in modo che non si basi su `AppMeasurement.js` o `s` oggetto. Imposta invece le variabili in un oggetto JavaScript formattato correttamente, che viene convertito in un oggetto JSON quando viene inviato a Adobe. Avere un [Livello dati](../../prepare/data-layer.md) sul tuo sito ti aiuta enormemente a impostare i valori, in quanto puoi continuare a fare riferimento a tali valori.

Per inviare dati ad Adobe Analytics, il payload dell’SDK web deve utilizzare `data.__adobe.analytics` con tutte le variabili di analytics impostate all’interno di questo oggetto. Le variabili all&#39;interno di questo oggetto condividono nomi e formati identici come controparti AppMeasurement di variabili. Ad esempio, se imposti il `products` , non suddividerla in singoli oggetti come si farebbe con XDM. Invece, includila come stringa esattamente se imposti il `s.products` variabile:

```json
{
  "data": {
    "__adobe": {
      "analytics": {
        "products": "Shoes,Men's sneakers,1,49.99"
      }
    }
  }
}
```

Infine, questo payload contiene tutti i valori desiderati e tutti i riferimenti al `s` nell&#39;implementazione vengono rimossi. Per impostare questo oggetto payload, è possibile utilizzare una qualsiasi delle risorse fornite da JavaScript, inclusa la notazione del punto per impostare i singoli valori.

```js
// Define the payload and set objects within it
var dataObj = {data: {__adobe: {analytics: {}}}};
dataObj.data.__adobe.analytics.pageName = window.document.title;
dataObj.data.__adobe.analytics.eVar1 = "Example value";

// Alternatively, set values in an object and use a spread operator to achieve identical results
var a = new Object;
a.pageName = window.document.title;
a.eVar1 = "Example value";
var dataObj = {data:{__adobe:{analytics:{...a}}}};
```

+++

+++**5. Chiamate al metodo di aggiornamento per utilizzare l’SDK per web**

Aggiorna tutte le istanze in cui chiami [`s.t()`](../../vars/functions/t-method.md) e [`s.tl()`](../../vars/functions/tl-method.md), sostituendoli con [`sendEvent`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/sendevent/overview) comando. Ci sono tre scenari da considerare:

* **Tracciamento della visualizzazione pagina**: sostituisci la chiamata di tracciamento della visualizzazione della pagina con l’SDK web `sendEvent` comando:

  ```js
  // If your current implementation has this line of code:
  s.t();
  
  // Replace it with this line of code. The dataObj object contains the variables to send.
  alloy("sendEvent", dataObj);
  ```

* **Tracciamento automatico dei collegamenti**: Il [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) la proprietà di configurazione è attivata per impostazione predefinita. Imposta automaticamente le variabili di tracciamento dei collegamenti corrette per inviare dati ad Adobe Analytics. Se vuoi disattivare il tracciamento automatico dei collegamenti, imposta questa proprietà su `false` all&#39;interno del [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) comando.

* **Tracciamento manuale dei collegamenti**: l’SDK per web non dispone di comandi separati tra le chiamate pageview e non pageview. Specifica la distinzione all&#39;interno dell&#39;oggetto payload.

  ```js
  // If your current implementation has this line of code:
  s.tl(true,"o","Example custom link");
  
  // Replace it with these lines of code. Add the required fields to the dataObj object.
  dataObj.data.__adobe.analytics.linkName = "Example custom link";
  dataObj.data.__adobe.analytics.linkType = "o";
  dataObj.data.__adobe.analytics.linkURL = "https://example.com";
  alloy("sendEvent", dataObj);
  ```

+++

+++**6. Convalidare e pubblicare le modifiche**

Dopo aver rimosso tutti i riferimenti ad AppMeasurement e al `s` pubblica le modifiche nell’ambiente di sviluppo per verificare che la nuova implementazione funzioni. Dopo aver verificato il corretto funzionamento di tutto, puoi pubblicare gli aggiornamenti in produzione.

Se migrato correttamente, `AppMeasurement.js` non è più richiesto sul sito e tutti i riferimenti a questo script possono essere rimossi.

+++

A questo punto, l’implementazione di Analytics si basa interamente sull’SDK per web ed è adeguatamente preparata per passare al Customer Journey Analytics in futuro.
