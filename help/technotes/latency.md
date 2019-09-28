---
description: Le seguenti informazioni possono essere utili per risolvere i problemi di latenza della suite di rapporti nei dati di Analytics.
keywords: dati mancanti;lento
seo-description: Le seguenti informazioni possono essere utili per risolvere i problemi di latenza della suite di rapporti nei dati di Analytics.
seo-title: Disponibilità e latenza dei dati
solution: Analytics
subtopic: Dati correnti
title: Disponibilità e latenza dei dati
topic: Rapporti
uuid: 1f0e67e3-6cea-4af8-8b18-7ae9223df7c8
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Disponibilità e latenza dei dati in Adobe Analytics

In genere è previsto che i dati completi vengano visualizzati nei report 2 ore dopo la raccolta dei dati. Le seguenti informazioni possono essere utili per risolvere i problemi di latenza della suite di rapporti nei dati di Analytics.

## Informazioni sulla gestione dei batch di dati

Ogni server di raccolta dati acquisisce ed elabora dati di analisi non elaborati, quindi carica i dati in batch su base oraria per il reporting. Il processo di trasferimento richiede in genere 30 minuti, pertanto la latenza normale per il traffico che si verifica direttamente dopo il completamento del processo di caricamento precedente è di circa 90 minuti (60 minuti fino al successivo caricamento batch, quindi 30 minuti per il trasferimento e la visualizzazione dei file). Per il traffico che si verifica direttamente prima di un caricamento, la latenza dei dati potrebbe essere di soli 30 minuti (0 minuti fino al successivo caricamento batch, 30 minuti per il trasferimento e la visualizzazione dei file).

Se necessario, l'Assistenza clienti Adobe può abilitare il caricamento di dati in batch di 30 minuti (anziché ogni ora) per le suite di rapporti più utilizzate.

## Contributori alla latenza

La latenza è un ritardo superiore alle 2 ore normalmente necessarie affinché i server di raccolta dati elaborino completamente i dati. Non incide sulla raccolta dei dati; i dati vengono ancora raccolti per un'implementazione di lavoro, indipendentemente dalla latenza di una suite di rapporti. La sua gravità (la quantità di dati correnti) e la lunghezza (il tempo necessario per risolverli) possono variare notevolmente. In genere è limitata a una singola suite di rapporti.

La latenza è causata da una delle seguenti categorie generali:

* **** Picco di traffico imprevisto: Questo tipo di latenza si verifica quando più dati vengono inviati a una suite di rapporti di quanto sia stato precedentemente impegnato o previsto. È la causa più comune di latenza.
* **** Problemi hardware normali: Adobe utilizza strategie all’avanguardia per la gestione e il monitoraggio dei centri dati, la ridondanza dei dati e l’affidabilità dell’hardware. L'hardware viene aggiornato regolarmente e insieme alle finestre di manutenzione pubblicate. La manutenzione di emergenza dell'hardware guasto può richiedere un arresto necessario e temporaneo nell'elaborazione dei dati (non nella raccolta dei dati) in quanto l'hardware sostitutivo viene portato online. Questo arresto temporaneo dell'elaborazione può determinare una latenza notevole.
* **** Dati anormali: Pattern di dati innaturali, come visite insolitamente lunghe causate da un bot o crawler, possono aumentare temporaneamente alcuni carichi di elaborazione che determinano latenza.

## Funzioni che dipendono dalla latenza

Alcune funzionalità di Adobe Experience Cloud offrono una quantità innata di latenza oltre ai tempi di elaborazione standard.

* Analytics per Target (A4T) richiede una latenza aggiuntiva di 5-10 minuti per consentire la memorizzazione dei dati raccolti da entrambe le piattaforme nello stesso hit.
* I dati con marca temporale richiedono un ulteriore tempo a causa dei diversi server su cui vengono elaborati questi dati. Gli hit con marca temporale ricevuti in tempo reale o in prossimità di essi possono richiedere fino a 15 minuti. Gli hit ricevuti con marca temporale di ieri possono richiedere fino a 2 ore. Gli hit più vecchi possono richiedere più tempo, aumentando ogni giorno fino a un massimo di circa 24 ore.

## Modalità per attenuare o prevenire la latenza

Esistono diverse strategie per evitare latenza o ridurre il tempo di recupero quando si verifica:

* **** Notifica ad Adobe i picchi di traffico previsti: Anche se è impossibile prevedere ogni picco di traffico al tuo sito, ci possono essere casi in cui si prevede di ricevere un aumento significativo del traffico. Alcuni esempi includono un periodo di vacanza particolarmente positivo, o poco dopo un push di grandi dimensioni della campagna. In questi casi, Adobe offre alla tua organizzazione un modo per informarci degli aumenti di traffico previsti, in modo da poter allocare ulteriori risorse di elaborazione alla tua suite di rapporti. Consultate [Pianificare un picco](../admin/c-traffic-management/t-traffic-schedule-spike.md) di traffico nella guida utente per informazioni su come notificare ad Adobe l’aumento del traffico.
* **** Considerate l'elaborazione del carico durante l'attivazione delle nuove funzioni: Alcune funzioni richiedono più elaborazione di altre. Più funzioni sono abilitate in una suite di rapporti, più difficile è recuperare dalla latenza. Quando attivi le funzionalità in una suite di rapporti, tieni presente le seguenti funzionalità che aumentano la quantità di dati da elaborare:

   * Implementazione di più di 20 eventi sulla stessa pagina
   * Regole VISTA complesse
   * Più di 20 valori nella variabile products
   * Serializzazione degli eventi

* Abilita filtro bot IAB: Il filtraggio [dei](https://marketing.adobe.com/resources/help/en_US/admin/c_bot_rules.html) bot può ridurre notevolmente la latenza se la suite di rapporti è frequentata da bot o crawler. Si consiglia di utilizzare l'elenco bot IAB, in quanto viene aggiornato e gestito dall' [Interactive Advertising Bureau](https://www.iab.net/about_the_iab). Un utente può personalizzare le proprie regole bot per integrare quelle dello IAB.

## Cosa fare in merito alla latenza

Nei casi in cui si verifica la latenza, assicuratevi che Adobe effettui il monitoraggio proattivo della pipeline di elaborazione e faccia tutto il possibile per ripristinare il tempo di elaborazione normale il più rapidamente possibile. Molti problemi di latenza vengono risolti in poche ore. Se hai a che fare con una suite di rapporti specifica, uno degli utenti supportati della tua organizzazione può contattare l'Assistenza clienti con l'ID suite di rapporti che presenta una latenza. Il rappresentante Adobe può convalidare la latenza e informare l'utente non appena il problema migliora e viene risolto.
