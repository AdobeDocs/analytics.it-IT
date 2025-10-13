---
title: Migrazione da AppMeasurement al Web SDK
description: Aggiorna la tua implementazione di Adobe Analytics dalla libreria JavaScript di AppMeasurement alla libreria JavaScript di Web SDK.
exl-id: c90246e8-0f04-4655-9204-33c0ef611b13
source-git-commit: 05690cc8c1ea0364cbab86f35666df1cc1b13e69
workflow-type: tm+mt
source-wordcount: '1323'
ht-degree: 7%

---

# Migrazione da AppMeasurement al Web SDK

Questo percorso di implementazione prevede un approccio metodologico di migrazione per passare da un’implementazione AppMeasurement a un’implementazione della libreria JavaScript Web SDK. Altri percorsi di implementazione sono trattati in pagine separate:

* [Estensione Analytics per estensione Web SDK](analytics-extension-to-web-sdk.md): adotta un approccio semplice e metodico per passare dall&#39;estensione tag Adobe Analytics all&#39;estensione tag Web SDK. Questo approccio elimina la necessità di utilizzare XDM fino a quando l’organizzazione non è pronta a utilizzare i servizi Adobe Experience Platform, come Customer Journey Analytics. Utilizzare l&#39;oggetto `data` invece dell&#39;oggetto `xdm` per inviare dati ad Adobe.
* [Libreria Web SDK JavaScript](web-sdk-javascript-library.md): una nuova installazione di Web SDK utilizzando la libreria Web SDK JavaScript (`alloy.js`). Gestisci autonomamente l’implementazione anziché utilizzare l’interfaccia utente dei tag. Richiede il gruppo di campi ExperienceEvent di Adobe Analytics, che include le variabili Analytics tipiche da includere nello schema XDM.
* [Estensione tag Web SDK](web-sdk-tag-extension.md): una nuova installazione di Web SDK in cui è possibile gestire l&#39;implementazione utilizzando i tag in Raccolta dati Adobe Experience Platform. Richiede il gruppo di campi ExperienceEvent di Adobe Analytics, che include le variabili Analytics tipiche da includere nello schema XDM.

## Vantaggi e svantaggi di questo percorso di implementazione

L’utilizzo di questo approccio alla migrazione presenta sia vantaggi che svantaggi. Valuta attentamente ogni opzione per decidere quale approccio è meglio per la tua organizzazione.

| Vantaggi | Svantaggi |
| --- | --- |
| <ul><li>**Utilizza l’implementazione esistente**: sebbene questo approccio richieda alcune modifiche all’implementazione, non richiede un’implementazione completamente nuova da zero. Puoi utilizzare il livello dati e il codice esistenti con modifiche minime alla logica di implementazione.</li><li>**Non richiede uno schema**: per questa fase della migrazione al Web SDK non è necessario uno schema XDM. È invece possibile popolare l&#39;oggetto `data`, che invia i dati direttamente ad Adobe Analytics. Una volta completata la migrazione al Web SDK, puoi creare uno schema per la tua organizzazione e utilizzare la mappatura dello stream di dati per popolare i campi XDM applicabili. Se in questa fase del processo di migrazione fosse necessario uno schema, l’organizzazione sarebbe costretta a utilizzare uno schema XDM di Adobe Analytics. L’utilizzo di questo schema rende più difficile per l’organizzazione utilizzare il proprio schema in futuro.</li></ul> | <ul><li>**Le modifiche all&#39;implementazione richiedono l&#39;intervento dello sviluppatore**: se si desidera apportare modifiche all&#39;implementazione di Web SDK, è necessario collaborare con il team di sviluppo per modificare il codice sul sito. L&#39;approccio con cui [esegue la migrazione all&#39;estensione tag Web SDK](analytics-extension-to-web-sdk.md) evita questo svantaggio.</li><li>**Debito tecnico per l&#39;implementazione**: poiché questo approccio utilizza una forma modificata dell&#39;implementazione esistente, può essere più difficile tenere traccia della logica di implementazione ed eseguire modifiche in futuro quando necessario.</li><li>**Richiede la mappatura per inviare i dati a Platform**: quando l’organizzazione è pronta per utilizzare Customer Journey Analytics, devi inviare i dati a un set di dati in Adobe Experience Platform. Questa azione richiede che ogni campo nell&#39;oggetto `data` sia una voce nello strumento di mappatura dello stream di dati che lo assegna a un campo dello schema XDM. La mappatura deve essere eseguita solo una volta per questo flusso di lavoro e non implica l’apportazione di modifiche all’implementazione. Tuttavia, si tratta di un passaggio aggiuntivo non richiesto quando si inviano dati in un oggetto XDM.</li></ul> |

