---
description: Passaggi che descrivono come gli amministratori possono abilitare l'accesso ai rapporti di Data Warehouse per un gruppo di utenti.
title: Aggiungere un gruppo utenti di Data Warehouse
topic: Data warehouse
uuid: d89294db-caa3-4044-b70d-65b512b0dc1c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Aggiungere un gruppo utenti di Data Warehouse

Passaggi che descrivono come gli amministratori possono abilitare l&#39;accesso ai rapporti di Data Warehouse per un gruppo di utenti.

1. Fai clic su **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL User Management]**.
1. Fai clic su **[!UICONTROL Edit Groups]**.
1. Fai clic su **[!UICONTROL Add New User Group]**.
1. Nella **[!UICONTROL Define User Group]** sezione digitare un nome nel campo Nome gruppo. fornite le seguenti informazioni di gruppo:

   Ad esempio, `Data Warehouse Access`.
1. Digitare una descrizione nel **[!UICONTROL Group Description]** campo.
1. Nella **[!UICONTROL Report Suite Access]** sezione, selezionate le suite di rapporti alle quali desiderate consentire l’accesso ai membri del gruppo.
1. In [!UICONTROL Tools], abilita **[!UICONTROL All Tools]**.

   In alternativa, fare clic **[!UICONTROL Customize]**, quindi attivare **[!UICONTROL Custom Data Warehouse Report]**.

1. In [!UICONTROL Assign User Logins], aggiungete gli accessi utente desiderati.
1. Fai clic su **[!UICONTROL Save Group]**.

   Al successivo accesso degli utenti a questo gruppo, verrà visualizzata l&#39;opzione Data Warehouse aggiunta al [!UICONTROL Reports & Analytics] menu.

   >[!NOTE]
   >
   >In caso di conflitto di autorizzazioni (ad esempio, un utente assegnato a due gruppi, uno dei quali nega l&#39;accesso a una funzionalità e gli altri concede lo stesso accesso), il sistema limita le autorizzazioni. Gli utenti appartenenti a gruppi che negano l&#39;accesso al data warehouse possono dover essere rimossi da tali gruppi.

>[!MORELIKETHIS]
>
>* [Gruppi](/help/admin/user-management2/c-user-groups/groups.md)

