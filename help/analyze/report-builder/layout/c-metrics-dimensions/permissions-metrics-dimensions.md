---
description: Adobe Report Builder ora offre impostazioni di autorizzazione simili a quelle degli Strumenti di amministrazione di Analytics.
title: Autorizzazioni di accesso utente per dimensioni e metriche
topic: Report builder
uuid: b561407d-c4fa-4f1e-8b16-5ca46fcbf36f
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Autorizzazioni di accesso utente per dimensioni e metriche

Adobe Report Builder ora offre impostazioni di autorizzazione simili a quelle degli Strumenti di amministrazione di Analytics.

In qualità di utente non amministratore, potreste aver creato in precedenza cartelle di lavoro con richieste che puntano a dimensioni e metriche a cui non avete accesso. Queste autorizzazioni vengono ora applicate.

Ad esempio, se aggiorni una richiesta che include dimensioni o metriche a cui non hai accesso, riceverai un errore di autorizzazione limitata:

![](assets/arb_restrc_perm.png)

Per **ogni** cartella di lavoro del Generatore di report gestita, effettuate le seguenti operazioni:

1. Aprire la cartella di lavoro.
1. Aggiorna tutte le richieste.
1. Se viene visualizzato un messaggio di errore Autorizzazione accesso utente, fate clic **[!UICONTROL Open CSV File]** per accedere all'elenco degli errori relativi alle autorizzazioni limitate.
1. Create un file "AllRestrictedPermissionErrors.xlsx" e copiate/incollate l’elenco degli errori di autorizzazione limitata dal file CSV in questo file.
1. Chiudere la cartella di lavoro del Generatore di report.

Dopo aver elaborato tutte le cartelle di lavoro, è necessario disporre di un elenco completo degli errori di autorizzazione limitata in "AllRestrictedPermissionErrors.xlsx". Inviate questo elenco al vostro amministratore di accesso utente di Adobe Analytics, chiedendogli di concedere l'accesso alle metriche e alle dimensioni.
