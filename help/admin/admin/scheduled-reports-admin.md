---
description: Consente agli utenti di livello amministratore di vedere e gestire i report pianificati nell'organizzazione.
seo-description: Consente agli utenti di livello amministratore di vedere e gestire i report pianificati nell'organizzazione.
seo-title: Coda dei report pianificati
solution: Analytics
title: Coda dei report pianificati
topic: Rapporti
uuid: 3 fcf 92 d 3-a 472-465 f-ad 7 a-c 48 cd 9 a 8238 b
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Coda dei report pianificati

Consente agli utenti di livello amministratore di vedere e gestire i report pianificati nell'organizzazione.

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Components]** &gt; **[!UICONTROL Scheduled Reports]**

Le funzionalità a livello di amministratore in Scheduled Reports Manager (Gestore report programmati) includono:

* The option to [Show all Scheduled Reports](../../admin/admin/scheduled-reports-admin.md#section_3F167CAAEEC24140B476CF95B7402690) in your organization.
* [Funzionalità avanzate di filtraggio](../../admin/admin/scheduled-reports-admin.md#section_206A52A85DE84947AAB3AD082FBF6275) dell'intera organizzazione.
* The new [Report Queue](../../admin/admin/scheduled-reports-admin.md#section_03C866115D354BB182E90BF4D52F1E0B) tab that lists all reports that are queued for execution on reporting servers.
* Exposing the [Schedule ID](../../admin/admin/scheduled-reports-admin.md#section_568B70F4228C4229977CB85D2DCD53A1) in the Report Queue interface.

## Show all Scheduled Reports {#section_3F167CAAEEC24140B476CF95B7402690}

On the **[!UICONTROL Report List]** tab, you can **[!UICONTROL Show All Scheduled Reports]** in your organization, in addition to the ones you personally scheduled.

>[!NOTE]
>
>The **[!UICONTROL Report Name]** column displays the name of the report which is being scheduled and the **[!UICONTROL File Name]** column displays any custom file name set by you in Advanced Delivery Options. Di conseguenza, se programmate più rapporti con lo stesso tipo di rapporto e specificate nomi personalizzati per ciascuno, il Gestore report pianificati visualizzerebbe più voci con lo stesso Nome rapporto, ma con nomi file diversi. poiché il rapporto sul back-end pianificato è lo stesso, la colonna Nome rapporto avrà gli stessi nomi di report per tutti i nomi dei file, ma personalizzati.

![](assets/show_all_scheduled_reports.png)

## Advanced Filtering Capabilities {#section_206A52A85DE84947AAB3AD082FBF6275}

For example, if you wanted to filter on all reports that are scheduled hourly, you would specify **[!UICONTROL Frequency equals Hourly]** in the **[!UICONTROL Advanced]** filter and click **[!UICONTROL Apply]**:

![](assets/advanced_filtering_schedl_reports.png)

## Report Queue {#section_03C866115D354BB182E90BF4D52F1E0B}

Questa coda consente di gestire e eliminare potenzialmente eventuali rapporti pianificati che eseguono la chiusura della coda. (Generalmente, i rapporti scadono dopo 4 ore.)

![](assets/scheduled_reports_2.png)

La coda di report consente anche di «saltare un report pianificato una volta». Just click the blue icon in the **[!UICONTROL Manage]** column.

## Schedule ID {#section_568B70F4228C4229977CB85D2DCD53A1}

Having the **[!UICONTROL Schedule ID]** exposed in the Report Queue interface helps when you need to contact Adobe Client Care for resolution of a scheduled reports issue.

![](assets/schedule_id.png)
