---
description: Illustra i passaggi necessari per abilitare l’implementazione di Adobe Analytics per supportare l’accesso ai dati personali e i diritti di eliminazione degli interessati.
title: Flusso di lavoro per la privacy
uuid: f24e8be3-8b5c-409b-ad6b-770198ae2549
exl-id: c364b364-6d77-4b2c-88ab-65daf812f242
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 98%

---

# Flusso di lavoro per la privacy

Questo flusso di lavoro delinea la procedura da seguire per preparare l’implementazione di Adobe Analytics al fine di supportare i diritti di accesso e la cancellazione delle persone interessate in base alla Privacy dei dati.

| Descrizione dell’attività | Collegamenti alle istruzioni e ad altre informazioni |
|--- |--- |
| **Passaggio 1**: assicurati che tutte le suite di rapporti che potrebbero contenere dati relativi alla Privacy dei dati siano state mappate nell’organizzazione Experience Cloud (o IMS).  Le richieste di Privacy dei dati vengono inviate usando un’organizzazione Experience Cloud e verranno applicate a tutte le suite di rapporti richieste dall’organizzazione. Le richieste non verranno applicate alle suite di rapporti che non sono state mappate nell’organizzazione, anche se fanno parte della società di accesso. | Consulta l’articolo su come [mappare le suite di rapporti per un’organizzazione](https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/report-suite-mapping.html). |
| **Passaggio 2**: imposta i criteri di conservazione dei dati. | È necessario impostare i criteri di conservazione dei dati affinché Adobe possa soddisfare le richieste di accesso o di cancellazione dei dati in base alla Privacy dei dati.  Per altre informazioni consulta le [Domande frequenti sulla conservazione dei dati in Analytics](/help/technotes/data-retention.md). |
| **Passaggio 3**: acquisisci familiarità con le etichette DULE/Privacy dei dati, gli ID di Adobe Analytics, i namespace e l’espansione dell’ID. | Leggi questi argomenti nella presente documentazione:<ul><li>[Etichette Privacy dei dati per le variabili di Analytics](/help/admin/c-data-governance/gdpr-labels.md)</li><li>[Tecniche di etichettatura consigliate](/help/admin/c-data-governance/gdpr-analytics-ids.md)</li></ul> |
| **Passaggio 4:** assegna etichette di identità, riservatezza e governance dei dati a ciascuna variabile in una suite di rapporti.  Nota: ricorda che l’etichettatura deve essere rivista ogni volta che viene creata una nuova suite di rapporti o quando viene abilitata la nuova variabile all’interno di una suite di rapporti. Potrebbe essere necessario rivedere l&#39;etichettatura anche quando vengono abilitate nuove integrazioni della soluzione, perché queste potrebbero esporre nuove variabili che potrebbero richiedere le etichette. Una nuova implementazione delle app mobili o dei siti web potrebbe cambiare il modo in cui vengono usate le variabili esistenti. Anche per queste potrebbe essere necessario aggiornare le etichette. | Segui le istruzioni riportate nell’articolo su come [etichettare i dati della suite di rapporti](/help/admin/c-data-governance/gdpr-setup-reportsuite.md). |
| **Passaggio 5**: collegati all’API Privacy dei dati di Adobe e invia le richieste di accesso e cancellazione. | In qualità di cliente di Adobe Analytics, puoi inviare singole richieste di Privacy dei dati per accedere e cancellare i dati di un cliente, richiamando l’[API Privacy dei dati di Adobe Experience Cloud](https://www.adobe.io/apis/experienceplatform/gdpr.html). Nelle richieste puoi inviare qualsiasi identificatore di Analytics (come descritto nella sezione [Tecniche di etichettatura consigliate](/help/admin/c-data-governance/gdpr-analytics-ids.md)) insieme ai rispettivi ID dei namespace (ID dell’origine dati). |
| **Passaggio 6**: visualizza e gestisci le impostazioni di Privacy dei dati della suite di rapporti. | Segui le istruzioni riportate nell’articolo su come [visualizzare le impostazioni di governance dei dati della suite di rapporti](/help/admin/c-data-governance/gdpr-view-settings.md) |
