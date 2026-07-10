---
title: Suite di rapporti globali in Adobe Analytics
description: Comprendere i vantaggi e i requisiti dell’utilizzo di una suite di rapporti globale.
feature: Implementation Basics
exl-id: fa949b1e-80bd-41cf-a294-c840503b568f
role: Admin, Developer, Leader
TQID: https://experienceleague.adobe.com/Y96K5iwjDCqXBzMeYVGJA06e115acL3aZOJl8oCBBEs
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b0ca67c6-0a35-482c-ad91-baac1bcb26d6id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7aid: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: c8add8f2-4250-4fd9-9cde-9707036c567did: df312454-73c4-43f6-a90e-18f5043f074cid: e7d92df1-c5ba-4e93-85df-f83171b889beid: f1f1a2d4-0976-4881-b091-c2bb8de7ffacid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: f8a45b24-4be7-4f1b-909b-60d06b483a20id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a947d2d7f45d4155a61cbfe0f8110851cca32e60
workflow-type: tm+mt
source-wordcount: 885
ht-degree: 3%

---

# Considerazioni globali sulla suite di rapporti

Una suite di rapporti globale è una suite di rapporti che raccoglie dati da tutti i domini e le app di proprietà della tua organizzazione. Questa tecnica di raccolta dei dati richiede preparazione e può richiedere il coordinamento tra i team all’interno della tua organizzazione.

## Vantaggi

Nella maggior parte dei casi, Adobe consiglia di implementare una suite di rapporti globale.

* **Dati aggregati:** le suite di rapporti globali ti consentono di visualizzare i KPI e gli eventi di successo nei tuoi siti di proprietà. La segmentazione e le suite di rapporti virtuali possono essere utilizzate per visualizzare dati specifici per il sito.
* **Supporto per Cross-Device Analytics:** CDA richiede una suite di rapporti che raccolga dati da più posizioni, ad esempio dal sito Web e dall&#39;app mobile. Dispositivi separati possono unire i dati se implementati correttamente. Per ulteriori informazioni, consulta [Analisi multidispositivo](../../components/cda/overview.md) nella guida utente dei componenti.
* **Non è necessaria più di una suite di rapporti:** Tutti i dati possono essere raccolti in una singola suite di rapporti, pertanto è meno probabile che uno sviluppatore invii erroneamente i dati alla suite di rapporti sbagliata.
* **Non è necessario eseguire rollup:** le rollup sono una funzione abbastanza datata che aggrega i dati di singole suite di rapporti su base giornaliera. Le aggregazioni dati non deduplicano i dati relativi a visite o visitatori, il che può portare a numeri gonfiati. Per ulteriori informazioni, consulta [Rollup](../../admin/tools/manage-rs/rollup-report-suite.md) nella guida utente dell&#39;amministratore.
* **Risparmio di tempo:** i progetti, le classificazioni, i segmenti e le metriche calcolate di Workspace sono associati alla stessa suite di rapporti globale. Gli amministratori dedicano meno tempo alla gestione di questi componenti e alla governance dei dati.
* **Attribuzione cross-brand più precisa:** se una visita inizia su un sito e poi fa clic su un altro sito prima di attivare un evento di successo, l&#39;attribuzione viene raccolta in modo accurato. Ad esempio, un visitatore fa clic su un collegamento di ricerca a pagamento e arriva al sito A. Quindi fanno clic su un collegamento al sito B, quindi effettuano un acquisto. Una suite di rapporti globale attribuisce correttamente gli attributi che si riacquistano in ricerca a pagamento.
* **Implementazione semplificata:** poiché tutti i marchi/siti inviano dati alla stessa suite di rapporti, le implementazioni in ogni sito sono allineate. Questa governance applicata assicura che una dimensione o metrica specifica sia salvata nello stesso eVar o evento. Amministratori, tester, proprietari della gestione dei tag e analisti traggono vantaggio da questa semplificazione.

