---
description: Adobe Report Builder ora dispone di impostazioni di autorizzazione simili a quelle degli Strumenti di amministrazione di Analytics.
title: Autorizzazioni di accesso utente per dimensioni e metriche
uuid: b561407d-c4fa-4f1e-8b16-5ca46fcbf36f
feature: Report Builder
role: User, Admin
exl-id: 53cfdcf4-31c3-40ab-aca4-8f0f9be6fe13
source-git-commit: bb908f8dd21f7f11d93eb2e3cc843f107b99950d
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 6%

---

# Autorizzazioni di accesso utente per dimensioni e metriche

Adobe Report Builder offre impostazioni di autorizzazione simili a quelle degli strumenti di amministrazione di Analytics.

In qualità di utente non amministratore, potresti aver creato in precedenza cartelle di lavoro con richieste che puntano a dimensioni e metriche a cui non hai accesso. Queste autorizzazioni vengono ora applicate.

Ad esempio, se aggiorni una richiesta che include dimensioni o metriche a cui non hai accesso, riceverai un Errore di autorizzazione limitata. Il messaggio di errore indica che una richiesta non è disponibile per l’account utente a causa di autorizzazioni amministrative.

![Schermata che mostra il messaggio di errore Autorizzazione limitata.](assets/arb_restrc_perm.png)

Segui queste istruzioni per **ogni** cartella di lavoro di Report Builder gestita:

1. Aprire la cartella di lavoro.
1. Aggiorna tutte le richieste.
1. Se viene richiesto un errore di autorizzazione di accesso utente, fare clic su **[!UICONTROL Open CSV File]** per accedere all&#39;elenco degli errori relativi alle autorizzazioni limitate.
1. Crea un file &quot;AllRestrictedPermissionErrors.xlsx&quot; e copia/incolla l’elenco degli errori di autorizzazione con restrizioni dal file CSV in questo file.
1. Chiudere la cartella di lavoro del Report Builder.

Dopo aver elaborato tutte le cartelle di lavoro, è necessario disporre di un elenco completo degli errori di autorizzazione con restrizioni in &quot;AllRestrictedPermissionErrors.xlsx&quot;. Invia questo elenco all’amministratore degli accessi utente di Adobe Analytics, chiedendogli di concederti l’accesso alle metriche e alle dimensioni.
