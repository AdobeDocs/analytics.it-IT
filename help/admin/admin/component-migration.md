---
description: Spiega come migrare componenti e progetti da Adobe Analytics a Customer Journey Analytics.
title: Migrazione di componenti e progetti da Adobe Analytics a Customer Journey Analytics
feature: Admin Tools
source-git-commit: 8a9c3b4d6c7a59582a6fd8bdc5464c2dbed3ad1b
workflow-type: tm+mt
source-wordcount: '1018'
ht-degree: 4%

---

# Migrazione di componenti e progetti da Adobe Analytics a Customer Journey Analytics

Gli amministratori di Adobe Analytics possono eseguire la migrazione di componenti e progetti Adobe Analytics al Customer Journey Analytics.

Il processo di migrazione include:

* Ricreare i progetti Adobe Analytics nel Customer Journey Analytics.

* Dimensioni e metriche corrispondenti dalle suite di rapporti di Adobe Analytics alle dimensioni e alle metriche nelle visualizzazioni dati del Customer Journey Analytics.

  Alcune dimensioni e metriche vengono abbinate automaticamente; altre devono corrispondere manualmente come parte del processo di migrazione.

## Prerequisiti

Prima che i progetti e le dimensioni e metriche associate siano pronti per la migrazione, devi effettuare le seguenti operazioni:

