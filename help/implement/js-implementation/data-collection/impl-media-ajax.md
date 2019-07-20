---
description: AJAX è un concetto emergente nella progettazione Web che utilizza più tecnologie per creare e gestire contenuti dinamici sulle pagine Web.
keywords: Implementazione di Analytics
seo-description: AJAX è un concetto emergente nella progettazione Web che utilizza più tecnologie per creare e gestire contenuti dinamici sulle pagine Web.
seo-title: Applicazioni Rich Media per AJAX
solution: Analytics
title: Applicazioni Rich Media per AJAX
topic: Sviluppatore e implementazione
uuid: ffe 6 a 263-ae 18-4875-badb-b 3 aea 3 efcb 64
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Applicazioni Rich Media per AJAX

AJAX è un concetto emergente nella progettazione Web che utilizza più tecnologie per creare e gestire contenuti dinamici sulle pagine Web.

The need to track user interaction with [!UICONTROL AJAX] and other rich media applications is paramount to analytics success and realization of the return on investment in the Web design. The focus of this white paper is to provide recommendations for tracking rich Internet applications, specifically those that use [!UICONTROL AJAX].

## Rich Internet Applications (RIA) {#section_CDCAFC4E05B44985BCBF34DFCB35DCA6}

Le applicazioni Rich Internet (RIA) stanno modificando il volto del Web. Ponte il divario tra la promessa di tecnologie on-demand per le masse e esperienze utente realistiche. Le RIA sono maturate per anni. Il maggior numero di utenti si sono verificati in avanti con l'adozione di browser in scala ampia, che supportano le tecnologie correlate che alimentano queste applicazioni. Anche se l'RIA dispone di molti moduli e tecnologie di supporto, le più comuni e più comuni sono AJAX e Flash. È importante comprendere che la tecnologia non è quella che definisce una RIA, ma la sua usabilità e applicazione.

## What to Track {#section_E96EC5127E554B8384FD0A7A0B3118DF}

Una delle domande più comunemente poste con RIA è la modalità di tracciamento dell'attività di micro livello separata dall'attività a livello di macro, e quando è opportuna l'esecuzione di entrambe. Ad esempio, supponiamo che un'applicazione consenta ai clienti di configurare in modo univoco un prodotto. L'applicazione può presentare passaggi significativi a cui sono esposti gli utenti. Questi passaggi sono considerati visualizzazioni di pagina? Inoltre, all'interno di ogni passaggio sono presenti attività di livello micro-level. Queste attività devono essere tracciate come visualizzazioni di pagina?

Cosa succede se desiderate comprendere il flusso tra attività, o quali funzioni ottenere il maggior numero di attività? I problemi di RIA sono che ogni applicazione è univoca. Sono progettati per simulare azioni realistiche e, poiché le azioni sono relative alla situazione, sono infinite. Tuttavia, la maggior parte delle applicazioni dispone di alcuni componenti principali: passaggi milestone steps, funzioni e azioni di micro livello nelle funzionalità. Pertanto, sebbene ogni applicazione richieda una certa quantità di dati da misurare, alcune generalizzazioni possono essere applicate al tracciamento RIA.
In genere, l'attività a livello di macro rappresenta il caricamento dell'applicazione. Questo fornisce informazioni su visite, visitatori, istanze, valore per azioni future e così via. Può e deve rappresentare anche i passaggi principali del processo. Una regola valida consiste nel fatto che se un'azione RIA modifica l'applicazione più di 50% (o se si considera che cambia in modo significativo l'esperienza o il contenuto dell'utente), è a livello di macro e deve essere tracciata come visualizzazione di pagina.
L'attività di livello Micro include eventuali modifiche inferiori a 50% (o non può essere considerata una modifica significativa dell'esperienza o del contenuto dell'utente). L'attivazione delle selezioni colore, ad esempio, viene considerata attività di micro livello. Adobe consiglia di collegare il monitoraggio a livello di micro-level alle funzionalità. Ad esempio, in caso di attivazione/disattivazione dei colori, è importante capire quali colori sono stati considerati? O è più importante sapere che è stata utilizzata la funzione di selezione del colore? Entrambi sono importanti e, in tal caso, acquisisci entrambi, ma per misurare l'efficacia di RIA, considera l'attività a livello di funzionalità più preziosa.

Tutte le attività di micro livello devono essere tracciate come collegamenti personalizzati con specifiche misurate attraverso variabili di traffico associate (prop ed evar, se l'utilizzo deve essere misurato rispetto agli eventi di successo). In questo modo le visualizzazioni di pagina non vengono inflingate da attività di micro-livello e consentono l'analisi dei percorsi tramite la variabile traffic.

## What to Analyze {#section_56824EF675874BA99127A566F6B1383F}

È importante comprendere con quale efficacia la tua RIA sta guidando il successo. Il successo è maggiormente misurato tramite le conversioni. Un'analisi a livello di macro fornisce informazioni sull'efficacia RIA nel suo complesso. L'analisi a livello di micro può fornire informazioni su quali funzioni contribuiscono alla conversione.

Misura l'efficienza della tua RIA. Si tratta di un'analisi dell'attività di micro livello rispetto alle metriche di macro RIA. Gli utenti passano più passaggi del necessario per raggiungere lo stesso obiettivo? Le metriche di analisi possono includere attività/attività delle caratteristiche; visualizzazioni di pagina/attività delle funzioni, visitatori/attività di funzione e così via.

Condurre analisi sul flusso dei percorsi ed eseguire l'analisi. Gli utenti evitano la RIA e cercano un altro percorso all'obiettivo? Eseguire report di abbandono basati sul sito e sul flusso RIA. Eseguire analisi dei percorsi dalle pagine di destinazione per misurare i pattern di traffico reali. Guardate le barriere e gli incentivi per guidare gli utenti verso l'obiettivo.

## Suggested Metrics {#section_AB7047D6C74740C6B6E47ED93602DB07}

* Visite RIA
* RIA Visitatori
* Visualizzazioni di pagina RIA
* Attività della funzione RIA (collegamenti personalizzati) misura la misurazione dell'attività per funzione

## Suggested Analysis {#section_5BE0FB9ECA3049E5965BEAD733DA5B6E}

* Funzioni RIA/Visualizzazioni pagina RIA
* Attività RIA/Visite RIA -
* Visualizzazioni pagina RIA/Metrica di successo - Rapporto conversione: misura efficacia applicazione
* Totale metrica RIA/Metrica successo - Rapporto conversione: misurazione dell'efficienza dell'applicazione
* Funzione Feature RIA/Success Metric - Conversion Ratio: misurazione dell'efficienza delle funzioni applicazione
* Flusso percorsi da e verso RIA
* Percentuali di abbandono tramite processo di conversione RIA

