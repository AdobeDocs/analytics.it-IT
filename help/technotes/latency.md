---
description: Le informazioni seguenti possono risolvere problemi relativi alla latenza delle suite di rapporti nei dati di Analytics.
keywords: dati mancanti; slow
seo-description: Le informazioni seguenti possono risolvere problemi relativi alla latenza delle suite di rapporti nei dati di Analytics.
seo-title: Disponibilità e latenza dei dati
solution: Analytics
subtopic: Dati correnti
title: Disponibilità e latenza dei dati
topic: Rapporti
uuid: 1 f 0 e 67 e 3-6 cea -4 af 8-8 b 18-7 ae 9223 df 7 c 8
translation-type: tm+mt
source-git-commit: 1fdd14497171dbf5850ec1b1d873a06931d58435

---


# Disponibilità e latenza dei dati in Adobe Analytics

In genere è possibile visualizzare i dati completi nei rapporti 2 ore dopo la raccolta dei dati. Le informazioni seguenti possono risolvere problemi relativi alla latenza delle suite di rapporti nei dati di Analytics.

## Gestione dei batch di dati

Ogni server di raccolta dati acquisisce ed elabora dati di analisi grezzi, quindi carica i dati in batch su base oraria per generare rapporti. Il processo di trasferimento richiede in genere 30 minuti, pertanto la latenza normale per il traffico che si verifica direttamente dopo il processo di caricamento precedente dura circa 90 minuti (60 minuti fino al verificarsi del caricamento successivo, quindi 30 minuti per il trasferimento e la visualizzazione del file). Per il traffico che si verifica direttamente prima di un caricamento, la latenza dati potrebbe essere di 30 minuti (0 minuti fino al verificarsi del caricamento successivo, quindi 30 minuti per il trasferimento e la visualizzazione dei file).

Se necessario, l'Assistenza clienti Adobe può abilitare 30 minuti di caricamento dei dati (anziché oraria) per le suite di rapporti più utilizzate.

## Collaboratori alla latenza

La latenza è un ritardo più lungo delle 2 ore più lunghe necessarie ai server di raccolta dati per elaborare completamente i dati. Non influisce sulla raccolta dei dati; i dati vengono raccolti per un'implementazione funzionante, a prescindere da quanto sia latante una suite di rapporti. La sua gravità (in base alla posizione dei dati) e alla lunghezza (il tempo necessario per la risoluzione) può variare notevolmente. In genere è limitata a una singola suite di rapporti.

La latenza è causata da una delle seguenti categorie generali:

* **Picco traffico imprevisto:** Questo tipo di latenza si verifica quando più dati vengono inviati a una suite di rapporti rispetto a quanto promesso o previsto. È la causa più comune della latenza.
* **Problemi hardware normali:** Adobe utilizza strategie ottimali per la gestione e il monitoraggio dei dati dei dati, la ridondanza dei dati e l'affidabilità hardware. L'hardware viene aggiornato regolarmente e in combinazione con le finestre di manutenzione pubblicate. La manutenzione di emergenza per hardware non riuscito può richiedere un arresto necessario e temporaneo nell'elaborazione dati (non nella raccolta dati) come hardware sostitutivo. Questo arresto temporaneo nell'elaborazione può dare luogo a latenza visibili.
* **Dati anomali:** Pattern di dati unnaturali, ad esempio visite univoche causate da un bot o da un colore srler, possono aumentare temporaneamente alcuni carichi di elaborazione che generano latenza.

## Funzioni che dipendono dalla latenza

Alcune funzionalità in Adobe Experience Cloud sono dotate di una latenza innata sull'ora di elaborazione standard.

* Analytics for Target (A 4 T) richiede ulteriori 5-10 minuti di latenza per consentire la memorizzazione di dati raccolti da entrambe le piattaforme nello stesso hit.
* I dati con marca temporale richiedono un tempo aggiuntivo a causa di diversi server elaborati. Gli hit con marca temporale ricevuti in tempo reale o quasi in tempo reale possono richiedere fino a 15 minuti. Gli hit ricevuti con marca temporale di ieri possono richiedere fino a 2 ore. Gli hit precedenti possono richiedere più tempo, aumentando ogni giorno fino a circa 24 ore.

## Modalità per attenuare o impedire la latenza

Esistono diverse strategie per impedire la latenza o ridurre il tempo di recupero quando si verifica:

* **Notifica ad Adobe i picchi di traffico previsti:** Benché sia impossibile anticipare ogni picco di traffico al sito, ci potrebbe essere un caso in cui si prevede di ricevere un aumento significativo del traffico. Gli esempi includono un periodo festivo particolarmente efficace o poco dopo un grande push della campagna. In questi casi, Adobe consente alla vostra organizzazione di ricevere un'indicazione del traffico previsto, in modo da allocare ulteriori risorse di elaborazione alla vostra suite di rapporti. See [Schedule a traffic spike](../admin/c-traffic-management/t-traffic-schedule-spike.md) in the Admin user guide to learn how to notify Adobe of increased traffic.
* **Considerate il carico di elaborazione durante l'attivazione delle nuove funzioni:** Alcune funzioni richiedono molte risorse di elaborazione. Più funzioni sono abilitate in una suite di rapporti, più difficile è recuperare dalla latenza. Quando abilitate le funzionalità in una suite di rapporti, tenete a mente le seguenti funzionalità che aumentano la quantità di dati da elaborare:

   * Implementazione di più di 20 eventi sulla stessa pagina
   * Regole VISTA complesse
   * Più di 20 valori nella variabile products
   * Serializzazione degli eventi

* Enable IAB Bot filtering: [Bot filtering](https://marketing.adobe.com/resources/help/en_US/admin/index.html?f=c_bot_rules) can greatly reduce latency if your report suite is frequented by bots or crawlers. It is recommended to use the IAB bot list, as it is updated and maintained by the [Interactive Advertising Bureau](https://www.iab.net/about_the_iab). Un utente può personalizzare le proprie regole bot per completarle dall'IAB.

## Come fare per la latenza

Nei casi in cui si verifica latenza, assicuratevi che Adobe monitori in modo proattivo la pipeline di elaborazione e faccia tutto ciò che è possibile per tornare alla normale velocità di elaborazione il più rapidamente possibile. Molti problemi di latenza vengono risolti entro ore. Se ti interessa una suite di rapporti specifica, uno degli utenti supportati della tua organizzazione può contattare l'Assistenza clienti con l'ID della suite di rapporti che si verifica latenza. Il rappresentante Adobe può convalidare la latenza e informare l'utente durante il miglioramento e la risoluzione del problema.
