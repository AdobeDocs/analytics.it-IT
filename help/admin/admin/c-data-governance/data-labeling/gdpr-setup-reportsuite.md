---
description: Etichettare i dati della suite di rapporti significa assegnare etichette di identità, riservatezza e governance dei dati a ciascuna variabile in una determinata suite di rapporti.
title: Etichettare i dati della suite di rapporti
feature: Data Governance
role: Admin
exl-id: d1bd833c-3fd4-4572-a5dc-d7bab8a79cb8
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 43%

---

# Etichettare i dati della suite di rapporti

Etichettare i dati della suite di rapporti significa assegnare etichette di identità, riservatezza e governance dei dati a ciascuna variabile in una determinata suite di rapporti. Assicurati innanzitutto di conoscere bene le [etichette e le relative definizioni](/help/admin/admin/c-data-governance/data-labeling/gdpr-labels.md).

>[!NOTE]
>
>Ricorda che l’etichettatura deve essere rivista ogni volta che viene creata una nuova suite di rapporti o quando viene abilitata una nuova variabile all’interno di una suite di rapporti. Potrebbe essere necessario rivedere l&#39;etichettatura anche quando vengono abilitate nuove integrazioni della soluzione, perché queste potrebbero esporre nuove variabili che potrebbero richiedere le etichette. Una nuova implementazione delle app mobili o dei siti web potrebbe cambiare il modo in cui vengono usate le variabili esistenti. Anche per queste potrebbe essere necessario aggiornare le etichette.

## Assegnare o modificare le etichette di privacy della suite di rapporti {#assign-edit}

**Esempio**: in qualità di titolare del trattamento dei dati, pianifica di raccogliere gli indirizzi e-mail e gli ID cookie degli interessati per elaborare le loro richieste di Privacy dei dati. Questi ID cookie sono memorizzati in una suite di rapporti in Adobe Analytics.

1. In Adobe Analytics, passa a **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Data configuration and collection]** > **[!UICONTROL Data governance]**.

   ![Etichetta privacy](assets/privacy_rs_settings.png)

1. Seleziona una suite di rapporti dal selettore **[!UICONTROL Report Suites]** in alto.

1. Nella sezione del filtro a sinistra, seleziona i gruppi di variabili che desideri etichettare. Puoi assegnare un’etichetta a un solo gruppo di variabili alla volta.

   * **Componenti standard** - I componenti standard sono dimensioni e metriche predefinite di Analytics, raccolte per impostazione predefinita all&#39;interno di un&#39;implementazione di Analytics.
   * **Variabili di conversione** - La variabile di conversione Custom Insight (o eVar) viene inserita nel codice di Adobe nelle pagine Web selezionate del sito. Il suo scopo principale è segmentare le metriche di successo della conversione nei rapporti di marketing personalizzati. Un eVar può essere basato sulle visite e funzionare in modo simile ai cookie. I valori trasmessi nelle variabili eVar seguono l’utente per un periodo di tempo predeterminato.
   * **Variabili elenco** - Le variabili elenco sono variabili personalizzate che puoi utilizzare come preferisci. Funzionano in modo simile alle eVar, ma possono contenere più valori nello stesso hit. Le variabili elenco non hanno un limite di caratteri.
   * **Variabili di traffico** - Le variabili di traffico (o proprietà) di Custom Insight consentono di correlare dati personalizzati con eventi specifici relativi al traffico. Le variabili prop sono incorporate nel codice di implementazione in ogni pagina del sito web.
   * **Eventi di successo** - Gli eventi di successo (noti anche come eventi di conversione o eventi personalizzati) sono azioni che possono essere tracciate. È possibile determinare la natura dell’evento di successo. Ad esempio, se un visitatore acquista un articolo, l’evento di acquisto potrebbe essere considerato l’evento di successo.
   * **Classificazioni** - I raggruppamenti di classificazione vengono utilizzati per mappare i dati di reporting di Analytics alle proprietà correlate. Le classificazioni possono essere utilizzate per diversi scopi, ma sono più comunemente utilizzate per classificare i codici di tracciamento delle campagne (sia interni che esterni) e gli ID prodotto.

1. Selezionare una variabile facendo clic sulla relativa casella di controllo, quindi fare clic su **[!UICONTROL Edit Privacy Labels]** sulla barra blu visualizzata nella parte inferiore dello schermo.

   ![Modifica](assets/edit-label.png)

   Questa schermata mostra le etichette attualmente applicate e consente di applicarne di nuove. A seconda del componente, potrebbe non essere possibile applicare o modificare tutte le etichette.

   ![Etichette applicate](assets/edit-labels2.png)

1. Dopo aver completato l’etichettatura, fai clic su **[!UICONTROL Apply]**.

