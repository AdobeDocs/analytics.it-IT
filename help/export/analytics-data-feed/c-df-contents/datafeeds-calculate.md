---
description: Descrive come calcolare metriche comuni utilizzando i feed di dati.
keywords: Data Feed;job;metrics;pre column;post column;bots;date filtering;event string;common;formulas
title: Calcolare metriche
topic: Reports and analytics
uuid: a45ea5bb-7c83-468f-b94a-63add78931d7
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 1%

---


# Utilizzare i feed di dati per calcolare le metriche comuni

Descrive come calcolare metriche comuni utilizzando i feed di dati.

>[!IMPORTANT]
>
>Gli hit normalmente esclusi da Adobe  Analytics sono inclusi nei feed di dati. Utilizzare `exclude_hit > 0` per rimuovere gli hit esclusi dalle query sui dati non elaborati. I dati di origine dati sono inclusi anche nei feed di dati. Se si desidera escludere le origini dati, escludere tutte le righe con `hit_source = 5,7,8,9`.

## Visualizzazioni pagina

1. Conteggia il numero di righe in cui il valore è compreso `post_pagename` o `post_page_url`.

## Visite

1. Concatenate `post_visid_high`, `post_visid_low`, `visit_num`e `visit_start_time_gmt`.
1. Conta il numero univoco di valori.

>[!NOTE]
>
>Le irregolarità di Internet, le irregolarità del sistema o l’uso di ID visitatore personalizzati possono raramente utilizzare gli stessi `visit_num` valori per visite diverse. Utilizzate `visit_start_time_gmt` quando contate le visite per essere certi che tali visite siano conteggiate.

## Visitatori

Tutti i metodi utilizzati da Adobe per identificare i visitatori univoci (ID visitatore personalizzato,  servizio ID Experience Cloud, ecc.) sono tutti calcolati come valore in `post_visid_high` e `post_visid_low`. La concatenazione di queste due colonne può essere utilizzata come standard per identificare i visitatori univoci, indipendentemente da come siano stati identificati come visitatori univoci. Per capire quale metodo Adobe ha utilizzato per identificare un visitatore univoco, usa la colonna `post_visid_type`.

1. Concatenate `post_visid_high` e `post_visid_low`.
2. Conta il numero univoco di valori.

## Collegamenti personalizzati, di download o di uscita

1. Conteggia il numero di righe in cui:
   * `post_page_event = 100` per collegamenti personalizzati
   * `post_page_event = 101` per i collegamenti di download
   * `post_page_event = 102` per i collegamenti di uscita

## Eventi personalizzati

Tutte le metriche vengono conteggiate nella `post_event_list` colonna come numeri interi delimitati da virgole. Utilizzare `event.tsv` per far corrispondere i valori numerici all&#39;evento desiderato. Ad esempio, `post_event_list = 1,200` indica che l&#39;hit conteneva un evento di acquisto e un evento personalizzato 1.

1. Conta il numero di volte in cui viene visualizzato il valore di ricerca dell’evento `post_event_list`.

## Tempo trascorso

Gli hit devono essere raggruppati per visita, quindi ordinati in base al numero di hit all’interno della visita.

1. Concatenate `post_visid_high`, `post_visid_low`, `visit_num`e `visit_start_time_gmt`.
2. Ordinare per questo valore concatenato, quindi applicare un ordinamento secondario per `visit_page_num`.
3. Se un hit non è l&#39;ultimo di una visita, sottrae il `post_cust_hit_time` valore dall&#39;hit successivo `post_cust_hit_time` .
4. Questo numero è la quantità di tempo (in secondi) trascorso per l’hit. I filtri possono essere applicati per evidenziare i valori o gli eventi delle dimensioni.

## Ordini, unità e ricavi

Se il `currency` valore di un hit non corrisponde alla valuta di una suite di rapporti, viene convertito utilizzando il tasso di conversione di quel giorno. La colonna `post_product_list` utilizza il valore della valuta convertita, pertanto tutti gli hit usano la stessa valuta in questa colonna.

1. Escludere tutte le righe in cui `duplicate_purchase = 1`.
2. Include solo le righe in cui `event_list` contiene l&#39;evento di acquisto.
3. Analizzare la `post_product_list` colonna per estrarre tutti i dati di prezzo. La `post_product_list` colonna è formattata come la `s.products` variabile.
4. Calcola la metrica desiderata:
   * Conteggio del numero di righe per il calcolo degli ordini
   * Somma il numero di unità `quantity` nella stringa di prodotto da calcolare
   * Somma il numero di `price` nella stringa di prodotto per calcolare le entrate
