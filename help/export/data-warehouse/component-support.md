---
title: Supporto dei componenti nella Data Warehouse
description: Scopri quali dimensioni e metriche aggiuntive sono disponibili in Data Warehouse e cosa non è supportato.
feature: Data Warehouse
exl-id: ce7411a4-a720-47b7-90d5-4d867eff4bae
source-git-commit: d929e97a9d9623a8255f16729177d812d59cec05
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 13%

---

# Supporto dei componenti in Data Warehouse

L’elaborazione univoca nell’architettura Data Warehouse consente di utilizzare alcuni componenti che in genere non sono disponibili in altre funzionalità di Adobe Analytics. A causa della sua architettura unica, alcuni componenti non sono disponibili per l’utilizzo nei rapporti o nei segmenti. Utilizza questa pagina per capire cosa può essere utilizzato e cosa no.

## Componenti specifici di Data Warehouse

Alcune dimensioni e metriche utilizzabili in Data Warehouse non sono disponibili quando si utilizzano altre funzionalità in Adobe Analytics.

### Dimension supportati esclusivamente

* **ID Experience Cloud**: per le implementazioni che utilizzano il servizio ID Experience Cloud (ECID), un numero a 128 bit costituito da due numeri concatenati a 64 bit aggiunti a 19 cifre.
* **URL pagina**: URL della pagina in cui si è verificato l&#39;hit.
* **ID acquisto**: identificatore univoco per un acquisto, impostato utilizzando la variabile purchaseID.
* **ID visitatore**: fornisce l&#39;identificatore univoco del visitatore. Questo valore è uguale al valore concatenato di `visid_high` e `visid_low` colonne nei feed di dati. Per ulteriori informazioni, vedere [Riferimento colonna dati](../analytics-data-feed/c-df-contents/datafeeds-reference.md) in Feed dati.

### Metriche supportate in modo esclusivo

* **Visite**: questa metrica nel contesto di Data Warehouse esclude le visite dei cookie non persistenti.
* **Visite - Tutti i visitatori**: questa metrica nel contesto della Data Warehouse è più simile alla metrica Visite in altri strumenti di Adobe Analytics.

## Componenti non supportati in Data Warehouse

Alcune dimensioni e metriche non sono supportate in Data Warehouse.

>[!NOTE]
>
>Se una dimensione o una metrica non è supportata in Data Warehouse, non sono supportati neanche i segmenti che utilizzano questi componenti. Verifica sempre la compatibilità del prodotto durante la creazione o la modifica di un segmento.

### Dimension non supportati

* AM/PM
* Alcune dimensioni basate su percorsi, tra cui:
   * Tutte le dimensioni di entrata, ad eccezione della pagina di entrata
   * Tutte le dimensioni di uscita, tranne Pagina di uscita e Collegamento di uscita
   * Profondità di hit
   * Frequenza di ritorno
   * Tempo precedente all’evento
   * Tempo trascorso sulla pagina - Bucket
   * Tempo trascorso per ciascuna visita - Bucket
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
* Metriche di partecipazione (come descritto in [Creare una metrica di partecipazione](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/participation-metric.md))

### Dimension supportati in modo diverso

Sono supportate le seguenti dimensioni basate sul tempo. Tuttavia, l’output delle date non è standard quando si utilizzano queste dimensioni. In particolare, l&#39;anno viene compensato dal 1900 e i mesi sono a base zero.

* Anno
* Trimestre
* Mese
* Settimana
* Giorno
* Ora
* Minuto

## Segmenti come dimensioni nella Data Warehouse

Quando utilizzi un segmento come dimensione in Data Warehouse, il rapporto restituisce una colonna contenente `"0"` o `"1"`:

* **`"0"`**: l&#39;elemento dimensione non soddisfa i criteri del segmento.
* **`"1"`**: l&#39;elemento dimensione ha soddisfatto i criteri del segmento.
