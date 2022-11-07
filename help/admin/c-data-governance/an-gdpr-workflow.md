---
description: Illustra i passaggi necessari per abilitare l’implementazione di Adobe Analytics per supportare l’accesso ai dati personali e i diritti di eliminazione degli interessati.
title: Flusso di lavoro per la privacy
feature: Privacy
exl-id: c364b364-6d77-4b2c-88ab-65daf812f242
source-git-commit: ac9e4934cee0178fb00e4201cc3444d333a74052
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 88%

---

# Flusso di lavoro per la privacy

Questo flusso di lavoro delinea la procedura da seguire per preparare l’implementazione di Adobe Analytics al fine di supportare i diritti di accesso e la cancellazione delle persone interessate in base alla Privacy dei dati.

1. **Imposta i criteri di conservazione dei dati.** Affinché Adobe possa soddisfare le richieste di accesso o cancellazione dei dati in Data Privacy, è necessario un criterio di conservazione dei dati. Per altre informazioni consulta le [Domande frequenti sulla conservazione dei dati](/help/technotes/data-retention.md).
1. **Acquisisci familiarità con le etichette DULE/Privacy dei dati, gli ID di Adobe Analytics, i namespace e l’espansione dell’ID.** Consulta [Etichette di Privacy dei dati per le variabili di Analytics](/help/admin/c-data-governance/gdpr-labels.md) e [Tecniche di etichettatura consigliate](/help/admin/c-data-governance/gdpr-analytics-ids.md).
1. **Assegna etichette di identità, riservatezza e governance dei dati a ciascuna variabile in una suite di rapporti.** L’etichettatura deve essere rivista ogni volta che viene creata una nuova suite di rapporti o quando viene abilitata una nuova variabile all’interno di una suite di rapporti. Rivedi l’etichettatura anche quando vengono abilitate nuove integrazioni della soluzione, perché queste potrebbero esporre nuove variabili che neccessitano di etichette. Una nuova implementazione delle app mobili o dei siti web potrebbe cambiare il modo in cui vengono usate le variabili esistenti. Anche per queste potrebbe essere necessario aggiornare le etichette. Consulta [Etichettare i dati della suite di rapporti](/help/admin/c-data-governance/gdpr-setup-reportsuite.md).
1. **Collegati all’API Privacy dei dati di Adobe e invia le richieste di accesso e cancellazione.** In qualità di cliente Adobe Analytics, puoi inviare singole richieste di Privacy dei dati per accedere e cancellare i dati di un cliente, richiamando il [API di Adobe Experience Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html). Nelle richieste puoi inviare qualsiasi identificatore di Analytics (come descritto nella sezione [Tecniche di etichettatura consigliate](/help/admin/c-data-governance/gdpr-analytics-ids.md)) insieme ai rispettivi ID dei namespace (ID dell’origine dati).
1. **Visualizza e gestisci le impostazioni di Privacy dei dati della suite di rapporti.** Consulta [Visualizzare le impostazioni di governance dei dati della suite di rapporti](/help/admin/c-data-governance/gdpr-view-settings.md).
