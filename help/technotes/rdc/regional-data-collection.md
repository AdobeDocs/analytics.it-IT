---
title: Raccolta di dati regionali
description: Informazioni sulla raccolta dati regionali
translation-type: tm+mt
source-git-commit: 449a64e361523d7a68514d60541c443a4f696c9d

---


# Raccolta di dati regionali

Adobe Experience Cloud utilizza la raccolta dati regionale (RDC) in modo che le interazioni tra gli utenti finali e Adobe Experience Cloud avvengano il più possibile vicino ai tuoi utenti finali. Questo migliora le prestazioni del sito e dell&#39;app e garantisce che i dati vengano raccolti il più rapidamente possibile per ottimizzare l&#39;esperienza dell&#39;utente finale. Quando i dati delle tue proprietà digitali vengono raccolti a livello regionale in un Data Collection Center (DCC), vengono inoltrati tramite una connessione protetta a un Data Processing Center (DPC), dove vengono elaborati e resi disponibili per i prodotti Adobe Experience Cloud.

RDC attualmente include le seguenti posizioni (soggette a modifica):

## Raccolta di dati HTTP e di terze parti

| RDC Type | Centri di raccolta dati |
|---------------------|-------------------|
| impostazione predefinita | Oregon, Virginia, Irlanda, Parigi, Mumbai, Singapore, Tokyo, Sydney |

Nota: Se la richiesta di immagine di Analytics viene inviata agli `2o7.net` o `omtdrc.net` agli endpoint, avrai a disposizione una raccolta dati di terze parti. Potete determinare questo valore se visualizzate uno degli endpoint nell&#39;URL delle richieste.

## Raccolta dati HTTPS di prime parti

| RDC Type | Centri di raccolta dati |
|---------------------|-------------------|
| Globale (predefinito) | Oregon, Virginia, Irlanda, Parigi, Mumbai, Singapore, Tokyo, Sydney |
| Solo America | Oregon (Virginia) |
| Solo Europa | Irlanda, Parigi |
| Solo Asia Pacifico | Mumbai, Singapore, Tokyo, Sydney |

Nota: Experience Edge Global offre le migliori prestazioni agli utenti finali.  Se desideri utilizzare un altro tipo di RDC, contatta l&#39;Assistenza clienti Adobe.

## Come funziona RDC

L&#39;elenco seguente descrive il processo di raccolta dei dati utilizzato da Adobe:

1. Il DNS risolve automaticamente il nome host della raccolta all&#39;indirizzo IP del centro di raccolta dati più vicino al visitatore.
1. Il visitatore invia i dati a tale posizione.
1. I dati vengono inoltrati immediatamente attraverso una connessione protetta al centro di elaborazione dati, dove vengono elaborati e resi disponibili per i prodotti Adobe Experience Cloud.

## Vantaggi dell&#39;RDC

| Beneficio | Descrizione |
|---------|-----------|
| Prestazioni | Con RDC, i visitatori si connetteranno al DCC più vicino. Ciò significa che i tempi di risposta sulla pagina diminuiranno (meno è meglio), con conseguente tracciamento più preciso e tempi di caricamento più rapidi. |
| Ridondanza | In caso di interruzione delle comunicazioni con un DCC, la raccolta dei dati viene automaticamente indirizzata al DCC successivo più vicino, garantendo la continuità del servizio. |
| Ridondanza | In caso di interruzione delle comunicazioni tra il DCC e il DPC, l&#39;infrastruttura RDC di Adobe consente di risparmiare i dati localmente, quindi di inoltrarli al DPC al ripristino delle comunicazioni. |

## Cronologia revisioni documentazione

| Aggiornamento | Descrizione |
|--------|---------|
| 4 febbraio 2020 | Aggiorna posizioni RDC |
| 20 febbraio 2019 | Riscrittura completa. Sono state aggiunte informazioni sulla rete RDC. |
