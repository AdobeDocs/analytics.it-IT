---
title: Raccolta di dati regionali
description: Informazioni sulla raccolta di dati regionali
feature: Regional Data Collection
exl-id: 295e9736-2a58-48a8-9968-5dfa33b70d95
source-git-commit: 60c2422ef32a4fadbb975006c111d12878a98f53
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 1%

---

# Raccolta di dati regionali

Adobe Experience Cloud utilizza la raccolta di dati regionali (RDC) in modo che le interazioni tra gli utenti finali e Adobe Experience Cloud si verifichino il più vicino possibile agli utenti finali. Questo migliora le prestazioni del sito/app e assicura che i dati vengano raccolti il più rapidamente possibile per ottimizzare l’esperienza dell’utente finale. Una volta raccolti i dati dalle proprietà digitali a livello regionale in un Data Collection Center (DCC), questi vengono inoltrati tramite una connessione protetta a un Data Processing Center (DPC) in cui vengono elaborati e resi disponibili ai prodotti in Adobe Experience Cloud.

>[!IMPORTANT]
>
>Il pacchetto aggiuntivo China RDC (China Performance Optimization) è un componente aggiuntivo a pagamento per Adobe Analytics. L’ottimizzazione delle prestazioni di Adobe nella Cina continentale consente ai clienti con utenti in Cina di inviare tali dati direttamente ai server di raccolta edge di Adobe in Cina, anziché in altre aree a livello globale. Questo migliora i tempi di caricamento delle pagine e la precisione dei dati rispetto all’invio dei dati a nodi al di fuori della Cina. Si noti che i dati vengono infine trasferiti a uno dei Data Processing Center (DPC) di Adobe al di fuori della Cina. Per ulteriori informazioni, contattare il rappresentante commerciale Adobe.

RDC attualmente include le seguenti posizioni (soggette a modifica):

## Raccolta di dati di terze parti

| Tipo RDC | Centri di raccolta dati |
|---------------------|-------------------|
| Impostazione predefinita | Oregon, Virginia, Irlanda, Parigi, Mumbai, Singapore, Tokyo, Sydney, Cina* |

*China RDC richiede il pacchetto aggiuntivo Cina. Vedi la nota &quot;Importante&quot; sopra.

>[!NOTE]
>
>Se la richiesta di immagine di Analytics viene inviata al `adobedc`, `2o7.net` o `omtrdc.net` endpoint, quindi la raccolta dati di terze parti. Puoi determinarlo se vedi uno degli endpoint nell&#39;URL delle richieste.

## Raccolta di dati di prime parti

| Tipo RDC | Centri di raccolta dati |
|---------------------|-------------------|
| Globale (predefinito) | Oregon, Virginia, Irlanda, Parigi, Mumbai, Singapore, Tokyo, Sydney |
| Globale + Cina* | Cina*, Oregon, Virginia, Irlanda, Parigi, Mumbai, Singapore, Tokyo, Sydney |
| Solo America | Oregon, Virginia |
| Solo Europa | Irlanda, Parigi |
| Solo Asia-Pacifico | Mumbai, Singapore, Tokyo, Sydney |
| Solo Cina* | Pechino |

*Solo Cina e i tipi RDC globali + Cina richiedono il pacchetto aggiuntivo Cina. Vedi la nota &quot;Importante&quot; sopra. Global + China indirizza i dati provenienti dalla Cina alla nostra RDC Cina durante il routing dei dati provenienti da fuori dalla Cina alla RDC più vicina al di fuori della Cina.

>[!NOTE]
>
>Experience Edge Global offre le migliori prestazioni per gli utenti finali.  Se desideri utilizzare un tipo RDC alternativo, contatta l’Assistenza clienti Adobe .

## Vantaggi dell&#39;RDC

| Beneficio | Descrizione |
| --- | --- |
| Prestazioni | Con RDC, i visitatori si connettono al DCC più vicino. Questo fornisce il tempo di risposta più veloce, con conseguente tracciamento più preciso e tempi di caricamento più rapidi. |
| Ridondanza | In caso di interruzione della comunicazione tra DCC e il tuo DPC, l&#39;infrastruttura RDC di Adobe salva i dati localmente, quindi li inoltra al DPC quando le comunicazioni vengono ripristinate. |

## Come funziona RDC

L’elenco seguente descrive il processo di raccolta dei dati utilizzato dall’Adobe:

1. Il DNS risolve automaticamente il nome host della raccolta all&#39;indirizzo IP del centro di raccolta dati più vicino al visitatore.
1. Il visitatore invia i dati a tale posizione.
1. I dati vengono inoltrati immediatamente tramite una connessione protetta al Centro di elaborazione dei dati, dove vengono elaborati e resi disponibili ai prodotti in Adobe Experience Cloud.
