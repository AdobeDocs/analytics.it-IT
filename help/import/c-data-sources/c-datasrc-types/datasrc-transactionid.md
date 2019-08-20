---
description: Gli ID transazione possono essere integrati selezionando la categoria Generico (ID transazione).
seo-description: Gli ID transazione possono essere integrati selezionando la categoria Generico (ID transazione).
seo-title: ID transazione
solution: Analytics
subtopic: Origini dati
title: ID transazione
topic: Sviluppatore e implementazione
uuid: f 3370 bb 7-3 f 28-460 b-a 20 d-c 9 e 58 d 7301 d 4
translation-type: tm+mt
source-git-commit: e9cb3575780db9eb5c9a766ef20d596e504a20d0

---


# ID transazione

Gli ID transazione possono essere integrati selezionando la categoria Generico (ID transazione).

Consultate [Integrazione di dati offline](../../../import/c-data-sources/datasrc-integrating-offline-data.md#concept_B5C576220F1548B5A3A57112AA3960C6).

Data uploaded with *`transactionID`* automatically associates with the same marketing channel that processed the original server call that contained the *`transactionID`*.

**Dimensioni ID transazione**

| Nome colonna | Descrizione |
|--- |--- |
| ID transazione | (Obbligatorio) Valore univoco che rappresenta una transazione online generata nell'attività offline. |
| Data | Utilizzare il formato data seguente: MM/GG/AAAA/HH/mm/SS (ad esempio, 01/01/2015/06/00/00). |
| Codice di tracciamento | Nome del codice di tracciamento. |
| Categoria | Nome della categoria.  Se specifichi una categoria, devi anche selezionare un prodotto. |
| Canale | Nome del canale. |
| Evarn | Nome evarn. I valori validi per N sono numeri interi 1 - 250. |
| Prodotto | Nome del prodotto. |
| Stato | Nome dello stato. |
| ZIP | Nome dello ZIP. |

<p class="head"> <b>Metriche ID transazione</b> </p>



| Nome colonna | Descrizione |
|--- |--- |
| ClickThrough | Numero di visualizzazioni del codice di tracciamento. |
| Aggiunte al carrello | Numero di aggiunte al carrello. |
| Aperture carrello | Numero di aperture del carrello. |
| Rimozioni dal carrello | Numero di rimozioni dal carrello. |
| Visualizzazioni carrello | Numero di visualizzazioni del carrello. |
| Pagamenti | Numero di pagamenti. |
| Eventn | Numero di volte in cui si è verificato eventn. I valori validi per N sono numeri interi 1 - 1000. Se specifichi un evento Visualizzazione, devi specificare anche la dimensione dei dati corrispondenti (eVar). Ad esempio, se includi visualizzazioni eVar2, devi elencare eVar2 con un valore. |
| Visualizzazioni evarn | Numero di volte in cui evarn è stato visualizzato. I valori validi per N sono numeri interi 1 - 250. |
| Prezzo | Prezzo del prodotto. |
| Ordini | Numero di ordini inseriti. |
| Visualizzazioni prodotto | Numero di visualizzazioni del prodotto. |
| Quantità | Numero di unità vendute. |
