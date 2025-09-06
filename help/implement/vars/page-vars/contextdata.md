---
title: contextData
description: Le variabili di dati di contesto ti consentono di definire variabili personalizzate in ogni pagina leggibile dalle regole di elaborazione.
feature: Appmeasurement Implementation
exl-id: f2c747a9-1a03-4f9f-8025-9f4745403a81
role: Admin, Developer
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '570'
ht-degree: 3%

---

# contextData

Le variabili di dati di contesto ti consentono di definire variabili personalizzate in ogni pagina leggibile dalle regole di elaborazione. Invece di assegnare esplicitamente i valori alle variabili di Analytics nel codice, puoi inviare dati in variabili di dati di contesto. Le regole di elaborazione accettano quindi i valori delle variabili di dati di contesto e li trasmettono alle rispettive variabili di Analytics. Consulta [Regole di elaborazione](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) nella Guida utente di amministrazione.

Le variabili di dati contestuali sono utili ai team di sviluppo per raccogliere dati in elementi denominati anziché in variabili numerate. Ad esempio, invece di richiedere ai team di sviluppo di assegnare l&#39;autore della pagina a `eVar10`, puoi richiedere loro di assegnarlo a `s.contextData["author"]`. Un amministratore di Analytics della tua organizzazione può quindi creare regole di elaborazione per mappare le variabili di dati di contesto in variabili di Analytics a scopo di reporting. In ultima analisi, i team di sviluppo si preoccuperebbero solo delle variabili di dati di contesto anziché delle numerose variabili di pagina offerte da Adobe.

## Variabili di dati di contesto tramite Web SDK

Se si utilizza l&#39;[**oggetto XDM**](/help/implement/aep-edge/xdm-var-mapping.md), tutti i campi non mappati a una variabile Adobe Analytics vengono inclusi automaticamente come variabile di dati di contesto. Puoi anche impostare esplicitamente i dati contestuali utilizzando l’oggetto XDM. Puoi quindi utilizzare [Regole di elaborazione](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) per assegnare la variabile di dati di contesto alla variabile di Analytics desiderata.  Per ulteriori informazioni, vedi [Mappatura di altri campi XDM su variabili Analytics](../../aep-edge/xdm-var-mapping.md#mapping-other-xdm-fields-to-analytics-variables).

Se si utilizza l&#39;[**oggetto dati**](/help/implement/aep-edge/data-var-mapping.md), tutte le variabili di dati di contesto si trovano all&#39;interno di `data.__adobe.analytics.contextData` come coppie chiave-valore:

```js
alloy("sendEvent", {
  "data": {
    "__adobe": {
      "analytics": {
        "contextData": {
          "example_variable": "Example value",
          "second_example": "Another value"
        }
      }
    }
  }
});
```

L&#39;interfaccia delle [regole di elaborazione](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) mostrerebbe `example_variable` e `second_example` nei menu a discesa applicabili.

## Variabili di dati di contesto tramite l’estensione Adobe Analytics

La raccolta dati di Adobe Experience Platform non dispone di una posizione dedicata per impostare le variabili di dati di contesto. Utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## s.contextData in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La variabile `s.contextData` non accetta direttamente un valore. Impostare invece le proprietà di questa variabile su una stringa.

```js
// Assign the example_variable property a value
s.contextData["example_variable"] = "Example value";
```

* Le variabili di dati di contesto valide contengono solo caratteri alfanumerici, trattini bassi e punti. Adobe non garantisce la raccolta dei dati nelle regole di elaborazione se includi altri caratteri, ad esempio i trattini.
* Non avviare le variabili di dati di contesto con `"a."`. Questo prefisso è riservato e utilizzato da Adobe. Ad esempio, non utilizzare `s.contextData["a.InstallEvent"]`.
* Le variabili di dati di contesto non fanno distinzione tra maiuscole e minuscole. Le variabili `s.contextData["example"]` e `s.contextData["EXAMPLE"]` sono identiche.
* Una singola chiave non può contenere più di un valore. Se si desidera utilizzare variabili di dati di contesto per variabili multivalore, concatenare tutti i valori utilizzando un delimitatore (in genere una virgola) e trasmetterli a una [prop elenco](prop.md#list-props) o a una [variabile elenco](list.md) utilizzando le regole di elaborazione.

## Utilizzare le regole di elaborazione per popolare le variabili di analisi

>[!WARNING]
>
>Le variabili di dati di contesto vengono eliminate dopo l’esecuzione delle regole di elaborazione. Se non hai regole di elaborazione attive che inseriscono valori nelle variabili, quei dati vengono persi definitivamente!

1. Aggiorna l’implementazione per impostare i nomi e i valori delle variabili di dati di contesto.
2. Accedi ad Adobe Analytics e vai a **[!UICONTROL Admin]** > **[!UICONTROL Report]** suite.
3. Seleziona la suite di rapporti desiderata, quindi vai a **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Processing Rules]**.
4. Crea una regola di elaborazione che imposta una variabile di Analytics sul valore della variabile di dati di contesto.
5. Salva le modifiche.

Le regole di elaborazione diventano effettive immediatamente dopo il salvataggio. Non si applicano ai dati storici.

## Inviare dati contestuali in una chiamata di tracciamento dei collegamenti

Includere la variabile di dati di contesto come proprietà di `contextData` in [`s.linkTrackVars`](../config-vars/linktrackvars.md):

```js
s.contextData["example_variable"] = "Example value";
s.linkTrackVars = "contextData.example_variable";
s.tl(true,"o","Example context data link");
```

## Incrementare gli eventi utilizzando le variabili di dati di contesto

Durante la creazione di regole di elaborazione, puoi assegnare variabili di dati di contesto agli eventi.

* Se una variabile di dati di contesto contiene qualsiasi tipo di testo, l’evento viene incrementato di uno.
* Se una variabile di dati di contesto contiene un numero intero, l’evento viene incrementato di tale numero intero.

```js
// Assigning this context data variable to an event increments it by one
s.contextData["example_text"] = "Text value";

// Assigning this context data variable to an event increments it by four
s.contextData["example_number"] = "4";
```
