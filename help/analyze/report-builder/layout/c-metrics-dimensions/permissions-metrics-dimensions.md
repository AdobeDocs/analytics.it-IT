---
description: Adobe Report Builder ora dispone di impostazioni di autorizzazione simili a quelle disponibili in Strumenti di amministrazione di Analytics.
title: Autorizzazioni di accesso utente per dimensioni e metriche
uuid: b561407d-c4fa-4f1e-8b16-5ca46fcbf36f
feature: Report Builder
role: User, Admin
exl-id: 53cfdcf4-31c3-40ab-aca4-8f0f9be6fe13
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 7%

---

# Autorizzazioni di accesso utente per dimensioni e metriche

Adobe Report Builder ora dispone di impostazioni di autorizzazione simili a quelle disponibili in Strumenti di amministrazione di Analytics.

In qualità di utente non amministratore, è possibile che in precedenza siano state create cartelle di lavoro con richieste che puntano a dimensioni e metriche a cui non si ha accesso. Queste autorizzazioni vengono ora applicate.

Ad esempio, se aggiorni una richiesta che include dimensioni o metriche a cui non hai accesso, ottieni un errore di autorizzazione limitata:

![](assets/arb_restrc_perm.png)

Segui queste istruzioni per **ogni cartella di lavoro di Report Builder** gestita:

1. Apri la cartella di lavoro.
1. Aggiorna tutte le richieste.
1. Se viene richiesto un errore di autorizzazione accesso utente, fare clic su **[!UICONTROL Open CSV File]** per accedere all&#39;elenco degli errori relativi alle autorizzazioni limitate.
1. Crea un file &quot;AllRestrictedPermissionErrors.xlsx&quot; e copia/incolla in questo file l&#39;elenco degli errori di autorizzazione limitata dal file CSV.
1. Chiudere la cartella di lavoro del Report Builder.

Dopo aver elaborato tutte le cartelle di lavoro, è necessario disporre di un elenco completo degli errori di autorizzazione limitati in &quot;AllRestrictedPermissionErrors.xlsx&quot;. Invia questo elenco al tuo amministratore degli accessi utente di Adobe Analytics chiedendogli di concedere l’accesso alle metriche e alle dimensioni.
