---
description: Consente agli utenti a livello di amministratore di visualizzare e gestire i rapporti pianificati in tutta l’organizzazione.
title: Coda dei report pianificati
feature: Admin Tools
uuid: 3fcf92d3-a472-465f-ad7a-c48cd9a8238b
exl-id: 7287e6c7-e354-48a0-9343-35dccfc46e63
source-git-commit: e7346b11a7d3eb4c18ec02df6c8a07574e02a2b4
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 2%

---

# Coda dei report pianificati

Consente agli utenti a livello di amministratore di visualizzare e gestire i rapporti pianificati in tutta l’organizzazione.

**[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL All components]** > **[!UICONTROL Scheduled Reports]**

Le funzionalità a livello di amministratore in Scheduled Reports Manager includono:

* L’opzione [Mostra tutti i report pianificati](/help/admin/admin/scheduled-reports-admin.md#section_3F167CAAEEC24140B476CF95B7402690) nella tua organizzazione.
* [Funzionalità di filtro avanzate](/help/admin/admin/scheduled-reports-admin.md#section_206A52A85DE84947AAB3AD082FBF6275) nell’intera organizzazione.
* Il nuovo [Coda report](/help/admin/admin/scheduled-reports-admin.md#section_03C866115D354BB182E90BF4D52F1E0B) che elenca tutti i rapporti in coda per l’esecuzione sui server di reporting.
* Esposizione delle [ID pianificazione](/help/admin/admin/scheduled-reports-admin.md#section_568B70F4228C4229977CB85D2DCD53A1) nell’interfaccia Report Queue.

## Mostra tutti i report pianificati {#section_3F167CAAEEC24140B476CF95B7402690}

Sulla **[!UICONTROL Report List]** è possibile **[!UICONTROL Show All Scheduled Reports]** nella tua organizzazione, oltre a quelli che hai personalmente pianificato.

>[!NOTE]
>
>La **[!UICONTROL Report Name]** visualizza il nome del report in corso di pianificazione e il **[!UICONTROL File Name]** In Opzioni di consegna avanzate viene visualizzato il nome di file personalizzato impostato da te. Di conseguenza, se si pianificano più rapporti dello stesso tipo e si specificano nomi personalizzati per ciascuno di essi, in Gestione rapporti programmati verranno visualizzate più voci con lo stesso nome del rapporto ma con nomi di file diversi. Questo perché il report di back end programmato è lo stesso, quindi la colonna Nome report avrebbe gli stessi nomi di report per tutti i nomi di file eccetto quelli personalizzati (come impostato).

![](/help/admin/admin/assets/show_all_scheduled_reports.png)

## Funzionalità di filtro avanzate {#section_206A52A85DE84947AAB3AD082FBF6275}

Ad esempio, se desideri filtrare tutti i rapporti pianificati ogni ora, specifica **[!UICONTROL Frequency equals Hourly]** in **[!UICONTROL Advanced]** filtra e fai clic su **[!UICONTROL Apply]**:

![](/help/admin/admin/assets/advanced_filtering_schedl_reports.png)

## Coda report {#section_03C866115D354BB182E90BF4D52F1E0B}

Questa coda ti consente di gestire e potenzialmente eliminare tutti i rapporti pianificati che si stanno &quot;bloccando&quot; la coda. In genere, i rapporti scadono dopo 4 ore.

![](/help/admin/admin/assets/scheduled_reports_2.png)

La coda dei report consente inoltre di &quot;saltare un report pianificato una volta&quot;. Fai clic sull’icona blu nel **[!UICONTROL Manage]** colonna.

## ID pianificazione {#section_568B70F4228C4229977CB85D2DCD53A1}

Avere **[!UICONTROL Schedule ID]** esposto nell’interfaccia della coda dei rapporti aiuta a contattare l’Assistenza clienti di Adobe per la risoluzione di un problema di rapporti pianificati.

![](/help/admin/admin/assets/schedule_id.png)
