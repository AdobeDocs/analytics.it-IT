---
description: Elenco di eventi predefiniti.
keywords: Implementazione di Analytics; evento
seo-description: Elenco di eventi predefiniti.
seo-title: Che cos'è un evento predefinito?
solution: Analytics
title: Che cos'è un evento predefinito?
topic: Sviluppatore e implementazione
uuid: 4 d 0799 ba -0 f 97-42 c 3-a 620-36 c 03 f 9995 da
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Che cos'è un evento predefinito?

Elenco di eventi predefiniti.

| all'evento | L'evento success si verifica ogni volta che un visitatore visualizza un prodotto. |
|---|---|
| Scview | L'evento Success si verifica ogni volta che viene visualizzato un carrello. |
| Scoen | L'evento success si verifica ogni volta che un visitatore apre un carrello per la prima volta. |
| Cetd | L'evento success si verifica ogni volta che un prodotto viene aggiunto a un carrello. |
| Scremove | L'evento success si verifica ogni volta che un elemento viene estratto da un carrello. |
| Sccheckout | L'evento success si verifica nella prima pagina di un checkout. |
| purchase | L'evento Success si verifica nella pagina finale di un checkout (include Entrate, Ordini e Unità). |

Quando si verifica uno degli eventi predefiniti sopra, un'istanza dell'evento viene incrementata. Potete visualizzare le metriche correlate all'evento in diversi rapporti diversi. Consultate di seguito un esempio del codice utilizzato per configurare eventi predefiniti.

```js
s.events="scAdd"
```

```js
s.events="scOpen,scAdd"
```

* In the first example above, *`scAdd`* is the value of the event. Ogni volta che un elemento viene aggiunto al carrello, l'evento viene incrementato.
* Nel secondo esempio, due valori vengono acquisiti allo stesso tempo. Quando si verificano più eventi di successo sulla stessa pagina, ogni evento viene incrementato.

