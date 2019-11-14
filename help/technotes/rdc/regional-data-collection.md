---
title: Raccolta di dati regionali
description: Informazioni sulla raccolta dati regionali
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Raccolta di dati regionali

Informazioni sulla raccolta dati regionali (RDC) e su come modificare la rete di raccolta, se necessario.

Per migliorare le prestazioni di raccolta dei dati, tutti i clienti Adobe Experience Cloud sono stati convertiti in raccolte dati regionali (RDC) in modo che la raccolta si verifichi il più vicino possibile agli utenti finali. Questo migliora le prestazioni del sito e dell'app e garantisce che i dati vengano raccolti il più rapidamente possibile per ottimizzare l'esperienza dell'utente finale. Quando i dati delle tue proprietà digitali vengono raccolti a livello regionale in un centro di raccolta dati (DCC), vengono inoltrati tramite una connessione protetta a un centro di elaborazione dati (DPC), dove vengono elaborati e resi disponibili per i prodotti Adobe Experience Cloud. RDC è l’impostazione predefinita per le nuove implementazioni dal 2009.

RDC attualmente include le seguenti posizioni (soggette a modifica):

## Raccolta di dati di terze parti

| RDC Type | Centri di raccolta dati |
|---------------------|-------------------|
| impostazione predefinita | San Jose, Virginia, Londra, Singapore, Hong Kong, Sydney, Amsterdam |
| Solo Cina | Pechino |

Nota: Se la richiesta di immagine di Analytics viene inviata agli `2o7.net` o `omtdrc.net` agli endpoint, avrai a disposizione una raccolta dati di terze parti. Potete determinare questo valore se visualizzate uno degli endpoint nell'URL delle richieste.

## Raccolta dati di prime parti

| RDC Type | Centri di raccolta dati |
|---------------------|-------------------|
| Standard | San Jose, Virginia, Londra, Singapore |
| Tutte | Standard plus Hong Kong, Sydney, Amsterdam |
| Solo Stati Uniti | San Jose (Virginia) |
| Solo UE | Londra, Amsterdam |
| Solo India | Mumbai |

## Come funziona RDC

L'elenco seguente descrive il processo di raccolta dei dati utilizzato da Adobe:

1. Il DNS risolve automaticamente il nome host della raccolta all'indirizzo IP del centro di raccolta dati più vicino al visitatore.
1. Il visitatore invia i dati a tale posizione.
1. I dati vengono inoltrati immediatamente attraverso una connessione protetta al centro di elaborazione dati, dove vengono elaborati e resi disponibili per i prodotti Adobe Experience Cloud.

## Vantaggi dell'RDC

| Beneficio | Descrizione |
|---------|-----------|
| Prestazioni | Con RDC, i visitatori si connetteranno al DCC più vicino. Ciò significa che i tempi di risposta sulla pagina diminuiranno (meno è meglio), con conseguente tracciamento più preciso e tempi di caricamento più rapidi. Informazioni più dettagliate sui tempi di risposta sono disponibili in Miglioramenti delle prestazioni con RDC. |
| Ridondanza | In caso di interruzione delle comunicazioni con un DCC, la raccolta dei dati viene automaticamente indirizzata al DCC successivo più vicino, garantendo la continuità del servizio. |
| Ridondanza | In caso di interruzione delle comunicazioni tra il DCC e il DPC, l'infrastruttura RDC di Adobe consente di risparmiare i dati localmente, quindi di inoltrarli al DPC al ripristino delle comunicazioni. |

## Cronologia revisioni documentazione

| Aggiornamento | Descrizione |
|--------|---------|
| 20 febbraio 2019 | Riscrittura completa. Sono state aggiunte informazioni sulla rete RDC. |
