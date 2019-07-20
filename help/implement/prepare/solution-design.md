---
title: Creare un documento di progettazione della soluzione
seo-title: Creare un documento di progettazione della soluzione
description: Scopri il documento di progettazione della soluzione e come usarlo nell'organizzazione.
seo-description: Scopri il documento di progettazione della soluzione e come usarlo nell'organizzazione.
translation-type: tm+mt
source-git-commit: d195fb85711f58383577bf1d7b4da4078b909427

---


# Creare un documento di progettazione della soluzione

Un documento di progettazione della soluzione (noto anche come riferimento di progettazione della soluzione o di requisiti aziendali) è sostanzialmente il blueprint dell'implementazione dell'analisi. Definisce i criteri identificati dalle parti interessate all'interno dell'organizzazione e li converte in variabili all'interno di Adobe Analytics. Senza una, le organizzazioni hanno un tempo difficile per coordinare le esigenze di reporting e tendono a perderne la raccolta.

## Prerequisiti

[Convalida dell'implementazione e della pubblicazione di Analytics per la produzione](../implement-with-launch/validate-publish-prod.md) - Anche se non direttamente necessario, Adobe consiglia di disporre di un'implementazione di base per la raccolta di dati critici, in modo da determinare e implementare i dati di business aggiuntivi.

## Proprietà e posizione del documento di progettazione

* **Determinare chi sarà responsabile della gestione del documento della progettazione della soluzione.** Questo ruolo può essere un singolo o un team. Assicuratevi che mantenere la progettazione della soluzione sia mantenuto anche attraverso modifiche di ruolo o riorganizzazione aziendale. È un documento live e deve essere mantenuto correttamente.
* **Determinare dove risiederà il documento della soluzione.** Non esiste una posizione ottimale per la posizione dei documenti della progettazione della soluzione, ma in genere risiedono in una posizione interna accessibile a livello globale. Gli esempi includono un foglio di lavoro condiviso o un'area di lavoro collaborativa come sharepoint o un wiki interno. Non deve essere modificabile per tutti, ma è vantaggioso per coloro che possono accedere ai rapporti almeno in grado di visualizzarli.

## Definire i requisiti di business

Quando si determinano i dati da raccogliere, è facile dire «tutto», che può rapidamente diventare difficoltoso per gestire e persino ottenere meno valore rispetto alla raccolta di quantità più concise di dati.

1. **Individua gli indicatori prestazioni chiave.** Cosa desiderate fare ai visitatori? La risposta a questa domanda varia in base al settore e al settore verticale e può essere più semplice. Gli esempi includono acquisti, registrazioni o clic di annunci.
1. **Scopri i dati più importanti da raccogliere.** Ponete domande di business a cui desiderate risposte specifiche. Le risposte a queste domande forniscono informazioni su come migliorare i KPI.
1. **Prendi queste domande e determinate le tue esigenze di tracciamento.** Raggruppateli in dimensioni e metriche.
   * Le dimensioni sono variabili che contengono testo. Esempi includeranno termine di ricerca interno, categoria di prodotti o nome dell'area su cui un visitatore ha fatto clic.
   * Le metriche sono eventi specifici che desideri che un visitatore faccia: quando eseguono un'azione che desideri, il numero arriva in alto. Esempi includono l'invio di un ordine, l'iscrizione a una newsletter o l'invio di una risposta sondaggio.
1. **Mappare dimensioni e metriche in una pagina o in un foglio di calcolo.** Questa pagina o tabella diventa in ultima analisi il documento della tua soluzione. Alcune colonne o punti bullet utili da includere:
   * Stato di implementazione: Pianificato, attivo, inattivo, edizioni, ecc. Questo informa i visualizzatori del documento sullo stato della variabile, se è stato implementato, o in caso di problemi con la raccolta di dati.
   * Nome variabile: Ad esempio, «Termini di ricerca interni». Questo valore è ciò che analizza gli analisti quando lavori in Analytics.
   * Variabile Analytics mappata su: A quale variabile di Analytics predefinita o personalizzata potete assegnare i valori. Le dimensioni in genere rientrano in evar, mentre le metriche rientrano in eventi.
   * Logica: Una descrizione della modalità di impostazione della variabile e il relativo valore. Ad esempio, «Set only on internal search pages. Prende il valore del parametro della stringa query d. "
   * Qualsiasi altra nota che desideri includere nella variabile

## Risorse aggiuntive

La definizione di un documento di progettazione della soluzione è un progetto piuttosto complesso, in particolare per le organizzazioni che non ne hanno già creato uno. Se desiderate ulteriore assistenza, Adobe fornisce consulenza specializzata per aiutarvi a iniziare a usare Adobe Analytics. Contatta l'Account Manager se desideri iscrivere i servizi professionali di Adobe. A [Technical pre-implementation questionnaire](assets/technical-pre-implementation-questionnaire.pdf) can be filled out so Adobe knows exactly how to help based on your organization's needs.

Esistono anche diversi partner Adobe specializzati nell'Aiuto per la creazione di un documento di progettazione della soluzione, nonché per implementare Adobe Analytics sul sito.

> [!NOTE] I membri della community Analytics hanno scoperto i seguenti collegamenti utili, non sono di proprietà di Adobe. Prendere in considerazione questa nota durante la visualizzazione del contenuto.

* [7 Passaggi per configurare la progettazione della soluzione Web Analytics](https://resources.observepoint.com/blog/7-steps-solution-design-data-governance) da visitepoint
* [Un framework per il processo di analisi digitale](https://analyticsdemystified.com/analytics-strategy/framework-digital-analytics-process/) di Analytics Demystified
* [The Solution Design Reference is actually your BFF](http://numericanalytics.com/why-a-simple-piece-of-documentation-is-the-key-to-analytics-success-the-solution-design-reference-is-actually-your-bff/) by Numeric Analytics
* [Come fare per associare la mappa tag di Adobe Analytics](http://www.anttikoski.fi/how-to-make-adobe-analytics-tagging-map-aka-solution-design-requirements-for-sitecatalyst-implementation/) ad Antti Koski
* [Importanza del documento Progettazione della soluzione](https://www.ebiquity.com/news-insights/analytics/the-importance-of-the-solution-design-document) per Ebiquity

## Passaggi successivi

Implementare le variabili nel documento della progettazione della soluzione.

* Introduzione alle evar: Scopri come funziona un evar, come funziona e come usarne uno nell'implementazione
* Introduzione agli eventi: Scopri come funziona un evento di successo, come funziona e come usarne uno nell'implementazione
