---
title: list
description: Variabili personalizzate che contengono più valori nello stesso hit.
feature: Variables
exl-id: 612f6f10-6b68-402d-abb8-beb6f44ca6ff
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 100%

---

# list

Le variabili elenco sono variabili personalizzate che puoi utilizzare come preferisci. Funzionano in modo simile alle eVar, ma possono contenere più valori nello stesso hit. Le variabili elenco non hanno un limite di caratteri.

Assicurati di registrare in che modo utilizzi ciascuna variabile elenco e la relativa logica nel [documento di progettazione della soluzione](../../prepare/solution-design.md).

>[!NOTE]
>
>Le variabili elenco memorizzano i 250 valori più recenti per visitatore. Se per un visitatore sono presenti più di 250 valori univoci, i valori meno recenti non sono attribuiti alle metriche.

## Impostare le variabili elenco nelle impostazioni delle suite di rapporti

Assicurati di configurare ogni variabile elenco nelle impostazioni della suite di rapporti prima di utilizzarla nell’implementazione. Consulta [Variabili di conversione](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md) nella guida per l’amministratore. Questo passaggio si applica a tutti i metodi di implementazione.

## Variabili elenco tramite il Web SDK

Le variabili elenco sono [mappate per Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=it) nei campi XDM da `_experience.analytics.customDimensions.lists.list1.list[]` a `_experience.analytics.customDimensions.lists.list3.list[]`. Ogni elemento matrice contiene un oggetto `"value"` che contiene ogni stringa. Non è necessario fornire un delimitatore, poiché viene incluso automaticamente utilizzando il valore specificato nelle [Impostazioni della suite di rapporti](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md). Ad esempio, se una virgola (“`,`”) è configurata come delimitatore per la variabile elenco 1, il seguente oggetto XDM compila la variabile `list1` con `"Example value 1,Example value 2,Example value 3"`.

```json
"xdm": {
  "_experience": {
    "analytics": {
      "customDimensions": {
        "lists": {
          "list1": {
            "list": [
              {
                "value": "Example value 1"
              },
              {
                "value": "Example value 2"
              },
              {
                "value": "Example value 3"
              }
            ]
          }
        }
      }
    }
  }
}
```

>[!NOTE]
>
>Lo schema XDM di Adobe contiene oggetti `key` oltre a oggetti `value` in ogni matrice `list[]`. Adobe non utilizza questi oggetti `key` durante l’invio di dati ad Adobe Analytics.

## Variabili elenco tramite l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## s.list1 - s.list3 in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Ogni variabile elenco è una stringa che contiene valori personalizzati specifici dell’organizzazione. Non hanno un numero massimo di byte; tuttavia, ogni singolo valore ha un massimo di 255 byte. Il delimitatore utilizzato viene determinato quando si imposta la variabile nelle [Impostazioni della suite di rapporti](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md). Non utilizzare spazi quando si delimitano più elementi.

```js
// A list variable configured with a comma as a delimiter
s.list1 = "Example value 1,Example value 2,Example value 3";
```

>[!TIP]
>
>Se imposti valori duplicati nello stesso hit, Adobe deduplica tutte le istanze di tali valori. Ad esempio, se imposti `s.list1 = "Brick,Brick";`, nei rapporti viene conteggiata un’istanza.

## Confrontare le prop elenco con le variabili elenco

Le prop elenco e le variabili elenco possono entrambe contenere più valori nello stesso hit. Tuttavia, esistono diverse differenze chiave tra questi due tipi di variabili.

* Qualsiasi prop può diventare una prop elenco. Puoi effettivamente disporre di un massimo 75 prop elenco, se ogni prop è una prop elenco. Sono disponibili solo tre variabili elenco.
* Le prop elenco hanno un limite di 100 byte per l’intera variabile. Le variabili elenco hanno un limite di 255 byte per valore e nessun limite totale di byte.
* Le prop elenco non persistono oltre l’hit impostato. Le variabili elenco dispongono di un’impostazione di scadenza a piacimento. Tuttavia, con l’[Elaborazione al momento del rapporto](/help/components/vrs/vrs-report-time-processing.md), puoi applicare l’attribuzione personalizzata sia alle prop elenco che alle variabili elenco.
