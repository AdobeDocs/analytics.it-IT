---
title: Supporto dei componenti in Data Warehouse
description: Scopri quali dimensioni e metriche aggiuntive sono disponibili in Data Warehouse e cosa non è supportato.
feature: Data Warehouse
exl-id: ce7411a4-a720-47b7-90d5-4d867eff4bae
source-git-commit: 3af2cca02675e424b3f704a95d46de92886a88d8
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 17%

---

# Supporto dei componenti in Data Warehouse

L’elaborazione univoca nell’architettura Data Warehouse consente di utilizzare alcuni componenti che in genere non sono disponibili in altre funzionalità di Adobe Analytics. A causa della sua architettura unica, alcuni componenti non sono disponibili per l’utilizzo nei rapporti o nei segmenti. Utilizza questa pagina per capire cosa può essere utilizzato e cosa no.

## Componenti specifici di Data Warehouse

Alcune dimensioni e metriche utilizzabili in Data Warehouse non sono disponibili quando si utilizzano altre funzionalità in Adobe Analytics.

### Dimension supportati esclusivamente

* **ID EXPERIENCE CLOUD**: per le implementazioni che utilizzano il servizio ID Experience Cloud (ECID), un numero a 128 bit costituito da due numeri concatenati a 64 bit aggiunti a 19 cifre.
* **URL della pagina**: URL della pagina in cui si è verificato l’hit.
* **ID acquisto**: identificatore univoco di un acquisto, impostato utilizzando la variabile purchaseID.
* **ID visitatore**: fornisce l’identificatore univoco del visitatore. Questo valore è uguale al valore concatenato di `visid_high` e `visid_low` colonne nei feed di dati. Consulta [Riferimento colonna dati](../analytics-data-feed/c-df-contents/datafeeds-reference.md) in Feed dati per ulteriori informazioni.

### Metriche supportate in modo esclusivo

* **Visite**: questa metrica nel contesto di Data Warehouse esclude le visite dei cookie non persistenti.
* **Visite - Tutti i visitatori**: questa metrica nel contesto della Data Warehouse è più simile alla metrica Visite in altri strumenti di Adobe Analytics.

## Componenti non supportati in Data Warehouse

Alcune dimensioni e metriche non sono supportate in Data Warehouse.

>[!NOTE]
>
>Se una dimensione o una metrica non è supportata in Data Warehouse, non sono supportati neanche i segmenti che utilizzano questi componenti. Verifica sempre la compatibilità del prodotto durante la creazione o la modifica di un segmento.

### Dimension non supportati

* Alcune dimensioni basate sul tempo, tra cui:
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
   * Tutte le dimensioni di entrata, ad eccezione della pagina di entrata
   * Tutte le dimensioni di uscita, tranne Pagina di uscita e Collegamento di uscita
   * Profondità di hit
   * Frequenza di ritorno
   * Tempo precedente all’evento
   * Tempo trascorso sulla pagina - Bucket
   * Tempo trascorso per ciascuna visita - Bucket
   * Profondità della visita
* Classificazione di tutte le pagine di ricerca
* Variabili di gerarchia
* Tipo di hit
* Pagine non trovate (disponibili come dimensioni; non supportate per la segmentazione)
* Ricerca a pagamento
* Visite a pagina singola
* Tracking del motivo di rinuncia
* Stati degli Stati Uniti

### Metriche non supportate

* Alcune metriche basate sui percorsi, tra cui:
   * Messaggi non recapitati
   * Voci
   * Uscite
   * Ricariche
   * Accesso singolo
   * Metriche &quot;Tempo trascorso&quot;
