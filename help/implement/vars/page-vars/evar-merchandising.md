---
title: eVar (variabile merchandising)
description: Variabili personalizzate collegate a singoli prodotti.
feature: Variables
exl-id: 26e0c4cd-3831-4572-afe2-6cda46704ff3
mini-toc-levels: 3
source-git-commit: 68389772dec0420a66767bb0af9dea3122e1cb0f
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 100%

---

# eVar  (Merchandising)

*Questa pagina della guida descrive come implementare le eVar di merchandising. Per informazioni sul funzionamento delle eVar di merchandising come dimensione, consulta [eVar (dimensione merchandising)](/help/components/dimensions/evar-merchandising.md) nella guida utente dei Componenti.*

Per una discussione dettagliata sul funzionamento delle eVar di merchandising, consulta [eVar di merchandising e metodi di ricerca dei prodotti](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/merchandising-evars.html?lang=it).

## Impostare le eVar nelle impostazioni della suite di rapporti

Prima di utilizzare le eVar nell’implementazione, accertati di configurarle nella sintassi desiderata nelle impostazioni della suite di rapporti. Consulta [Variabili di conversione](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md) nella guida per l’amministratore.

>[!WARNING]
>
>Se le eVar di merchandising non sono configurate correttamente, si ottengono valori imprevisti o perdite di dati per la variabile. Assicurati che siano configurate correttamente per la tua implementazione.

## Implementazione utilizzando la sintassi di prodotto

Quando è abilitata la “Sintassi del prodotto”, la categoria merchandising viene popolata direttamente all’interno della variabile `products`, pertanto non è necessario selezionare e impostare un evento di binding. Questo è il metodo consigliato e deve essere utilizzato a meno che il valore non sia disponibile per essere impostato in `products` quando si verifica l’evento di successo.

```js
// The bare minimum to set a merchandising eVar with product syntax
s.products = ";Example product;;;;eVar1=Example merchandising value";

// An example single product with product syntax
s.products = "Example category;Example product;1;5.99;event1=1;eVar1=Turtles";

// Tie a merchandising eVar to a different values on two different products
s.products = "Birds;Scarlet Macaw;1;4200;;eVar1=talking bird,Birds;Turtle dove;2;550;;eVar1=love birds";
```

Il valore della `eVar1` viene assegnato al prodotto. Tutti gli eventi di successo successivi che riguardano questo prodotto vengono attribuiti al valore eVar.

### Sintassi di prodotto utilizzando il Web SDK

Le variabili di merchandising della sintassi di prodotto sono [mappate per Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=it) in diversi campi XDM.

* Le eVar di merchandising della sintassi di prodotto sono mappate in `productListItems[]._experience.analytics.customDimensions.eVars.eVar1` a `productListItems[]._experience.analytics.customDimensions.eVars.eVar250`.
* Gli eventi di merchandising della sintassi di prodotto sono mappati in `productListItems[]._experience.analytics.event1to100.event1.value` a `productListItems[]._experience.analytics.event901to1000.event1000.value`. I campi XDM della [Serializzazione degli eventi](events/event-serialization.md) sono mappati in `productListItems[]._experience.analytics.event1to100.event1.id` a `productListItems[]._experience.analytics.event901to1000.event1000.id`.

>[!NOTE]
>
>Quando imposti gli eventi in `productListItems`, non è necessario impostarli nella stringa evento. Se sono impostati in entrambe le posizioni, il valore nella stringa evento ha la precedenza.

L’esempio seguente mostra un singolo [prodotto](products.md) che utilizza più eVar ed eventi di merchandising:

```js
"productListItems": [
    {
        "name": "Bahama Shirt",
        "priceTotal": "12.99",
        "quantity": 3,
        "_experience": {
            "analytics": {
                "customDimensions" : {
                    "eVars" : {
                        "eVar10" : "green",
                        "eVar33" : "large"
                    }
                },
                "event1to100" : {
                    "event4" : {
                        "value" : 1
                    },
                    "event10" : {
                        "value" : 2,
                        "id" : "abcd"
                    }
                }
            }
        }
    }
]
```

L’oggetto dell’esempio precedente viene inviato ad Adobe Analytics come `";Bahama Shirt;3;12.99;event4|event10=2:abcd;eVar10=green|eVar33=large"`.

## Implementazione utilizzando la sintassi per le variabili di conversione

La sintassi per le variabili di conversione viene utilizzata quando il valore eVar non è disponibile per essere impostato nella variabile `products`. Generalmente, questo scenario indica che la pagina non contiene nessun contesto del canale di merchandising o del metodo di ricerca. In questi casi, è possibile impostare la variabile merchandising prima di arrivare alla pagina del prodotto e il valore persiste finché non si verifica l’evento di binding.

Quando si verifica l’evento di binding selezionato durante la configurazione, il valore persistente dell’eVar è associato al prodotto. Ad esempio, se `prodView` è specificato come evento di binding, la categoria di merchandising viene associata all’elenco di prodotti corrente solo al momento in cui si verifica l’evento. Solo gli eventi di binding successivi possono aggiornare un’eVar di merchandising già assegnata a un prodotto.

```js
// Place on the same or previous page before the binding event:
s.eVar1 = "Aviary";

// Place on the page where the binding event occurs:
s.events = "prodView";
s.products = ";Canary";
```

Il valore `"Aviary"` della `eVar1` viene assegnato al prodotto `"Canary"`. Tutti gli eventi di successo successivi che riguardano questo prodotto vengono attribuiti a `"Canary"`. Inoltre, il valore corrente della variabile merchandising è associato a tutti i prodotti successivi fino a quando non viene soddisfatta una delle seguenti condizioni:

* L’eVar scade (in base all’impostazione “Scade dopo”)
* L’eVar di merchandising viene sovrascritta con un nuovo valore.

### Sintassi per la variabile di conversione utilizzando il Web SDK

La sintassi per le variabili di conversione che utilizzano il Web SDK funziona in modo simile all’implementazione di altre [eVar](evar.md) ed [eventi](events/events-overview.md). L’XDM che rispecchia l’esempio precedente è simile al seguente:

Imposta l’eVar sulla stessa chiamata di evento oppure su quella precedente:

```js
"_experience": {
    "analytics": {
        "customDimensions": {
            "eVars": {
                "eVar1" : "Aviary"
            }
        }
    }
}
```

Imposta l’evento di binding e i valori per la stringa di prodotti:

```js
"commerce": {
    "productViews" : {
        "value" : 1
    }
},
"productListItems": [
    {
        "name": "Canary"
    }
]
```
