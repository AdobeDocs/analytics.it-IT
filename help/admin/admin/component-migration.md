---
description: Spiega come migrare componenti e progetti da Adobe Analytics a Customer Journey Analytics.
title: Migrazione di componenti e progetti da Adobe Analytics a Customer Journey Analytics
feature: Admin Tools
source-git-commit: 8eb26f7aa3dcbb21f4d0c042b8d6958aa0a19cf6
workflow-type: tm+mt
source-wordcount: '1649'
ht-degree: 7%

---

# Migrazione di componenti e progetti da Adobe Analytics a Customer Journey Analytics

Gli amministratori di Adobe Analytics possono eseguire la migrazione di componenti e progetti Adobe Analytics al Customer Journey Analytics.

Il processo di migrazione include:

* Ricreare i progetti Adobe Analytics nel Customer Journey Analytics.

* Mappatura di dimensioni e metriche dalle suite di rapporti di Adobe Analytics alle dimensioni e alle metriche nelle visualizzazioni dati del Customer Journey Analytics.

  Alcune dimensioni e metriche vengono mappate automaticamente; altre devono essere mappate manualmente come parte del processo di migrazione.

## Prepararsi per una migrazione

Prima di iniziare la migrazione dei progetti all’interno dell’organizzazione, completa i prerequisiti, scopri cosa è e cosa non viene migrato e crea un piano di migrazione per l’organizzazione.

### Prerequisiti

Prima che i progetti e le dimensioni e metriche associate siano pronti per la migrazione, devi effettuare le seguenti operazioni:

