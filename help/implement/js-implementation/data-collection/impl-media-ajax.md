---
description: AJAX è un concetto emergente nella progettazione Web che utilizza più tecnologie per creare e gestire contenuti dinamici sulle pagine Web.
keywords: Implementazione di Analytics
seo-description: AJAX è un concetto emergente nella progettazione Web che utilizza più tecnologie per creare e gestire contenuti dinamici sulle pagine Web.
seo-title: Applicazioni Rich Media per AJAX
solution: Analytics
title: Applicazioni Rich Media per AJAX
topic: Sviluppatore e implementazione
uuid: ffe6a263-ae18-4875-badb-b3aea3efcb64
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Applicazioni Rich Media per AJAX

AJAX è un concetto emergente nella progettazione Web che utilizza più tecnologie per creare e gestire contenuti dinamici sulle pagine Web.

La necessità di monitorare l'interazione dell'utente con [!UICONTROL AJAX] e altre applicazioni rich media è fondamentale per il successo dell'analisi e la realizzazione del ritorno sull'investimento nella progettazione Web. L'obiettivo del Libro bianco è quello di fornire raccomandazioni per il monitoraggio delle applicazioni Internet avanzate, in particolare quelle che utilizzano [!UICONTROL AJAX].

## Applicazioni Rich Internet (RIA) {#section_CDCAFC4E05B44985BCBF34DFCB35DCA6}

Le RIA (Rich Internet Applications) stanno cambiando la faccia del Web. Risolvono il divario tra la promessa di tecnologie on-demand per le masse ed esperienze utente realistiche. Le RIA stanno maturando da anni. I maggiori passi avanti sono stati fatti con l'adozione su larga scala dei browser, che supportano le tecnologie sottostanti che alimentano queste applicazioni. Sebbene RIA disponga di molte forme e tecnologie di supporto, le più comuni, e forse più diffuse, sono AJAX e Flash. È importante comprendere che la tecnologia non è ciò che definisce una RIA, ma la sua usabilità e applicazione.

## Cosa tenere traccia {#section_E96EC5127E554B8384FD0A7A0B3118DF}

Una delle domande più frequenti con la RIA è come monitorare l'attività di micro-livello separatamente dall'attività di macro-livello, e quando è appropriato eseguire una delle due. Ad esempio, supponiamo che tu abbia un'applicazione che consente ai clienti di configurare in modo univoco un prodotto. L'applicazione può presentare passaggi significativi a cui sono esposti gli utenti. Questi passaggi sono considerati visualizzazioni di pagina? Inoltre, all'interno di ogni fase vi sono attività di microlivello. Queste attività devono essere tracciate come visualizzazioni di pagina?

Cosa succede se vuoi capire il flusso tra le attività, o quali funzioni ottengono più attività? Il problema con RIA è che ogni applicazione è univoca. Sono progettati per imitare azioni realistiche, e poiché le azioni sono relative alla situazione, le possibilità sono infinite. Tuttavia, la maggior parte delle applicazioni presenta alcuni componenti principali: passaggi cardine, funzioni e azioni di micro livello all'interno delle funzionalità. Quindi, mentre ogni applicazione richiede una certa considerazione su cosa specificamente misurare, ci sono alcune generalizzazioni che possono essere applicate al tracciamento RIA.
L'attività a livello di macro in genere costituisce il caricamento dell'applicazione. Questo fornisce informazioni su visite, visitatori, istanze, valore per azioni future e così via. Può e deve anche rappresentare una tappa importante del processo. Una buona regola è che se un'azione RIA modifica l'applicazione di oltre il 50% (o qualsiasi cosa venga considerata un cambiamento significativo dell'esperienza utente o del contenuto), si tratta di un livello macro e deve essere monitorata come una visualizzazione di pagina.
L'attività a più livelli include modifiche inferiori al 50% (o non considerate un cambiamento significativo dell'esperienza utente o del contenuto). Il passaggio tra le selezioni di colore, ad esempio, sarebbe considerato attività di micro livello. Adobe consiglia di tenere traccia dei microlivelli in relazione alle funzioni. Ad esempio, nel caso di alternare tra i colori, è davvero importante capire quali colori sono stati considerati? O è più importante sapere che è stata utilizzata la funzione di selezione del colore? Forse entrambi sono importanti, e in tal caso, catturate entrambi, ma quando misurate l'efficacia di RIA, considerate l'attività a livello di funzionalità più preziosa.

Tutte le attività di micro-livello devono essere tracciate come collegamenti personalizzati con specifiche misurate tramite variabili di traffico associate (prop ed eVar se l'uso deve essere misurato in base a eventi di successo). In questo modo le visualizzazioni di pagina non vengono ingrandite dall’attività di micro livello e viene consentita l’analisi dei percorsi attraverso la variabile di traffico.

## Cosa analizzare {#section_56824EF675874BA99127A566F6B1383F}

È importante capire quanto efficacemente la vostra RIA stia guidando il successo. Il successo è misurato soprattutto attraverso le conversioni. Un'analisi a livello di macro fornisce informazioni approfondite sull'efficacia delle RIA nel suo insieme. L'analisi microlivello può fornire informazioni sulle funzioni che consentono di promuovere la conversione.

È necessario misurare l'efficienza della RIA. Si tratta di un'analisi dell'attività di microlivello relativa alle metriche delle macro RIA. Gli utenti passano attraverso più passaggi del necessario per raggiungere lo stesso obiettivo? Le metriche di analisi possono includere attività visite/funzionalità; visualizzazioni delle pagine/attività delle funzioni, visitatori/attività delle funzioni e così via.

Eseguire l’analisi sul flusso del percorso e uscire. Gli utenti stanno evitando l’RIA e stanno trovando un altro percorso verso l’obiettivo? Eseguire rapporti di abbandono generati intorno al sito e al flusso RIA. Eseguire l'analisi dei percorsi dalle pagine di destinazione per misurare i pattern di traffico effettivi. Osservate le barriere e gli incentivi per guidare gli utenti verso l'obiettivo.

## Metriche suggerite {#section_AB7047D6C74740C6B6E47ED93602DB07}

* Visite RIA
* Visitatori RIA
* Visualizzazioni pagina RIA
* L'attività delle funzioni RIA (collegamenti personalizzati) misura l'attività di clic per funzione

## Analisi suggerita {#section_5BE0FB9ECA3049E5965BEAD733DA5B6E}

* RIA Feature Activity / Visualizzazioni pagina RIA
* RIA Feature Activity / RIA Visite -
* Visualizzazioni pagina RIA / Metrica di successo - Rapporto di conversione: efficacia delle misure di applicazione
* Totale attività RIA/metrica di successo - Rapporto di conversione: efficienza delle applicazioni di misura
* Funzionalità RIA Activity / Metrica Success - Rapporto di conversione: misura dell'efficienza della funzione applicazione
* Flusso percorso da e verso RIA
* Tassi di abbandono attraverso il processo di conversione RIA

