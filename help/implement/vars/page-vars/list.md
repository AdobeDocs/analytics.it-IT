---
title: list
description: Variabili personalizzate che contengono più valori nello stesso hit.
feature: Variables
exl-id: 612f6f10-6b68-402d-abb8-beb6f44ca6ff
source-git-commit: 25eccb2b9fe3827e62b0ae98d9bebf7a97b239f5
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 1%

---

# elenco

Le variabili elenco sono variabili personalizzate che puoi utilizzare come desideri. Funzionano in modo simile alle eVar, ma possono contenere più valori nello stesso hit. Le variabili elenco non hanno un limite di caratteri.

Assicurati di registrare in che modo utilizzi ciascuna variabile di elenco e la relativa logica nel [documento di progettazione della soluzione](../../prepare/solution-design.md).

>[!NOTE]
>
>Le variabili elenco memorizzano i 250 valori più recenti per visitatore. Se per un visitatore sono presenti più di 250 valori univoci, i valori meno recenti non sono attribuiti alle metriche.

## Impostare le variabili elenco nelle impostazioni delle suite di rapporti

Assicurati di configurare ogni variabile dell’elenco nelle impostazioni della suite di rapporti prima di utilizzarla nell’implementazione. Vedi [Variabili di conversione](/help/admin/admin/conversion-var-admin/list-var-admin.md) nella guida Amministratore. Questo passaggio si applica a tutti i metodi di implementazione.

## Elencare le variabili utilizzando l’SDK per web

Variabili di elenco [mappato per Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=it) nei campi XDM `_experience.analytics.customDimensions.lists.list1.list[]` a `_experience.analytics.customDimensions.lists.list3.list[]`. Ogni elemento array contiene `"value"` oggetto che contiene ogni stringa. Non è necessario fornire un delimitatore; viene incluso automaticamente utilizzando il valore specificato in [Impostazioni della suite di rapporti](/help/admin/admin/conversion-var-admin/list-var-admin.md). Ad esempio, se una virgola (&#39;`,`&#39;) è configurato come delimitatore per la variabile di elenco 1, il seguente oggetto XDM popola `list1` variabile con `"Example value 1,Example value 2,Example value 3"`.

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
>Lo schema XDM di Adobe contiene `key` oltre a `value` oggetti in ogni `list[]` array. Adobe non utilizza questi `key` durante l’invio di dati ad Adobe Analytics.

## Elencare le variabili utilizzando l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l&#39;editor di codice personalizzato seguendo la sintassi AppMeasurement.

## s.list1 - s.list3 in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Ogni variabile di elenco è una stringa che contiene valori personalizzati specifici dell’organizzazione. Non hanno un numero massimo di byte; tuttavia, ogni singolo valore ha un massimo di 255 byte. Il delimitatore utilizzato viene determinato quando si imposta la variabile in [Impostazioni della suite di rapporti](/help/admin/admin/conversion-var-admin/list-var-admin.md). Non utilizzare spazi quando si delimitano più elementi.

```js
// A list variable configured with a comma as a delimiter
s.list1 = "Example value 1,Example value 2,Example value 3";
```

>[!TIP]
>
>Se imposti valori duplicati nello stesso hit, Adobe deduplica tutte le istanze di tali valori. Ad esempio, se si imposta `s.list1 = "Brick,Brick";`, un’istanza viene conteggiata nei rapporti.

## Confrontare proprietà elenco con variabili elenco

Le proprietà di elenco e le variabili di elenco possono contenere più valori nello stesso hit. Tuttavia, esistono diverse differenze chiave tra questi due tipi di variabili.

* Qualsiasi prop può diventare una proprietà di elenco. Puoi effettivamente avere fino a 75 proprietà elenco, se ogni proprietà è una proprietà elenco. Sono disponibili solo tre variabili elenco.
* Le proprietà di elenco hanno un limite di 100 byte per l&#39;intera variabile. Le variabili elenco hanno un limite di 255 byte per valore e nessun limite totale di byte.
* Le proprietà dell’elenco non persistono oltre l’hit impostato. Le variabili elenco dispongono di un’impostazione di scadenza. Tuttavia, con [elaborazione dei tempi di report](/help/components/vrs/vrs-report-time-processing.md), puoi applicare l’attribuzione personalizzata sia alle proprietà dell’elenco che alle variabili dell’elenco.