Adobe consiglia di seguire questo percorso di implementazione nei seguenti scenari:

* È disponibile un’implementazione esistente utilizzando la libreria JavaScript di Adobe Analytics AppMeasurement. Se disponi di un&#39;implementazione che utilizza l&#39;estensione tag Adobe Analytics, segui [Esegui migrazione dall&#39;estensione tag Adobe Analytics all&#39;estensione tag Web SDK](analytics-extension-to-web-sdk.md).
* Intendi utilizzare Customer Journey Analytics in futuro, ma non desideri sostituire l’implementazione di Analytics con un’implementazione di Web SDK da zero. La sostituzione dell’implementazione da zero sul Web SDK richiede il massimo impegno, ma offre anche l’architettura di implementazione a lungo termine più efficiente. Se la tua organizzazione è disposta a passare attraverso l&#39;implementazione di un SDK Web pulito, consulta [Inserire dati tramite Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk) nella guida utente di Customer Journey Analytics.

## Passaggi necessari per la migrazione al Web SDK

Le seguenti fasi contengono obiettivi concreti da perseguire. Fai clic su ogni passaggio per istruzioni dettagliate su come eseguirlo.

+++**1. Crea e configura un flusso di dati**

Creare uno stream di dati in Raccolta dati di Adobe Experience Platform. Quando invii dati a questo stream di dati, questi vengono inoltrati ad Adobe Analytics. In futuro, lo stesso flusso di dati inoltra i dati a Customer Journey Analytics.

