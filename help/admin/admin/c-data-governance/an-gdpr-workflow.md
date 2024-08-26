---
description: Illustra i passaggi necessari per abilitare l’implementazione di Adobe Analytics per supportare l’accesso ai dati personali e i diritti di eliminazione degli interessati.
title: Flusso di lavoro per la privacy
feature: Privacy
role: Admin
exl-id: c364b364-6d77-4b2c-88ab-65daf812f242
source-git-commit: eb2b8135ffcf2a22184818b34efcd97a931437f6
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 76%

---

# Flusso di lavoro per la privacy

Questo flusso di lavoro delinea la procedura da seguire per preparare l’implementazione di Adobe Analytics al fine di supportare i diritti di accesso e la cancellazione delle persone interessate in base alla Privacy dei dati.

1. Inizia con la pagina [Panoramica Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=it) in Adobe Experience Platform per avere un&#39;idea delle domande da porre prima di etichettare i dati di Analytics.
1. **Imposta i criteri di conservazione dei dati.** Affinché Adobe possa soddisfare le richieste di accesso o cancellazione dei dati in Data Privacy, è necessario un criterio di conservazione dei dati. Per ulteriori informazioni, vedere [Domande frequenti sulla conservazione dei dati](/help/technotes/data-retention.md). Per utilizzare l’API Privacy Service, assicurati che il periodo di conservazione dei dati sia impostato in Adobe Analytics.
1. **Acquisisci familiarità con le etichette Privacy dei dati, gli ID di Adobe Analytics, i namespace e l&#39;espansione dell&#39;ID.** Consulta [Etichette di Privacy dei dati per le variabili di Analytics](/help/admin/admin/c-data-governance/data-labeling/gdpr-labels.md) e [Tecniche di etichettatura consigliate](/help/admin/admin/c-data-governance/data-labeling/gdpr-analytics-ids.md).
1. **Acquisisci familiarità con le etichette Privacy dei dati, gli ID di Adobe Analytics, i namespace e l&#39;espansione dell&#39;ID.** Consulta [Etichette di Privacy dei dati per le variabili di Analytics](/help/admin/admin/c-data-governance/data-labeling/gdpr-labels.md) e [Tecniche di etichettatura consigliate](/help/admin/admin/c-data-governance/data-labeling/gdpr-analytics-ids.md).
1. **Assegna etichette di identità, riservatezza e governance dei dati a ciascuna variabile in una suite di rapporti.** L’etichettatura deve essere rivista ogni volta che viene creata una nuova suite di rapporti o quando viene abilitata una nuova variabile all’interno di una suite di rapporti. Rivedi l’etichettatura anche quando vengono abilitate nuove integrazioni della soluzione, perché queste potrebbero esporre nuove variabili che neccessitano di etichette. Una nuova implementazione delle app mobili o dei siti web potrebbe cambiare il modo in cui vengono usate le variabili esistenti. Anche per queste potrebbe essere necessario aggiornare le etichette. Consulta [Etichettare i dati della suite di rapporti](/help/admin/admin/c-data-governance/data-labeling/gdpr-namespaces.md).
1. **Collegati all’API Privacy dei dati di Adobe e invia le richieste di accesso e cancellazione.** In qualità di cliente di Adobe Analytics, puoi inviare singole richieste di privacy dei dati per accedere ai dati di un cliente e cancellarli, richiamando l’[API Privacy Service di Adobe Experience](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=it). Nelle richieste puoi inviare qualsiasi identificatore di Analytics (come descritto nella sezione [Tecniche di etichettatura consigliate](/help/admin/admin/c-data-governance/data-labeling/gdpr-analytics-ids.md)) insieme ai rispettivi ID dei namespace (ID dell’origine dati).
1. **Visualizza e gestisci le impostazioni di Privacy dei dati della suite di rapporti.** Consulta [Visualizzare le impostazioni di governance dei dati della suite di rapporti](/help/admin/admin/c-data-governance/data-labeling/gdpr-view-settings.md).
