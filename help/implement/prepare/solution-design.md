---
title: Creare un documento di progettazione della soluzione
description: Scopri cos’è un documento di progettazione della soluzione e come utilizzarlo nell’organizzazione.
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Creare un documento di progettazione della soluzione

Un documento di progettazione della soluzione (noto anche come documento di riferimento per la progettazione della soluzione o per i requisiti aziendali) è in sostanza il progetto di implementazione dell'analisi. Definisce i criteri identificati dai soggetti interessati nell’organizzazione e li traduce in variabili in Adobe Analytics. Senza di esso, le organizzazioni hanno un tempo difficile nel coordinare le esigenze di reporting e tendono a perdere la raccolta di dati importanti.

## Prerequisiti

[Convalidare l'implementazione di Analytics e pubblicarla in produzione](../implement-with-launch/validate-publish-prod.md) - Anche se non è direttamente necessaria, Adobe consiglia di implementare un'implementazione di base per raccogliere dati critici mentre vengono stabiliti e implementati ulteriori requisiti aziendali.

## Proprietà e posizione del documento di progettazione

* **Determinare chi sarà responsabile nella tua organizzazione per la manutenzione del documento di progettazione della soluzione.** Questo ruolo può essere un singolo o un team. Assicurati che la manutenzione della progettazione della soluzione sia preservata anche attraverso modifiche dei ruoli o ristrutturazioni dell'organizzazione. Si tratta di un documento vivo e deve essere mantenuto in modo adeguato.
* **Stabilire dove risiederà il documento della soluzione.** Non esiste un'unica soluzione ideale per i documenti di progettazione della soluzione, ma generalmente vivono in una posizione interna ampiamente accessibile. Alcuni esempi includono un foglio di calcolo condiviso o un'area di lavoro collaborativa come SharePoint o un wiki interno. Non è necessario che sia modificabile per tutti, ma è vantaggioso per coloro che possono accedere ai rapporti per almeno essere in grado di visualizzarli.

## Definizione dei requisiti aziendali

Nel determinare quali dati raccogliere, è facile dire "tutto", ma che può rapidamente diventare ingombrante da gestire, e può anche fornire meno valore rispetto alla raccolta più concisa quantità di dati.

1. **Determinare gli indicatori prestazioni chiave.** Cosa volete che facciano i visitatori? La risposta a questa domanda varia a seconda dell'industria e del settore verticale e può essere composta da più elementi. Alcuni esempi includono acquisti, registrazioni o clic di annunci.
1. **Scopri i dati più importanti da raccogliere.** Fai domande aziendali alle quali vuoi trovare risposte specifiche. Le risposte a queste domande fornirebbero informazioni approfondite su come migliorare i KPI.
1. **Fai queste domande e determina quali sono le tue esigenze di tracciamento.** Raggruppali in dimensioni e metriche.
   * Le dimensioni sono variabili che contengono testo. Esempi possono includere termini di ricerca interni, categoria di prodotti o il nome di un'area su cui un visitatore ha fatto clic.
   * Le metriche sono eventi specifici che un visitatore deve fare: quando esegue un’azione desiderata, il numero aumenta di uno. Ad esempio, è possibile inviare un ordine, iscriversi a una newsletter o inviare una risposta a un sondaggio.
1. **Mappare dimensioni e metriche in una pagina o in un foglio di calcolo.** Questa pagina o questa tabella diventa in definitiva il documento di progettazione della soluzione. Alcune colonne o punti elenco utili includono:
   * Stato di implementazione: Pianificati, attivi, inattivi, problemi ecc. In questo modo si informano gli utenti del documento sullo stato della variabile, se questa è stata implementata o se si verificano problemi con la raccolta dei dati.
   * Nome variabile: Ad esempio, "Termini di ricerca interna". Questo valore è ciò che gli analisti vedono quando lavorano in Analytics.
   * Variabile di Analytics mappata a: Specifica la variabile Analytics predefinita o personalizzata a cui assegnare i valori. Le dimensioni in genere rientrano in eVar, mentre le metriche rientrano in eventi.
   * Logica: Una descrizione di come viene impostata la variabile e di cosa ne determina il valore. Ad esempio, "Set only on internal search pages. Prende il valore del parametro della stringa query q."
   * Eventuali altre note che si desidera includere relative alla variabile

## Risorse aggiuntive

La definizione di un documento di progettazione della soluzione è un progetto piuttosto complesso, soprattutto per le organizzazioni che non ne hanno creato uno precedente. Se si desidera ulteriore assistenza, Adobe fornisce consulenza specializzata per consentirvi di iniziare a utilizzare Adobe Analytics. Contatta il tuo Account Manager per richiedere i servizi professionali di Adobe. È possibile compilare un questionario [di pre-implementazione](assets/technical-pre-implementation-questionnaire.pdf) tecnica in modo che Adobe sappia esattamente come fornire assistenza in base alle esigenze aziendali.

Esistono anche diversi partner Adobe specializzati nella creazione di documenti per la progettazione di una soluzione e nell'implementazione di Adobe Analytics sul sito.

> [!NOTE] Sebbene i membri della comunità Analytics abbiano trovato utili i seguenti collegamenti, non sono di proprietà di Adobe. Tenete presente questa nota quando ne visualizzate il contenuto.

* [7 Passaggi per configurare la progettazione](https://resources.observepoint.com/blog/7-steps-solution-design-data-governance) della soluzione Web Analytics tramite ObservePoint
* [Framework for Digital Analytics Process](https://analyticsdemystified.com/analytics-strategy/framework-digital-analytics-process/) by Analytics Demystified
* [Il riferimento alla progettazione della soluzione è in realtà il vostro BFF](http://numericanalytics.com/why-a-simple-piece-of-documentation-is-the-key-to-analytics-success-the-solution-design-reference-is-actually-your-bff/) by Numeric Analytics
* [Come creare una mappa](http://www.anttikoski.fi/how-to-make-adobe-analytics-tagging-map-aka-solution-design-requirements-for-sitecatalyst-implementation/) dei tag di Adobe Analytics da Antti Koski
* [Importanza del documento](https://www.ebiquity.com/news-insights/analytics/the-importance-of-the-solution-design-document) di progettazione della soluzione da parte di Ebiquity

## Passaggi successivi

Implementa le variabili nel documento di progettazione della soluzione.

* Introduzione alle eVar: Scopri cos'è un'eVar, come funziona e come utilizzarne una nell'implementazione
* Introduzione agli eventi: Scopri cos’è un evento di successo, come funziona e come utilizzarlo nell’implementazione
