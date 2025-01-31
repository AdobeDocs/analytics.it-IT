---
description: Elenca le API interessate dalla migrazione degli utenti
title: 'API interessate dalla migrazione degli utenti '
feature: Admin Tools
exl-id: 82d0a1cd-1e25-4157-9bb9-bba1049fdc48
role: Admin, Developer
source-git-commit: b90356050a6ff39e1688a10f6aa0af284284e2a6
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 100%

---

# API interessate dalla migrazione degli utenti {#apis-affected-by-the-migration}

Adobe sta eseguendo la migrazione di tutte società di accesso ad Analytics da [!DNL my.omniture.com] all’autenticazione mediante Adobe Experience Cloud. Una volta che una società inizia questa migrazione, la creazione e la gestione programmatiche degli utenti mediante le autorizzazioni specifiche di Analytics e i metodi di `GetLoginKey` disponibili tramite le versioni v1.3 e v1.4 della API di amministrazione di Analytics non saranno più supportati. Tali operazioni ora saranno abilitate in Experience Cloud tramite [!DNL adobe.io].

## Metodi API interessati {#methods}

I seguenti metodi API nelle versioni v1.3 e v1.4 della API di amministrazione non saranno più supportati dopo l’inizio della migrazione degli utenti:

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

Se la tua società attualmente utilizza questi metodi, attendi una notifica di pre-migrazione a partire dal 31 marzo 2018. La notifica verrà inviata almeno 30 giorni prima che la tua società inizi la migrazione all’autenticazione di Experience Cloud e, in quel momento, questi metodi cesseranno di essere supportati.

Se la tua società non utilizza nessuno di questi metodi, non è necessaria alcuna azione se non verificare di non iniziare a utilizzare questi metodi.

Per ulteriori informazioni:

* [Informazioni generali sulla gestione utenti](https://helpx.adobe.com/it/enterprise/help/users.html)
* [Forum della API di gestione utenti](https://community.adobe.com/t5/enterprise-teams/bd-p/enterprise-and-teams)
* [Migrazione dell’accesso e della gestione utenti di Analytics a Experience Cloud](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/user-management/migrate-users/c-migration-tool.html?lang=it)
