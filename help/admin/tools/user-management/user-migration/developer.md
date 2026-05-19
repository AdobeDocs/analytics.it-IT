---
description: Elenca le API interessate dalla migrazione degli utenti
title: API interessate dalla migrazione degli utenti
feature: Admin Tools
exl-id: 82d0a1cd-1e25-4157-9bb9-bba1049fdc48
role: Admin, Developer
TQID: https://experienceleague.adobe.com/vrfYIoa98hEoUVW17cwOLWTPk-3MIRS2wwLPB-ZB5DA
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: fd307ce7-56f5-4ee3-af68-a7833ff6e85eid: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 9e2c89f4188c723b4623a6e7859b74ede15e155b
workflow-type: tm+mt
source-wordcount: 229
ht-degree: 32%

---

# API interessate dalla migrazione degli utenti{#apis-affected-by-the-migration}

Adobe sta eseguendo la migrazione di tutte le società di accesso ad Analytics da [!DNL my.omniture.com] all&#39;autenticazione tramite Adobe CX Enterprise. Una volta che una società inizia questa migrazione, la creazione e la gestione programmatiche degli utenti mediante le autorizzazioni specifiche di Analytics e i metodi di `GetLoginKey` disponibili tramite le versioni v1.3 e v1.4 della API di amministrazione di Analytics non saranno più supportati. Tali azioni verranno ora abilitate in CX Enterprise tramite `adobe.io`.

## Metodi API interessati {#methods}

I seguenti metodi API nelle versioni v1.3 e v1.4 di Admin API non saranno più supportati una volta iniziata la migrazione utente:

* Company.GetLoginKey
* Permissions.AddLogin
* Permissions.Authenticate
* Permissions.DeleteGroup
* Permissions.DeleteLogin
* Permissions.GetGroup
* Permissions.GetGroups
* Permissions.GetLogin
* Permissions.GetLogins
* Permissions.GetReportSuiteGroups
* Permissions.RemoveLoginSegment
* Permissions.SaveGroup
* Permissions.SaveLogin
* Permissions.GetLoginSegment

## Azioni da intraprendere {#actions}

Se la tua azienda utilizza attualmente questi metodi, cerca una notifica di premigrazione a partire dal 31 marzo 2018. La notifica verrà inviata almeno 30 giorni prima dell&#39;inizio della migrazione all&#39;autenticazione aziendale CX e, in tale momento, questi metodi non saranno più supportati.

Se la tua azienda non utilizza nessuno di questi metodi, non è necessaria alcuna azione se non quella di assicurarsi di non iniziare a utilizzare questi metodi.

Per ulteriori informazioni:

* [Informazioni generali sulla gestione utenti](https://helpx.adobe.com/it/enterprise/help/users.html)
* [Forum API per la gestione degli utenti](https://community.adobe.com/t5/enterprise-teams/bd-p/enterprise-and-teams)
* [Migrazione di Analytics User Access and Management a CX Enterprise](/help/admin/tools/user-management/user-migration/c-migration-tool.md)
