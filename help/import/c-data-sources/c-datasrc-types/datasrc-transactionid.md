---
description: Gli ID transazione possono essere integrati selezionando la categoria Generico (ID transazione).
solution: Analytics
subtopic: Data sources
title: ID transazione
topic: Developer and implementation
uuid: f3370bb7-3f28-460b-a20d-c9e58d7301d4
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# ID transazione

Gli ID transazione possono essere integrati selezionando la categoria Generico (ID transazione).

Consulta [Integrazione dei dati](/help/import/c-data-sources/datasrc-integrating-offline-data.md)offline.

Data uploaded with *`transactionID`* automatically associates with the same marketing channel that processed the original server call that contained the *`transactionID`*.

**Dimensioni ID transazione**

| Nome colonna | Descrizione |
|--- |--- |
| ID transazione | (Obbligatorio) Valore univoco che rappresenta una transazione online generata nell'attività offline. |
| Data | Utilizzare il formato data seguente: MM/GG/AAAA/HH/mm/SS (ad esempio, 01/01/2015/06/00/00). |
| Codice di tracciamento | Nome del codice di tracciamento. |
| Categoria | Nome della categoria.  Se specifichi una categoria, devi anche selezionare un prodotto. |
| Canale | Nome del canale. |
| eVarN | Nome eVarN. I valori validi per N sono numeri interi 1 - 250. |
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
| EventN | Numero di volte in cui si è verificato eventN. I valori validi per N sono numeri interi 1 - 1000.  Se specifichi un evento Visualizzazione, devi specificare anche la dimensione dei dati corrispondenti (eVar). Ad esempio, se includi visualizzazioni eVar2, devi elencare eVar2 con un valore. |
| Visualizzazioni eVarN | Numero di volte in cui è stata visualizzata eVarN. I valori validi per N sono numeri interi 1 - 250. |
| Prezzo | Prezzo del prodotto. |
| Ordini | Numero di ordini inseriti. |
| Visualizzazioni prodotto | Numero di visualizzazioni del prodotto. |
| Quantità | Numero di unità vendute. |
