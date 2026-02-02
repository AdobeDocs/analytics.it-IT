---
title: Configurare Le Impostazioni Per Report Builder
description: Scopri come configurare le impostazioni per Report Builder.
role: Admin
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: d158ad45-d467-4355-b091-f015bde7a243
source-git-commit: c3fe537967473754a3b5fe88c7b383647b2c742e
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 4%

---

# Impostazioni di Report Builder


Utilizza il riquadro **Impostazioni** per configurare le impostazioni a livello di applicazione, ad esempio la lingua visualizzata dall&#39;interfaccia utente o se utilizzare o meno la modalità offline. Le impostazioni vengono applicate immediatamente e vengono impostate per tutte le sessioni future fino a quando non vengono modificate.

Per modificare le impostazioni di Report Builder

1. Seleziona l&#39;icona **Impostazioni**.

1. Apportare modifiche a [attivazione della modalità offline](#off-line-mode), [selezione di una lingua](#language) o [attivazione della risoluzione dei problemi](#troubleshooting).

1. Seleziona **[!UICONTROL Apply]**.

   ![Riquadro dell&#39;intervallo di date di Report Builder con il pulsante Annulla e applica.](./assets/report-builder-settings.png){zoomable="yes"}

## Modalità offline

Quando crei e modifichi un blocco di dati in modalità offline, i dati non vengono recuperati. Al contrario, i dati di simulazione vengono utilizzati in modo da poter lavorare rapidamente senza attendere l’esecuzione della richiesta. Quando sei di nuovo online, seleziona ![Aggiorna](/help/assets/icons/Refresh.svg) **[!UICONTROL Refresh data block]** o ![AggiornaDocumento](/help/assets/icons/DocumentRefresh.svg) **[!UICONTROL Refresh all data blocks]** per aggiornare i blocchi di dati con i dati effettivi.

Per attivare la modalità offline

1. Seleziona ![Impostazione](/help/assets/icons/Setting.svg).

1. Attiva **[!UICONTROL Enable off-line mode]**.

1. Immettere un numero intero positivo nel campo **[!UICONTROL Display metric data]** come.

1. Seleziona **[!UICONTROL Apply]**.


## Lingua

È possibile scegliere la lingua per l&#39;interfaccia di Report Builder. Sono disponibili tutte le lingue di Customer Journey Analytics supportate.

Per selezionare la lingua utilizzata nell&#39;interfaccia di Report Builder:

1. Selezionare una lingua dal menu a discesa **[!UICONTROL Language]**.

1. Seleziona **Applica.**

## Risoluzione dei problemi

L&#39;impostazione **[!UICONTROL Troubleshooting logs]** registra tutti i dati client/server in un file locale. Utilizza questa opzione per risolvere i ticket di supporto.

Per abilitare i registri di risoluzione dei problemi, selezionare **[!UICONTROL Log report builder request to local file]**.

<!--
Use the **Settings** pane to configure application-level settings such as the language displayed by the UI or whether or not to work in off-line mode. The settings are applied immediately and they are set for all future sessions until they're changed.

To change Report Builder settings

1. Click the **Settings** icon.

1. Make changes to Enable off-line mode, select a Language, or enable Troubleshooting log settings.

1. Click **Apply**.

    ![Report Builder settings.](./assets/image38.png)

## Off-line mode

When creating and editing a data block in off-line mode, data is not retrieved. Instead, simulation data is used so that you can quickly create and edit a data block without waiting for the request to run. When you are back online, the *Refresh data block* command or *Refresh all data blocks* command refreshes the data blocks that you created with actual data.

To enable off-line mode

1. Click the **[!UICONTROL Settings]** icon.

1. Select **[!UICONTROL Enable off-line mod]e**.

1. Enter a positive integer in the **[!UICONTROL Display metric data as]** field.

1. Click **[!UICONTROL Apply]**.

## Language

You can choose the language for the Report Builder UI. All supported Adobe Analytics languages are available.

To select the language used in the Report Builder UI

 1. Click Settings.

 1. Select a language from the **[!UICONTROL Language]** drop down menu.

     ![Report Builder date range pane showing the Language list with English selected.](./assets/image39.png)

 1. Click **[!UICONTROL Apply].**

## Troubleshooting

Use the Troubleshooting setting to log all client/server data to a local file. Use this option to help resolve support tickets.

To enable the Troubleshooting option, select **[!UICONTROL Log report builder data block to web console]**.
-->