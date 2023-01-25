---
description: Scopri come disabilitare gli accessi legacy per gli utenti di Analytics.
title: Disattivazione degli accessi legacy
feature: Admin Tools
exl-id: 3e619700-722d-429b-94dc-7aa162e114c0
source-git-commit: a17297af84e1f5e7fe61f886eb3906c462229087
workflow-type: ht
source-wordcount: '174'
ht-degree: 100%

---

# Disattivazione degli accessi legacy {#disable-legacy-logins}

Scopri come disabilitare gli accessi legacy per gli utenti di Analytics.

Dopo avere eseguito la migrazione dei tuoi utenti dal sistema legacy di gestione degli utenti di Analytics all’Admin Console di Adobe, puoi disattivare i loro accessi legacy. La disattivazione degli accessi legacy reindirizza gli utenti all’accesso di Experience Cloud nel caso tentino di utilizzare l’accesso legacy.

1. Apri lo strumento di migrazione in **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL User ID Migration]**.
1. Nella sezione [!DNL User Information], individua il dominio contenente gli utenti con cui vuoi collaborare, quindi fai clic su **[!UICONTROL Select Users]**.
1. Seleziona gli utenti per cui vuoi disattivare l’accesso legacy.

   ![](/help/admin/admin-console/user-management2/user-migration/assets/user-info.png)

   Gli utenti idonei avranno lo stato *`Migrated`* nella colonna Stato di migrazione. Non puoi disattivare l’accesso legacy di un utente finché non ne esegui la migrazione.
1. Fai clic su **[!UICONTROL Disable Legacy Login]**, quindi su **[!UICONTROL Done]**.

   Disattiva accesso legacy indica quali dei tuoi utenti possono continuare a utilizzare i propri nome utente e password legacy per [!DNL my.omniture.com].

   Non puoi disattivare gli accessi legacy per un utente che deve ancora essere migrato. Una volta disattivato, l’utente deve utilizzare il proprio Experience Cloud ID per accedere ad Analytics.
