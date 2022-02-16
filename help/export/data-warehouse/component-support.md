---
title: Supporto dei componenti nella Data Warehouse
description: Scopri quali dimensioni e metriche aggiuntive sono disponibili in Data Warehouse e cosa non è supportato.
feature: Data Warehouse
exl-id: ce7411a4-a720-47b7-90d5-4d867eff4bae
source-git-commit: 4daa5c8bdbcb483f23a3b8f75dde9eeb48516db8
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 17%

---

# Supporto dei componenti nella Data Warehouse

L’architettura di elaborazione unica di Data Warehouse consente ad alcuni componenti che in genere non sono disponibili in altre funzionalità di Adobe Analytics. A causa della sua architettura univoca, alcuni componenti non sono disponibili per l’utilizzo in report o segmenti. Utilizza questa pagina per capire cosa può essere utilizzato e cosa non può.

## Componenti unici della Data Warehouse

Alcune dimensioni e metriche possono essere utilizzate nella Data Warehouse, mentre non sono disponibili utilizzando altre funzionalità in Adobe Analytics.

### Dimension supportati esclusivamente

* ID Experience Cloud: Per le implementazioni che utilizzano il servizio Experience Cloud ID (ECID), è disponibile un numero a 128 bit composto da due numeri concatenati a 64 bit aggiunti a 19 cifre.
* URL della pagina: L&#39;URL della pagina su cui si è verificato l&#39;hit.
* ID acquisto: Identificatore univoco per un acquisto, impostato utilizzando la variabile purchaseID.
* ID visitatore: Fornisce l&#39;identificatore univoco per il visitatore. Questo valore è lo stesso del valore concatenato di `visid_high` e `visid_low` nei feed di dati. Vedi [Riferimento colonna dati](../analytics-data-feed/c-df-contents/datafeeds-reference.md) in Feed dati per ulteriori informazioni.

### Metriche supportate esclusivamente

* Visite: Questa metrica nel contesto della Data Warehouse esclude le visite non persistenti dei cookie.
* Visite - Tutti i visitatori: Questa metrica nel contesto della Data Warehouse ha una parità più stretta con la metrica delle visite in altri strumenti all’interno di Adobe Analytics.

## Componenti non supportati nella Data Warehouse

Alcune dimensioni e metriche non sono supportate in Data Warehouse.

>[!NOTE]
>
>Se una dimensione o una metrica non è supportata nella Data Warehouse, non sono supportati nemmeno i segmenti che utilizzano questi componenti. Verifica sempre la compatibilità del prodotto durante la creazione o la modifica di un segmento.

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
   * Tutte le dimensioni di immissione, eccetto Pagina di ingresso
   * Tutte le dimensioni di uscita, eccetto Pagina di uscita e Collegamento di uscita
   * Profondità di hit
   * Frequenza di ritorno
   * Tempo precedente all’evento
   * Tempo trascorso sulla pagina - Bucket
   * Tempo trascorso per ciascuna visita - Bucket
   * Profondità della visita
* Classificazione di tutte le pagine di ricerca
* Variabili di gerarchia
* Tipo di hit
* Pagine non trovate (disponibili come dimensione); non supportato per la segmentazione)
* Ricerca a pagamento
* Visite a pagina singola
* Tracking del motivo di rinuncia
* Stati degli Stati Uniti

### Metriche non supportate

* Alcune metriche basate su percorsi, tra cui:
   * Rimbalzi
   * Voci
   * Uscite
   * Ricariche
   * Accesso singolo
   * Metriche &quot;Time Spent&quot;
