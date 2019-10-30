---
description: Scopri come disabilitare gli accessi legacy per gli utenti di Analytics.
seo-description: Scopri come disabilitare gli accessi legacy per gli utenti di Analytics.
seo-title: Disattivazione degli accessi legacy
title: Disattivazione degli accessi legacy
uuid: 085874b2-10bf-4a56-a337-f3104428d71e
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Disattivazione degli accessi legacy{#disable-legacy-logins}

Scopri come disabilitare gli accessi legacy per gli utenti di Analytics.

Dopo avere eseguito la migrazione dei tuoi utenti dal sistema legacy di gestione degli utenti di Analytics all’Admin Console di Adobe, puoi disattivare i loro accessi legacy. La disattivazione degli accessi legacy reindirizza gli utenti all’accesso di Experience Cloud nel caso tentino di utilizzare l’accesso legacy.

1. Apri lo strumento di migrazione in **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL User ID Migration]**.
1. In the [!DNL User Information] section, locate the domain containing the users you want to work with, then click **[!UICONTROL Select Users]**.
1. Seleziona gli utenti per cui vuoi disattivare l’accesso legacy.

   ![](assets/user-info.png)

   Gli utenti idonei avranno lo stato *`Migrated`* nella colonna Stato di migrazione. Non puoi disattivare l’accesso legacy di un utente finché non ne esegui la migrazione.
1. Fate clic **[!UICONTROL Disable Legacy Login]**, quindi fate clic **[!UICONTROL Done]**.

   Disattiva accesso legacy indica quali dei tuoi utenti possono continuare a utilizzare i propri nome utente e password legacy [!DNL my.omniture.com].

   Non puoi disattivare gli accessi legacy per un utente che deve ancora essere migrato. Una volta disattivato, l’utente deve utilizzare il proprio Experience Cloud ID per accedere ad Analytics.

