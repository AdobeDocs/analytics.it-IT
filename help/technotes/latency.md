---
description: Le seguenti informazioni possono essere utili per risolvere eventuali problemi di latenza della suite di rapporti nei dati di Analytics.
keywords: dati mancanti;lento
title: Disponibilità e latenza dei dati
feature: Data Configuration and Collection
exl-id: fedef3ea-dde6-460f-90e3-1e661ed29b78
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '818'
ht-degree: 0%

---

# Disponibilità e latenza dei dati in Adobe Analytics

In genere, è possibile prevedere di visualizzare dati completi nei rapporti 2 ore dopo la raccolta dei dati. Le seguenti informazioni possono essere utili per risolvere eventuali problemi di latenza della suite di rapporti nei dati di Analytics.

## Informazioni sulla gestione in batch dei dati

Ogni server di raccolta dati acquisisce ed elabora i dati di analisi non elaborati, quindi carica i dati in batch su base oraria per i rapporti. Il processo di trasferimento richiede in genere 30 minuti, pertanto la latenza normale per il traffico che si verifica direttamente dopo il completamento del processo di caricamento precedente è di circa 90 minuti (60 minuti fino al successivo caricamento batch, quindi 30 minuti per il trasferimento e la visualizzazione dei file). Per il traffico che si verifica direttamente prima di un caricamento, la latenza dei dati potrebbe essere di 30 minuti (0 minuti fino al successivo caricamento batch, quindi 30 minuti per il trasferimento e la visualizzazione dei file).

Se necessario, l’Assistenza clienti di Adobe può abilitare caricamenti di dati in batch di 30 minuti (anziché orari) per le suite di rapporti più utilizzate.

## Collaboratori alla latenza

La latenza è un ritardo più lungo delle tipiche 2 ore necessarie ai server di raccolta dati per elaborare completamente i dati. Non influisce sulla raccolta dei dati; i dati vengono comunque raccolti per un’implementazione funzionante, indipendentemente dalla latenza di una suite di rapporti. La sua gravità (il livello di aggiornamento dei dati) e la lunghezza (il tempo necessario per risolverli) possono variare notevolmente. Di solito è limitato a una singola suite di rapporti.

La latenza è causata da una delle seguenti categorie generali:

* **Picco di traffico imprevisto:** Questo tipo di latenza si verifica quando vengono inviati a una suite di rapporti più dati di quelli impegnati contrattualmente o previsti. È la causa più comune di latenza.
* **Problemi hardware normali:** Adobe utilizza strategie all&#39;avanguardia per la gestione e il monitoraggio del centro dati, la ridondanza dei dati e l&#39;affidabilità hardware. L&#39;hardware viene aggiornato regolarmente e insieme alle finestre di manutenzione pubblicate. La manutenzione di emergenza dell&#39;hardware guasto può richiedere un arresto necessario e temporaneo dell&#39;elaborazione dei dati (non nella raccolta dati) quando l&#39;hardware sostitutivo viene portato online. Questa interruzione temporanea dell’elaborazione può causare una latenza notevole.
* **Dati anormali:** I pattern di dati non naturali, ad esempio visite insolitamente lunghe causate da un bot o da un crawler, possono aumentare temporaneamente alcuni carichi di elaborazione che determinano latenza.

## Funzioni che dipendono dalla latenza

Alcune funzionalità di Adobe Experience Cloud offrono una latenza innata oltre al tempo di elaborazione standard.

* Analytics for Target (A4T) richiede una latenza aggiuntiva di 5-10 minuti per consentire l’archiviazione dei dati raccolti da entrambe le piattaforme nello stesso hit.
* I dati con marca temporale richiedono un tempo aggiuntivo a causa di server diversi in cui vengono elaborati. Gli hit con marca temporale ricevuta in tempo reale o quasi, possono richiedere fino a 15 minuti. Gli hit ricevuti con una marca temporale di ieri possono richiedere fino a 2 ore. Gli hit più vecchi possono richiedere più tempo, aumentando ogni giorno fino a un tetto di circa 24 ore.

## Modi per mitigare o prevenire la latenza

Esistono diverse strategie per evitare la latenza o ridurre il tempo di ripristino quando si verifica:

* **Notifica ad Adobe i picchi di traffico previsti:** Anche se è impossibile prevedere ogni picco di traffico sul sito, in alcuni casi potrebbe verificarsi un aumento significativo del traffico. Alcuni esempi includono un periodo di vacanza particolarmente riuscito o poco dopo un invio di una campagna di grandi dimensioni. In questi casi, Adobe consente alla tua organizzazione di informarci sugli aumenti di traffico previsti, in modo da poter allocare risorse di elaborazione aggiuntive alla suite di rapporti. Per informazioni su come segnalare ad Adobe un aumento del traffico, consulta [Pianificare un picco di traffico](/help/admin/tools/manage-rs/edit-settings/c-traffic-management/t-traffic-schedule-spike.md) nella guida utente dell&#39;amministratore.
* **Durante l&#39;attivazione di nuove funzionalità, prendere in considerazione l&#39;elaborazione del carico:** Alcune funzionalità richiedono una maggiore elaborazione rispetto ad altre. Più funzioni sono abilitate in una suite di rapporti, più è difficile ripristinarle dalla latenza. Quando abiliti le funzioni in una suite di rapporti, tieni presente le seguenti funzioni che aumentano la quantità di dati da elaborare:

   * Implementazione di più di 20 eventi sulla stessa pagina
   * Regole VISTA complesse
   * Più di 20 valori nella variabile prodotti
   * Serializzazione degli eventi

* Abilita filtro bot IAB: [Il filtro bot](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-removal.md) può ridurre notevolmente la latenza se la suite di rapporti è frequentata da bot o crawler. Si consiglia di utilizzare l&#39;elenco di bot IAB, in quanto è aggiornato e gestito da [Interactive Advertising Bureau](https://www.iab.net/about_the_iab). Un utente può personalizzare le proprie regole bot per integrare quelle di IAB.

## Come comportarsi con la latenza

Nei casi in cui si verifica la latenza, assicurati che Adobe monitori in modo proattivo la pipeline di elaborazione e faccia tutto il possibile per riportare il tempo di elaborazione alla normalità il più rapidamente possibile. Molti problemi di latenza vengono risolti in poche ore. Se ti interessa una suite di rapporti specifica, uno degli utenti supportati dalla tua organizzazione può contattare l’Assistenza clienti con l’ID della suite di rapporti che presenta latenza. Il rappresentante di Adobe può convalidare la latenza e fornire informazioni man mano che il problema migliora e viene risolto.