* Utilizza il connettore di origine di Analytics per visualizzare i dati della suite di rapporti di Adobe Analytics nel Customer Journey Analytics. Per farlo, devi:

   * [Configurare le suite di rapporti per l’acquisizione in Adobe Experience Platform e Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=en#set-up-report-suites-for-ingestion-into-the-adobe-experience-platform-and-customer-journey-analytics)

   * [Inserire e utilizzare i dati](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/analytics.html?lang=it)

* Assicurati che gli utenti nel Customer Journey Analytics siano assegnati alle visualizzazioni dati in cui vengono mappati i dati.

  Per ulteriori informazioni, consulta [Autorizzazioni di Customer Journey Analytics nell’Admin Console](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html?lang=en#customer-journey-analytics-permissions-in-admin-console) in [Controllo dell’accesso al Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html).

  La scheda Autorizzazioni fa parte di ciascun profilo di prodotto in Admin Console. Puoi aggiungere utenti a profili di prodotto specifici. Dopodiché dovrai assegnare i diritti a visualizzazioni di dati specifiche e specificare quali autorizzazioni hanno gli utenti in un profilo di prodotto.

* Creare un piano di migrazione come descritto nella sezione seguente. [Creare un piano di migrazione come organizzazione](#create-a-migration-plan-as-an-organization).

### Informazioni incluse in una migrazione

La tabella seguente illustra gli elementi di un progetto e di un componente inclusi in una migrazione:


|  | Progetti | Dimension e metriche |
|---------|----------|---------|
| **Intervalli di date** | Sì | N/D |
| **Segmenti** | Sì | N/D |
| **Segmenti rapidi** | Sì | N/D |
| **Pannelli** | Sì | N/D |
| **Visualizzazioni** | Sì | N/D |
| **Proprietario** | (definito dall’utente che esegue la migrazione) | ? |
| **Cura** | No | N/D |
| **Condivisione (ruoli di progetto)** | No | No |
| **Annotazioni** | No | N/D |
| **Struttura delle cartelle** | No | N/D |
| **Descrizioni** | Sì | ? |
| **Tag** | ? | ? |
| **Schedules** | ? | N/D |
| **Attribuzione (sulle dimensioni)** | N/D | ? |
| **Rilevamento delle anomalie** | ? | N/D |
| **Analisi contributi** | ? | N/D |
| **Avvisi** | ? | N/D |

{style="table-layout:auto"}

### Creare un piano di migrazione come organizzazione

Poiché tutti i componenti mappati per una determinata migrazione di progetto vengono applicati a qualsiasi migrazione di progetto futura per l’intera organizzazione, è importante che la tua organizzazione pianifichi in anticipo tutte le migrazioni di progetto.

È necessario decidere come organizzazione la mappatura di dimensioni e metriche. In questo modo i singoli amministratori non possono prendere decisioni all’interno di un silo se si considera un solo progetto.

## Migrare progetti Adobe Analytics al Customer Journey Analytics

>[!IMPORTANT]
>
>Prima di eseguire la migrazione di progetti al Customer Journey Analytics come descritto in questa sezione, ulteriori informazioni sulla migrazione di progetti sono disponibili in [Pianificare la migrazione](#plan-the-migration) sopra.
>
>Qualsiasi dimensione o metrica mappata è permanente, sia per questo progetto che per tutti i progetti futuri migrati in tutta l’organizzazione. Al termine della migrazione, non sarà più possibile modificare le mappature effettuate.

1. In Adobe Analytics, seleziona la scheda [!UICONTROL **Amministrazione**], quindi seleziona [!UICONTROL **Tutte le attività di amministrazione**].

1. Sotto [!UICONTROL **Configurazione e raccolta dati**], seleziona [!UICONTROL **Migrazione dei componenti**].

1. Individua il progetto di cui vuoi eseguire la migrazione. Puoi filtrare, ordinare o cercare nell’elenco dei progetti.

   Per impostazione predefinita, vengono visualizzati solo i progetti condivisi con te. Per visualizzare tutti i progetti dell’organizzazione, seleziona la **Filtro** , quindi espandi [!UICONTROL **Altri filtri**] e seleziona [!UICONTROL **Mostra tutto**]. Per ulteriori informazioni su come filtrare, ordinare e cercare nell’elenco dei progetti, consulta [Filtrare, ordinare ed eseguire ricerche nell’elenco dei progetti](#filter-sort-and-search-the-list-of-projects).)

1. Passa il puntatore del mouse sul progetto di cui vuoi eseguire la migrazione, quindi seleziona la **Migra** icona ![Migra progetto](assets/migrate.svg).

   Oppure

   Seleziona il progetto di cui vuoi eseguire la migrazione, quindi fai clic su [!UICONTROL **Migra al Customer Journey Analytics**].

   È possibile selezionare un solo progetto alla volta per la migrazione.

   Il [!UICONTROL **Migra nome_progetto a Customer Journey Analytics**] viene visualizzata.

   <!-- add screenshot -->

1. In [!UICONTROL **Proprietario del progetto**] , inizia a digitare il nome dell’utente che desideri impostare come proprietario del progetto nel Customer Journey Analytics, quindi selezionane il nome nel menu a discesa.

   Il proprietario specificato dispone dei diritti di gestione completi per il progetto.

1. In [!UICONTROL **Schema della mappa per le suite di rapporti**] , seleziona una suite di rapporti.

1. In [!UICONTROL **Visualizzazione dati**] dal menu a discesa, seleziona la visualizzazione dati del Customer Journey Analytics in cui desideri eseguire la migrazione del progetto e dei componenti.

1. Seleziona [!UICONTROL **Mappa schema**].

1. In [!UICONTROL **Mappa schema**] , espandere la sezione [!UICONTROL **Dimension**] e [!UICONTROL **Metriche**] sezioni.

   Alcune dimensioni e metriche in Adobe Analytics vengono mappate automaticamente a una dimensione o metrica nel Customer Journey Analytics. Altri devono essere mappati manualmente.

   **Mappare automaticamente dimensioni e metriche**

   Alcune dimensioni e metriche in Adobe Analytics vengono mappate automaticamente a una dimensione o metrica nel Customer Journey Analytics. Non puoi prendere decisioni di mappatura per queste dimensioni e metriche.

   Ad esempio, il **Visite** metrica in Adobe Analytics viene mappata automaticamente con **Sessioni** metrica nel Customer Journey Analytics.

   Puoi selezionare qualsiasi dimensione o metrica per visualizzare i relativi ID associati.

   <!-- update screenshot after I can see the Status column -->

   ![Schema di migrazione del progetto](assets/project-migration-schema.png)

   **Mappare manualmente dimensioni e metriche**

   Alcune dimensioni e metriche in Adobe Analytics non possono essere mappate automaticamente a una dimensione o metrica nel Customer Journey Analytics.

   Quando non è possibile mappare automaticamente una dimensione o una metrica, accanto al valore viene visualizzato un contatore arancione [!UICONTROL **Dimension**] o [!UICONTROL **Metriche**] intestazione di sezione, che indica il numero di dimensioni o metriche da mappare manualmente. Nella tabella, un’icona di avvertenza ![icona di avviso](assets/schema-warning.png) viene visualizzato accanto a ciascuna dimensione o metrica da mappare manualmente.

   Inoltre, la [!UICONTROL **Stato**] la colonna dice [!UICONTROL **Non mappato**].

   <!-- update screenshot after I can see the Status column -->

   ![Mappa manuale dello schema di migrazione](assets/schema-manual-map.png)

1. Per mappare manualmente dimensioni e metriche, seleziona una dimensione o una metrica contenente un’icona di avviso ![icona di avviso](assets/schema-warning.png), quindi in [!UICONTROL **Metrica di Customer Journey Analytics mappata**] campo (o [!UICONTROL **Dimensione Customer Journey Analytics mappato**] se stai mappando una dimensione), seleziona la dimensione o la metrica nel Customer Journey Analytics che desideri mappare alla dimensione o alla metrica selezionata.

   ![mappare dimensioni e metriche](assets/schema-manual-map-drop-down.png)

   Dopo aver mappato una dimensione o una metrica, l’icona di avviso scompare e il simbolo [!UICONTROL **Stato**] la colonna cambia in [!UICONTROL **Mappato**] con un punto verde. (Stato di [!UICONTROL **Mappato**] un punto grigio indica che la dimensione o la metrica è stata mappata durante una migrazione precedente; non è possibile aggiornare eventuali mappature precedenti.)

   Ripeti questo processo per ogni dimensione o metrica contenente l’icona di avviso.

   Dopo aver mappato tutte le dimensioni e le metriche nella suite di rapporti di Adobe Analytics su una dimensione o metrica nella visualizzazione dati del Customer Journey Analytics, un segno di spunta verde ![segno di spunta](assets/report-suite-check.png) viene visualizzato accanto al nome della suite di rapporti nella [!UICONTROL **Schema della mappa per le suite di rapporti**] sezione.

1. (Condizionale) Se il progetto di cui stai eseguendo la migrazione contiene più di una suite di rapporti, seleziona un’altra suite di rapporti in [!UICONTROL **Schema della mappa per le suite di rapporti**] quindi ripetere i passaggi da 6 a 10. <!-- double-check that the step numbers are still correct -->

1. Seleziona [!UICONTROL **Migra**].

   >[!WARNING]
   >
   >   Dopo aver selezionato, viene visualizzato un messaggio di avviso sullo schermo [!UICONTROL **Migra**]. Prima di scegliere di continuare, assicurati che tutte le dimensioni o metriche mappate siano permanenti, sia per questo progetto che per tutti i progetti futuri migrati in tutta l’organizzazione. Se si continua, le mappature create non potranno essere modificate.

   Al termine di una migrazione, il [!UICONTROL **Stato della migrazione**] fornisce un riepilogo di ciò che è stato trasferito.

   Se la migrazione non riesce, consulta la [Ritentare una migrazione non riuscita](#retry-a-failed-migration) per ulteriori informazioni.

## Ritentare una migrazione non riuscita

Se una migrazione non riesce, puoi riprovare.

È possibile ritentare una migrazione non riuscita in uno dei modi seguenti:

>[!NOTE]
>
>Se la migrazione continua a non riuscire dopo un nuovo tentativo, contatta l’Assistenza clienti con l’ID del progetto. Puoi trovare l’ID del progetto nella pagina Stato della migrazione. <!-- when does this page display? How can they get there -->

1. In Adobe Analytics, seleziona la scheda [!UICONTROL **Amministrazione**], quindi seleziona [!UICONTROL **Tutte le attività di amministrazione**].

1. Sotto [!UICONTROL **Configurazione e raccolta dati**], seleziona [!UICONTROL **Migrazione dei componenti**].

1. Seleziona [!UICONTROL **Non riuscito**] nel [!UICONTROL **Stato della migrazione**] accanto al progetto che si desidera riprovare.

   ![colonna dello stato di migrazione non riuscita](assets/migration-failed.png)

   Il [!UICONTROL **Stato della migrazione**] viene visualizzata la pagina.

   Questa pagina viene visualizzata anche subito dopo aver completato i passaggi di migrazione descritti nella sezione [Migrare progetti Adobe Analytics al Customer Journey Analytics](#migrate-adobe-analytics-projects-to-customer-journey-analytics) sopra.

1. Seleziona [!UICONTROL **Ritenta migrazione**].

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
| [!UICONTROL **Altri filtri**] | Sono disponibili i seguenti filtri aggiuntivi: <ul><li>[!UICONTROL **Il mio**]: mostra solo i progetti in cui sei impostato come proprietario.</li><li>[!UICONTROL **Condiviso con me**]: mostra solo i progetti che sono stati condivisi con te.</li><li>[!UICONTROL **Preferiti**]: mostra solo i progetti contrassegnati come preferiti. (Puoi contrassegnare un progetto come preferito dalla sezione [pagina di destinazione del progetto](/help/analyze/landing.md).)</li><li>[!UICONTROL **Mensile**]</li><li>[!UICONTROL **Annuale**]</li></ul> |

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
