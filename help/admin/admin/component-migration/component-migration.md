---
description: Spiega come migrare componenti e progetti da Adobe Analytics a Customer Journey Analytics.
title: Migrazione di componenti e progetti da Adobe Analytics a Customer Journey Analytics
feature: Admin Tools
exl-id: 49c7e47a-464b-4465-9b30-d77f886ca6dc
source-git-commit: 96c202870a4e584cf3625d6e4d40024b787c2f0e
workflow-type: tm+mt
source-wordcount: '1498'
ht-degree: 5%

---

# Migrazione di componenti e progetti da Adobe Analytics a Customer Journey Analytics

Gli amministratori di Adobe Analytics possono eseguire la migrazione dei progetti Adobe Analytics e dei relativi componenti a Customer Journey Analytics.

Il processo di migrazione include:

* mappatura dei progetti Adobe Analytics in Customer Journey Analytics;

* mappatura di dimensioni e metriche dalle suite di rapporti di Adobe Analytics alle dimensioni e alle metriche nelle visualizzazioni dati in Customer Journey Analytics.

  Alcune dimensioni e metriche vengono mappate automaticamente; altre devono essere mappate manualmente come parte del processo di migrazione. Anche i segmenti vengono migrati, ma non è necessario mapparli come parte del processo di migrazione.

  Al termine della migrazione, tutti i componenti migrati vengono visualizzati nel riepilogo della migrazione.