* Utilizza il connettore di origine di Analytics per visualizzare i dati della suite di rapporti di Adobe Analytics nel Customer Journey Analytics. Per farlo, devi:

   * [Configurare le suite di rapporti per l’acquisizione in Adobe Experience Platform e Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=en#set-up-report-suites-for-ingestion-into-the-adobe-experience-platform-and-customer-journey-analytics)

   * [Inserire e utilizzare i dati](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/analytics.html?lang=it)

* Assicurati che gli utenti nel Customer Journey Analytics siano assegnati alle visualizzazioni dati in cui i dati vengono rilevati.

  Per ulteriori informazioni, consulta [Autorizzazioni di Customer Journey Analytics nell’Admin Console](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html?lang=en#customer-journey-analytics-permissions-in-admin-console) in [Controllo dell’accesso al Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html).

  La scheda Autorizzazioni fa parte di ciascun profilo di prodotto in Admin Console. Puoi aggiungere utenti a profili di prodotto specifici. Dopodiché dovrai assegnare i diritti a visualizzazioni di dati specifiche e specificare quali autorizzazioni hanno gli utenti in un profilo di prodotto.

## Creare un piano di migrazione come organizzazione

Poiché tutti i componenti associati a una determinata migrazione di progetto vengono applicati a qualsiasi migrazione di progetto futura per l’intera organizzazione, è importante che la tua organizzazione pianifichi in anticipo tutte le migrazioni di progetto.

È necessario decidere come organizzazione quali dimensioni e metriche troveranno corrispondenza con cosa corrisponderà a cosa, al fine di evitare che singoli amministratori prendano decisioni all’interno di un silo al momento della migrazione di un progetto.

## Migrare progetti Adobe Analytics al Customer Journey Analytics

>[!IMPORTANT]
>
>Prima di eseguire la migrazione di progetti al Customer Journey Analytics come descritto in questa sezione, ulteriori informazioni sulla migrazione di progetti sono disponibili in [Pianificare la migrazione](#plan-the-migration) sopra.
>
>Tutte le dimensioni o metriche corrispondenti sono permanenti, sia per questo progetto che per tutti i progetti futuri migrati in tutta l’organizzazione. Se si continua, le corrispondenze create non potranno essere modificate.



1. In Adobe Analytics seleziona la [!UICONTROL **Amministratore**] , quindi seleziona [!UICONTROL **Tutti gli amministratori**].

1. Sotto [!UICONTROL **Configurazione e raccolta dati**], seleziona [!UICONTROL **Migrazione dei componenti**].

1. (Condizionale) Per trovare rapidamente il progetto di cui vuoi eseguire la migrazione, puoi effettuare le seguenti operazioni:

   * Filtra l’elenco dei progetti selezionando l’icona Filtro.

     Puoi filtrare in base ai seguenti criteri:

      * Stato

      * Tag

      * Suite di rapporti

      * Proprietari

      * Altri filtri

   * Utilizza il campo di ricerca per cercare il progetto di cui vuoi eseguire la migrazione.

1. Passa il puntatore del mouse sul progetto di cui vuoi eseguire la migrazione, quindi seleziona la **Migra** icona ![Migra progetto](assets/migrate.svg).

   Oppure

   Seleziona il progetto di cui vuoi eseguire la migrazione, quindi fai clic su [!UICONTROL **Migra al Customer Journey Analytics**].

   È possibile selezionare un solo progetto alla volta per la migrazione.

   Il [!UICONTROL **Migra nome_progetto a Customer Journey Analytics**] viene visualizzata.

   <!-- add screenshot -->

1. In [!UICONTROL **Proprietario del progetto**] , inizia a digitare il nome dell’utente che desideri impostare come proprietario del progetto nel Customer Journey Analytics, quindi selezionane il nome nel menu a discesa.

   Il proprietario specificato dispone dei diritti di gestione completi per il progetto.

1. In [!UICONTROL **Schema di corrispondenza per le suite di rapporti**] , seleziona una suite di rapporti.

1. In [!UICONTROL **Visualizzazione dati**] dal menu a discesa, seleziona la visualizzazione dati del Customer Journey Analytics in cui desideri eseguire la migrazione del progetto e dei componenti.

1. Seleziona [!UICONTROL **Corrispondenza schema**].

1. In [!UICONTROL **Corrispondenza schema**] , espandere la sezione [!UICONTROL **Dimension**] e [!UICONTROL **Metriche**] sezioni.

   Alcune dimensioni e metriche in Adobe Analytics vengono automaticamente abbinate a una dimensione o metrica in Customer Journey Analytics. Gli altri devono essere abbinati manualmente.

   **Dimensioni e metriche con corrispondenza automatica**

   Alcune dimensioni e metriche in Adobe Analytics vengono automaticamente abbinate a una dimensione o metrica in Customer Journey Analytics. Non puoi prendere decisioni corrispondenti per queste dimensioni e metriche.

   Ad esempio, il **Visite** metrica in Adobe Analytics viene automaticamente abbinata alla **Sessioni** metrica nel Customer Journey Analytics.

   Puoi selezionare qualsiasi dimensione o metrica per visualizzare i relativi ID associati.

   <!-- update screenshot after I can see the Status column -->

   ![Schema di migrazione del progetto](assets/project-migration-schema.png)

   **Abbinare manualmente dimensioni e metriche**

   Altre dimensioni e metriche in Adobe Analytics non possono corrispondere automaticamente a una dimensione o metrica in Customer Journey Analytics.

   Quando una dimensione o una metrica non può essere abbinata automaticamente, accanto al valore visualizzato un contatore arancione [!UICONTROL **Dimension**] o [!UICONTROL **Metriche**] intestazione di sezione, che indica il numero di dimensioni o metriche a cui deve corrispondere manualmente. Nella tabella, un’icona di avvertenza ![icona di avviso](assets/schema-warning.png) viene visualizzato accanto a ciascuna dimensione o metrica a cui deve essere applicata manualmente la corrispondenza.

   <!-- update screenshot after I can see the Status column -->

   ![Corrispondenza manuale schema di migrazione](assets/schema-manual-map.png)

1. Per associare manualmente dimensioni e metriche, seleziona una dimensione o una metrica contenente un’icona di avviso ![icona di avviso](assets/schema-warning.png), quindi in [!UICONTROL **Metrica di Customer Journey Analytics corrispondente**] campo (o [!UICONTROL **Dimensione Customer Journey Analytics corrispondente**] se stai facendo corrispondere una dimensione), seleziona la dimensione o la metrica nel Customer Journey Analytics che desideri far corrispondere alla dimensione o alla metrica selezionata.

   ![abbinare dimensioni e metriche](assets/schema-manual-map-drop-down.png)

   Ripeti questo processo per ogni dimensione o metrica contenente l’icona di avviso.

   Una volta che tutte le dimensioni e le metriche nella suite di rapporti di Adobe Analytics sono state associate a una dimensione o metrica nella visualizzazione dati del Customer Journey Analytics, un segno di spunta verde ![segno di spunta](assets/report-suite-check.png) viene visualizzato accanto al nome della suite di rapporti nella [!UICONTROL **Schema di corrispondenza per le suite di rapporti**] sezione.

1. (Condizionale) Se il progetto di cui stai eseguendo la migrazione contiene più di una suite di rapporti, seleziona un’altra suite di rapporti in [!UICONTROL **Schema di corrispondenza per le suite di rapporti**] quindi ripetere i passaggi da 6 a 10. <!-- double-check that the step numbers are still correct -->

1. Seleziona [!UICONTROL **Migra**].

   >[!WARNING]
   >
   >   Dopo aver selezionato, viene visualizzato un messaggio di avviso sullo schermo [!UICONTROL **Migra**]. Prima di scegliere di continuare, assicurati che tutte le dimensioni o metriche corrispondenti siano permanenti, sia per questo progetto che per tutti i progetti futuri migrati in tutta l’organizzazione. Se si continua, le corrispondenze create non potranno essere modificate.
