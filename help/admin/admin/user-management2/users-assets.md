---
description: Gestisci gli utenti di Analytics e le relative risorse in Adobe Admin Console.
title: Gestire utenti e risorse di Analytics
feature: Admin Tools
exl-id: 849a8279-4850-4458-bdd2-85052a17ee21
role: Admin
source-git-commit: 869b44b826de5cb35d13000133092397cb16ccaa
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 1%

---

# Gestire account utente, risorse e scadenze legacy

Puoi gestire gli account utente legacy, il loro stato di migrazione, i dati di scadenza, il trasferimento di risorse ad altri utenti e altro ancora tramite **[!UICONTROL Admin]> [!UICONTROL All Admin] >[!UICONTROL Analytics users & admin]**.

La schermata Utenti mostra un elenco degli utenti Adobe Analytics correnti, con le seguenti colonne:

| Colonna | Descrizione |
|---|---|
| [!UICONTROL User ID] | ID utente utilizzato dall’utente per accedere ad Adobe Analytics. |
| [!UICONTROL Name] | Nome dell&#39;utente. |
| [!UICONTROL Migration status] | Lo stato della migrazione da un account utente legacy a un’Enterprise ID o a Adobe ID.  Lo stato può essere Non avviato, In coda o Migrato. |
| [!UICONTROL Email] | Indirizzo e-mail dell’utente. |
| [!UICONTROL Legacy login] | Stato dell&#39;accesso legacy, che può essere abilitato o disabilitato. |
| [!UICONTROL Date created] | Timestamp di creazione dell’account utente in Adobe Analytics. |
| [!UICONTROL Last Analytics access] | Timestamp dell’ultimo accesso dell’account utente ad Adobe Analytics, |
| [!UICONTROL Expiration] | Data di scadenza dell’account utente oppure Nessuno se l’account utente non è in scadenza. |

![Utenti](assets/users.png)

- Per cercare un utente specifico, utilizza ![Ricerca](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) *Cerca per titolo* campo.
- Per filtrare l’elenco in base allo stato di migrazione, seleziona ![Freccia](https://spectrum.adobe.com/static/icons/ui_18/ChevronSize100.svg) **[!UICONTROL Migration status]**.
- Per filtrare l’elenco in base allo stato di accesso legacy, seleziona ![Freccia](https://spectrum.adobe.com/static/icons/ui_18/ChevronSize100.svg) **[!UICONTROL Legacy login]**.
- Per modificare la visualizzazione delle colonne, selezionare ![Impostazioni colonna](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg) e seleziona le colonne dalla finestra a comparsa.

Puoi applicare varie azioni quando selezioni uno o più utenti dall’elenco:

| Azione | Descrizione |
|---|---|
| ![Migra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Briefcase_18_N.svg) **[!UICONTROL Migrate]** | Puoi eseguire la migrazione di uno o più utenti a Enterprise ID o Adobe ID. |
| ![Calendario bloccato](https://spectrum.adobe.com/static/icons/workflow_18/Smock_CalendarLocked_18_N.svg) **[!UICONTROL Set expiration]** | Puoi impostare una data di scadenza per l’utilizzo dell’accesso legacy di Adobe Analytics per gli utenti selezionati.  Selezionare la data in cui si desidera utilizzare un popup del calendario per specificare la data. Seleziona **[!UICONTROL Done]** per confermare la scadenza. |
| ![Trasferire le risorse](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Switch_18_N.svg) **[!UICONTROL Transfer assets]** | Questa azione è disponibile solo quando si seleziona un utente. Se l’utente dispone di risorse che possono essere trasferite, puoi selezionare gli elementi dell’account (come segnalibri, dashboard e altro ancora). Seleziona **[!UICONTROL Transfer]** per completare il trasferimento.<br/>![Trasferisce le risorse](assets/transfer-assets.png) |
| ![Elimina account](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Delete accounts]** | Viene visualizzata una finestra di dialogo per confermare l’eliminazione degli account selezionati. Seleziona **[!UICONTROL OK]** per eliminare gli account. Seleziona **[!UICONTROL Cancel]** per annullare. |
| ![Esporta in CSV](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FileCSV_18_N.svg) **[!UICONTROL Export to CSV]** | Questa azione scarica immediatamente un file contenente un elenco di valori separati da virgole degli utenti selezionati con i relativi dettagli (nome, stato della migrazione, e-mail e altro). |

