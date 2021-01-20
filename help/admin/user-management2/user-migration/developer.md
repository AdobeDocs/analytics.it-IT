---
description: Elenca le API interessate dalla migrazione degli utenti
title: API interessate dalla migrazione degli utenti
uuid: 9a5d43be-e146-476b-961e-49ea0a30b500
translation-type: tm+mt
source-git-commit: f2fe11eeafc7b188ff7a886847b33a82ab80e47a
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 92%

---


# API interessate dalla migrazione degli utenti{#apis-affected-by-the-migration}

Adobe sta eseguendo la migrazione di tutte società di accesso ad Analytics da [!DNL my.omniture.com] all’autenticazione mediante Adobe Experience Cloud. Una volta che una società inizia questa migrazione, la creazione e la gestione programmatiche degli utenti mediante le autorizzazioni specifiche di Analytics e i metodi di `GetLoginKey` disponibili tramite le versioni v1.3 e v1.4 della API di amministrazione di Analytics non saranno più supportati. Tali operazioni ora saranno abilitate in Experience Cloud tramite [!DNL adobe.io].

## Metodi API interessati {#section-d19051ac26cc49aeb124f767c4760254}

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

## Azioni da intraprendere {#section-8b0b89a862614f729ebdbe092ce99027}

Se la tua società attualmente utilizza questi metodi, attendi una notifica di pre-migrazione a partire dal 31 marzo 2018. La notifica verrà inviata almeno 30 giorni prima che la tua società inizi la migrazione all’autenticazione di Experience Cloud e, in quel momento, questi metodi cesseranno di essere supportati.

Se la tua società non utilizza nessuno di questi metodi, non è necessaria alcuna azione se non verificare di non iniziare a utilizzare questi metodi.

Per ulteriori informazioni:

* [Informazioni generali sulla gestione utenti](https://helpx.adobe.com/it/enterprise/help/users.html)
* [Gestione utenti tramite adobe.io](https://www.adobe.io/apis/cloudplatform/usermanagement/docs/gettingstarted.html)
* [Forum della API di gestione utenti](https://forums.adobe.com/community/umapi/overview)
* [Migrazione dell’accesso e della gestione utenti di Analytics a Experience Cloud](https://docs.adobe.com/content/help/it-IT/analytics/admin/user-product-management/user-management/migrate-users/c-migration-tool.html)

