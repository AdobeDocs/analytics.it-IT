---
title: Suite di rapporti globali in Adobe Analytics
description: Comprendere i vantaggi e i requisiti dell’utilizzo di una suite di rapporti globale.
feature: Implementation Basics
exl-id: fa949b1e-80bd-41cf-a294-c840503b568f
role: Admin, Developer, Leader
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '854'
ht-degree: 0%

---

# Considerazioni globali sulla suite di report

Una suite di rapporti globale è una suite di rapporti che raccoglie dati da tutti i domini e le app di proprietà della tua organizzazione. Questa tecnica di raccolta dei dati richiede preparazione e può richiedere il coordinamento tra i team all’interno della tua organizzazione.

## Vantaggi

L’Adobe consiglia di implementare una suite di rapporti globale nella maggior parte dei casi.

* **Dati aggregati:** Le suite di rapporti globali consentono di visualizzare i KPI e gli eventi di successo nei siti di tua proprietà. La segmentazione e le suite di rapporti virtuali possono essere utilizzate per visualizzare dati specifici per il sito.
* **Supporto per Cross-Device Analytics:** CDA richiede una suite di rapporti che raccolga dati da più posizioni, ad esempio dal sito web e dall’app mobile. Dispositivi separati possono unire i dati se implementati correttamente. Consulta [Analytics tra dispositivi](../../components/cda/overview.md) nella guida utente Componenti per ulteriori informazioni.
* **Non è necessaria più di una suite di rapporti:** Tutti i dati possono essere raccolti in una singola suite di rapporti, pertanto è meno probabile che uno sviluppatore invii erroneamente i dati alla suite di rapporti sbagliata.
* **Non è necessario eseguire rollup:** Le aggregazioni dati sono una funzione abbastanza datata che aggrega i dati di singole suite di rapporti su base giornaliera. Le aggregazioni dati non deduplicano i dati relativi a visite o visitatori, il che può portare a numeri gonfiati. Consulta [Rollup](../../admin/admin/c-manage-report-suites/rollup-report-suite.md) per ulteriori informazioni, consulta la guida utente dell’amministratore.
* **Risparmio di tempo:** I progetti Workspace, le classificazioni, i segmenti e le metriche calcolate sono legati alla stessa suite di rapporti globale. Gli amministratori dedicano meno tempo alla gestione di questi componenti e alla governance dei dati.
* **Attribuzione cross-brand più precisa:** Se una visita inizia su un sito e poi fa clic su un altro sito prima di attivare un evento di successo, l’attribuzione viene raccolta in modo accurato. Ad esempio, un visitatore fa clic su un collegamento di ricerca a pagamento e arriva al sito A. Quindi fanno clic su un collegamento al sito B, quindi effettuano un acquisto. Una suite di rapporti globale attribuisce correttamente gli attributi che si riacquistano in ricerca a pagamento.
* **Implementazione semplificata:** Poiché tutti i marchi/siti inviano dati alla stessa suite di rapporti, le implementazioni in ciascun sito sono allineate. Questa governance applicata assicura che una dimensione o metrica specifica venga salvata nello stesso eVar o evento. Amministratori, tester, proprietari della gestione dei tag e analisti traggono vantaggio da questa semplificazione.

>[!NOTE]
>
>Coordinare l’implementazione di una suite di rapporti globale è un progetto di grandi dimensioni. Adobe consiglia di collaborare con un consulente per ridurre le complicazioni e i problemi che possono sorgere.

## Avvio di una nuova implementazione con una suite di rapporti globale

Utilizza le seguenti linee guida generali per comprendere il processo di implementazione di una suite di rapporti globale.

1. Crea la suite di rapporti globale in Adobe Analytics. Consulta [Creare una suite di rapporti](/help/admin/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md) per ulteriori informazioni, consulta la guida utente dell’amministratore.
1. Lavora con i team della tua organizzazione responsabili di ciascun dominio. Molti team hanno requisiti di reporting specifici per la propria area di business.
1. Registra e aggrega tutti questi requisiti in un [Documento di progettazione della soluzione](solution-design.md). Se i team hanno requisiti simili per una dimensione, possono utilizzare la stessa variabile personalizzata. Ad esempio, se il sito A e il sito B richiedono entrambi una dimensione di breadcrumb, le implementazioni per entrambi i siti possono inviare tali dati tramite eVar1.

   >[!IMPORTANT]
   >
   >Assicurati che qualsiasi variabile personalizzata venga utilizzata in modo simile tra i domini. Non utilizzare lo stesso eVar o evento per scopi diversi nei siti.
1. Assicurati che ogni dominio abbia un livello di dati per semplificare la raccolta dati. I dati possono comunque essere raccolti senza un livello di dati, ma l’affidabilità e la longevità dell’implementazione diminuiscono, soprattutto in seguito a riprogettazioni del sito.
1. Utilizza i tag in Adobe Experience Platform per implementare Analytics. Siti diversi richiederanno probabilmente elementi di dati diversi. Utilizza le regole specifiche per ciascun dominio per assicurarti che ogni elemento dati sia compilato correttamente, quindi assegna tali elementi dati alle rispettive eVar ed eventi. Consulta la sezione [panoramica sui tag](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=it).
1. Includi [Servizio Adobe Experience Cloud ID](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it) e utilizza [appendVisitorIDsTo](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/appendvisitorid.html?lang=it) funzione. Questa funzione unisce i dati dei visitatori quando gli utenti fanno clic da un dominio all’altro.

## Modifica di un’implementazione esistente con una suite di rapporti globale

Il processo di spostamento di un’implementazione esistente su più siti in un’unica suite di rapporti globale richiede più tempo e coordinazione tra i team della tua organizzazione.

1. Determina se desideri utilizzare una delle suite di rapporti esistenti o se vuoi iniziare da capo con una nuova suite di rapporti. Se desideri modificare gli utilizzi delle variabili esistenti nell’implementazione, è consigliabile iniziare con una nuova suite di rapporti.
2. Determina una data di cutover per il momento in cui desideri passare a una suite di rapporti globale. Il momento migliore per effettuare un passaggio è tra due periodi di reporting significativi, oppure insieme a modifiche importanti al sito. Alcuni esempi includono l’inizio di un trimestre o anno fiscale, durante un aggiornamento del sito o la modifica a un nuovo sistema di gestione dei tag.
3. Segui i passaggi precedenti (crea una suite di rapporti, raccogli i requisiti di reporting in un documento di progettazione della soluzione e stabilisci un livello dati su ciascun sito). Quando implementi i tag in Adobe Experience Platform, convalida l’implementazione utilizzando una versione di sviluppo del sito web.
4. Dopo aver confermato che l’implementazione funziona sullo sviluppo, invia in tempo reale l’implementazione dei tag alla data di cutover.

## Pagine correlate

[Passaggio dall’assegnazione di tag a più suite a una suite di rapporti globale e a suite di rapporti virtuali](../../components/vrs/vrs-considerations.md)
[Confronto delle aggregazioni dati e delle suite di rapporti globali](../../admin/admin/c-manage-report-suites/rollup-report-suite.md)
