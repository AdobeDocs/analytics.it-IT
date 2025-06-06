---
description: Descrive come calcolare le metriche comuni utilizzando i feed di dati.
keywords: Feed di dati; processo; metriche; pre-colonna; post-colonna; bot; filtro data; stringa evento; comune; formule
title: Calcolare metriche
feature: Data Feeds
exl-id: f9b0d637-7a6e-416a-adff-3c7e533bfac7
source-git-commit: adee2f1013cfd2ae231e3133b5a5327b8792bd16
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 76%

---

# Utilizzare i feed di dati per calcolare le metriche comuni

Descrive come calcolare le metriche comuni utilizzando i feed di dati.

>[!NOTE]
>
>Gli hit normalmente esclusi da Analysis Workspace sono inclusi nei feed di dati. Considera l’aggiunta delle seguenti condizioni alle query, se pertinenti:
>
>* **`exclude_hit`**: Analysis Workspace include solo dati in cui `exclude_hit = 0`.
>* **`customer_perspective`**: Analysis Workspace include solo dati in cui `customer_perspective = 0`, a meno che non si utilizzi una suite di rapporti virtuale che include hit in background per dispositivi mobili.
>* **`hit_source`**: i dati provenienti da origini dati potrebbero contenere differenze tra i dati non elaborati e Analysis Workspace. Se desideri escludere gli hit dalle origini dati, escludi tutte le righe in cui `hit_source = 5,7,8,9`.

## Visualizzazioni pagina

1. Conteggio del numero di righe in cui si trova un valore `post_pagename` o `post_page_url`.

## Occorrenze

1. Conteggio del numero totale di righe.

## Visite

1. Concatena `post_visid_high`, `post_visid_low`, `visit_num`, e `visit_start_time_gmt`.
1. Conteggio del numero univoco di valori.

>[!TIP]
>
>Le irregolarità di Internet, quelle del sistema o l’utilizzo di ID visitatore personalizzati possono utilizzare raramente gli stessi valori `visit_num` per visite diverse. Anche se facoltativo, utilizza `visit_start_time_gmt` durante il conteggio delle visite per assicurarti che queste visite siano conteggiate.

## Visitatori

Tutti i metodi utilizzati da Adobe per identificare visitatori univoci (ID visitatore personalizzato, servizio Experience Cloud ID, ecc.) vengono tutti calcolati come valore in `post_visid_high` e `post_visid_low`. La concatenazione di queste due colonne può essere utilizzata come standard per identificare i visitatori univoci indipendentemente da come sono stati identificati come visitatori univoci. Se desideri comprendere quale metodo utilizza Adobe per identificare un visitatore univoco, utilizza la colonna `post_visid_type`.

1. Concatena `post_visid_high` e `post_visid_low`.
2. Conteggio del numero univoco di valori.

## Collegamenti personalizzati, di download o di uscita

1. Conteggio del numero di righe in cui:
   * `post_page_event = 100` per i collegamenti personalizzati
   * `post_page_event = 101` per i collegamenti di download
   * `post_page_event = 102` per i collegamenti di uscita

## Eventi personalizzati

Tutte le metriche sono conteggiate nella colonna `post_event_list` come numeri interi delimitati da virgole. Utilizza `event.tsv` per far corrispondere i valori numerici con l’evento desiderato. Ad esempio: `post_event_list = 1,200` indica che l’hit contiene un evento di acquisto e un evento personalizzato 1.

1. Conteggio del numero di volte in cui il valore di ricerca dell’evento viene visualizzato in `post_event_list`.

## Tempo trascorso

Gli hit devono prima essere raggruppati per visita, quindi ordinati in base al numero di hit all’interno della visita.

1. Concatena `post_visid_high`, `post_visid_low`, `visit_num`, e `visit_start_time_gmt`.
2. Ordina per questo valore concatenato, quindi applica un ordinamento secondario per `visit_page_num`.
3. Se un hit non è l’ultimo di una visita, sottrai il valore `post_cust_hit_time` dal valore `post_cust_hit_time` dell’hit successivo.
4. Questo numero è la quantità di tempo trascorso (in secondi) per l’hit. I filtri possono essere applicati per evidenziare elementi dimensionali o eventi.

## Ordini, unità ed entrate

Se il valore `currency` di un hit non corrisponde alla valuta di una suite di rapporti, viene convertito utilizzando il tasso di conversione di quel giorno. La colonna `post_product_list` utilizza il valore della valuta convertita, in modo che tutti gli hit utilizzino la stessa valuta in questa colonna.

1. Escludi tutte le righe in cui `duplicate_purchase = 1`.
2. Includi solo righe in cui `event_list` contiene l’evento di acquisto.
3. Analizza la colonna `post_product_list` per estrarre tutti i dati relativi al prezzo. La colonna `post_product_list` è formattata come la variabile `s.products`.
4. Calcola la metrica desiderata:
   * Conteggio del numero di righe per il calcolo degli ordini
   * Somma il numero di `quantity` nella stringa di prodotto per calcolare le unità
   * Somma il numero di `price` nella stringa di prodotto per calcolare le entrate
