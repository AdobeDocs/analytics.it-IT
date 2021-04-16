---
description: Passaggi che descrivono come gli amministratori possono abilitare l’accesso ai rapporti di Data Warehouse a un gruppo di utenti.
title: Aggiungere un gruppo utenti di Data Warehouse
feature: Data Warehouse
uuid: d89294db-caa3-4044-b70d-65b512b0dc1c
exl-id: 8737ab60-2ad1-4795-808b-d0200078a333
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 10%

---

# Aggiungere un gruppo utenti di Data Warehouse

Passaggi che descrivono come gli amministratori possono abilitare l’accesso ai rapporti di Data Warehouse a un gruppo di utenti.

1. Fai clic su **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL User Management]**.
1. Fai clic su **[!UICONTROL Edit Groups]**.
1. Fai clic su **[!UICONTROL Add New User Group]**.
1. Nella sezione **[!UICONTROL Define User Group]** digitare un nome nel campo Nome gruppo. fornire le seguenti informazioni di gruppo:

   Ad esempio, `Data Warehouse Access`.
1. Digita una descrizione nel campo **[!UICONTROL Group Description]** .
1. Nella sezione **[!UICONTROL Report Suite Access]** , seleziona le suite di rapporti a cui desideri che i membri del gruppo possano accedere.
1. In [!UICONTROL Tools], abilita **[!UICONTROL All Tools]**.

   In alternativa, fai clic su **[!UICONTROL Customize]**, quindi abilita **[!UICONTROL Custom Data Warehouse Report]**.

1. Alla voce [!UICONTROL Assign User Logins], aggiungi gli accessi utente desiderati.
1. Fai clic su **[!UICONTROL Save Group]**.

   Al successivo accesso degli utenti a questo gruppo, visualizzeranno l&#39;opzione Data Warehouse aggiunta al menu [!UICONTROL Reports & Analytics] .

   >[!NOTE]
   >
   >In caso di autorizzazioni in conflitto (ad esempio un utente assegnato a due gruppi, uno dei quali nega l&#39;accesso a una funzione e l&#39;altro concede lo stesso accesso), il sistema limita le autorizzazioni. Gli utenti che appartengono a gruppi che negano l&#39;accesso al data warehouse possono dover essere rimossi da tali gruppi.

>[!MORELIKETHIS]
>
>* [Gruppi](/help/admin/user-management2/c-user-groups/groups.md)

