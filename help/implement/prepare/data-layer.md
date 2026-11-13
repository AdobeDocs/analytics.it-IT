---
title: Creare un livello dati
description: Scopri in che modo un livello dati supporta l’implementazione di Analytics, perché Adobe consiglia Adobe Client Data Layer e come leggere i valori del livello dati con ciascun metodo di implementazione.
feature: Implementation Basics
exl-id: 271dd8fa-3ba1-4a7f-b16a-c48a736a5bb5
role: Admin, Developer, Leader
TQID: 'https://experienceleague.adobe.com/JmxM3-AVA5--7Xt4kuES35KFtYbicdGO9JZXsygzuuE'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: df312454-73c4-43f6-a90e-18f5043f074c
    internal-label: Tags
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 7151dca7425bfb99271db71a3132485f85941a5e
workflow-type: tm+mt
source-wordcount: '1063'
ht-degree: 7%
---
# Creare un livello dati

Un livello dati è una struttura JavaScript sul sito che espone i dati raccolti dall’implementazione di Analytics, come nomi di pagina, dettagli del prodotto e ID degli ordini. Il codice del sito scrive sul livello dati e l’implementazione lo legge per impostare le variabili di Analytics. Poiché l’implementazione non dipende dal HTML della pagina, puoi riprogettare il sito senza interrompere la raccolta dati.

## Prerequisiti

[Crea un documento di progettazione della soluzione](solution-design.md): è importante che la tua organizzazione si allinei ai requisiti di tracciamento. Assicurati di aver preparato un documento di progettazione della soluzione prima di rivolgerti ai team di sviluppo della tua organizzazione. I dati necessari per la progettazione della soluzione determinano cosa contiene il livello dati.

## Scegli una specifica del livello dati {#specifications}

Adobe consiglia [Adobe Client Data Layer](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/overview) (ACDL) per implementazioni nuove o ristrutturate. ACDL è una libreria JavaScript open-source che offre al sito un metodo standard per inviare dati ed eventi a un array `adobeDataLayer` globale. I tag, il Web SDK e AppMeasurement possono essere letti da esso e i componenti core di Adobe Experience Manager possono popolarlo automaticamente.

