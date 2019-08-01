---
description: nulle
seo-description: nulle
seo-title: API interessate dalla migrazione
title: API interessate dalla migrazione
uuid: 9 a 5 d 43 be-e 146-476 b -961 e -49 ea 0 a 30 b 500
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2fcd72e6c61f8004268e583b934e9cf474e5e44f

---


# API interessate dalla migrazione{#apis-affected-by-the-migration}

## API interessate dalla migrazione {#topic-8d34296a67d74b1081c3f7e8f650f3ce}

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

* [Informazioni generali sulla gestione utenti](https://helpx.adobe.com/enterprise/help/users.html)
* [Gestione utenti tramite adobe.io](https://www.adobe.io/apis/cloudplatform/usermanagement/docs/gettingstarted.html)
* [Forum della API di gestione utenti](https://forums.adobe.com/community/umapi/overview)
* [Migrazione dell’accesso e della gestione utenti di Analytics a Experience Cloud](https://marketing.adobe.com/resources/help/en_US/experience-cloud/admin-console/analytics-migration/)

