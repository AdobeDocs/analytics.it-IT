---
title: eVar (variabile merchandising)
description: Variabili personalizzate collegate a singoli prodotti.
feature: Appmeasurement Implementation
exl-id: 26e0c4cd-3831-4572-afe2-6cda46704ff3
mini-toc-levels: 3
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/BdChWcR9AJqLZ0KjOxSvFAjB8-58JmmGahrpvTyFeFI'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
    internal-label: Appmeasurement implementation
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
source-git-commit: ca917b867cd84b09b899ce7b72586f0b15003106
workflow-type: tm+mt
source-wordcount: '762'
ht-degree: 30%
---
# eVar (merchandising)

>[!BEGINSHADEBOX]

*Questa pagina della guida descrive come implementare le eVar di merchandising. Per informazioni sul funzionamento delle eVar di merchandising come dimensione, consulta [eVar (dimensione merchandising)](/help/components/dimensions/evar-merchandising.md) nella guida utente dei Componenti.*

>[!ENDSHADEBOX]

Le eVar di merchandising associano un valore ai singoli prodotti, in modo che gli eventi di successo che riguardano ciascun prodotto vengano attribuiti al valore associato a tale prodotto. È possibile impostare il valore in uno dei due modi seguenti:

* **[!UICONTROL Product Syntax]**: impostare il valore su ciascun prodotto nella variabile [`products`](products.md).
* **[!UICONTROL Conversion Variable Syntax]**: impostare il valore nell&#39;eVar stesso. Il valore si associa ai prodotti in un hit che contiene un evento di binding.

Per informazioni sul funzionamento di binding, allocazione e scadenza, vedere [eVar (dimensione merchandising)](/help/components/dimensions/evar-merchandising.md).

## Impostare le eVar nelle impostazioni della suite di rapporti

Prima di utilizzare le eVar nell’implementazione, accertati di configurarle nella sintassi desiderata nelle impostazioni della suite di rapporti. Consulta [Variabili di conversione](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md) nella guida per l’amministratore.

>[!WARNING]
>
>Se le eVar di merchandising non sono configurate correttamente, si ottengono valori imprevisti o perdite di dati per la variabile. Assicurati che siano configurate correttamente per la tua implementazione.

## Scegli una sintassi

Utilizza [!UICONTROL Product Syntax] quando il valore merchandising è disponibile al momento dell&#39;impostazione della variabile `products` o quando i prodotti nello stesso hit richiedono valori diversi. Utilizzare [!UICONTROL Conversion Variable Syntax] quando il valore è noto prima del prodotto, ad esempio il termine di ricerca o la campagna interna che ha portato il visitatore al prodotto. Vedi [Funzionamento del binding e dell&#39;allocazione](/help/components/dimensions/evar-merchandising.md#how-binding-and-allocation-work) per un confronto completo.

## Implementazione utilizzando la sintassi di prodotto

Quando [!UICONTROL Product Syntax] è abilitato, il valore di merchandising viene impostato direttamente all&#39;interno della variabile `products`, pertanto gli eventi di binding non vengono utilizzati. Le eVar di merchandising si trovano nell’ultimo segmento di ciascun prodotto:

```js
s.products = "[category];[name];[quantity];[revenue];[events];[eVars]";
```

Delimitare più eVar di merchandising sullo stesso prodotto con una barra verticale (`|`). I segnaposto vuoti per quantità, ricavi ed eventi sono necessari anche se non vengono utilizzati. Senza di essi, il valore eVar viene ignorato.

Il valore è associato al prodotto in tale hit. Se un valore successivo sostituisce un&#39;associazione esistente dipende dall&#39;impostazione [!UICONTROL Allocation]. Vedi [Funzionamento del binding e dell&#39;allocazione](/help/components/dimensions/evar-merchandising.md#how-binding-and-allocation-work).

```js
// The bare minimum to set a merchandising eVar with product syntax
s.products = ";Example product;;;;eVar1=Example merchandising value";

// An example single product with product syntax
s.products = "Example category;Example product;1;5.99;event1=1;eVar1=Turtles";

// Tie a merchandising eVar to different values on two different products
s.products = "Birds;Scarlet Macaw;1;4200;;eVar1=talking bird,Birds;Turtle dove;2;550;;eVar1=love birds";
```

### Sintassi di prodotto utilizzando il Web SDK

Se si utilizza l&#39;[**oggetto XDM**](/help/implement/aep-edge/xdm-var-mapping.md), le variabili di merchandising della sintassi di prodotto utilizzano i campi XDM seguenti:

* Le eVar di merchandising della sintassi di prodotto sono mappate in `xdm.productListItems[]._experience.analytics.customDimensions.eVars.eVar1` a `xdm.productListItems[]._experience.analytics.customDimensions.eVars.eVar250`.
* Gli eventi di merchandising della sintassi di prodotto sono mappati in `xdm.productListItems[]._experience.analytics.event1to100.event1.value` a `xdm.productListItems[]._experience.analytics.event901to1000.event1000.value`. I campi XDM della [Serializzazione degli eventi](events/event-serialization.md) sono mappati in `xdm.productListItems[]._experience.analytics.event1to100.event1.id` a `xdm.productListItems[]._experience.analytics.event901to1000.event1000.id`.

>[!NOTE]
>
>Quando imposti gli eventi in `productListItems`, non è necessario impostarli nella stringa evento. Se sono impostati in entrambe le posizioni, il valore nella stringa evento ha la precedenza.

L’esempio seguente mostra un singolo [prodotto](products.md) che utilizza più eVar ed eventi di merchandising:

```json
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

Se si utilizza l&#39;[**oggetto dati**](/help/implement/aep-edge/data-var-mapping.md), le eVar di merchandising della sintassi prodotto sono impostate in `data.__adobe.analytics.products`, utilizzando la stessa sintassi della variabile AppMeasurement `products`. L’equivalente dell’oggetto dati dell’esempio XDM precedente:

```json
"data": {
  "__adobe": {
    "analytics": {
      "products": ";Bahama Shirt;3;12.99;event4|event10=2:abcd;eVar10=green|eVar33=large"
    }
  }
}
```

## Implementazione utilizzando la sintassi per le variabili di conversione

Utilizzare [!UICONTROL Conversion Variable Syntax] quando il valore eVar non è disponibile per essere impostato nella variabile `products`. In genere, questo scenario significa che la pagina di prodotto non presenta alcun contesto del canale di merchandising o del metodo di ricerca. In questi casi, imposta l’eVar di merchandising sulla pagina in cui si verifica l’evento di binding o prima di essa. Il valore persiste fino alla scadenza o viene sovrascritto con un nuovo valore.

Quando un hit contiene sia la variabile `products` che un [!UICONTROL Merchandising Binding Event] selezionato, il valore corrente di eVar si associa a ogni prodotto in tale hit. L’impostazione di eVar insieme a un prodotto senza un evento di binding non associa il valore. Se un&#39;associazione successiva sostituisce un&#39;associazione esistente dipende dall&#39;impostazione [!UICONTROL Allocation]. Vedi [Funzionamento del binding e dell&#39;allocazione](/help/components/dimensions/evar-merchandising.md#how-binding-and-allocation-work).

Per un esempio che imposta più eVar di metodo di ricerca dei prodotti contemporaneamente, vedere [Best practice: metodi di ricerca dei prodotti](/help/components/dimensions/evar-merchandising.md#best-practice-product-finding-methods).

L’esempio seguente imposta un’eVar di merchandising prima dell’evento di binding:

```js
// Place on the same or previous page before the binding event:
s.eVar1 = "Aviary";

// Place on the page where the binding event occurs:
s.events = "prodView";
s.products = ";Canary";
```

Se [!UICONTROL Product View Event] è un evento di binding, il valore `"Aviary"` per `eVar1` è associato al prodotto `"Canary"`. Gli eventi di successo successivi che riguardano questo prodotto vengono attribuiti a `"Aviary"`. Il valore `"Aviary"` si associa anche ai prodotti negli hit successivi che contengono un evento di binding, fino a quando non viene soddisfatta una delle seguenti condizioni:

* EVar scade (in base all&#39;impostazione [!UICONTROL Expire After]).
* L’eVar di merchandising viene sovrascritta con un nuovo valore.

### Sintassi per la variabile di conversione utilizzando il Web SDK

Se utilizzi l&#39;[**oggetto XDM**](/help/implement/aep-edge/xdm-var-mapping.md), la sintassi funziona in modo simile all&#39;implementazione di altri [eVar](evar.md) e [eventi](events/events-overview.md). Se si utilizza l&#39;[**oggetto dati**](/help/implement/aep-edge/data-var-mapping.md), la sintassi segue AppMeasurement.

L’XDM che rispecchia l’esempio di AppMeasurement precedente è simile al seguente.

Imposta l’eVar sulla stessa chiamata di evento oppure su quella precedente:

```json
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

```json
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

Gli oggetti dati che rispecchiano l’esempio di AppMeasurement precedente hanno l’aspetto seguente.

Imposta l’eVar sulla stessa chiamata di evento oppure su quella precedente:

```json
"data": {
  "__adobe": {
    "analytics": {
      "eVar1": "Aviary"
    }
  }
}
```

Imposta l’evento di binding e i valori per la stringa di prodotti:

```json
"data": {
  "__adobe": {
    "analytics": {
      "events": "prodView",
      "products": ";Canary"
    }
  }
}
```