La tua organizzazione è libera di utilizzare altre specifiche, ad esempio [Customer Experience Digital Data Layer](https://www.w3.org/2013/12/ceddl-201312.pdf) (CEDDL), che memorizza i dati in un oggetto `digitalData` globale, o una specifica personalizzata. La cosa più importante è che l’organizzazione si allinea su una specifica che soddisfa le sue esigenze.

La tabella seguente confronta ACDL con livelli di dati basati su oggetti come CEDDL:

| | Adobe Client Data Layer (`adobeDataLayer`) | Livello dati basato su oggetti, ad esempio CEDDL (`digitalData`) |
| --- | --- | --- |
| Scrittura dei dati nel codice del sito | Invia oggetti: `adobeDataLayer.push({ page: { name: "Home" } })` | Imposta proprietà: `digitalData.page.pageInfo.pageName = "Home"` |
| Come la tua implementazione legge un valore | `adobeDataLayer.getState("page.name")` o un **elemento dati con stato calcolato dal livello dati** dall&#39;estensione tag Adobe Client Data Layer | `digitalData.page.pageInfo.pageName` o un elemento dati **Variabile JavaScript** dall&#39;estensione tag Core |
| In che modo l’implementazione sa che i dati sono pronti | Il codice del sito invia un evento, ad esempio `{ event: "page view" }`, e l&#39;implementazione lo ascolta. I listener vengono eseguiti anche per gli eventi inviati prima che vengano aggiunti. | L’implementazione deve leggere l’oggetto dopo che il codice del sito ha completato il popolamento, ad esempio utilizzando una regola di chiamata diretta. |

## Esempio di livello dati {#example}

ACDL non richiede una struttura dati specifica. Progetta la struttura intorno al documento di progettazione della soluzione e documentala per tutti coloro che scrivono sul livello dati o leggono da esso. Gli esempi in questa guida utilizzano la seguente struttura.

Quando viene caricata una pagina, il codice del sito invia i dati della pagina e un evento di visualizzazione della pagina:

```js
window.adobeDataLayer = window.adobeDataLayer || [];
window.adobeDataLayer.push({
  event: "page view",
  page: {
    name: "Home",
    section: "Products",
    url: "https://example.com/products",
    referrer: "https://example.com/"
  }
});
```

Quando un visitatore completa un acquisto, il codice del sito invia i dettagli dell’ordine e un evento di acquisto:

```js
window.adobeDataLayer.push({
  event: "purchase",
  transaction: { id: "ABC123" },
  products: [
    { name: "Example product", category: "Example category", quantity: 1, price: 25 }
  ]
});
```

ACDL unisce ogni push in un singolo oggetto denominato stato calcolato, che viene letto dall’implementazione. Gli oggetti evento indicano all’implementazione quando leggerla. Vedi [Dati e stato calcolato](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/concepts/computed-state) e [Eventi](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/concepts/events).

## Flusso di lavoro {#workflow}

Generalmente, l’implementazione di Adobe Analytics utilizzando un livello dati segue questi passaggi:

1. **Collabora con il tuo team di sviluppo del sito per implementare un livello dati**: il tuo team di sviluppo del sito è principalmente responsabile della verifica che il livello dati contenga valori corretti. Esamina questa pagina con il tuo team di sviluppo del sito per assicurarti che le aspettative siano allineate tra i team. Consulta [Installare Adobe Client Data Layer](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/install).
1. **Convalida il livello dati utilizzando una console del browser**: apri la console per sviluppatori del browser, operazione che puoi eseguire nella maggior parte dei browser con la chiave `F12`. Eseguire `adobeDataLayer.getState()` per visualizzare lo stato calcolato oppure `adobeDataLayer.getState("page.name")` per visualizzare un singolo valore. Vedere [Verificare l&#39;installazione](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/install#verify).
1. **Connetti il livello dati ad Adobe Analytics**: questo passaggio varia in base al metodo di implementazione della tua organizzazione. Vedi [Connettere il livello dati ad Adobe Analytics](#connect).

## Collegare il livello dati ad Adobe Analytics {#connect}

La tabella seguente mostra la modalità di lettura di ciascun metodo di implementazione da Adobe Client Data Layer:

| Metodo di implementazione | Come leggere il livello dati | Ulteriori informazioni |
| --- | --- | --- |
| Estensione tag Web SDK | Attiva le regole con l&#39;evento **Data Layer push** dall&#39;estensione Adobe Client Data Layer. Mappa i valori del livello dati ai campi XDM o all&#39;oggetto `data` con l&#39;azione **Aggiorna variabile** del Web SDK, quindi inviali con l&#39;azione **Invia evento**. | [Invia dati Adobe Client Data Layer con Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/web-sdk), [Mappatura campo oggetto XDM](../aep-edge/xdm-var-mapping.md) e [Mappatura campo oggetto dati](../aep-edge/data-var-mapping.md) |
| Libreria JavaScript di Web SDK | Ascolta gli eventi del livello dati con `addEventListener()` e imposta i campi XDM o `data` dal livello dati quando chiami `sendEvent`. | [Invia dati Adobe Client Data Layer con Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/web-sdk), [Mappatura campo oggetto XDM](../aep-edge/xdm-var-mapping.md) e [Mappatura campo oggetto dati](../aep-edge/data-var-mapping.md) |
| Estensione Analytics | Attiva le regole con l&#39;evento **Data Layer push** e crea **Data Layer computed state** elementi dati dall&#39;estensione Adobe Client Data Layer. Assegna gli elementi dati alle variabili di Analytics nell&#39;azione **Imposta variabili**, quindi invia i dati con l&#39;azione **Invia beacon**. | [Mappatura di oggetti livello dati su elementi dati](../launch/layer-to-elements.md) e [Mappatura di elementi dati su variabili Analytics](../launch/elements-to-variable.md) |
| AppMeasurement | Leggi i valori con `getState()` dopo il caricamento di ACDL, quindi chiama `s.t()`. | [Leggi il livello dati con AppMeasurement](#appmeasurement) |

### Leggere il livello dati con AppMeasurement {#appmeasurement}

ACDL aggiunge il metodo `getState()` all&#39;array `adobeDataLayer` al caricamento della libreria. Per fare in modo che la libreria sia stata caricata e che lo stato calcolato includa i dati più recenti, leggi i valori all&#39;interno di un listener di eventi:

```js
window.adobeDataLayer = window.adobeDataLayer || [];
window.adobeDataLayer.push(function(dl) {
  dl.addEventListener("page view", function(event) {
    s.pageName = dl.getState("page.name");
    s.channel = dl.getState("page.section");
    s.t();
  });
});
```

Il listener viene eseguito una volta per ogni evento `page view`, inclusi gli eventi inviati prima dell&#39;aggiunta del listener. Nelle pagine delle variabili di questa guida, ad esempio [`pageName`](../vars/page-vars/pagename.md), viene illustrato come leggere i singoli valori con `getState()`. Utilizza gli esempi in un listener come questo o nell&#39;editor di codice personalizzato di una regola di estensione di Analytics che attiva un evento **push** del livello dati.

Se l&#39;implementazione invia più di un hit per pagina, ad esempio in un&#39;applicazione a pagina singola, utilizza [`clearVars()`](../vars/functions/clearvars.md) in modo che i valori di un hit non persistano al successivo.

## Passaggi successivi

* [Mappatura di oggetti livello dati su elementi dati](../launch/layer-to-elements.md): utilizza il livello dati del tuo sito nei tag di Adobe Experience Platform.
* [Documentazione di Adobe Client Data Layer](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/overview): scopri ogni metodo, evento e best practice ACDL.
