---
description: Elenco di eventi predefiniti.
keywords: Analytics Implementation;event
solution: Analytics
title: L'evento predefinito
topic: Developer and implementation
uuid: 4d0799ba-0f97-42c3-a620-36c03f9995da
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# L'evento predefinito

Elenco di eventi predefiniti.

| all'evento | L'evento di successo si verifica ogni volta che un visitatore visualizza un prodotto. |
|---|---|
| scView | L'evento di successo si verifica ogni volta che viene visualizzato un carrello. |
| scOpen | L'evento di successo si verifica ogni volta che un visitatore apre un carrello per la prima volta. |
| scAdd | L'evento di successo si verifica ogni volta che un prodotto viene aggiunto a un carrello. |
| scRemove | L'evento di successo si verifica ogni volta che un elemento viene estratto da un carrello. |
| scCheckout | L'evento di successo si verifica nella prima pagina di un checkout. |
| purchase | L'evento di successo si verifica nella pagina finale di un checkout (include Entrate, Ordini e Unità). |

Quando si verifica uno degli eventi predefiniti sopra, un'istanza dell'evento viene incrementata. Potete visualizzare le metriche relative all'evento in diversi rapporti diversi. Vedere di seguito un esempio del codice utilizzato per configurare eventi predefiniti.

```js
s.events="scAdd"
```

```js
s.events="scOpen,scAdd"
```

* Nel primo esempio, *`scAdd`* è il valore dell'evento. Ogni volta che un elemento viene aggiunto al carrello, l'evento viene incrementato.
* Nel secondo esempio, vengono acquisiti due valori contemporaneamente. Quando si verificano più eventi di successo sulla stessa pagina, ogni evento viene incrementato.

