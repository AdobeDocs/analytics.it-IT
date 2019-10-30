---
description: Consente agli utenti di livello amministratore di visualizzare e gestire i rapporti pianificati in tutta l'organizzazione.
seo-description: Consente agli utenti di livello amministratore di visualizzare e gestire i rapporti pianificati in tutta l'organizzazione.
seo-title: Coda dei report pianificati
solution: Analytics
title: Coda dei report pianificati
topic: Rapporti
uuid: 3fcf92d3-a472-465f-ad7a-c48cd9a8238b
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Coda dei report pianificati

Consente agli utenti di livello amministratore di visualizzare e gestire i rapporti pianificati in tutta l'organizzazione.

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Components]** &gt; **[!UICONTROL Scheduled Reports]**

Le funzionalità di livello amministratore in Scheduled Reports Manager includono:

* Opzione per [visualizzare tutti i report](../../admin/admin/scheduled-reports-admin.md#section_3F167CAAEEC24140B476CF95B7402690) pianificati nella tua organizzazione.
* [Funzionalità](../../admin/admin/scheduled-reports-admin.md#section_206A52A85DE84947AAB3AD082FBF6275) di filtro avanzate in tutta l'organizzazione.
* La nuova scheda Coda [](../../admin/admin/scheduled-reports-admin.md#section_03C866115D354BB182E90BF4D52F1E0B) report in cui sono elencati tutti i report in coda per l'esecuzione sui server di report.
* Esposizione dell'ID [](../../admin/admin/scheduled-reports-admin.md#section_568B70F4228C4229977CB85D2DCD53A1) pianificazione nell'interfaccia Coda report.

## Mostra tutti i rapporti pianificati {#section_3F167CAAEEC24140B476CF95B7402690}

Nella **[!UICONTROL Report List]** scheda, puoi **[!UICONTROL Show All Scheduled Reports]** entrare nella tua organizzazione, oltre a quelle che hai personalmente pianificato.

> [!NOTE] Nella **[!UICONTROL Report Name]** colonna viene visualizzato il nome del rapporto in corso di programmazione e nella **[!UICONTROL File Name]** colonna viene visualizzato il nome di file personalizzato impostato dall'utente in Opzioni di consegna avanzate. Di conseguenza, se si pianificano più rapporti dello stesso tipo e si specificano nomi personalizzati per ciascuno di essi, Gestore report pianificati visualizzerebbe più voci con lo stesso Nome rapporto ma con nomi di file diversi. Questo perché il rapporto di back-end pianificato è lo stesso, quindi la colonna Nome rapporto avrà gli stessi nomi di rapporto per tutti i nomi di file, tranne i nomi personalizzati (come impostato).

![](assets/show_all_scheduled_reports.png)

## Funzionalità di filtro avanzate {#section_206A52A85DE84947AAB3AD082FBF6275}

Ad esempio, se desiderate filtrare tutti i rapporti pianificati ogni ora, specificate **[!UICONTROL Frequency equals Hourly]** nel **[!UICONTROL Advanced]** filtro e fate clic su **[!UICONTROL Apply]**:

![](assets/advanced_filtering_schedl_reports.png)

## Coda report {#section_03C866115D354BB182E90BF4D52F1E0B}

Questa coda consente di gestire ed eliminare potenzialmente tutti i rapporti pianificati che "bloccano" la coda. In genere, i report scadono dopo 4 ore.

![](assets/scheduled_reports_2.png)

La coda di report consente inoltre di "saltare un report pianificato una volta". Basta fare clic sull'icona blu nella **[!UICONTROL Manage]** colonna.

## ID pianificazione {#section_568B70F4228C4229977CB85D2DCD53A1}

La visualizzazione **[!UICONTROL Schedule ID]** nell'interfaccia Coda report consente di contattare Adobe Client Care per risolvere un problema dei report pianificati.

![](assets/schedule_id.png)
