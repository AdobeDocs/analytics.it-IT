---
title: Supporto dei componenti in Data Warehouse
description: Scopri ulteriori dimensioni e metriche disponibili in Data Warehouse e cosa non sono supportate.
translation-type: tm+mt
source-git-commit: 8f3f11ada9bd12498dc40931cc987aa550b8d655

---


# Supporto dei componenti in Data Warehouse

L'architettura di elaborazione univoca di Data Warehouse consente alcuni componenti che in genere non sono disponibili in altre funzionalità di Adobe Analytics. A causa della sua architettura univoca, alcuni componenti non sono disponibili per l'uso nei report o nei segmenti. Utilizza questa pagina per capire cosa può essere utilizzato e cosa no.

## Componenti univoci per Data Warehouse

In Data Warehouse sono disponibili dimensioni e metriche, che non sono disponibili utilizzando altre funzionalità in Adobe Analytics.

### Dimensioni supportate esclusivamente

* ID visitatore Experience Cloud: Per le implementazioni che utilizzano il servizio Experience Cloud ID (ECID), un numero a 128 bit composto di due numeri di 64 bit concatenati a 19 cifre.
* URL pagina: L'URL della pagina in cui si è verificato l'hit.
* ID acquisto: Identificatore univoco per un acquisto, impostato utilizzando la variabile ordaseid.
* ID visitatore: Fornisce l'identificatore univoco del visitatore. Questo valore corrisponde al valore concatenato delle `visid_high``visid_low` colonne nei feed di dati. Consulta [Riferimento alla colonna Dati](../analytics-data-feed/c-df-contents/datafeeds-reference.md) in Feed dati per ulteriori informazioni.

### Metriche supportate esclusivamente

* Visite: Questa metrica nel contesto di Data Warehouse esclude le visite dei cookie non persistenti.
* Visite - Tutti i visitatori: Questa metrica nel contesto di Data Warehouse è simile alla metrica Visite in altri strumenti di Adobe Analytics.

## Componenti non supportati in Data Warehouse

Alcune dimensioni e metriche non sono supportate in Data Warehouse.

> [!NOTE] Se una dimensione o una metrica non è supportata in Data Warehouse, i segmenti che utilizzano tali componenti non sono supportati. Verificate sempre la compatibilità del prodotto quando create o modificate un segmento.

### Dimensioni non supportate

* Alcune dimensioni basate sul tempo, tra cui:
   * AM/PM
   * Giorno del mese
   * Giorno della settimana
   * Giorno dell’anno
   * Ora del giorno
   * Minuto
   * Mese dell’anno
   * Trimestre dell’anno
   * Settimana/fine settimana
   * Anno
* Alcune dimensioni basate su percorsi, tra cui:
   * Tutte le dimensioni di voce, tranne la pagina di immissione
   * Tutte le dimensioni di uscita, tranne Uscita pagina e Collegamento uscita
   * Profondità hit
   * Restituisci frequenza
   * Tempo precedente all'evento
   * Tempo trascorso sulla pagina - Piegato
   * Tempo trascorso per visita - Perforato
   * Profondità visita
* Tutte le classificazioni di ricerca
* Variabili di gerarchia
* Tipo di occorrenza
* Pagine non trovate (disponibili come dimensioni; non supportato per la segmentazione)
* Ricerca pagata
* Visite a pagina singola
* Motivo di rifiuto del tracciamento
* Stati Uniti

### Metriche non supportate

* Alcune metriche basate sui percorsi, tra cui:
   * Bounce
   * Voci
   * Uscite
   * Ricariche
   * Accesso singolo
   * Metriche Tempo trascorso
