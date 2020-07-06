---
description: Consente agli utenti di livello amministratore di visualizzare e gestire i rapporti pianificati in tutta l'organizzazione.
title: Coda dei report pianificati
topic: Reports
uuid: 3fcf92d3-a472-465f-ad7a-c48cd9a8238b
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 2%

---


# Coda dei report pianificati

Consente agli utenti di livello amministratore di visualizzare e gestire i rapporti pianificati in tutta l&#39;organizzazione.

**[!UICONTROL Analytics]** (Workspace) > **[!UICONTROL Components]** (Progetto) > **[!UICONTROL Scheduled Reports]** (Annulla/Ripeti)

Le funzionalità di livello amministratore in Scheduled Reports Manager includono:

* Opzione per [visualizzare tutti i report](/help/admin/admin/scheduled-reports-admin.md#section_3F167CAAEEC24140B476CF95B7402690) pianificati nella tua organizzazione.
* [Funzionalità](/help/admin/admin/scheduled-reports-admin.md#section_206A52A85DE84947AAB3AD082FBF6275) di filtro avanzate in tutta l&#39;organizzazione.
* La nuova scheda Coda [](/help/admin/admin/scheduled-reports-admin.md#section_03C866115D354BB182E90BF4D52F1E0B) report in cui sono elencati tutti i report in coda per l&#39;esecuzione sui server di report.
* Esposizione dell&#39;ID [](/help/admin/admin/scheduled-reports-admin.md#section_568B70F4228C4229977CB85D2DCD53A1) pianificazione nell&#39;interfaccia Coda report.

## Mostra tutti i rapporti pianificati {#section_3F167CAAEEC24140B476CF95B7402690}

Nella **[!UICONTROL Report List]** scheda, puoi **[!UICONTROL Show All Scheduled Reports]** entrare nella tua organizzazione, oltre a quelle che hai personalmente pianificato.

>[!NOTE]
>
>Nella **[!UICONTROL Report Name]** colonna viene visualizzato il nome del rapporto in corso di programmazione e nella **[!UICONTROL File Name]** colonna viene visualizzato il nome di file personalizzato impostato dall&#39;utente in Opzioni di consegna avanzate. Di conseguenza, se si pianificano più rapporti dello stesso tipo e si specificano nomi personalizzati per ciascuno di essi, Gestore report pianificati visualizzerebbe più voci con lo stesso Nome rapporto ma con nomi di file diversi. Questo perché il rapporto di back-end pianificato è lo stesso, quindi la colonna Nome rapporto avrà gli stessi nomi di rapporto per tutti i nomi di file, tranne i nomi personalizzati (come impostato).

![](assets/show_all_scheduled_reports.png)

## Funzionalità di filtro avanzate {#section_206A52A85DE84947AAB3AD082FBF6275}

Ad esempio, se desiderate filtrare tutti i rapporti pianificati ogni ora, specificate **[!UICONTROL Frequency equals Hourly]** nel **[!UICONTROL Advanced]** filtro e fate clic su **[!UICONTROL Apply]**:

![](assets/advanced_filtering_schedl_reports.png)

## Coda report {#section_03C866115D354BB182E90BF4D52F1E0B}

Questa coda consente di gestire ed eliminare potenzialmente tutti i rapporti pianificati che &quot;bloccano&quot; la coda. In genere, i report scadono dopo 4 ore.

![](assets/scheduled_reports_2.png)

La coda di report consente inoltre di &quot;saltare un report pianificato una volta&quot;. Basta fare clic sull&#39;icona blu nella **[!UICONTROL Manage]** colonna.

## ID pianificazione {#section_568B70F4228C4229977CB85D2DCD53A1}

La visualizzazione **[!UICONTROL Schedule ID]** nell&#39;interfaccia Coda report consente di contattare Adobe Client Care per risolvere un problema dei report pianificati.

![](assets/schedule_id.png)
