---
title: Suite di rapporti globali in Adobe Analytics
description: Scopri i vantaggi e i requisiti dell’utilizzo di una suite di rapporti globale.
feature: Implementation Basics
exl-id: fa949b1e-80bd-41cf-a294-c840503b568f
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '871'
ht-degree: 1%

---

# Considerazioni globali sulla suite di report

Una suite di rapporti globale è una suite di rapporti che raccoglie dati da tutti i domini e le app di proprietà della tua organizzazione. Questa tecnica di raccolta dati richiede preparazione e può richiedere il coordinamento tra i team all’interno della tua organizzazione.

## Vantaggi

Nella maggior parte dei casi, Adobe consiglia di implementare una suite di rapporti globale.

* **Dati aggregati:** Le suite di rapporti globali consentono di visualizzare gli eventi KPI e di successo nei siti di proprietà. La segmentazione e le suite di rapporti virtuali possono essere utilizzate per visualizzare dati specifici per il sito.
* **Supporto per Analytics tra dispositivi:** CDA richiede una suite di rapporti che raccoglie dati da più posizioni, come il tuo sito web e l’app mobile. Se implementati correttamente, dispositivi separati possono unire i dati. Vedi [Analisi multidispositivo](../../components/cda/overview.md) nella guida utente Componenti per ulteriori informazioni.
* **Non è necessaria più di una suite di rapporti:** Tutti i dati possono essere raccolti in una singola suite di rapporti, pertanto è meno probabile che uno sviluppatore invii erroneamente i dati alla suite di rapporti sbagliata.
* **Non è necessario eseguire il rollup:** I rollup sono una funzione datata che aggrega quotidianamente i dati delle singole suite di rapporti. I rollup non deduplicano i dati di visite o visitatori, il che può causare numeri in eccesso. Vedi [Rollup](../../admin/c-manage-report-suites/rollup-report-suite.md) nella guida utente di Admin per ulteriori informazioni.
* **Risparmia tempo:** I progetti, le classificazioni, i segmenti e le metriche calcolate dell’area di lavoro sono legati alla stessa suite di rapporti globale. Gli amministratori dedicano meno tempo alla gestione di questi componenti e alla governance dei dati.
* **Attribuzione più precisa tra marchi:** Se una visita inizia su un sito e poi fa clic su un altro sito di proprietà prima di attivare un evento di successo, l’attribuzione viene raccolta accuratamente. Ad esempio, un visitatore fa clic su un collegamento di ricerca a pagamento e arriva al sito A. Quindi fa clic su un collegamento al sito B, quindi effettua un acquisto. Una suite di rapporti globale attribuisce correttamente l’acquisto alla ricerca a pagamento.
* **Implementazione semplificata:** Poiché tutti i marchi/siti inviano dati alla stessa suite di rapporti, le tue implementazioni in ciascun sito sono allineate. Questa governance forzata assicura che una dimensione o metrica specifica venga salvata nello stesso eVar o evento. Questa semplificazione si applica agli amministratori, ai tester, ai proprietari della gestione dei tag e agli analisti.

>[!NOTE]
>
>Coordinare un’implementazione globale della suite di rapporti è un progetto di grandi dimensioni. L&#39;Adobe consiglia di lavorare con un consulente per ridurre le complicazioni e i problemi che insorgono.

## Avvio di una nuova implementazione con una suite di rapporti globale

Segui le seguenti linee guida generali per comprendere il processo di implementazione di una suite di rapporti globale.

1. Crea la suite di rapporti globale in Adobe Analytics. Vedi [Creare una suite di rapporti](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md) nella guida utente di Admin per ulteriori informazioni.
1. Collabora con i team della tua organizzazione responsabili per ogni dominio. Molti team hanno requisiti di reporting specifici per la propria area di attività.
1. Registra e aggrega tutti questi requisiti in un [Documento di progettazione della soluzione](solution-design.md). Se i team hanno requisiti simili per una dimensione, possono utilizzare la stessa variabile personalizzata. Ad esempio, se sia il sito A che il sito B richiedono una dimensione di breadcrumb, le implementazioni per entrambi i siti possono inviare tali dati tramite eVar1.

   >[!IMPORTANT]
   >
   >Assicurati che qualsiasi variabile personalizzata sia utilizzata in modo simile tra i domini. Non utilizzare lo stesso eVar o evento per scopi diversi nei siti.
1. Assicurati che ogni dominio abbia un livello dati per semplificare la raccolta dati. I dati possono ancora essere raccolti senza un livello di dati, ma l’affidabilità e la longevità dell’implementazione diminuiscono, soprattutto quando il sito viene riprogettato.
1. Utilizza i tag in Adobe Experience Platform per implementare Analytics. Siti diversi richiederanno probabilmente elementi di dati diversi. Utilizza regole specifiche per ciascun dominio per assicurarti che ogni elemento dati sia popolato correttamente, quindi assegna tali elementi dati ai rispettivi eVar ed eventi. Fai riferimento a [panoramica dei tag](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=it).
1. Includi il [Servizio Adobe Experience Cloud ID](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it) e utilizza [appendVisitorIDsTo](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/appendvisitorid.html) funzione . Questa funzione unisce i dati del visitatore quando gli utenti fanno clic da un dominio a un altro.

## Modifica di un’implementazione esistente con una suite di rapporti globale

Il processo di spostamento di un’implementazione esistente tra più siti in un’unica suite di rapporti globale richiede più tempo e coordinamento tra i team dell’organizzazione.

1. Determina se desideri utilizzare una delle suite di rapporti esistenti o inizia con una nuova suite di rapporti. Se desideri modificare gli usi per le variabili esistenti nell’implementazione, è consigliabile iniziare con una nuova suite di rapporti.
2. Determina una data limite per passare a una suite di rapporti globale. Il momento migliore per eseguire un cutover è tra due periodi di reporting significativi o insieme a modifiche importanti al sito. Gli esempi includono l&#39;inizio di un trimestre o di un anno fiscale, durante un aggiornamento del sito o il passaggio a un nuovo sistema di gestione dei tag.
3. Segui i passaggi indicati in precedenza (crea una suite di rapporti, raccogli i requisiti di reporting in un documento di progettazione della soluzione e stabilisci un livello di dati su ciascun sito). Quando implementi i tag in Adobe Experience Platform, convalida l’implementazione utilizzando una versione di sviluppo del sito web.
4. Dopo aver confermato che l’implementazione funziona su dev, invia l’implementazione dei tag in tempo reale alla data di consegna.

## Pagine correlate

[Passaggio dall’assegnazione tag a più suite a una suite di rapporti globale e a suite di rapporti virtuali](../../components/vrs/vrs-considerations.md)
[Confronto di rollup e suite di rapporti globali](../../admin/c-manage-report-suites/rollup-report-suite.md)
