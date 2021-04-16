---
description: Le seguenti informazioni possono essere utili per risolvere eventuali problemi di latenza della suite di rapporti nei dati di Analytics.
keywords: dati mancanti;lento
subtopic: Current data
title: Disponibilità dei dati e latenza
topic-fix: Reports
uuid: 1f0e67e3-6cea-4af8-8b18-7ae9223df7c8
exl-id: fedef3ea-dde6-460f-90e3-1e661ed29b78
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '806'
ht-degree: 0%

---

# Disponibilità dei dati e latenza in Adobe Analytics

In genere i dati completi vengono visualizzati nei rapporti 2 ore dopo la raccolta. Le seguenti informazioni possono essere utili per risolvere eventuali problemi di latenza della suite di rapporti nei dati di Analytics.

## Informazioni sulla gestione in batch dei dati

Ogni server di raccolta dati acquisisce ed elabora dati di analisi non elaborati e quindi carica i dati in batch su base oraria per il reporting. Il processo di trasferimento richiede in genere 30 minuti, quindi la latenza normale per il traffico che si verifica direttamente al termine del processo di caricamento precedente è di circa 90 minuti (60 minuti fino al successivo caricamento batch, quindi 30 minuti per il trasferimento e la visualizzazione dei file). Per il traffico che si verifica direttamente prima di un caricamento, la latenza dei dati potrebbe essere breve fino a 30 minuti (0 minuti fino a quando non si verifica il successivo caricamento batch, quindi 30 minuti per il trasferimento e la visualizzazione dei file).

Se necessario, l’Assistenza clienti Adobe può abilitare il caricamento di dati in batch da 30 minuti (anziché ogni ora) per le suite di rapporti più utilizzate.

## Contribuenti alla latenza

La latenza è un ritardo superiore alle 2 ore tipiche necessarie ai server di raccolta dati per elaborare completamente i dati. Non incide sulla raccolta dei dati; i dati vengono ancora raccolti per un’implementazione funzionante, indipendentemente dalla latenza di una suite di rapporti. La sua gravità (la corrente dei dati) e la sua lunghezza (il tempo necessario per risolverli) possono variare notevolmente. In genere è limitato a una singola suite di rapporti.

La latenza è causata da una delle seguenti categorie generali:

* **Picco di traffico imprevisto:** questo tipo di latenza si verifica quando vengono inviati più dati a una suite di rapporti di quanti siano stati impegnati o previsti per contratto. È la causa più comune di latenza.
* **Problemi hardware normali:** Adobe utilizza strategie all’avanguardia per la gestione e il monitoraggio dei centri dati, la ridondanza dei dati e l’affidabilità dell’hardware. L&#39;hardware viene aggiornato regolarmente e insieme alle finestre di manutenzione pubblicate. La manutenzione di emergenza dell&#39;hardware guasto può richiedere un arresto necessario e temporaneo nell&#39;elaborazione dei dati (non nella raccolta dei dati) in quanto l&#39;hardware sostitutivo viene portato online. Questo blocco temporaneo dell&#39;elaborazione può causare una latenza notevole.
* **Dati anormali:** i pattern di dati non naturali, come le visite insolitamente lunghe causate da un bot o da un crawler, possono aumentare temporaneamente alcuni carichi di elaborazione che determinano latenza.

## Funzioni dipendenti dalla latenza

Alcune funzionalità di Adobe Experience Cloud offrono una quantità innata di latenza oltre ai tempi di elaborazione standard.

* Analytics for Target (A4T) richiede una latenza aggiuntiva di 5-10 minuti per consentire la memorizzazione dei dati raccolti da entrambe le piattaforme nello stesso hit.
* I dati con marca temporale richiedono un tempo aggiuntivo a causa dei diversi server su cui vengono elaborati. Gli hit con marca temporale ricevuti in tempo reale o in prossimità di essi possono richiedere fino a 15 minuti. Gli hit ricevuti con una marca temporale di ieri possono richiedere fino a 2 ore. Gli hit più vecchi possono richiedere più tempo, aumentando ogni giorno fino a un tetto di circa 24 ore.

## Modi per attenuare o prevenire la latenza

Esistono diverse strategie per evitare la latenza o ridurre il tempo di recupero quando si verifica:

* **Notifica Adobe dei picchi di traffico previsti:** Anche se è impossibile prevedere ogni picco di traffico per il tuo sito, ci possono essere casi in cui ti aspetti di ricevere un aumento significativo del traffico. Gli esempi includono un periodo di vacanza particolarmente positivo o poco dopo un push di una campagna di grandi dimensioni. In questi casi, Adobe offre all’organizzazione un modo per informarci degli aumenti di traffico previsti, in modo da poter allocare ulteriori risorse di elaborazione alla suite di rapporti. Per informazioni su come avvisare l’Adobe di un aumento del traffico, consulta [Pianificare un picco di traffico](/help/admin/c-traffic-management/t-traffic-schedule-spike.md) nella guida utente dell’amministratore .
* **Quando si attivano nuove funzioni, considera il carico di elaborazione:**  alcune funzioni richiedono un&#39;elaborazione più intensa di altre. Più funzioni sono abilitate in una suite di rapporti, più è difficile recuperare dalla latenza. Quando abiliti le funzioni di una suite di rapporti, ricorda quanto segue che aumenta la quantità di dati da elaborare:

   * Implementazione di più di 20 eventi sulla stessa pagina
   * Regole VISTA complesse
   * Più di 20 valori nella variabile prodotti
   * Serializzazione degli eventi

* Abilita il filtro bot IAB: [Filtro bot](/help/admin/admin/bot-removal/bot-removal.md) può ridurre notevolmente la latenza se la suite di rapporti è frequentata da bot o crawler. Si consiglia di utilizzare l&#39;elenco di bot IAB, in quanto viene aggiornato e gestito da [Interactive Advertising Bureau](https://www.iab.net/about_the_iab). Un utente può personalizzare le proprie regole bot per integrarle da IAB.

## Cosa fare sulla latenza

Nei casi in cui si verifica una latenza, assicurati che Adobe monitori in modo proattivo la pipeline di elaborazione e faccia tutto il possibile per riportare il tempo di elaborazione al livello normale il più rapidamente possibile. Molti problemi di latenza vengono risolti in poche ore. Se hai a che fare con una suite di rapporti specifica, uno degli utenti supportati della tua organizzazione può contattare l’Assistenza clienti con l’ID della suite di rapporti che presenta una latenza. Il rappresentante di Adobe può convalidare la latenza e informarti quando il problema migliora e viene risolto.
