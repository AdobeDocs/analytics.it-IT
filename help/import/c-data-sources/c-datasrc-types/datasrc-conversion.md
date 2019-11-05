---
description: Origini dati supporta le dimensioni e metriche di dati di conversione seguenti per i tipi di dati elaborati come conversione.
seo-description: Origini dati supporta le dimensioni e metriche di dati di conversione seguenti per i tipi di dati elaborati come conversione.
seo-title: Conversione
solution: Analytics
subtopic: Origini dati
title: Conversione
topic: Sviluppatore e implementazione
uuid: 5e7907b1-6c9c-4073-876b-410f3a29767d
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Conversione

Origini dati supporta le dimensioni e metriche di dati di conversione seguenti per i tipi di dati elaborati come conversione.

## Dimensioni di conversione e metriche {#section_FA1731B232B246DABEDF5A5D84159084}

Se specifichi un evento Visualizzazione, devi specificare anche la dimensione dei dati corrispondenti (eVar). Ad esempio, se includi visualizzazioni eVar2, devi elencare eVar2 con un valore. Il numero di eventi personalizzati e visualizzazioni eVar supportati da una suite di rapporti dipende dal contratto e varia a seconda delle società.

<p class="head"> <b>Dimensioni di conversione</b> </p>

| Nome colonna | Descrizione |
|--- |--- |
| Codice di tracciamento | Nome del codice di tracciamento. |
| Data | Utilizzare il formato data seguente: MM/GG/AAAA/HH/mm/SS (ad esempio, 01/01/2015/06/00/00). |
| Categoria | Nome della categoria.  Se specifichi una categoria, devi anche selezionare un prodotto. |
| Canale | Nome del canale. |
| eVarn | Nome eVarn. I valori validi per n sono numeri interi 1 - 75. |
| Prodotto | Nome del prodotto. |
| Stato | Nome dello stato. |
| ZIP | Nome dello ZIP. |

<p class="head"> <b>Metriche di conversione</b> </p>

| Nome colonna | Descrizione |
|--- |--- |
| ClickThrough | Numero di visualizzazioni del codice di tracciamento. |
| Aggiunte al carrello | Numero di aggiunte al carrello. |
| Aperture carrello | Numero di aperture del carrello. |
| Rimozioni dal carrello | Numero di rimozioni dal carrello. |
| Visualizzazioni carrello | Numero di visualizzazioni del carrello. |
| Pagamenti | Numero di pagamenti. |
| Evento n | Numero di volte in cui si è verificato l'evento n. I valori validi per n sono numeri interi 1 - 100.  Se specifichi un evento Visualizzazione, devi specificare anche la dimensione dei dati corrispondenti (eVar). Ad esempio, se includi visualizzazioni eVar2, devi elencare eVar2 con un valore. |
| Visualizzazioni eVarn | Numero di volte in cui è stata visualizzata l'eVar n. I valori validi per n sono numeri interi 1 - 75. |
| Prezzo | Prezzo del prodotto. |
| Ordini | Numero di ordini inseriti. |
| Visualizzazioni prodotto | Numero di visualizzazioni del prodotto. |
| Quantità | Numero di unità vendute. |
