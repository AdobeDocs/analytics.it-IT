---
description: nulle
keywords: Analytics Implementation
solution: Analytics
title: Panoramica delle variabili merchandising
topic: Developer and implementation
uuid: 2ccf516a-a7ee-48ab-92aa-414228a4102f
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Panoramica delle variabili merchandising

Per misurare il successo di campagne esterne o termini di ricerca esterna, in genere si desidera che un singolo valore riceva credito per qualsiasi evento di successo che si verifichi. Ad esempio, se un cliente fa clic su un collegamento in una campagna e-mail per visitare il sito Web, tutti gli acquisti effettuati di conseguenza devono essere accreditati su tale campagna.

Ma che dire degli eventi guidati da una ricerca interna o da una ricerca per categoria quando un cliente cerca più elementi? Ad esempio, un cliente cerca nel sito "goggles" e aggiunge una coppia al carrello:

![](assets/merch-example-goggles.png)

Prima del checkout, il cliente cerca "cappotto invernale", quindi aggiunge una giacca giù al carrello:

![](assets/merch-example-coat.png)

Quando l'acquisto è completato, supponendo che l'allocazione non sia stata modificata da Most Recent, avrete una ricerca interna per "cappotto invernale" accreditato con l'acquisto di un paio di occhiali. Buona per "cappotto invernale", ma cattiva per le decisioni di marketing:

| Termine di ricerca interno | Ricavi |
|---|---|
| strato invernale | $157 |

**Come le variabili merchandising risolvono il problema**

Le variabili di merchandising tra categorie, o "evar di merchandising", consentono di assegnare il valore corrente di un eVar a un prodotto al momento in cui si verifica un evento di successo. Questo valore rimane legato a tale prodotto, anche se successivamente vengono impostati uno o più nuovi valori per tale eVar.

Se il merchandising è abilitato per l'eVar nell'esempio precedente, il termine di ricerca "occhialini" è legato agli occhiali da neve Fernie e il termine di ricerca "cappotto invernale" è legato alla giacca El Gordo Down. Le variabili di merchandising allocano le entrate a livello di prodotto, in modo che ogni termine riceva credito per l'importo delle entrate per il prodotto a cui era associato il termine:

| Termine di ricerca interno | Ricavi |
|---|---|
| strato invernale | $119 |
| occhiali | $38 |

