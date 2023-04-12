---
title: Creare un documento di progettazione della soluzione
description: Scopri cos’è un documento di progettazione della soluzione e come utilizzarlo nell’organizzazione.
feature: Implementation Basics
exl-id: 0b5c5ddd-5f53-4790-a649-1381135dacda
source-git-commit: 34ba0e09cd909951a777b0ad3da080958633f97e
workflow-type: tm+mt
source-wordcount: '697'
ht-degree: 2%

---

# Creare un documento di progettazione della soluzione

Un documento di progettazione della soluzione (noto anche come documento di riferimento per la progettazione della soluzione o per i requisiti aziendali) è in sostanza il modello di implementazione di Analytics. Definisce i criteri identificati dalle parti interessate in tutta l’organizzazione e li traduce in variabili in Adobe Analytics. Senza di essa, le organizzazioni hanno tempi difficili nel coordinare le esigenze di reporting e tendono a perdere la raccolta di dati importanti.

## Prerequisiti

[Convalidare l’implementazione di Analytics e pubblicare in produzione](../launch/validate-publish-prod.md) - Sebbene non sia direttamente richiesto, l&#39;Adobe raccomanda l&#39;implementazione di base per la raccolta di dati critici mentre vengono stabiliti e implementati ulteriori requisiti aziendali.

## Proprietà e ubicazione del documento di progettazione

* **Stabilisci chi all’interno della tua organizzazione sarà responsabile della manutenzione del documento di progettazione della soluzione.** Questo ruolo può essere individuale o team. Assicurati che la manutenzione della progettazione della soluzione sia preservata anche attraverso modifiche dei ruoli o ristrutturazioni dell&#39;organizzazione. Si tratta di un documento vivo e deve essere adeguatamente conservato.
* **Stabilisci dove risiederà il documento della soluzione.** Non esiste un unico posto ideale per la conservazione dei documenti di progettazione della soluzione, ma generalmente si trovano in una posizione interna ampiamente accessibile. Alcuni esempi includono un foglio di lavoro condiviso o un&#39;area di lavoro collaborativa come SharePoint o un wiki interno. Non è necessario che sia modificabile per tutti, ma è vantaggioso per coloro che possono accedere alla segnalazione per almeno essere in grado di visualizzarla.

## Definizione dei requisiti aziendali

Nel determinare quali dati raccogliere, è facile dire &quot;tutto&quot;, tuttavia che può rapidamente diventare ingombrante da gestire, e può anche fornire meno valore della raccolta più concisa quantità di dati.

1. **Determina gli indicatori prestazioni chiave.** Cosa desideri che facciano in definitiva i visitatori? La risposta a questa domanda varia a seconda dell&#39;industria e del settore verticale, e può essere molteplici. Alcuni esempi includono acquisti, registrazioni o clic su annunci.
1. **Scopri i dati più importanti da raccogliere.** Fai domande aziendali a cui desideri risposte specifiche. Le risposte a queste domande forniscono informazioni su come migliorare i KPI.
1. **Prendi queste domande e stabilisci quali sono le tue esigenze di tracciamento.** Raggruppali in dimensioni e metriche.
   * I Dimension sono variabili che contengono testo. Gli esempi includono il termine di ricerca interno, la categoria di prodotto o il nome di un’area su cui un visitatore ha fatto clic.
   * Le metriche sono eventi specifici che un visitatore deve fare: quando esegue un’azione desideri, il numero aumenta di uno. Ad esempio, l’invio di un ordine, l’abbonamento a una newsletter o l’invio di una risposta a un sondaggio.
1. **Mappare dimensioni e metriche in una pagina o in un foglio di calcolo.** Questa pagina o tabella diventa in definitiva il documento di progettazione della soluzione. Alcune colonne o punti elenco utili includono:
   * Stato di implementazione: Pianificato, attivo, inattivo, problemi, ecc. In questo modo si informa il visualizzatore del documento dello stato della variabile, se è stata implementata, o se si verificano problemi con la raccolta dei dati.
   * Nome della variabile: Ad esempio, &quot;Termini di ricerca interna&quot;. Questo valore è ciò che gli analisti vedono quando lavorano in Analytics.
   * Variabile di Analytics mappata a: A quale variabile predefinita o personalizzata di Analytics si sceglie di assegnare i valori. I Dimension in genere rientrano in eVar, mentre le metriche rientrano in eventi .
   * Logica: Descrizione dell’impostazione della variabile e del relativo valore. Ad esempio, &quot;Impostato solo sulle pagine di ricerca interne. Prende il valore del parametro della stringa query q.&quot;
   * Qualsiasi altra nota che desideri includere relativa alla variabile

## Risorse aggiuntive

La definizione di un documento di progettazione della soluzione è un progetto piuttosto complesso, soprattutto per le organizzazioni che non ne hanno creato uno prima. Se desideri ricevere ulteriore assistenza, Adobe fornisce consulenza specializzata per aiutarti a far iniziare la tua organizzazione con Adobe Analytics. Contatta il team dell&#39;account Adobe per accedere ai servizi professionali di Adobe. A [Questionario tecnico di pre-attuazione](assets/technical-pre-implementation-questionnaire.pdf) può essere compilato in modo che l’Adobe sappia esattamente come aiutare in base alle esigenze della tua organizzazione.

Esistono anche diversi partner di Adobe specializzati nella creazione di un documento di progettazione della soluzione e nell’implementazione di Adobe Analytics sul sito.

## Passaggi successivi

Implementa le variabili nel documento di progettazione della soluzione.

[Creare un livello di dati](data-layer.md): Traduci le variabili nel documento di progettazione in variabili JavaScript sul sito.
