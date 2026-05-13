---
description: Etichettare i dati della suite di rapporti significa assegnare etichette di identità, riservatezza e governance dei dati a ciascuna variabile in una determinata suite di rapporti.
title: Panoramica sull’etichettatura della privacy
feature: Data Governance
role: Admin
exl-id: d1bd833c-3fd4-4572-a5dc-d7bab8a79cb8
TQID: https://experienceleague.adobe.com/xEs37qiYjTVJWRDKa7HwJqfTtyBYKstA6ehq1-0qKt0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: b8734a57-d5fb-44a8-8ee1-65225cecaeaeid: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
subfeature_v2: id: b22bc0f7-b089-4966-95a1-31e7b3b69b79id: b99602d0-836e-4dbb-979f-c0dec53f883cid: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: eddd9b14-83bd-4ff4-9072-54a4a484abb7id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 519
ht-degree: 32%

---

# Panoramica sull’etichettatura della privacy

Etichettare i dati della suite di rapporti significa assegnare etichette di identità, riservatezza e governance dei dati a ciascuna variabile in una determinata suite di rapporti. Assicurati innanzitutto di conoscere bene le [etichette e le relative definizioni](/help/admin/tools/privacy-labeling/labels.md).

>[!NOTE]
>
>Ricorda che l’etichettatura deve essere rivista ogni volta che viene creata una nuova suite di rapporti o quando viene abilitata una nuova variabile all’interno di una suite di rapporti. Potrebbe essere inoltre necessario rivedere l’etichettatura quando vengono abilitate nuove integrazioni di soluzioni, in quanto queste possono esporre nuove variabili che possono richiedere l’etichettatura. Una reimplementazione delle app mobili o dei siti web potrebbe modificare il modo in cui vengono utilizzate le variabili esistenti, e potrebbe essere necessario aggiornare le etichette.

## Assegnare o modificare le etichette di privacy della suite di rapporti {#assign-edit}

**Esempio**: in qualità di titolare del trattamento dei dati, pianifica di raccogliere gli indirizzi e-mail e gli ID cookie degli interessati per elaborare le loro richieste di Privacy dei dati. Questi ID cookie sono memorizzati in una suite di rapporti in Adobe Analytics.

1. In Adobe Analytics, passa a **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Data configuration and collection]** > **[!UICONTROL Data governance]**.

   ![Etichetta privacy](assets/privacy_rs_settings.png)

1. Seleziona una suite di rapporti dal selettore **[!UICONTROL Report Suites]** in alto.

1. Nella sezione del filtro a sinistra, seleziona i gruppi di variabili che desideri etichettare. Puoi assegnare un’etichetta a un solo gruppo di variabili alla volta.

   * **Componenti standard** - I componenti standard sono dimensioni e metriche predefinite di Analytics, raccolte per impostazione predefinita all&#39;interno di un&#39;implementazione di Analytics.
   * **Variabili di conversione** - La variabile di conversione Custom Insight (o eVar) viene inserita nel codice Adobe in alcune pagine Web del sito. Il suo scopo principale è segmentare le metriche di successo della conversione nei rapporti di marketing personalizzati. Un eVar può essere basato sulle visite e funzionare in modo simile ai cookie. I valori trasmessi nelle variabili eVar seguono l’utente per un periodo di tempo predeterminato.
   * **Variabili elenco** - Le variabili elenco sono variabili personalizzate che puoi utilizzare come preferisci. Funzionano in modo simile alle eVar, ma possono contenere più valori nello stesso hit. Le variabili elenco non hanno un limite di caratteri.
   * **Variabili di traffico** - Le variabili di traffico (o proprietà) di Custom Insight consentono di correlare dati personalizzati con eventi specifici relativi al traffico. Le variabili prop sono incorporate nel codice di implementazione in ogni pagina del sito web.
   * **Eventi di successo** - Gli eventi di successo (noti anche come eventi di conversione o eventi personalizzati) sono azioni che possono essere tracciate. È possibile determinare la natura dell’evento di successo. Ad esempio, se un visitatore acquista un articolo, l’evento di acquisto potrebbe essere considerato l’evento di successo.
   * **Classificazioni** - I raggruppamenti di classificazione vengono utilizzati per mappare i dati di reporting di Analytics alle proprietà correlate. Le classificazioni possono essere utilizzate per diversi scopi, ma sono più comunemente utilizzate per classificare i codici di tracciamento delle campagne (sia interni che esterni) e gli ID prodotto.

1. Selezionare una variabile facendo clic sulla relativa casella di controllo, quindi fare clic su **[!UICONTROL Edit Privacy Labels]** sulla barra blu visualizzata nella parte inferiore dello schermo.

   ![Modifica](assets/edit-label.png)

   Questa schermata mostra le etichette attualmente applicate e consente di applicarne di nuove. A seconda del componente, potrebbe non essere possibile applicare o modificare tutte le etichette.

   ![Etichette applicate](assets/edit-labels2.png)

1. Dopo aver completato l’etichettatura, fai clic su **[!UICONTROL Apply]**.

