---
title: Suite di rapporti globali in Adobe  Analytics
description: Scopri i vantaggi e i requisiti di una suite di rapporti globale.
translation-type: tm+mt
source-git-commit: 9704267cd3ebf480facd68f6cca44167b1d9686d
workflow-type: tm+mt
source-wordcount: '878'
ht-degree: 3%

---


# Considerazioni globali sulla suite di report

Una suite di rapporti globale è una suite di rapporti che raccoglie dati da tutti i domini e le app di proprietà dell&#39;organizzazione. Questa tecnica di raccolta dei dati richiede preparazione e può richiedere il coordinamento tra i team all&#39;interno dell&#39;organizzazione.

## Vantaggi

Nella maggior parte dei casi, Adobe consiglia di implementare una suite di rapporti globale.

* **Dati aggregati:** Le suite di rapporti globali consentono di visualizzare gli eventi KPI e di successo nei siti di proprietà. La segmentazione e le suite di rapporti virtuali possono essere utilizzate per visualizzare dati specifici per il sito.
* **Supporto per  Analytics cross-device:** CDA richiede una suite di rapporti che raccoglie dati da più luoghi, come il sito Web e l’app mobile. I dispositivi separati possono unire i dati se implementati correttamente. Per ulteriori informazioni, consulta [Dispositivi  Analytics](../../components/cda/overview.md) nella guida utente Componenti.
* **Non sono necessarie più suite di rapporti:** Tutti i dati possono essere raccolti in una singola suite di rapporti, pertanto è meno probabile che uno sviluppatore invii erroneamente i dati alla suite di rapporti sbagliata.
* **Non è necessario eseguire il rollup:** I rollup sono una funzione piuttosto datata che aggrega quotidianamente i dati delle singole suite di rapporti. I rollup non deduplicano i dati delle visite o dei visitatori, il che può causare un aumento dei numeri. Per ulteriori informazioni, consulta [Rollup](../../admin/c-manage-report-suites/rollup-report-suite.md) nella guida utente di amministrazione.
* **Risparmio di tempo:** I progetti, le classificazioni, i segmenti e le metriche calcolate dell&#39;area di lavoro sono legati alla stessa suite di rapporti globale. Gli amministratori dedicano meno tempo alla gestione di questi componenti e alla gestione dei dati.
* **Attribuzione più precisa tra marchi:** Se una visita inizia su un sito e poi fa clic su un altro dei siti di proprietà prima di attivare un evento di successo, l&#39;attribuzione viene raccolta accuratamente. Ad esempio, un visitatore fa clic su un collegamento di ricerca a pagamento e accede al sito A. Quindi fanno clic su un collegamento al sito B, quindi effettuano un acquisto. Una suite di rapporti globale attribuisce correttamente l&#39;acquisto alla ricerca a pagamento.
* **Implementazione semplificata:** Poiché tutti i marchi/siti inviano dati alla stessa suite di rapporti, le tue implementazioni in ogni sito sono allineate. Questa governance forzata assicura che una dimensione o metrica specifica venga salvata nello stesso eVar o evento. Questa semplificazione è utile per amministratori, tester, proprietari di tag e analisti.

>[!NOTE]
>
>Coordinare un&#39;implementazione globale della suite di rapporti è un progetto di grandi dimensioni. Adobe consiglia di collaborare con un consulente per ridurre le complicazioni e i problemi che possono insorgere.

## Avvio di una nuova implementazione con una suite di rapporti globale

Utilizzate le seguenti linee guida generali per comprendere il processo di implementazione di una suite di rapporti globale.

1. Crea la suite di rapporti globale in Adobe  Analytics. Per ulteriori informazioni, consulta [Creare una suite](../../admin/admin-console/create-report-suite.md) di rapporti nella guida per l&#39;utente Admin.
2. Collaborate con i team dell&#39;organizzazione responsabili per ogni dominio. Molti team hanno requisiti di reporting specifici per la propria area di attività.
3. Registrazione e aggregazione di tutti questi requisiti in un documento [di progettazione della](solution-design.md)soluzione. Se i team hanno requisiti simili per una dimensione, possono utilizzare la stessa variabile personalizzata. Ad esempio, se il sito A e il sito B richiedono entrambe una dimensione di breadcrumb, le implementazioni per entrambi i siti possono inviare tali dati tramite eVar1.
   > [!IMPORTANT] Accertatevi che qualsiasi variabile personalizzata specificata venga utilizzata in modo simile tra i domini. Non utilizzare lo stesso eVar o evento per scopi diversi nei siti.
4. Accertatevi che ciascun dominio disponga di un livello dati per semplificare la raccolta dei dati. I dati possono ancora essere raccolti senza un livello di dati, ma l&#39;affidabilità e la durata dell&#39;implementazione diminuiscono, soprattutto quando il sito viene riprogettato.
5. Utilizzate  Adobe Experience Platform Launch per implementare  Analytics. Siti diversi richiederanno probabilmente elementi di dati diversi. Utilizza regole specifiche per ciascun dominio per verificare che ciascun elemento dati sia popolato correttamente, quindi assegna tali elementi ai rispettivi eVar ed eventi. Consulta Panoramica [di](https://docs.adobe.com/content/help/it-IT/launch/using/overview.html) Launch nella guida utente di Launch del Adobe Experience Platform .
6. Include il servizio [](https://docs.adobe.com/content/help/it-IT/id-service/using/home.html) Adobe Experience Cloud ID e utilizza la funzione [appendVisitorIDsTo](https://docs.adobe.com/content/help/it-IT/id-service/using/id-service-api/methods/appendvisitorid.html) . Questa funzione unisce i dati dei visitatori quando gli utenti fanno clic da un dominio all&#39;altro.

## Modifica di un&#39;implementazione esistente con una suite di rapporti globale

Il processo di spostamento di un&#39;implementazione esistente tra più siti in una singola suite di rapporti globale richiede più tempo e coordinamento tra i team dell&#39;organizzazione.

1. Determinate se desiderate utilizzare una delle suite di rapporti esistenti o iniziare a utilizzarne una nuova. Per modificare gli usi delle variabili esistenti nell&#39;implementazione, è consigliabile iniziare con una nuova suite di rapporti.
2. Determinare una data di interruzione per il passaggio a una suite di rapporti globale. Il momento migliore per effettuare un ritaglio è tra due periodi di reporting significativi o insieme a modifiche importanti al sito. Alcuni esempi includono l&#39;inizio di un trimestre fiscale o di un anno, durante l&#39;aggiornamento di un sito o la modifica di un nuovo sistema di gestione dei tag.
3. Segui i passaggi indicati sopra (crea una suite di rapporti, raccogli i requisiti per la creazione di rapporti in un documento di progettazione di una soluzione e stabilisci un livello dati su ciascun sito). Quando implementate Launch, convalidate l’implementazione utilizzando una versione di sviluppo del sito Web.
4. Dopo aver confermato che l’implementazione sta lavorando su dev, fai in modo che l’implementazione di Launch sia live entro la data limite.

## Pagine correlate

[Passaggio dall’assegnazione di tag a più suite a una suite di rapporti globale e suite](../../components/vrs/vrs-considerations.md)di rapporti virtuali[Confronto tra rollup e suite di rapporti globali](../../admin/c-manage-report-suites/rollup-report-suite.md)
