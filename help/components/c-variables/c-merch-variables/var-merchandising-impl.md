---
description: Descrive come abilitare e implementare una variabile merchandising.
keywords: Analytics Implementation;merchandising;variabile;sintassi del prodotto;Conversion Variable Syntax;s.products
seo-description: Descrive come abilitare e implementare una variabile merchandising.
seo-title: Implementazione di una variabile di merchandising
solution: Analytics
title: Implementazione di una variabile di merchandising
topic: Sviluppatore e implementazione
translation-type: tm+mt
source-git-commit: f3c3a3c74434586f2bd8bcf3c23f488994129394

---


# Implementazione di una variabile di merchandising

Descrive come abilitare e implementare una variabile merchandising.

## Attivare una variabile Merchandising

Il merchandising può essere abilitato per qualsiasi eVar personalizzato in **[!UICONTROL Admin Tools]** &gt; **[!UICONTROL Report Suites]** &gt; **[!UICONTROL Conversion Variables]**.

![](assets/merch-enable.png)

| Impostazione | Descrizione |
|--- |--- |
| Scade dopo | Determina per quanto tempo i valori merchandising devono persistere. |
|  Merchandising | **** Sintassi prodotto: Il valore è impostato all'interno `s.products`.<br>**** Sintassi della variabile di conversione: Il valore viene impostato nell'eVar di merchandising designata. |
| Evento di binding Merchandising (solo sintassi della variabile Conversion) | Indica se un prodotto deve essere associato alla categoria di merchandising corrente. Per selezionare più eventi, tenete premuto Ctrl e fate clic su più elementi nell’elenco. È possibile selezionare un evento solo quando è selezionata la "Sintassi variabile di conversione". |

## Implementazione tramite sintassi prodotto

Quando Product Syntax (Sintassi prodotto) è abilitata, la categoria merchandising viene compilata direttamente all'interno della variabile products, quindi la selezione e l'impostazione di un evento di binding non è obbligatoria. Questo è il metodo consigliato e deve essere utilizzato a meno che il valore non sia disponibile per l'impostazione in `s.products` corrispondenza dell'evento success.

### Sintassi

```js
s.products="category;product;quantity;price;event_incrementer;eVarN=merch_category|eVarM=merch_category2";
```

### Esempio 

```js
s.events="prodView";
s.products=";Snow Goggles;;;;eVar1=goggles";
```

Il valore "goggles" per eVar1 è assegnato al prodotto "Snow Goggles". Tutti gli eventi di successo successivi (aggiunta di prodotti, pagamenti, acquisti e così via) che coinvolgono questo prodotto vengono accreditati agli "occhiali".

## Implementazione tramite sintassi variabile di conversione

La sintassi della variabile di conversione deve essere utilizzata quando il valore eVar non è disponibile per l'impostazione in `s.products`. Ciò significa in genere che la pagina non ha contesto del canale di merchandising o del metodo di ricerca. In questi casi, è necessario impostare la variabile merchandising prima di arrivare alla pagina del prodotto e il valore persiste fino al verificarsi dell'evento di binding.

Quando si verifica l'evento di binding selezionato durante la configurazione, il valore persistente dell'eVar è associato al prodotto. Ad esempio, se prodView è specificato come evento di binding, la categoria merchandising è associata all'elenco di prodotti corrente solo al momento in cui si verifica l'evento. Solo gli eventi di binding successivi possono aggiornare un'eVar di merchandising già assegnata a un prodotto.

### Sintassi

Posizionarsi sulla stessa pagina o nella pagina precedente prima dell'evento di binding:

```js
s.eVar1="merchandising_category";
```

Posizionarsi sulla pagina in cui si verifica l'evento di binding:

```js
s.events="prodView";
s.products="category;product";
```

### Esempio 

A pagina 1 della visita:

```js
s.eVar1="Outdoors"
```

A pagina 2 della visita:

```js
s.events="prodView";
s.products=";Snow Goggles";
```

Il valore "Outdoors" per eVar1 è assegnato al prodotto "Snow Goggles". Tutti gli eventi di successo successivi (prodotti aggiunti, pagamenti, acquisti e così via) che coinvolgono questo prodotto vengono accreditati su "Snow Goggles". Inoltre, il valore corrente della variabile merchandising è associato a tutti i prodotti successivi fino al soddisfacimento di una delle seguenti condizioni:

* Scadenza eVar (in base all'impostazione "Scade dopo")
* L'eVar di merchandising viene sovrascritto con un nuovo valore.

## Informazioni aggiuntive esterne

[Advanced Conversion Syntax Merchandising](https://analyticsdemystified.com/adobe-analytics/advanced-conversion-syntax-merchandising/) on [!DNL analyticsdemystified.com]
