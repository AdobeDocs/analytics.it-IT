---
title: Raccolta di dati regionali
seo-title: Raccolta dati regionali di Adobe Analytics
description: Informazioni sulla raccolta dati regionali
seo-description: Informazioni sulla raccolta dati regionali
translation-type: tm+mt
source-git-commit: 1fdd14497171dbf5850ec1b1d873a06931d58435

---


# Raccolta di dati regionali

Informazioni sulla raccolta di dati regionali (RDC) e su come modificare la rete della raccolta, se necessario.

Per migliorare le prestazioni della raccolta dati, tutti i clienti Adobe Experience Cloud sono stati convertiti in raccolta dati regionali (RDC), in modo che la raccolta si verifichi il più vicino possibile agli utenti finali. Questo migliora le prestazioni del sito/dell'app e assicura che i dati vengano raccolti il più rapidamente possibile per ottimizzare l'esperienza utente finale. Quando i dati delle proprietà digitali vengono raccolti localmente a un Centro di raccolta dati (DCC), vengono inoltrati attraverso una connessione protetta a un centro di elaborazione dati (DPC), dove vengono elaborati e resi disponibili ai prodotti in Adobe Experience Cloud. A partire da 2009, RDC è l'impostazione predefinita per le nuove implementazioni.

RDC include attualmente le seguenti posizioni (soggette a modifica):

## Raccolta dati di terze parti

| Tipo RDC | Centri raccolta dati |
|---------------------|-------------------|
| impostazione predefinita | San Jose, Virginia, Londra, Singapore, Hong Kong, Sydney, Amsterdam |
| Solo Cina | Pechino |

Note: If your Analytics image request is sent to the `2o7.net` or `omtdrc.net` endpoints, then you have third-party data collection. Potete determinare questa opzione se nell'URL delle richieste viene visualizzato un endpoint.

## Raccolta dati di prime parti

| Tipo RDC | Centri raccolta dati |
|---------------------|-------------------|
| Standard | San Jose, Virginia, London, Singapore |
| Tutte | Standard più Hong Kong, Sydney, Amsterdam |
| Solo USA | San Jose, Virginia |
| Solo UE | Londra, Amsterdam |
| Solo India | Mumbai |

## Funzionamento di RDC

L'elenco seguente descrive il processo di raccolta dati utilizzato da Adobe:

1. DNS risolve automaticamente il nome host della raccolta all'indirizzo IP di Data Collection Center più vicino al visitatore.
1. Il visitatore invia i dati a tale posizione.
1. I dati vengono immediatamente trasmessi attraverso una connessione protetta al Centro elaborazione dati, dove vengono elaborati e resi disponibili ai prodotti in Adobe Experience Cloud.

## Vantaggi dell'RDC

| Beneficio | Descrizione |
|---------|-----------|
| Prestazioni | Con RDC, i visitatori si connetteranno al DCC più vicino. Ciò significa che i tempi di risposta sulla pagina diminuiranno (con valori più bassi), per un tracciamento più preciso e tempi di caricamento più rapidi. Informazioni più dettagliate sui tempi di risposta sono disponibili in Miglioramenti in termini di prestazioni con RDC. |
| Ridondanza | Se si verifica un'interruzione nella comunicazione con un DCC, la raccolta dati viene automaticamente instradata al DCC più prossimo che garantisce la continuità del servizio. |
| Ridondanza | Se si verificano interruzioni nella comunicazione tra DCC e il DPC, l'infrastruttura RDC di Adobe salva i dati localmente, quindi lo trasmette al DPC quando le comunicazioni vengono ripristinate. |

## Cronologia revisioni documentazione

| Aggiornamento | Descrizione |
|--------|---------|
| 20 febbraio 2019 | Riscrittura completa. Sono state aggiunte informazioni sulla rete RDC. |
