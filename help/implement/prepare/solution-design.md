---
title: Creare un documento di progettazione della soluzione
description: Scopri cos’è un documento di progettazione della soluzione e come utilizzarlo nella tua organizzazione.
feature: Implementation Basics
exl-id: 0b5c5ddd-5f53-4790-a649-1381135dacda
role: Admin, Developer, Leader
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '697'
ht-degree: 2%

---

# Creare un documento di progettazione della soluzione

Un documento di progettazione della soluzione (noto anche come Solution Design Reference o documento sui requisiti aziendali) è in sostanza il blueprint dell’implementazione di Analytics. Definisce i criteri identificati dalle parti interessate in tutta l’organizzazione e li traduce in variabili all’interno di Adobe Analytics. Senza una, le organizzazioni hanno difficoltà a coordinare le esigenze di reporting e tendono a perdere la raccolta di dati importanti.

## Prerequisiti

[Convalida l&#39;implementazione di Analytics e pubblica in produzione](../launch/validate-publish-prod.md) - Anche se non è direttamente richiesto, l&#39;Adobe consiglia di implementare un&#39;implementazione di base, in modo da raccogliere i dati critici e al contempo definire e implementare requisiti aziendali aggiuntivi.

## Proprietà e ubicazione del documento di progettazione

* **Determinare chi, all&#39;interno dell&#39;organizzazione, sarà responsabile della gestione del documento di progettazione della soluzione.** Questo ruolo può essere un singolo utente o un team. Assicurati che la manutenzione della progettazione della soluzione sia preservata anche attraverso modifiche dei ruoli o ristrutturazioni dell’organizzazione. Si tratta di un documento vivo e deve essere mantenuto in modo adeguato.
* **Determinare la posizione del documento della soluzione.** Non esiste un&#39;unica posizione ottimale per i documenti di progettazione delle soluzioni, ma in genere si trovano in una posizione interna ampiamente accessibile. Alcuni esempi includono un foglio di calcolo condiviso o un’area di lavoro collaborativa come SharePoint o un wiki interno. Non deve essere modificabile per tutti, ma è utile per coloro che possono accedere ai rapporti almeno per poterlo visualizzare.

## Definire i requisiti aziendali

Quando si determinano i dati da raccogliere, è facile dire &quot;tutto&quot;, tuttavia ciò può diventare rapidamente difficile da gestire e può persino fornire meno valore rispetto alla raccolta di quantità più concise di dati.

1. **Determinare gli indicatori di prestazioni chiave.** Come desideri che facciano i visitatori? La risposta a questa domanda varia a seconda del settore e del settore verticale, e può essere molteplici. Alcuni esempi includono acquisti, registrazioni o clic sugli annunci.
1. **Individuare i dati più importanti da raccogliere.** Poni alle domande di lavoro a cui desideri risposte specifiche. Le risposte a queste domande fornirebbero approfondimenti su come migliorare i KPI.
1. **Rispondi a queste domande e determina quali sono le tue esigenze di tracciamento.** raggrupparle in dimensioni e metriche.
   * I Dimension sono variabili che contengono testo. Alcuni esempi includono il termine di ricerca interno, la categoria di prodotto o il nome di un’area su cui un visitatore ha fatto clic.
   * Le metriche sono eventi specifici che desideri che un visitatore faccia: quando esegui un’azione desiderata, il numero aumenta di uno. Alcuni esempi includono l’invio di un ordine, l’abbonamento a una newsletter o l’invio di una risposta al sondaggio.
1. **Mappare dimensioni e metriche in una pagina o in un foglio di calcolo.** Questa pagina o tabella diventa il documento di progettazione della soluzione. Alcune colonne o punti elenco utili da includere:
   * Stato di implementazione: pianificato, attivo, inattivo, problemi, ecc. In questo modo gli utenti del documento verranno informati sullo stato della variabile, se è stata implementata o se si verificano problemi con la raccolta dei dati.
   * Nome della variabile: ad esempio, &quot;Termini di ricerca interni&quot;. Questo valore corrisponderebbe a quello visualizzato dagli analisti quando lavorano in Analytics.
   * Variabile di Analytics mappata a: la variabile di Analytics predefinita o personalizzata a cui scegli di assegnare i valori. I Dimension in genere rientrano nelle eVar, mentre le metriche rientrano negli eventi.
   * Logica: una descrizione dell’impostazione della variabile e di ciò che ne determina il valore. Ad esempio, &quot;Imposta solo sulle pagine di ricerca interne. Accetta il valore del parametro della stringa di query q.&quot;
   * Qualsiasi altra nota che desideri includere relativa alla variabile

## Risorse aggiuntive

La definizione di un documento di progettazione della soluzione è un progetto piuttosto complesso, soprattutto per le organizzazioni che non ne hanno mai creato uno prima. Se desideri ulteriore assistenza, Adobe fornisce consulenza specializzata per aiutarti a rendere operativa la tua organizzazione con Adobe Analytics. Contatta il team del tuo account Adobe se desideri integrare i servizi professionali di Adobe. È possibile compilare un [questionario tecnico di pre-implementazione](assets/technical-pre-implementation-questionnaire.pdf) in modo che Adobe sappia esattamente come aiutarti in base alle esigenze della tua organizzazione.

Ci sono anche diversi partner di Adobi specializzati nell’assistenza per la creazione di un documento di progettazione della soluzione e nell’implementazione di Adobe Analytics sul sito.

## Passaggi successivi

Implementa le variabili nel documento di progettazione della soluzione.

[Creare un livello dati](data-layer.md): traduci le variabili nel documento di progettazione in variabili JavaScript sul sito.
