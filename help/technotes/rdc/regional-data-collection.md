---
title: Raccolta di dati regionali
description: Informazioni sulla raccolta di dati regionali
translation-type: tm+mt
source-git-commit: 731209e28dab9f17e06948614149a4c99938fdae
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 2%

---


# Raccolta di dati regionali

Adobe Experience Cloud utilizza la raccolta dati regionale (RDC) in modo che le interazioni tra gli utenti finali e Adobe Experience Cloud avvengano il più possibile vicino ai tuoi utenti finali. Questo migliora le prestazioni del sito e dell&#39;app e garantisce che i dati vengano raccolti il più rapidamente possibile per ottimizzare l&#39;esperienza dell&#39;utente finale. Una volta raccolti i dati delle proprietà digitali a livello regionale in un centro di raccolta dati (DCC), questi vengono inoltrati attraverso una connessione protetta a un centro di elaborazione dati (DPC), dove vengono elaborati e resi disponibili per i prodotti Adobe Experience Cloud.

>[!IMPORTANT]
>
>Il pacchetto aggiuntivo China RDC (China Performance Optimization) è un componente aggiuntivo caricabile per  Adobe Analytics.  Ottimizzazione delle prestazioni del Adobe in Cina continentale consente ai clienti cinesi di inviare dati direttamente al nodo Edge China, anziché ad altre posizioni a livello globale. Questo migliora i tempi di caricamento delle pagine e la precisione dei dati rispetto all&#39;invio dei dati a nodi esterni alla Cina. Per ulteriori informazioni, contattare il rappresentante commerciale  Adobe.

RDC attualmente include le seguenti posizioni (soggette a modifica):

## Raccolta di dati HTTP e di terze parti

| RDC Type | Centri di raccolta dati |
|---------------------|-------------------|
| impostazione predefinita | Oregon, Virginia, Irlanda, Parigi, Mumbai, Singapore, Tokyo, Sydney, Cina* |

Nota: Se la tua richiesta di immagine Analytics viene inviata agli `adobedc`, `2o7.net` o `omtrdc.net` agli endpoint, hai a disposizione una raccolta dati di terze parti. Potete determinare questo valore se visualizzate uno degli endpoint nell&#39;URL delle richieste.

*China RDC richiede il pacchetto China Add-On. Vedi la nota &quot;Importante&quot; sopra.

## Raccolta dati HTTPS di prime parti

| RDC Type | Centri di raccolta dati |
|---------------------|-------------------|
| Globale (predefinito) | Oregon, Virginia, Irlanda, Parigi, Mumbai, Singapore, Tokyo, Sydney |
| Solo America | Oregon (Virginia) |
| Solo Europa | Irlanda, Parigi |
| Solo Asia Pacifico | Mumbai, Singapore, Tokyo, Sydney |
| Solo Cina* | Pechino |

*China RDC richiede il pacchetto China Add-On. Vedi la nota &quot;Importante&quot; sopra.

Nota: Experience Edge Global offre le migliori prestazioni agli utenti finali.  Se desideri utilizzare un altro tipo di RDC, contatta l&#39;Assistenza clienti  Adobe.

## Vantaggi dell&#39;RDC

| Beneficio | Descrizione |
| --- | --- |
| Prestazioni | Con RDC, i visitatori si connetteranno al DCC più vicino. Questo fornisce il tempo di risposta più veloce, con conseguente tracciamento più preciso e tempi di caricamento più rapidi. |
| Ridondanza | In caso di interruzione delle comunicazioni con un DCC, la raccolta dei dati viene automaticamente indirizzata al DCC successivo più vicino, garantendo la continuità del servizio. |
| Ridondanza | In caso di interruzione delle comunicazioni tra il DCC e il DPC, &#39;infrastruttura RDC del Adobe consente di salvare i dati in locale, quindi di inoltrarli al DPC quando le comunicazioni vengono ripristinate. |

## Funzionamento di RDC

L&#39;elenco seguente descrive il processo di raccolta dei dati utilizzato dall&#39;Adobe :

1. Il DNS risolve automaticamente il nome host della raccolta all&#39;indirizzo IP del centro di raccolta dati più vicino al visitatore.
1. Il visitatore invia i dati a tale posizione.
1. I dati vengono immediatamente inoltrati attraverso una connessione protetta al centro di elaborazione dati, dove vengono elaborati e messi a disposizione dei prodotti nell&#39;Adobe Experience Cloud.
