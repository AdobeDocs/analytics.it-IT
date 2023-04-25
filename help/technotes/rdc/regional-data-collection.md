---
title: Raccolta di dati regionali
description: Informazioni sulla raccolta di dati regionali
feature: Regional Data Collection
exl-id: 295e9736-2a58-48a8-9968-5dfa33b70d95
source-git-commit: f75d123c93d446776492dd933d03d32c2496fa69
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 1%

---

# Raccolta di dati regionali

Adobe Experience Cloud utilizza la raccolta di dati regionali (RDC) in modo che le interazioni tra i visitatori e l’Adobe si verifichino il più vicino possibile ai visitatori. Una volta raccolti i dati regionali in un centro di raccolta dati (DCC, Data Collection Center), questi vengono inoltrati tramite una connessione protetta a un centro di elaborazione dati (DPC, Data Processing Center). Dopo l’elaborazione, i dati sono disponibili per i prodotti in Adobe Experience Cloud. Per modificare il tipo di RDC, contatta l’Assistenza clienti Adobe.

Il processo di raccolta dei dati regionali utilizza i seguenti passaggi:

1. Il DNS risolve automaticamente il nome host della raccolta all&#39;indirizzo IP del centro di raccolta dati più vicino al visitatore.
1. Il visitatore invia i dati a tale posizione.
1. I dati vengono inoltrati immediatamente tramite una connessione protetta al Centro di elaborazione dei dati, dove vengono elaborati e resi disponibili ai prodotti in Adobe Experience Cloud.

L’utilizzo della raccolta di dati regionali offre diversi vantaggi:

* **Prestazioni**: Con RDC, i visitatori si connettono al DCC più vicino. Questa ottimizzazione fornisce il tempo di risposta più veloce, con conseguente tracciamento più preciso e tempi di caricamento più rapidi.
* **Ridondanza**: Se si verifica un&#39;interruzione nella comunicazione tra DCC e il tuo DPC, l&#39;infrastruttura RDC di Adobe salva i dati localmente, quindi li inoltra al DPC quando le comunicazioni vengono ripristinate.

RDC attualmente include le seguenti posizioni (soggette a modifica):

## Raccolta di dati di terze parti

| Tipo RDC | Centri di raccolta dati |
| --- | --- |
| Impostazione predefinita | Oregon, Virginia, Irlanda, Parigi, Mumbai, Singapore, Tokyo, Sydney, Cina* |

{style="table-layout:auto"}

*China RDC richiede il pacchetto aggiuntivo Cina. Vedi [Ottimizzazione delle prestazioni in Cina](#china-performance-optimization) sotto.

>[!NOTE]
>
>Se la richiesta di immagine di Analytics viene inviata al `adobedc.net`, `2o7.net` o `omtrdc.net` endpoint, quindi la raccolta dati di terze parti. Puoi determinarlo se vedi uno degli endpoint nell&#39;URL delle richieste.

## Raccolta di dati di prime parti

| Tipo RDC | Centri di raccolta dati |
| --- | --- |
| Globale (predefinito) | Oregon, Virginia, Irlanda, Parigi, Mumbai, Singapore, Tokyo, Sydney |
| Globale + Cina* | Cina*, Oregon, Virginia, Irlanda, Parigi, Mumbai, Singapore, Tokyo, Sydney |
| Solo America | Oregon, Virginia |
| Solo Europa | Irlanda, Parigi |
| Solo Asia-Pacifico | Mumbai, Singapore, Tokyo, Sydney |
| Solo Cina* | Pechino |

{style="table-layout:auto"}

*Solo Cina e i tipi RDC globali + Cina richiedono il pacchetto aggiuntivo Cina. Global + China indirizza i dati provenienti dalla Cina all&#39;RDC della Cina Adobe mentre indirizzano i dati provenienti dall&#39;estero alla RDC più vicina al di fuori della Cina. Vedi [Ottimizzazione delle prestazioni in Cina](#china-performance-optimization) sotto.

## Ottimizzazione delle prestazioni in Cina

Il pacchetto aggiuntivo China RDC (China Performance Optimization) è un componente aggiuntivo a pagamento per Adobe Analytics. L’ottimizzazione delle prestazioni di Adobe in Cina consente ai clienti con utenti in Cina di inviare tali dati direttamente ai server di raccolta dati di Adobe in Cina anziché in altre aree a livello globale. Questa ottimizzazione migliora i tempi di caricamento delle pagine e la precisione dei dati rispetto all’invio dei dati a posizioni esterne alla Cina. I dati vengono infine trasferiti a uno dei Data Processing Center (DPC) di Adobe al di fuori della Cina. Per ulteriori informazioni, contatta il tuo rappresentante commerciale Adobe.

>[!NOTE]
>
>Il pacchetto aggiuntivo di RDC per la Cina non è supportato per [SDK per web](/help/implement/aep-edge/overview.md).

