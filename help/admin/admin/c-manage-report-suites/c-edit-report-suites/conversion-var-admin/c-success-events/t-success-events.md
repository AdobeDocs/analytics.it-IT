---
description: Passaggi che descrivono come configurare gli eventi di successo.
title: Configurare eventi di successo
feature: Event
role: Admin
exl-id: 0e9a6d8f-2ce7-4551-885d-bd77ff131da0
source-git-commit: d173a6c6c9751a86f4218ec842da17da14f8485b
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 82%

---

# Configurare eventi di successo

Per configurare eventi di successo:

1. Fai clic su **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Seleziona una suite di rapporti.
1. Fai clic su **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Success Events]**.

   ![Risultato del passaggio](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/assets/success_event_page.png)

1. Nella colonna **[!UICONTROL Name]** seleziona la casella di controllo accanto a ogni elemento per abilitarne la modifica, quindi specifica il nome desiderato.
1. Nella colonna **[!UICONTROL Type]** seleziona la casella di controllo accanto a ogni elemento per abilitare l’elenco a discesa, quindi seleziona il tipo desiderato.

   >[!NOTE]
   >
   >Prima di modificare un tipo di evento, vedi [Cambiare tipo di evento](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/event-type.md).

   Vedi [Pagina Eventi di successo: descrizioni](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) per informazioni su questi elementi.

1. Nella colonna **[!UICONTROL Polarity]** specifica se una tendenza verso l’alto per questa metrica è buona o cattiva.
1. Nella colonna **[!UICONTROL Visibility]** puoi nascondere le metriche standard (integrate), gli eventi personalizzati e gli eventi incorporati in Menu, Selettori metriche, Generatore metriche calcolate e Generatore segmenti.

   Questa impostazione non influisce sulla raccolta di dati per quella metrica o evento; influisce solo sulla sua visibilità nell’interfaccia utente, come segue:


   | Impostazione | Visibile in | Non visibile in |
   |---------|----------|---------|
   | [!UICONTROL **Visibile ovunque**] | <ul><li>Analysis Workspace</li><li>Generatore di segmenti</li><li>Generatore di metrica calcolata</li></ul> | N/D |
   | [!UICONTROL **Generatori**] | <ul><li>Generatore di segmenti</li><li>Generatore di metrica calcolata</li><li>Analysis Workspace</li></ul> |
   | [!UICONTROL **Nascosto ovunque**] | N/D | <ul><li>Analysis Workspace</li><li>Generatore di segmenti</li><li>Generatore di metrica calcolata</li></ul> |

1. Fornisci una descrizione.
1. Controlla se registrare sempre l’evento.
1. Abilitare o disabilitare le metriche di partecipazione.

   >[!NOTE]
   >
   >Puoi abilitare la partecipazione per un massimo di 100 eventi personalizzati. Inoltre, puoi creare metriche di partecipazione nel generatore [Metriche calcolate](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/participation-metric.md).

1. Fai clic su **[!UICONTROL Save]**.