1. Passa a [experience.adobe.com](https://experience.adobe.com) e accedi con le tue credenziali.
1. Utilizzare la home page o il selettore di prodotti in alto a destra per passare a **[!UICONTROL Data Collection]**.
1. Nel menu di navigazione a sinistra, selezionare **[!UICONTROL Datastreams]**.
1. Seleziona **[!UICONTROL New Datastream]**.
1. Immettere il nome desiderato, quindi selezionare **[!UICONTROL Save]**.
1. Una volta creato lo stream di dati, selezionare **[!UICONTROL Add Service]**.
1. Nel menu a discesa del servizio, selezionare **[!UICONTROL Adobe Analytics]**.
1. Immetti lo stesso ID suite di rapporti del sito a cui invii attualmente i dati di analisi. Fai clic su **[!UICONTROL Save]**.

![Aggiungi servizio Adobe Analytics](assets/datastream-rsid.png) {style="border:1px solid lightslategray"}

Il flusso di dati è ora pronto per ricevere e trasmettere dati ad Adobe Analytics. Prendi nota dell’ID dello stream di dati, in quanto questo ID è richiesto durante la configurazione del Web SDK nel codice.

+++

+++**2. Installa la libreria Web SDK JavaScript**

Fare riferimento alla versione più recente di `alloy.js` in modo che sia possibile utilizzare le relative chiamate al metodo. Per informazioni dettagliate e blocchi di codice da utilizzare, vedere [Installare il Web SDK utilizzando la libreria JavaScript](https://experienceleague.adobe.com/it/docs/experience-platform/web-sdk/install/library).

+++

+++**3. Configura Web SDK**

Configurare l&#39;implementazione in modo che punti allo stream di dati creato nel passaggio precedente utilizzando il comando Web SDK [`configure`](https://experienceleague.adobe.com/it/docs/experience-platform/web-sdk/commands/configure/overview). Il comando `configure` deve essere impostato su ogni pagina, in modo da poterlo includere insieme al codice di installazione della libreria.

Utilizzare le proprietà [`datastreamId`](https://experienceleague.adobe.com/it/docs/experience-platform/web-sdk/commands/configure/datastreamid) e [`orgId`](https://experienceleague.adobe.com/it/docs/experience-platform/web-sdk/commands/configure/orgid) nel comando Web SDK `configure`:

* Imposta `datastreamId` sull&#39;ID dello stream di dati recuperato dal passaggio precedente.
* Imposta `orgId` per l&#39;organizzazione IMS della tua organizzazione.

```js
alloy("configure", {
    datastreamId: "ebebf826-a01f-4458-8cec-ef61de241c93",
    orgId: "ADB3LETTERSANDNUMBERS@AdobeOrg"
});
```

Facoltativamente, è possibile impostare altre proprietà nel comando [`configure`](https://experienceleague.adobe.com/it/docs/experience-platform/web-sdk/commands/configure/overview) in base ai requisiti di implementazione della propria organizzazione.

+++

+++**4. Aggiorna la logica del codice per utilizzare un payload JSON**

Modificare l&#39;implementazione di Analytics in modo che non si basi su `AppMeasurement.js` o sull&#39;oggetto `s`. Imposta invece le variabili in un oggetto JavaScript formattato correttamente, che viene convertito in un oggetto JSON quando inviato ad Adobe. Disporre di un [livello dati](../../prepare/data-layer.md) sul sito è molto utile quando si impostano i valori, in quanto è possibile continuare a fare riferimento agli stessi valori.

Per inviare dati ad Adobe Analytics, il payload di Web SDK deve utilizzare `data.__adobe.analytics` con tutte le variabili di analisi impostate all&#39;interno di questo oggetto. Le variabili all’interno di questo oggetto condividono nomi e formati identici alle corrispondenti variabili AppMeasurement. Ad esempio, se imposti la variabile `products`, non suddividerla in singoli oggetti come si farebbe con XDM. Invece, includila come stringa esattamente se imposti la variabile `s.products`:

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

Questo payload contiene tutti i valori desiderati e tutti i riferimenti all&#39;oggetto `s` nell&#39;implementazione vengono rimossi. Puoi utilizzare una qualsiasi delle risorse fornite da JavaScript per impostare questo oggetto payload, inclusa la notazione del punto per impostare i singoli valori.

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

+++**5. Aggiorna le chiamate del metodo per utilizzare Web SDK**

Aggiorna tutte le istanze in cui chiami [`s.t()`](../../vars/functions/t-method.md) e [`s.tl()`](../../vars/functions/tl-method.md), sostituendole con il comando [`sendEvent`](https://experienceleague.adobe.com/it/docs/experience-platform/web-sdk/commands/sendevent/overview). Ci sono tre scenari da considerare:

* **Tracciamento visualizzazione pagina**: sostituire la chiamata di tracciamento visualizzazione pagina con il comando Web SDK `sendEvent`:

  ```js
  // If your current implementation has this line of code:
  s.t();
  
  // Replace it with this line of code. The dataObj object contains the variables to send.
  alloy("sendEvent", dataObj);
  ```

* **Tracciamento automatico dei collegamenti**: la proprietà di configurazione [`clickCollectionEnabled`](https://experienceleague.adobe.com/it/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) è attivata per impostazione predefinita. Imposta automaticamente le variabili di tracciamento dei collegamenti corrette per inviare dati ad Adobe Analytics. Se si desidera disabilitare il rilevamento automatico dei collegamenti, impostare questa proprietà su `false` nel comando [`configure`](https://experienceleague.adobe.com/it/docs/experience-platform/web-sdk/commands/configure/overview).

* **Tracciamento manuale dei collegamenti**: il Web SDK non dispone di comandi separati tra le chiamate pageview e non pageview. Specifica la distinzione all&#39;interno dell&#39;oggetto payload.

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

+++**6. Convalida e pubblicazione delle modifiche**

Dopo aver rimosso tutti i riferimenti ad AppMeasurement e all&#39;oggetto `s`, pubblica le modifiche nell&#39;ambiente di sviluppo per verificare che la nuova implementazione funzioni. Dopo aver verificato il corretto funzionamento di tutto, puoi pubblicare gli aggiornamenti in produzione.

Se migrato correttamente, `AppMeasurement.js` non è più necessario nel sito e tutti i riferimenti a questo script possono essere rimossi.

+++

A questo punto, l’implementazione di Analytics è completamente sul Web SDK ed è adeguatamente preparata per il passaggio a Customer Journey Analytics in futuro.
