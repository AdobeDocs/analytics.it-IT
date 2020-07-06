---
title: Supporto dei componenti nella Data warehouse
description: Scopri ulteriori dimensioni e metriche disponibili nella Data warehouse e quali non sono supportate.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 10%

---


# Supporto dei componenti nella Data warehouse

L&#39;architettura di elaborazione  Data warehouse consente ad alcuni componenti che in genere non sono disponibili in altre funzionalità di Adobe  Analytics. A causa della sua architettura univoca, alcuni componenti non sono disponibili per l&#39;uso nei report o nei segmenti. Utilizzare questa pagina per comprendere cosa può essere utilizzato e cosa non può essere utilizzato.

## Componenti unici per la Data warehouse

Alcune dimensioni e metriche possono essere utilizzate nella Data warehouse, mentre non sono disponibili utilizzando altre funzionalità in Adobe  Analytics.

### Dimensioni supportate esclusivamente

* ID Experience Cloud : Per le implementazioni che utilizzano il  Experience Cloud ID Service (ECID), un numero a 128 bit composto da due numeri concatenati a 64 bit aggiunti a 19 cifre.
* URL pagina: L’URL della pagina su cui si è verificato l’hit.
* ID acquisto: Identificatore univoco per un acquisto, impostato utilizzando la variabile purchaseID.
* ID visitatore: Fornisce l&#39;identificatore univoco del visitatore. Questo valore è lo stesso del valore concatenato di `visid_high` e delle `visid_low` colonne nei feed di dati. Per ulteriori informazioni, consulta Riferimento [alla colonna](../analytics-data-feed/c-df-contents/datafeeds-reference.md) Dati in Feed dati.

### Metriche supportate esclusivamente

* Visite: Questa metrica nel contesto dell&#39;Data warehouse esclude le visite di cookie non persistenti.
* Visite - Tutti i visitatori: Questa metrica nel contesto della Data warehouse ha una maggiore parità con la metrica visite in altri strumenti all’interno di Adobe  Analytics.

## Componenti non supportati nella Data warehouse

Alcune dimensioni e metriche non sono supportate nella Data warehouse.

>[!NOTE]
>
>Se una dimensione o una metrica non è supportata nella Data warehouse, i segmenti che utilizzano questi componenti non sono supportati. Controlla sempre la compatibilità dei prodotti durante la creazione o la modifica di un segmento.

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
   * Frequenza di ritorno
   * Tempo precedente all&#39;evento
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
   * Rimbalzi
   * Voci
   * Uscite
   * Ricariche
   * Accesso singolo
   * Metriche &#39;Time Spent&#39;
