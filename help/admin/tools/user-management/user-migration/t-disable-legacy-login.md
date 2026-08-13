---
description: Scopri come disabilitare gli accessi legacy per gli utenti di Analytics.
title: Disattivazione degli accessi legacy
feature: Admin Tools
exl-id: 3e619700-722d-429b-94dc-7aa162e114c0
role: Admin
TQID: 'https://experienceleague.adobe.com/xwLXKuaeoKB5-TSVC7FLQXdUsBEeOg-zuITMa8Z3OIo'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: d124af73-4061-4b84-9063-ae2b60f2c1f3
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 174
ht-degree: 49%

---

# Disattivazione degli accessi legacy

Scopri come disabilitare gli accessi legacy per gli utenti di Analytics.

Dopo che gli utenti hanno eseguito la migrazione dal sistema legacy di gestione utenti di Analytics al Adobe Admin Console, puoi disabilitare i loro accessi legacy. La disattivazione degli accessi legacy reindirizza gli utenti all&#39;accesso a CX Enterprise se tentano di utilizzare l&#39;accesso legacy.

1. Apri lo strumento di migrazione in **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL User ID Migration]**.
1. Nella sezione [!DNL User Information], individua il dominio contenente gli utenti con cui vuoi collaborare, quindi fai clic su **[!UICONTROL Select Users]**.
1. Seleziona gli utenti per cui vuoi disattivare l’accesso legacy.

   ![](/help/admin/tools/user-management/user-migration/assets/user-info.png)

   Gli utenti idonei avranno lo stato *`Migrated`* nella colonna Stato di migrazione. Non puoi disattivare l’accesso legacy di un utente finché non ne esegui la migrazione.
1. Fai clic su **[!UICONTROL Disable Legacy Login]**, quindi su **[!UICONTROL Done]**.

   Disattiva accesso legacy indica quali dei tuoi utenti possono continuare a utilizzare i propri nome utente e password legacy per [!DNL my.omniture.com].

   Non è possibile disattivare gli accessi legacy per un utente non ancora migrato. Una volta disabilitato, l’utente deve utilizzare il proprio Experience Cloud ID per accedere ad Analytics.
