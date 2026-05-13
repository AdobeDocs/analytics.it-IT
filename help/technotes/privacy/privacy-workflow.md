---
description: Illustra i passaggi necessari per abilitare l’implementazione di Adobe Analytics per supportare l’accesso ai dati personali e i diritti di eliminazione degli interessati.
title: Flusso di lavoro per la privacy
feature: Data Governance
role: Admin
exl-id: c364b364-6d77-4b2c-88ab-65daf812f242
TQID: https://experienceleague.adobe.com/n0zqbcuPD2lvtgYNtdQx5VsBl-FrmzfqU-z2iIn83hg
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 333
ht-degree: 42%

---

# Flusso di lavoro per la privacy

Questo flusso di lavoro delinea la procedura da seguire per preparare l’implementazione di Adobe Analytics al fine di supportare i diritti di accesso e la cancellazione delle persone interessate in base alla Privacy dei dati.

1. Inizia con la pagina [Panoramica di Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=it) in Adobe Experience Platform per avere un&#39;idea delle domande da porre prima di etichettare i dati di Analytics.
1. **Imposta i criteri di conservazione dei dati.** Affinché Adobe possa soddisfare le richieste di accesso o cancellazione dei dati in Data Privacy, è necessario un criterio di conservazione dei dati.  Per ulteriori informazioni, vedere [Domande frequenti sulla conservazione dei dati](/help/technotes/data-retention.md). Per utilizzare l’API dei servizi di privacy, devi assicurarti che il periodo di conservazione dei dati sia impostato in Adobe Analytics.
1. **Acquisisci familiarità con le etichette Privacy dei dati, gli ID di Adobe Analytics e i namespace.** Consulta [Etichette Privacy dei dati per le variabili di Analytics](/help/admin/tools/privacy-labeling/labels.md) e [Tecniche di etichettatura consigliate](/help/admin/tools/privacy-labeling/best-practices.md).
1. **Assegna etichette di identità, riservatezza e governance dei dati a ciascuna variabile in una suite di rapporti.** L’etichettatura deve essere rivista ogni volta che viene creata una nuova suite di rapporti o quando viene abilitata una nuova variabile all’interno di una suite di rapporti. Rivedi l’etichettatura anche quando vengono abilitate nuove integrazioni della soluzione, perché queste potrebbero esporre nuove variabili che neccessitano di etichette. Una nuova implementazione delle app mobili o dei siti web potrebbe cambiare il modo in cui vengono usate le variabili esistenti. Anche per queste potrebbe essere necessario aggiornare le etichette. Consulta [Etichettare i dati della suite di rapporti](/help/admin/tools/privacy-labeling/namespaces.md).
1. **Connettiti all&#39;API Privacy dei dati di Adobe e invia le richieste di accesso e cancellazione.** In qualità di cliente di Adobe Analytics, puoi inviare singole richieste di Privacy dei dati per accedere e cancellare i dati di un cliente, richiamando l&#39;[API di Adobe Experience Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=it). Nelle richieste puoi inviare qualsiasi identificatore di Analytics (come descritto nella sezione sulle [best practice di etichettatura](/help/admin/tools/privacy-labeling/best-practices.md)) insieme ai rispettivi ID degli spazi dei nomi (ID dell’origine dati).
1. **Visualizza e gestisci le impostazioni di Privacy dei dati della suite di rapporti.** Vedi [Visualizza impostazioni di governance dei dati della suite di rapporti](/help/admin/tools/privacy-labeling/view-settings.md).
