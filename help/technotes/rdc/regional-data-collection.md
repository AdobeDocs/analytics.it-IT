---
title: Raccolta di dati regionali
description: Informazioni sulla raccolta di dati regionali
feature: Regional Data Collection
exl-id: 295e9736-2a58-48a8-9968-5dfa33b70d95
source-git-commit: a4dd138f0f2198da66caa272dd62b46f24b578b2
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 1%

---

# Raccolta di dati regionali

Adobe Experience Cloud utilizza la raccolta dati regionali (Regional Data Collection, RDC) in modo che le interazioni tra i visitatori e l’Adobe si verifichino il più vicino possibile ai visitatori. Una volta raccolti i dati a livello regionale in un centro di raccolta dati (DCC, noto anche come sito Edge), questi vengono inoltrati tramite una connessione protetta a un centro di elaborazione dati (DPC, noto anche come sito Core). Dopo l’elaborazione, i dati sono disponibili per i prodotti nel Adobe Experience Cloud. Per cambiare il tipo di RDC, contatta l’Assistenza clienti Adobe.

Il processo di raccolta dati regionali utilizza i seguenti passaggi:

1. Il DNS risolve automaticamente il nome host della raccolta nell’indirizzo IP del centro di raccolta dati più vicino al visitatore.
1. Il visitatore invia i dati a tale posizione.
1. I dati vengono immediatamente inoltrati tramite una connessione sicura al Centro di elaborazione dati, dove vengono elaborati e resi disponibili ai prodotti nel Adobe Experience Cloud.

L’utilizzo della raccolta dati regionali offre diversi vantaggi:

* **Prestazioni**: con RDC, i visitatori si connettono al DCC più vicino. Questa ottimizzazione fornisce il tempo di risposta più veloce, con conseguente tracciamento più preciso e tempi di caricamento più rapidi.
* **Ridondanza**: in caso di interruzione delle comunicazioni tra il DCC e il DPC, l&#39;infrastruttura RDC di Adobe salva i dati localmente e li inoltra al DPC quando le comunicazioni vengono ripristinate.

Attualmente RDC include le seguenti posizioni (soggette a modifica):

## Raccolta di dati di terze parti

| Tipo RDC | Data Collection Center |
| --- | --- |
| Impostazione predefinita | Oregon, Virginia, Irlanda, Parigi, Mumbai, Singapore, Tokyo, Sydney, Cina* |

{style="table-layout:auto"}

*China RDC richiede il pacchetto del componente aggiuntivo Cina. Consulta [Ottimizzazione delle prestazioni in Cina](#china-performance-optimization) di seguito.

>[!NOTE]
>
>Se la richiesta di immagine Analytics viene inviata al `adobedc.net`, `2o7.net` o `omtrdc.net` endpoint, quindi disponi di una raccolta dati di terze parti. Puoi determinarlo se visualizzi uno degli endpoint nell’URL delle richieste.

## Raccolta di dati di prime parti

| Tipo RDC | Data Collection Center |
| --- | --- |
| Globale (predefinito) | Oregon, Virginia, Irlanda, Parigi, Mumbai, Singapore, Tokyo, Sydney |
| Globale + Cina* | Cina*, Oregon, Virginia, Irlanda, Parigi, Mumbai, Singapore, Tokyo, Sydney |
| Solo Americhe | Oregon, Virginia |
| Solo Europa | Irlanda, Parigi |
| Solo Asia Pacifico | Mumbai, Singapore, Tokyo, Sydney |
| Solo Cina* | Pechino |

{style="table-layout:auto"}

*I tipi RDC solo Cina e Global + China richiedono il pacchetto del componente aggiuntivo Cina. Global + China indirizza i dati provenienti dall’interno della Cina all’RDC della Cina Adobe mentre invia i dati provenienti dall’esterno della Cina all’RDC più vicino fuori dalla Cina. Consulta [Ottimizzazione delle prestazioni in Cina](#china-performance-optimization) di seguito.

## Ottimizzazione delle prestazioni in Cina

Il pacchetto del componente aggiuntivo China RDC (China Performance Optimization) è un componente aggiuntivo a pagamento per Adobe Analytics. L’ottimizzazione delle prestazioni di Adobe nella Cina continentale consente ai clienti con utenti in Cina di inviare tali dati direttamente ai server di raccolta dati di Adobe in Cina invece che in altre località a livello globale. Questa ottimizzazione migliora i tempi di caricamento delle pagine e la precisione dei dati rispetto all’invio dei dati a posizioni al di fuori della Cina. I dati vengono infine trasferiti a uno dei centri di elaborazione dati (DPC) di Adobe al di fuori della Cina. Per ulteriori informazioni, contatta il rappresentante commerciale Adobe.

>[!NOTE]
>
>Il pacchetto del componente aggiuntivo RDC per la Cina non è supportato per [SDK per web](/help/implement/aep-edge/overview.md).