>[!NOTE]
>
>Le informazioni contenute in questa pagina descrivono come eseguire la migrazione dei progetti e dei relativi componenti associati all’interfaccia utente di.
>
>In alternativa, puoi eseguire la migrazione utilizzando le API. Per ulteriori informazioni, vedere [API Adobe Analytics](https://adobedocs.github.io/analytics-2.0-apis/?urls.primaryName=Analytics%202.0%20APIs). Tutte le definizioni API sono disponibili nel menu a discesa **[!UICONTROL Select a definition]**.


## Prepararsi per una migrazione

Prima di eseguire la migrazione di qualsiasi progetto al Customer Journey Analytics, scopri di più sulla migrazione dei progetti in [Preparare la migrazione di componenti e progetti da Adobe Analytics al Customer Journey Analytics](/help/admin/admin/component-migration/prepare-component-migration.md).

## Migrare progetti Adobe Analytics al Customer Journey Analytics

>[!IMPORTANT]
>
>Prima di eseguire la migrazione di progetti al Customer Journey Analytics come descritto in questa sezione, scopri di più sulla migrazione di progetti in [Preparare la migrazione di componenti e progetti da Adobe Analytics al Customer Journey Analytics](/help/admin/admin/component-migration/prepare-component-migration.md).
>
>**Qualsiasi dimensione o metrica mappata è permanente, sia per questo progetto che per tutti i progetti futuri migrati nell&#39;intera organizzazione IMS, indipendentemente dall&#39;utente che sta eseguendo la migrazione. Queste mappature possono essere modificate o annullate solo contattando l&#39;Assistenza clienti.**

1. In Adobe Analytics, seleziona la scheda [!UICONTROL **Amministrazione**], quindi seleziona [!UICONTROL **Tutte le attività di amministrazione**].

1. In [!UICONTROL **Configurazione e raccolta dati**], selezionare [!UICONTROL **Migrazione componenti**].

1. Individua il progetto di cui vuoi eseguire la migrazione. Puoi filtrare, ordinare o cercare nell’elenco dei progetti.

   Per impostazione predefinita, vengono visualizzati solo i progetti condivisi con te. Per visualizzare tutti i progetti della tua organizzazione, seleziona l&#39;icona **Filtro**, quindi espandi [!UICONTROL **Altri filtri**] e seleziona [!UICONTROL **Mostra tutto**]. Per ulteriori informazioni su come filtrare, ordinare e cercare nell&#39;elenco dei progetti, vedere [Filtrare, ordinare e cercare nell&#39;elenco dei progetti](#filter-sort-and-search-the-list-of-projects).

1. Passa il puntatore del mouse sul progetto di cui vuoi eseguire la migrazione, quindi seleziona l&#39;icona **Esegui migrazione** ![Esegui migrazione progetto](assets/migrate.svg).

   Oppure

   Seleziona il progetto di cui vuoi eseguire la migrazione, quindi seleziona [!UICONTROL **Esegui migrazione al Customer Journey Analytics**].

   È possibile selezionare un solo progetto alla volta per la migrazione.

   Viene visualizzata la finestra di dialogo [!UICONTROL **Migra nome_progetto al Customer Journey Analytics**].

   <!-- add screenshot -->

1. Nel campo [!UICONTROL **Proprietario progetto**], inizia a digitare il nome dell&#39;utente che desideri impostare come proprietario del progetto nel Customer Journey Analytics, quindi selezionane il nome nel menu a discesa.

   Il proprietario specificato dispone dei diritti di gestione completi per il progetto. Il proprietario deve essere un amministratore nel Customer Journey Analytics. Puoi cambiare la proprietà del progetto in un passaggio successivo.

1. Nella sezione [!UICONTROL **Schema mappa per suite di rapporti**], seleziona una suite di rapporti.

1. Nel menu a discesa [!UICONTROL **Visualizzazione dati**], selezionare la visualizzazione dati di Customer Journey Analytics in cui si desidera eseguire la migrazione del progetto e dei componenti.

1. Seleziona [!UICONTROL **Mappa schema**].

1. Nella sezione [!UICONTROL **Mappa schema**], espandi le sezioni [!UICONTROL **Dimension**] e [!UICONTROL **Metriche**].

   Alcune dimensioni e metriche in Adobe Analytics vengono mappate automaticamente a una dimensione o metrica nel Customer Journey Analytics. Altri devono essere mappati manualmente.

   **Mappa automaticamente dimensioni e metriche**

   >[!NOTE]
   >
   >   Se hai utilizzato Web SDK per acquisire dati in Adobe Experience Platform, le dimensioni e le metriche non possono essere mappate automaticamente. Per ulteriori informazioni, vedere [Prerequisiti](/help/admin/admin/component-migration/prepare-component-migration.md#prerequisites) in [Preparare la migrazione di componenti e progetti da Adobe Analytics al Customer Journey Analytics](/help/admin/admin/component-migration/prepare-component-migration.md).

   Alcune dimensioni e metriche in Adobe Analytics vengono mappate automaticamente a una dimensione o metrica nel Customer Journey Analytics. Non puoi prendere decisioni di mappatura per queste dimensioni e metriche.

   Ad esempio, la metrica **Visite** in Adobe Analytics viene mappata automaticamente con la metrica **Sessioni** nel Customer Journey Analytics.

   Puoi selezionare qualsiasi dimensione o metrica per visualizzare i relativi ID associati.

   <!-- update screenshot after I can see the Status column -->

   ![Schema di migrazione del progetto](assets/project-migration-schema.png)

   **Mappare manualmente dimensioni e metriche**

   Alcune dimensioni e metriche in Adobe Analytics non possono essere mappate automaticamente a una dimensione o metrica nel Customer Journey Analytics.

   Quando non è possibile mappare automaticamente una dimensione o una metrica, accanto all&#39;intestazione di sezione [!UICONTROL **Dimension**] o [!UICONTROL **Metriche**] viene visualizzato un contatore arancione che indica il numero di dimensioni o metriche da mappare manualmente. Nella tabella viene visualizzata un&#39;icona di avviso ![icona di avviso](assets/schema-warning.png) accanto a ogni dimensione o metrica da mappare manualmente.

   Inoltre, nella colonna [!UICONTROL **Stato**] è indicato [!UICONTROL **Non mappato**].

   <!-- update screenshot after I can see the Status column -->

   ![Mappa manuale dello schema di migrazione](assets/schema-manual-map.png)

1. Per mappare manualmente dimensioni e metriche, seleziona una dimensione o una metrica contenente l&#39;icona di avviso ![icona di avviso](assets/schema-warning.png), quindi nel campo [!UICONTROL **Metrica Customer Journey Analytics mappato**] (o nel campo [!UICONTROL **Dimensione Customer Journey Analytics mappato**] se stai mappando una dimensione) seleziona la dimensione o la metrica nel Customer Journey Analytics da mappare alla dimensione o alla metrica selezionata.

   ![mappare dimensioni e metriche](assets/schema-manual-map-drop-down.png)

   Dopo aver mappato una dimensione o una metrica, l&#39;icona di avviso scompare e la colonna [!UICONTROL **Stato**] diventa [!UICONTROL **Mappata**] con un punto verde. (Uno stato di [!UICONTROL **Mappato**] con un punto grigio indica che la dimensione o la metrica è stata mappata durante una migrazione precedente; le mappature precedenti non possono essere aggiornate.)

   Ripeti questo processo per ogni dimensione o metrica contenente l’icona di avviso.

   Dopo che tutte le dimensioni e le metriche nella suite di rapporti di Adobe Analytics sono state mappate a una dimensione o metrica nella suite di rapporti di Customer Journey Analytics, nella sezione [!UICONTROL **Mappa schema per suite di rapporti**] viene visualizzato un segno di spunta verde ![segno di spunta](assets/report-suite-check.png) accanto al nome della suite di rapporti.

1. (Condizionale) Se il progetto di cui si sta eseguendo la migrazione contiene più di una suite di rapporti, selezionare un&#39;altra suite di rapporti nella sezione [!UICONTROL **Mappa schema per suite di rapporti**], quindi ripetere i passaggi da 6 a 10. <!-- double-check that the step numbers are still correct -->

1. Seleziona [!UICONTROL **Migra**].

   >[!WARNING]
   >
   >   Dopo aver selezionato [!UICONTROL **Esegui migrazione**], viene visualizzato un messaggio di avviso sullo schermo. Prima di scegliere di continuare, assicurati che tutte le dimensioni o metriche mappate siano permanenti, sia per questo progetto che per tutti i progetti futuri migrati in tutta l’organizzazione. Se si continua, le mappature create non potranno essere modificate.

   Al termine di una migrazione, la pagina [!UICONTROL **Stato migrazione**] fornisce un riepilogo di ciò che è stato migrato.

   Se la migrazione non riesce, vedere la sezione [Riprova una migrazione non riuscita](#retry-a-failed-migration) di seguito per ulteriori informazioni.

1. (Facoltativo) Dopo la migrazione di un progetto, puoi trasferirne la proprietà a qualsiasi utente del Customer Journey Analytics. Per ulteriori informazioni, consulta [Trasferire risorse](https://experienceleague.adobe.com/en/docs/analytics-platform/using/tools/asset-transfer/transfer-assets) nella Guida al Customer Journey Analytics.

## Ritentare una migrazione non riuscita

Se una migrazione non riesce, puoi riprovare.

Prima di ritentare una migrazione non riuscita, assicurati di rimuovere [elementi non supportati](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html#understand-unsupported-elements-that-cause-errors) dal progetto.

>[!NOTE]
>
>Se la migrazione continua a non riuscire dopo un nuovo tentativo, contatta l’Assistenza clienti con l’ID del progetto. Puoi trovare l’ID del progetto nella pagina Stato della migrazione. <!-- when does this page display? How can they get there -->

Per ritentare una migrazione non riuscita:

1. In Adobe Analytics, seleziona la scheda [!UICONTROL **Amministrazione**], quindi seleziona [!UICONTROL **Tutte le attività di amministrazione**].

1. In [!UICONTROL **Configurazione e raccolta dati**], selezionare [!UICONTROL **Migrazione componenti**].

1. Selezionare [!UICONTROL **Non riuscito**] nella colonna [!UICONTROL **Stato migrazione**] accanto al progetto che si desidera riprovare.

   ![colonna dello stato di migrazione non riuscita](assets/migration-failed.png)

   Viene visualizzata la pagina [!UICONTROL **Stato migrazione**].

   Questa pagina viene visualizzata anche subito dopo aver completato i passaggi di migrazione descritti nella sezione [Migrare i progetti Adobe Analytics al Customer Journey Analytics](#migrate-adobe-analytics-projects-to-customer-journey-analytics) precedente.

1. Selezionare [!UICONTROL **Ritenta migrazione**].

## Filtrare, ordinare ed eseguire ricerche nell’elenco dei progetti

Puoi filtrare, ordinare ed eseguire ricerche nell’elenco dei progetti nella pagina Migrazione dei componenti.

### Filtrare l’elenco dei progetti

Puoi filtrare in base ai seguenti criteri:

| Filtro | Descrizione |
|---------|----------|
| [!UICONTROL **Stato**] | Stato della migrazione: <ul><li>[!UICONTROL **Non avviato**]</li><li>[!UICONTROL **Avviato**]</li><li>[!UICONTROL **Completato**]</li><li>[!UICONTROL **Non riuscito**]</li></ul>. |
| [!UICONTROL **Tag**] | Seleziona qualsiasi tag nell’elenco dei tag. Vengono visualizzati solo i progetti a cui sono applicati i tag selezionati. |
| [!UICONTROL **Suite di rapporti**] | Seleziona una suite di rapporti nell’elenco delle suite di rapporti. Vengono visualizzati solo i progetti che utilizzano le suite di rapporti selezionate. |
| [!UICONTROL **Proprietari**] | Selezionare un proprietario nell&#39;elenco dei proprietari. Vengono visualizzati solo i progetti di proprietà degli utenti selezionati. |
| [!UICONTROL **Altri filtri**] | Sono disponibili i seguenti filtri aggiuntivi: <ul><li>[!UICONTROL **Personali**]: mostra solo i progetti in cui sei impostato come proprietario.</li><li>[!UICONTROL **Condivisi con me**]: mostra solo i progetti condivisi con te.</li><li>[!UICONTROL **Preferiti**]: mostra solo i progetti contrassegnati come preferiti. Puoi contrassegnare un progetto come preferito dalla [pagina di destinazione del progetto](/help/analyze/landing.md).</li><li>[!UICONTROL **Mensile**]</li><li>[!UICONTROL **Annuale**]</li></ul> |

{style="table-layout:auto"}

### Ordinare l’elenco dei progetti

Puoi ordinare l’elenco dei progetti in base a qualsiasi colonna.

Per ordinare l’elenco dei progetti:

1. Selezionare l&#39;intestazione della colonna in base alla quale si desidera ordinare.

1. (Facoltativo) Seleziona nuovamente la stessa intestazione di colonna per invertire l’ordinamento.

### Cercare un progetto

Puoi cercare l’elenco dei progetti nella pagina Migrazione componenti per trovare il progetto di cui desideri eseguire la migrazione.

1. Nel campo di ricerca nella parte superiore della pagina di migrazione dei componenti, inizia a digitare il nome del progetto di cui desideri eseguire la migrazione.

1. Seleziona il progetto quando viene visualizzato nel menu a discesa.

<!-- is there going to be a way to customize the columns that are displayed? -->
