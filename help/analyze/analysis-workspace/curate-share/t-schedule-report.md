---
description: Scopri come inviare un progetto Analysis Workspace direttamente o secondo una pianificazione per la consegna e-mail.
keywords: Analysis Workspace
title: Inviare E Programmare Progetti
feature: Curate and Share
role: User, Admin
exl-id: 2d6854f7-8954-4d55-b2be-25981cfb348b
source-git-commit: 61fcafa0e2e6cb71d9b594984e9a0c71a76c13e4
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 34%

---

# Inviare e pianificare progetti

Puoi inviare progetti Adobe Analytics come file a utenti selezionati tramite e-mail. Puoi inviare file ad hoc oppure configurare i file da inviare in base a una pianificazione.

Quando invii dei file, tieni presente quanto segue:

* I file possono essere inviati in formato CSV o PDF.

* Tutti i tag applicati al progetto vengono applicati automaticamente all’esportazione.

Sono disponibili anche altri metodi di esportazione dei dati di Adobe Analytics, come descritto in [Panoramica sull&#39;esportazione](/help/export/home.md).

![Invia file](assets/send-file.png)

## Invia file

Per inviare un file ad hoc ai destinatari tramite e-mail:

1. Seleziona **[!UICONTROL Share]>[!UICONTROL Send file]**.
1. Specifica il tipo di file:
   * [!UICONTROL **CSV**]: scegli questa opzione se desideri utilizzare dati in formato testo normale.
   * [!UICONTROL **PDF**]: scegli questa opzione se vuoi che il file scaricato contenga tutte le tabelle e le visualizzazioni mostrate (visibili) nel progetto.
1. (Facoltativo) Utilizzare **[!UICONTROL Description]** per aggiungere una descrizione da includere nell&#39;e-mail.
1. Aggiungi destinatari o gruppi. Puoi anche immettere indirizzi e-mail.
1. (Facoltativo) Selezionare **[!UICONTROL Show scheduling options]** per [pianificare un&#39;esportazione di file](#schedule-file-export).
1. Fai clic su **[!UICONTROL Send Now]**. Seleziona **[!UICONTROL Cancel]** per annullare.


## Pianificare l’esportazione di file {#schedule}

Per inviare un file ai destinatari in base a una pianificazione tramite e-mail:

1. Seleziona **[!UICONTROL Share]>[!UICONTROL Schedule file export]**.
1. Specifica il tipo di file:
   * [!UICONTROL **CSV**]: scegli questa opzione se desideri utilizzare dati in formato testo normale.
   * [!UICONTROL **PDF**]: scegli questa opzione se vuoi che il file scaricato contenga tutte le tabelle e le visualizzazioni mostrate (visibili) nel progetto.
1. (Facoltativo) Utilizzare **[!UICONTROL Description]** per aggiungere una descrizione da includere nell&#39;e-mail.
1. Aggiungi destinatari o gruppi. Puoi anche immettere indirizzi e-mail.
1. (Solo per i clienti Healthcare Shield) Fornisci una password per [proteggere con password un report pianificato](#password-protect-a-new-scheduled-project).
1. Assicurarsi che **[!UICONTROL Show scheduling options]** sia selezionato.
1. Seleziona una **[!UICONTROL Frequency]**. Puoi scegliere tra:

   | Frequenza | Opzioni |
   |---|---|
   | **[!UICONTROL Send hourly]** | Immettere un valore per **[!UICONTROL Send every number of hours]**. |
   | **[!UICONTROL Send daily]** | Selezionare un **[!UICONTROL Daily frequency]**: **[!UICONTROL Send every day]**, **[!UICONTROL Send every weekday]** o **[!UICONTROL Custom frequency]**.<br/>Se si seleziona **[!UICONTROL Custom frequency]**, immettere un valore per **[!UICONTROL Send every number of days]**. |
   | **[!UICONTROL Send weekly]** | Immettere un valore per **[!UICONTROL Send every number of weeks]**. E seleziona un **[!UICONTROL Day of week]**. |
   | **[!UICONTROL Send monthly by day of the week]** | Selezionare **[!UICONTROL Day of week]** e **[!UICONTROL Week of month]**. |
   | **[!UICONTROL Send monthly by day of the month]** | Selezionare un valore da **[!UICONTROL Send on this day of the month]**. |
   | **[!UICONTROL Send yearly by day of the month]** | Selezionare un **[!UICONTROL Day of week]**, selezionare un **[!UICONTROL Week of month]** e selezionare un **[!UICONTROL Monthly of year]**. |
   | **[!UICONTROL Send yearly by specific date]** | Selezionare un **[!UICONTROL Month of year]** e un valore da **[!UICONTROL Send on this day of the month]**. |

1. Immettere una data di inizio in **[!UICONTROL Starting on]**. In alternativa, selezionare ![Calendario](/help/assets/icons/Calendar.svg) per scegliere una data di inizio dal calendario.

1. Immettere una data di fine in **[!UICONTROL Ending on]**. In alternativa, selezionare ![Calendario](/help/assets/icons/Calendar.svg) per scegliere una data di fine dal calendario.
1. Seleziona **[!UICONTROL Send on schedule]**. Seleziona **[!UICONTROL Cancel]** per annullare.


## Gestione progetti programmati {#manager}

I progetti Analysis Workspace pianificati possono essere gestiti dall&#39;interfaccia principale, utilizzando **[!UICONTROL Components]** > **[!UICONTROL Scheduled Projects]**. Per ulteriori informazioni, consulta [Progetti pianificati](/help/components/scheduled-projects-manager.md).

<!--
# Schedule projects

From the Workspace **Share menu**, you can send Analysis Workspace projects using email to selected recipients. Files can be sent in CSV or PDF format. After you share scheduled projects, you can edit the schedule settings to modify the frequency, receipient list, or file type using the Scheduled Projects manager.

## Send file now

To send a file immediately to recipients via email:

1. Click **[!UICONTROL Share] > [!UICONTROL Export file]**.
1. Specify the file type:
   * [!UICONTROL **CSV**]: Choose this option if you want plain-text data.
   * [!UICONTROL **PDF**]: Choose this option if you want the downloaded file to contain all the displayed (visible) tables and visualizations in the project.
1. (Optional) Add a description to include in the email to explain the file being received. 
1. Add recipients or groups. Email addresses can also be entered. 
1. Click **[!UICONTROL Send Now]**.
1. (Optional) Click **[!UICONTROL Show scheduling options]** to specify a delivery schedule.

![Send file now](assets/send-file-now.png)

## Send file on schedule

To send a file on a recurring schedule to recipients via email:

1. Click **[!UICONTROL Share] > [!UICONTROL Schedule file export]**.
1. Specify the file type (CSV or PDF).
1. (Optional) Add a description that will be included in the email to explain the file being received. 
1. Add recipients or groups. Email addresses can also be entered. 
1. Specify the range the schedule should be delivered over by modifying Starting on and Ending on inputs. The end date must be within a year from the day the schedule is created or modified.
1. Specify the delivery frequency. Each frequency allows for different customizations. 
1. Click **[!UICONTROL Send on schedule]**.

![](assets/send-on-schedule.png)

## Manage scheduled projects

When you manage scheduled projects, you can edit and delete recurring project schedules:

*  Change the file type (.csv or PDF)
*  Update the project description
*  Add or remove recipients
*  Change the frequency


Scheduled Analysis Workspace projects can be managed under **Analytics > Components > Scheduled Projects**.

For more information, see [Scheduled projects](/help/components/scheduled-projects-manager.md)
-->
