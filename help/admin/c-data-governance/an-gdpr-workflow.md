---
description: Illustra i passaggi necessari per abilitare l’implementazione di Adobe Analytics per supportare l’accesso ai dati personali e i diritti di eliminazione degli interessati.
title: Flusso di lavoro per la privacy
uuid: f24e8be3-8b5c-409b-ad6b-770198ae2549
exl-id: c364b364-6d77-4b2c-88ab-65daf812f242
source-git-commit: 7cb2489c2deaf8e75c71589895314067a010caf8
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 58%

---

# Flusso di lavoro per la privacy

Questo flusso di lavoro delinea la procedura da seguire per preparare l’implementazione di Adobe Analytics al fine di supportare i diritti di accesso e la cancellazione delle persone interessate in base alla Privacy dei dati.

1. **Imposta i criteri di conservazione dei dati.** È necessario un criterio di conservazione dei dati per Adobe soddisfare le richieste di accesso/cancellazione dei dati in Privacy dei dati.  Per ulteriori informazioni, consulta le [Domande frequenti sulla conservazione dei dati](/help/technotes/data-retention.md).
1. **Acquisisci familiarità con le etichette DULE/Privacy dei dati, gli ID di Adobe Analytics, i namespace e l’espansione dell’ID.** Consulta Etichette Privacy  [dei dati per le ](/help/admin/c-data-governance/gdpr-labels.md) variabili di Analytics e Tecniche  [di etichettatura consigliate](/help/admin/c-data-governance/gdpr-analytics-ids.md).
1. **Assegna etichette di identità, riservatezza e governance dei dati a ciascuna variabile in una suite di rapporti.** L’etichettatura deve essere rivista ogni volta che viene creata una nuova suite di rapporti o quando viene abilitata una nuova variabile all’interno di una suite di rapporti. Controlla anche l’etichettatura quando sono abilitate le nuove integrazioni di soluzioni, in quanto possono esporre nuove variabili che potrebbero richiedere l’etichettatura. Una reimplementazione delle tue app mobili o dei tuoi siti web può cambiare il modo in cui vengono utilizzate le variabili esistenti, il che può anche richiedere aggiornamenti delle etichette. Consulta [Etichettare i dati della suite di rapporti](/help/admin/c-data-governance/gdpr-setup-reportsuite.md).
1. **Collegati all’API Privacy dei dati di Adobe e invia le richieste di accesso e cancellazione.** In qualità di cliente di Adobe Analytics, puoi inviare singole richieste di Privacy dei dati per accedere e cancellare i dati di un cliente, richiamando l’[API Privacy dei dati di Adobe Experience Cloud](https://www.adobe.io/apis/experienceplatform/gdpr.html). Nelle richieste puoi inviare qualsiasi identificatore di Analytics (come descritto nella sezione [Tecniche di etichettatura consigliate](/help/admin/c-data-governance/gdpr-analytics-ids.md)) insieme ai rispettivi ID dei namespace (ID dell’origine dati).
1. **Visualizza e gestisci le impostazioni di Privacy dei dati della suite di rapporti.** Consulta  [Visualizzare le impostazioni di governance dei dati della suite di rapporti](/help/admin/c-data-governance/gdpr-view-settings.md).
