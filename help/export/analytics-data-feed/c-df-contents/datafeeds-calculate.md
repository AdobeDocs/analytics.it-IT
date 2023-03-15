---
description: Descrive come calcolare le metriche comuni utilizzando i feed di dati.
keywords: Feed dati;processo;metriche;colonna pre;colonna post;bot;filtro data;stringa evento;comune;formule
title: Calcolare metriche
feature: Data Feeds
exl-id: f9b0d637-7a6e-416a-adff-3c7e533bfac7
source-git-commit: ce71de7cdcde722fcfbc9ff04d22e5770c89e33d
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 3%

---

# Utilizzare i feed di dati per calcolare le metriche comuni

Descrive come calcolare le metriche comuni utilizzando i feed di dati.

>[!NOTE]
>
>Gli hit normalmente esclusi da Adobe Analytics sono inclusi nei feed di dati. Utilizzare `exclude_hit = 0` per rimuovere gli hit esclusi dalle query su dati non elaborati. I dati originati da origini dati sono inclusi anche nei feed di dati. Se desideri escludere le origini dati, escludi tutte le righe con `hit_source = 5,7,8,9`.

## Visualizzazioni pagina

1. Conteggio del numero di righe in cui si trova un valore `post_pagename` o `post_page_url`.

## Visite

1. Concatenare `post_visid_high`, `post_visid_low`, `visit_num`, e `visit_start_time_gmt`.
1. Conteggio del numero univoco di valori.

>[!NOTE]
>
>Irregolarità di Internet, irregolarità del sistema o uso di ID visitatore personalizzati raramente possono utilizzare lo stesso `visit_num` valori per visite diverse. Utilizzare `visit_start_time_gmt` quando si contano le visite per assicurarsi che queste visite siano conteggiate.

## Visitatori

Tutti i metodi utilizzati da Adobe per identificare visitatori univoci (ID visitatore personalizzato, servizio ID Experience Cloud, ecc.) sono tutti calcolati come valore in `post_visid_high` e `post_visid_low`. La concatenazione di queste due colonne può essere utilizzata come standard per identificare i visitatori univoci indipendentemente da come sono stati identificati come visitatori univoci. Se desideri capire quale Adobe di metodo utilizzato per identificare un visitatore univoco, utilizza la colonna `post_visid_type`.

1. Concatenare `post_visid_high` e `post_visid_low`.
2. Conteggio del numero univoco di valori.

## Collegamenti personalizzati, di download o di uscita

1. Conteggio del numero di righe in cui:
   * `post_page_event = 100` per collegamenti personalizzati
   * `post_page_event = 101` per i collegamenti di download
   * `post_page_event = 102` per i collegamenti di uscita

## Eventi personalizzati

Tutte le metriche sono conteggiate in `post_event_list` come numeri interi delimitati da virgole. Utilizzare `event.tsv` per far corrispondere i valori numerici con l’evento desiderato. Ad esempio: `post_event_list = 1,200` indica che l’hit contiene un evento di acquisto e un evento personalizzato 1.

1. Conteggio del numero di volte in cui il valore di ricerca evento viene visualizzato `post_event_list`.

## Tempo trascorso

Gli hit devono prima essere raggruppati per visita, quindi ordinati in base al numero di hit all’interno della visita.

1. Concatenare `post_visid_high`, `post_visid_low`, `visit_num`, e `visit_start_time_gmt`.
2. Ordina per questo valore concatenato, quindi applica un ordinamento secondario in base a `visit_page_num`.
3. Se un hit non è l’ultimo di una visita, sottrai il `post_cust_hit_time` valore dall’hit successivo `post_cust_hit_time` valore.
4. Questo numero è la quantità di tempo trascorso (in secondi) per l’hit. I filtri possono essere applicati per evidenziare elementi dimensionali o eventi.

## Ordini, unità e ricavi

Se un hit è `currency` il valore non corrisponde alla valuta di una suite di rapporti, viene convertito utilizzando il tasso di conversione di quel giorno. La colonna `post_product_list` utilizza il valore della valuta convertita, in modo che tutti gli hit utilizzino la stessa valuta in questa colonna.

1. Escludi tutte le righe in cui `duplicate_purchase = 1`.
2. Includi solo righe in cui `event_list` contiene l’evento di acquisto.
3. Analizzare `post_product_list` per estrarre tutti i dati relativi al prezzo. Il `post_product_list` è formattata come la `s.products` variabile.
4. Calcola la metrica desiderata:
   * Conteggio del numero di righe per il calcolo degli ordini
   * Somma il numero di `quantity` nella stringa di prodotto per calcolare le unità
   * Somma il numero di `price` nella stringa di prodotto per calcolare i ricavi
