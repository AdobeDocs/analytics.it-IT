---
title: Supporto dei componenti in Data Warehouse
description: Scopri ulteriori dimensioni e metriche disponibili in Data Warehouse e quali non sono supportate.
translation-type: tm+mt
source-git-commit: 00d4d59cb4c922b54a97ef7000e294ef3bf61f20

---


# Supporto dei componenti in Data Warehouse

L'esclusiva architettura di elaborazione di Data Warehouse consente ad alcuni componenti che in genere non sono disponibili in altre funzionalità di Adobe Analytics. A causa della sua architettura univoca, alcuni componenti non sono disponibili per l'uso nei report o nei segmenti. Utilizzare questa pagina per comprendere cosa può essere utilizzato e cosa non può.

## Componenti unici di Data Warehouse

Alcune dimensioni e metriche possono essere utilizzate in Data Warehouse, mentre non sono disponibili utilizzando altre funzionalità in Adobe Analytics.

### Dimensioni supportate esclusivamente

* Experience Cloud ID: Per le implementazioni che utilizzano il servizio Experience Cloud ID (ECID), un numero a 128 bit composto da due numeri concatenati a 64 bit aggiunti a 19 cifre.
* URL pagina: L’URL della pagina su cui si è verificato l’hit.
* ID acquisto: Identificatore univoco per un acquisto, impostato utilizzando la variabile purchaseID.
* ID visitatore: Fornisce l'identificatore univoco del visitatore. Questo valore è lo stesso del valore concatenato di `visid_high` e delle `visid_low` colonne nei feed di dati. Per ulteriori informazioni, consulta Riferimento [alla colonna](../analytics-data-feed/c-df-contents/datafeeds-reference.md) Dati in Feed dati.

### Metriche supportate esclusivamente

* Visite: Questa metrica nel contesto di Data Warehouse esclude le visite di cookie non persistenti.
* Visite - Tutti i visitatori: Questa metrica nel contesto di Data Warehouse presenta una maggiore parità con la metrica visite in altri strumenti di Adobe Analytics.

## Componenti non supportati in Data Warehouse

Alcune dimensioni e metriche non sono supportate in Data Warehouse.

> [!NOTE] Se una dimensione o una metrica non è supportata in Data Warehouse, i segmenti che utilizzano questi componenti non sono supportati. Controlla sempre la compatibilità dei prodotti durante la creazione o la modifica di un segmento.

### Dimensioni non supportate

* Alcune dimensioni temporizzate, tra cui:
   * AM/PM
   * Giorno del mese
   * Giorno della settimana
   * Giorno dell’anno
   * Ora del giorno
   * Minuto
   * Mese dell’anno
   * Trimestre dell’anno
   * Giorno feriale/Fine settimana
   * Anno
* Alcune dimensioni basate su percorsi, tra cui:
   * Tutte le dimensioni di immissione, tranne Pagina di entrata
   * Tutte le dimensioni di uscita, eccetto Pagina di uscita e Collegamento di uscita
   * Profondità di hit
   * Restituisci frequenza
   * Tempo precedente all'evento
   * Tempo trascorso sulla pagina - Interrotto
   * Tempo trascorso per visita - A intervalli
   * Profondità visita
* Seleziona tutte le pagine di ricerca
* Variabili di gerarchia
* Tipo di occorrenza
* Pagine non trovate (disponibili come dimensione); non supportato per la segmentazione)
* Ricerca pagata
* Visite a pagina singola
* Motivo rifiuto tracciamento
* Stati Uniti

### Metriche non supportate

* Alcune metriche basate sui percorsi, tra cui:
   * Bounce
   * Voci
   * Uscite
   * Ricariche
   * Accesso singolo
   * Metriche 'Time Spent'
