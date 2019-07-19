---
description: Gli ID visitatore possono essere integrati selezionando la categoria Generico (ID transazione).
seo-description: Gli ID visitatore possono essere integrati selezionando la categoria Generico (ID transazione).
seo-title: Visitor ID
solution: Analytics
subtopic: Origini dati
title: Visitor ID
topic: Sviluppatore e implementazione
uuid: 4 e 9 ce 675-72 c 2-42 a 4-8 f 2 e -25140 df 19539
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# ID visitatore

Gli ID visitatore possono essere integrati selezionando la categoria Generico (ID transazione).

See [Integrate Offline Data](../../../import/c-data-sources/datasrc-integrating-offline-data.md#concept_B5C576220F1548B5A3A57112AA3960C6).

<p class="head"> <b>Dimensioni ID visitatore</b> </p>

| Nome colonna | Descrizione |
|--- |--- |
| ID visitatore | (Obbligatorio) Valore univoco che rappresenta un cliente nei sistemi online e offline. |
| Data | Utilizzare il formato data seguente: MM/GG/AAAA/hh/mm/ss (ad esempio, 07/14/2017/06/00/00). |
| Codice di tracciamento | Nome del codice di tracciamento. |
| Categoria | Nome della categoria.  Se specifichi una categoria, devi anche selezionare un prodotto. |
| Canale | Nome del canale. |
| Evarn | Nome evarn. I valori validi per n sono numeri interi 1 - 75. |
| Prodotto | Nome del prodotto. |
| Stato | Nome dello stato. |
| ZIP | Nome dello ZIP. |

**Metriche ID visitatore**

| Nome colonna | Descrizione |
|--- |--- |
| ClickThrough | Numero di visualizzazioni del codice di tracciamento. |
| Aggiunte al carrello | Numero di aggiunte al carrello. |
| Aperture carrello | Numero di aperture del carrello. |
| Rimozioni dal carrello | Numero di rimozioni dal carrello. |
| Visualizzazioni carrello | Numero di visualizzazioni del carrello. |
| Pagamenti | Numero di pagamenti. |
| Evento n | Numero di volte in cui si è verificato l'evento n. I valori validi per n sono numeri interi 1 - 100.  Se specifichi un evento Visualizzazione, devi specificare anche la dimensione dei dati corrispondenti (eVar). Ad esempio, se includi visualizzazioni eVar2, devi elencare eVar2 con un valore. |
| Visualizzazioni evarn | Numero di volte in cui è stata visualizzata l'eVar n. I valori validi per n sono numeri interi 1 - 75. |
| Prezzo | Prezzo del prodotto. |
| Ordini | Numero di ordini inseriti. |
| Visualizzazioni prodotto | Numero di visualizzazioni del prodotto. |
| Quantità | Numero di unità vendute. |