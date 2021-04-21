---
description: Descrive come calcolare le metriche comuni utilizzando i feed di dati.
keywords: Feed dati;processo;metriche;pre colonna;post colonna;bot;filtro data;stringa evento;comune;formule
title: Calcolare metriche
feature: Nozioni di base su Reports & Analytics
uuid: a45ea5bb-7c83-468f-b94a-63add78931d7
exl-id: f9b0d637-7a6e-416a-adff-3c7e533bfac7
translation-type: tm+mt
source-git-commit: cddf2a76ca36914f133379959b7cbb5246bdd695
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 1%

---

# Utilizzare i feed di dati per calcolare le metriche comuni

Descrive come calcolare le metriche comuni utilizzando i feed di dati.

>[!IMPORTANT]
>
>Gli hit normalmente esclusi da Adobe Analytics sono inclusi nei feed di dati. Utilizza `exclude_hit > 0` per rimuovere gli hit esclusi dalle query sui dati non elaborati. I dati originati sono inclusi anche nei feed di dati. Se desideri escludere origini dati, escludi tutte le righe con `hit_source = 5,7,8,9`.

## Visualizzazioni pagina

1. Conta il numero di righe in cui un valore è espresso in `post_pagename` o `post_page_url`.

## Visite

1. Concatenare `post_visid_high`, `post_visid_low`, `visit_num` e `visit_start_time_gmt`.
1. Conta il numero univoco di valori.

>[!NOTE]
>
>Le irregolarità di Internet, le irregolarità del sistema o l’utilizzo di ID visitatore personalizzati possono raramente utilizzare gli stessi valori `visit_num` per visite diverse. Utilizza `visit_start_time_gmt` durante il conteggio delle visite per assicurarti che queste visite siano conteggiate.

## Visitatori

Tutti i metodi utilizzati dall&#39;Adobe per identificare i visitatori univoci (ID visitatore personalizzato, servizio ID Experience Cloud, ecc.) sono tutti calcolati come valore in `post_visid_high` e `post_visid_low`. La concatenazione di queste due colonne può essere utilizzata come standard per identificare i visitatori unici, indipendentemente da come sono stati identificati come visitatori unici. Per capire quale Adobe di metodo utilizzato per identificare un visitatore univoco, utilizza la colonna `post_visid_type`.

1. Concatenare `post_visid_high` e `post_visid_low`.
2. Conta il numero univoco di valori.

## Collegamenti personalizzati, di download o di uscita

1. Conta il numero di righe in cui:
   * `post_page_event = 100` per collegamenti personalizzati
   * `post_page_event = 101` per i collegamenti di download
   * `post_page_event = 102` per i collegamenti di uscita

## Eventi personalizzati

Tutte le metriche vengono conteggiate nella colonna `post_event_list` come numeri interi delimitati da virgole. Utilizza `event.tsv` per far corrispondere i valori numerici con l’evento desiderato. Ad esempio, `post_event_list = 1,200` indica che l’hit conteneva un evento di acquisto e un evento personalizzato 1.

1. Conta il numero di volte in cui il valore di ricerca dell’evento viene visualizzato in `post_event_list`.

## Tempo trascorso

Gli hit devono prima essere raggruppati per visita, quindi ordinati in base al numero di hit all’interno della visita.

1. Concatenare `post_visid_high`, `post_visid_low`, `visit_num` e `visit_start_time_gmt`.
2. Ordina per questo valore concatenato, quindi applica un ordinamento secondario per `visit_page_num`.
3. Se un hit non è l&#39;ultimo di una visita, sottrae il valore `post_cust_hit_time` dal valore `post_cust_hit_time` dell&#39;hit successivo.
4. Questo numero è la quantità di tempo (in secondi) trascorso per l’hit. I filtri possono essere applicati per concentrarsi su elementi o eventi dimensionali.

## Ordini, unità e ricavi

Se il valore `currency` di un hit non corrisponde alla valuta di una suite di rapporti, viene convertito utilizzando il tasso di conversione di quel giorno. La colonna `post_product_list` utilizza il valore della valuta convertita, pertanto tutti gli hit usano la stessa valuta in questa colonna.

1. Escludi tutte le righe in cui `duplicate_purchase = 1`.
2. Includi solo le righe in cui `event_list` contiene l’evento di acquisto.
3. Analizzare la colonna `post_product_list` per estrarre tutti i dati sul prezzo. La colonna `post_product_list` viene formattata come la variabile `s.products`.
4. Calcola la metrica desiderata:
   * Conteggio del numero di righe per calcolare gli ordini
   * Somma il numero di `quantity` nella stringa di prodotto per calcolare le unità
   * Somma il numero di `price` nella stringa di prodotto per calcolare i ricavi
