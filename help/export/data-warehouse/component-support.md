---
title: Supporto dei componenti in Data Warehouse
description: Scopri quali dimensioni e metriche aggiuntive sono disponibili in Data Warehouse e quali non sono supportate.
feature: Data Warehouse
exl-id: ce7411a4-a720-47b7-90d5-4d867eff4bae
source-git-commit: 527a9d5cdcb1ceb32073e2d444b892c0183394c1
workflow-type: tm+mt
source-wordcount: '570'
ht-degree: 8%

---

# Supporto dei componenti in Data Warehouse

L&#39;elaborazione unica nell&#39;architettura di Data Warehouse consente alcuni componenti che in genere non sono disponibili in altre funzionalità di Adobe Analytics. A causa della sua architettura unica, alcuni componenti non sono disponibili per l&#39;uso in report o segmenti. Utilizza questa pagina per capire cosa può essere utilizzato e cosa no.

## Componenti esclusivi di Data Warehouse

Alcune dimensioni e metriche che possono essere utilizzate in Data Warehouse non sono disponibili quando si utilizzano altre funzionalità in Adobe Analytics.

### Dimensioni supportate esclusivamente

* **Experience Cloud ID**: per le implementazioni che utilizzano il servizio Experience Cloud ID (ECID), un numero a 128 bit costituito da due numeri concatenati a 64 bit aggiunti a 19 cifre.
* **Pagina URL**: la pagina in URL si è verificato l&#39;hit.
* **ID acquisto**: identificatore univoco per un acquisto, impostato utilizzando la variabile purchaseID.
* **ID visitatore**: fornisce l&#39;identificatore univoco del visitatore. Questo valore è uguale al valore concatenato di `visid_high` e `visid_low` colonne nei feed di dati. Per ulteriori informazioni, vedere [Riferimento colonna dati](../analytics-data-feed/c-df-contents/datafeeds-reference.md) in Feed dati.

### Metriche supportate in modo esclusivo

* **Visite**: questa metrica nel contesto di Data Warehouse esclude le visite dei cookie non persistenti.
* **Visite - Tutti i visitatori**: questa metrica nel contesto di Data Warehouse è più simile alla metrica Visite in altri strumenti di Adobe Analytics.

## Componenti non supportati in Data Warehouse

Alcune dimensioni e metriche non sono supportate in Data Warehouse.

>[!NOTE]
>
>Se una dimensione o una metrica non è supportata in Data Warehouse, non sono supportati neanche i segmenti che utilizzano questi componenti. Verifica sempre la compatibilità del prodotto durante la creazione o la modifica di un segmento.

### Dimensioni non supportate

* AM/PM
* Alcune dimensioni basate su percorsi, tra cui:
   * Tutte le dimensioni di ingresso, ad eccezione di Pagina
   * Tutte le Esci dimensioni, ad eccezione Esci Pagina e Esci collegamento
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
* Metriche di partecipazione (come descritto in [Creare una metrica](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/participation-metric.md) di &quot;partecipazione&quot;)

### Dimensioni supportate in modo diverso (formattazione della data non standard)

Sono supportate le seguenti dimensioni basate sul tempo:

* Anno
* Trimestre
* Mese
* Settimana
* Giorno
* Ora
* Minuto

Tuttavia, l’output delle date non è standard quando si utilizzano queste dimensioni.

Nel calcolare l’output delle date in Data Warehouse, considera quanto segue:

* Le dimensioni data sono visualizzate nel seguente formato: `1YYMMDDHHMM`

* L&#39;anno (YY) viene compensato dal 1900. Ciò significa che si aggiungono `1900` ai primi 3 valori del campo data.

  Ad esempio, se il valore del campo Intervallo di date Settimana in Data Warehouse è `1250901`, aggiungere 1900 a 125, con conseguente risultato nell&#39;anno 2025.

* Tutti i mesi sono a base zero: gennaio è rappresentato da 00, febbraio da 01 e così via, come indicato di seguito:

   * 00: Gennaio
   * 01: Febbraio
   * 02 marzo
   * 03: Aprile
   * 04: Maggio
   * 05: Giugno
   * 06: Luglio
   * 07: Agosto
   * 08: Settembre
   * 09 ottobre
   * 10 novembre
   * 11 dicembre

  Se ad esempio il valore del campo Settimana intervallo di date in Data Warehouse è `1250901`, il mese verrà rappresentato come 09, che indica ottobre.




## Segmenti come dimensioni in Data Warehouse

Quando utilizzi un segmento come dimensione in Data Warehouse, il rapporto restituisce una colonna contenente `"0"` o `"1"`:

* **`"0"`**: l&#39;elemento dimensione non soddisfa i criteri del segmento.
* **`"1"`**: l&#39;elemento dimensione ha soddisfatto i criteri del segmento.
