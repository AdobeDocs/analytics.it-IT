---
description: Adobe Report Builder ora offre impostazioni di autorizzazione simili a quelle degli strumenti di amministrazione di Analytics.
seo-description: Adobe Report Builder ora offre impostazioni di autorizzazione simili a quelle degli strumenti di amministrazione di Analytics.
seo-title: Autorizzazioni di accesso utente per dimensioni e metriche
solution: Analytics
title: Autorizzazioni di accesso utente per dimensioni e metriche
topic: Generatore di report
uuid: b 561407 d-c 4 fa -4 f 1 e -8 b 16-5 ca 46 fcbf 36 f
translation-type: tm+mt
source-git-commit: d75c58caf1220031fa36483a0ad50ea6f7be7c39

---


# Autorizzazioni di accesso utente per dimensioni e metriche

Adobe Report Builder ora offre impostazioni di autorizzazione simili a quelle degli strumenti di amministrazione di Analytics.

In qualità di utente non amministratore, potreste avere già creato cartelle di lavoro con richieste che puntano a dimensioni e metriche a cui non potete accedere. Queste autorizzazioni vengono ora applicate.

Ad esempio, se aggiorna una richiesta che include dimensioni o metriche a cui non hai accesso, riceverai un errore Autorizzazione limitata:

![](assets/arb_restrc_perm.png)

Follow these instructions for **each** Report Builder workbook that you maintain:

1. Aprite la cartella di lavoro.
1. Aggiorna tutte le richieste.
1. If you get prompted with a User Access Permission error, click **[!UICONTROL Open CSV File]** to get access to the list of restricted permissions errors.
1. Create un file «AllRestrictedPermissionErrors.xlsx» e copiate/incollate l'elenco degli errori di autorizzazione limitati in questo file.
1. Chiudete la cartella di lavoro Generatore di report.

Dopo aver elaborato tutti i documenti di lavoro, in «AllRestrictedPermissionErrors.xlsx» dovreste avere un elenco completo degli errori di autorizzazione limitati. Invia questo elenco al tuo amministratore di accesso agli utenti di Adobe Analytics, chiedendogli di concedervi l'accesso alle metriche e alle dimensioni.