>[!NOTE]
>
>Coordinare l’implementazione di una suite di rapporti globale è un progetto di grandi dimensioni. Adobe consiglia di collaborare con un consulente per ridurre le complicazioni e i problemi che possono sorgere.

## Avvio di una nuova implementazione con una suite di rapporti globale

Utilizza le seguenti linee guida generali per comprendere il processo di implementazione di una suite di rapporti globale.

1. Crea la suite di rapporti globale in Adobe Analytics. Per ulteriori informazioni, consulta [Creare una suite di rapporti](/help/admin/tools/manage-rs/new-rs/t-create-a-report-suite.md) nella guida utente dell&#39;amministratore.
1. Lavora con i team della tua organizzazione responsabili di ciascun dominio. Molti team hanno requisiti di reporting specifici per la propria area di business.
1. Registra e aggrega tutti questi requisiti in un [documento di progettazione della soluzione](solution-design.md). Se i team hanno requisiti simili per una dimensione, possono utilizzare la stessa variabile personalizzata. Ad esempio, se il sito A e il sito B richiedono entrambi una dimensione di breadcrumb, le implementazioni per entrambi i siti possono inviare tali dati tramite eVar1.

   >[!IMPORTANT]
   >
   >Assicurati che qualsiasi variabile personalizzata venga utilizzata in modo simile tra i domini. Non utilizzare lo stesso eVar o evento per scopi diversi nei siti.
1. Assicurati che ogni dominio abbia un livello di dati per semplificare la raccolta dati. I dati possono comunque essere raccolti senza un livello di dati, ma l’affidabilità e la longevità dell’implementazione diminuiscono, soprattutto in seguito a riprogettazioni del sito.
1. Utilizza i tag in Adobe Experience Platform per implementare Analytics. Siti diversi richiederanno probabilmente elementi di dati diversi. Utilizza le regole specifiche per ciascun dominio per assicurarti che ogni elemento dati sia compilato correttamente, quindi assegna tali elementi dati alle rispettive eVar ed eventi. Consulta la [panoramica dei tag](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=it).
1. Includi il [servizio ID visitatore di Adobe](https://experienceleague.adobe.com/en/docs/id-service/using/home) e utilizza la funzione [`appendVisitorIDsTo`](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/appendvisitorid.html?lang=it). Questa funzione unisce i dati dei visitatori quando gli utenti fanno clic da un dominio all’altro.

## Modifica di un’implementazione esistente con una suite di rapporti globale

Il processo di spostamento di un’implementazione esistente su più siti in un’unica suite di rapporti globale richiede più tempo e coordinazione tra i team della tua organizzazione.

1. Determina se desideri utilizzare una delle suite di rapporti esistenti o se vuoi iniziare da capo con una nuova suite di rapporti. Se desideri modificare gli utilizzi delle variabili esistenti nell’implementazione, è consigliabile iniziare con una nuova suite di rapporti.
2. Determina una data di cutover per il momento in cui desideri passare a una suite di rapporti globale. Il momento migliore per effettuare un passaggio è tra due periodi di reporting significativi, oppure insieme a modifiche importanti al sito. Alcuni esempi includono l’inizio di un trimestre o anno fiscale, durante un aggiornamento del sito o la modifica a un nuovo sistema di gestione dei tag.
3. Segui i passaggi precedenti (crea una suite di rapporti, raccogli i requisiti di reporting in un documento di progettazione della soluzione e stabilisci un livello dati su ciascun sito). Quando implementi i tag in Adobe Experience Platform, convalida l’implementazione utilizzando una versione di sviluppo del sito web.
4. Dopo aver confermato che l’implementazione funziona sullo sviluppo, invia in tempo reale l’implementazione dei tag alla data di cutover.

>[!MORELIKETHIS]
>
>[Passaggio dall&#39;assegnazione di tag a più suite a una suite di rapporti globale e a suite di rapporti virtualiConfronto delle aggregazioni dati e delle suite di rapporti globali](../../admin/tools/manage-rs/rollup-report-suite.md)
