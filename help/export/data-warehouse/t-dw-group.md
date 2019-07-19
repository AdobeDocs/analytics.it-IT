---
description: Procedura che descrive in che modo gli amministratori possono abilitare Data Warehouse ad accedere a un gruppo di utenti.
seo-description: Procedura che descrive in che modo gli amministratori possono abilitare Data Warehouse ad accedere a un gruppo di utenti.
seo-title: Aggiungere un gruppo di utenti di Data Warehouse
solution: Analytics
title: Aggiungere un gruppo di utenti di Data Warehouse
topic: Data warehouse
uuid: d 89294 db-caa 3-4044-b 70 d -65 b 512 b 0 dc 1 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Aggiungere un gruppo di utenti di Data Warehouse

Procedura che descrive in che modo gli amministratori possono abilitare Data Warehouse ad accedere a un gruppo di utenti.

1. Click **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL User Management]**.
1. Fai clic su **[!UICONTROL Edit Groups]**.
1. Fai clic su **[!UICONTROL Add New User Group]**.
1. In the **[!UICONTROL Define User Group]** section, type a name in the Group Name field. fornite le seguenti informazioni sul gruppo:

   Ad esempio, `Data Warehouse Access`.
1. Type a description in the **[!UICONTROL Group Description]** field.
1. In the **[!UICONTROL Report Suite Access]** section, select the report suites that you want group members to be able to access.
1. Under [!UICONTROL Tools], enable **[!UICONTROL All Tools]**.

   Alternatively, click **[!UICONTROL Customize]**, then enable **[!UICONTROL Custom Data Warehouse Report]**.

1. Under [!UICONTROL Assign User Logins], add the desired user logins.
1. Fai clic su **[!UICONTROL Save Group]**.

   The next time the users added to this group log in, they will see the Data Warehouse option added to the [!UICONTROL Reports & Analytics] menu.

   >[!NOTE]
   >
   >In caso di autorizzazioni in conflitto (ad esempio un utente assegnato a due gruppi, uno dei quali nega l'accesso a una funzionalità e l'altro a uno stesso accesso), il sistema limita l'autorizzazione. Gli utenti che appartengono a gruppi che rifiutano l'accesso data warehouse possono essere rimossi da tali gruppi.

>[!MORE_ LIKE_ THIS]
>
>* [Gruppi](/help/admin/user-management2/c-user-groups/groups.md)

