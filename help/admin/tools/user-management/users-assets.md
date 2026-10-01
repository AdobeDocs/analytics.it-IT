---
description: Gestisci gli utenti di Analytics e le relative risorse in Adobe Admin Console.
title: Gestire utenti e risorse di Analytics
feature: Admin Tools
exl-id: 849a8279-4850-4458-bdd2-85052a17ee21
role: Admin
TQID: 'https://experienceleague.adobe.com/d8CK9Vf-eaEU6P9386J1eO-JpD5u4l3VoqRcMwvXcW0'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
    internal-label: Admin Tools
subfeature_v2:
  - id: d124af73-4061-4b84-9063-ae2b60f2c1f3
    internal-label: User management
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 8badbfc74bdc95a8ab673d4f00fe13e0829e64bb
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 2%
---
# Gestire account utente, risorse e scadenze legacy

Puoi gestire gli account utente legacy, il loro stato di migrazione, i dati di scadenza, il trasferimento di risorse ad altri utenti e altro ancora utilizzando **[!UICONTROL Admin]> [!UICONTROL All Admin] >[!UICONTROL Analytics users & admin]**.

La schermata Utenti mostra un elenco degli utenti Adobe Analytics correnti, con le seguenti colonne:

| Colonna | Descrizione |
|---|---|
| [!UICONTROL User ID] | ID utente utilizzato dall’utente per accedere ad Adobe Analytics. |
| [!UICONTROL Name] | Nome dell&#39;utente. |
| [!UICONTROL Migration status] | Lo stato della migrazione da un account utente legacy a un Enterprise ID o Adobe ID.  Lo stato può essere Non avviato, In coda o Migrato. |
| [!UICONTROL Email] | Indirizzo e-mail dell’utente. |
| [!UICONTROL Legacy login] | Stato dell&#39;accesso legacy, che può essere abilitato o disabilitato. |
| [!UICONTROL Date created] | Timestamp di creazione dell’account utente in Adobe Analytics. |
| [!UICONTROL Last Analytics access] | Timestamp dell’ultimo accesso dell’account utente ad Adobe Analytics, |
| [!UICONTROL Expiration] | Data di scadenza dell’account utente oppure Nessuno se l’account utente non è in scadenza. |

![Utenti](assets/users.png)

- Per cercare un utente specifico, utilizzare il campo ![Cerca](/help/assets/icons/Search.svg) *Cerca per titolo*.
- Per filtrare l&#39;elenco in base allo stato di migrazione, selezionare ![Casuale](/help/assets/icons/ChevronDown.svg) **[!UICONTROL Migration status]**.
- Per filtrare l&#39;elenco in base allo stato di accesso legacy, selezionare ![Chevron](/help/assets/icons/ChevronDown.svg) **[!UICONTROL Legacy login]**.
- Per modificare la visualizzazione delle colonne, selezionare ![Impostazioni colonna](/help/assets/icons/ColumnSetting.svg) e selezionare le colonne dal popup.

Puoi applicare varie azioni quando selezioni uno o più utenti dall’elenco:

| Azione | Descrizione |
|---|---|
| ![Migra](/help/assets/icons/Briefcase.svg) **[!UICONTROL Migrate]** | Puoi eseguire la migrazione di uno o più utenti a Enterprise ID o Adobe ID. |
| ![Calendario bloccato](/help/assets/icons/CalendarLocked.svg) **[!UICONTROL Set expiration]** | Puoi impostare una data di scadenza per l’utilizzo dell’accesso legacy di Adobe Analytics per gli utenti selezionati.  Selezionare la data in cui si desidera utilizzare un popup del calendario per specificare la data. Selezionare **[!UICONTROL Done]** per confermare la scadenza. |
| ![Trasferisci risorse](/help/assets/icons/Switch.svg) **[!UICONTROL Transfer assets]** | Questa azione è disponibile solo quando si seleziona un utente. Se l’utente dispone di risorse che possono essere trasferite, puoi selezionare gli elementi dell’account (come segnalibri, dashboard e altro ancora). Selezionare **[!UICONTROL Transfer]** per completare il trasferimento.<br/>![Trasferisce risorse](assets/transfer-assets.png) |
| ![Elimina account](/help/assets/icons/Delete.svg) **[!UICONTROL Delete accounts]** | Viene visualizzata una finestra di dialogo per confermare l’eliminazione degli account selezionati. Selezionare **[!UICONTROL OK]** per eliminare gli account. Seleziona **[!UICONTROL Cancel]** per annullare. |
| ![Esporta in CSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Export to CSV]** | Questa azione scarica immediatamente un file contenente un elenco di valori separati da virgole degli utenti selezionati con i relativi dettagli (nome, stato della migrazione, e-mail e altro). |

