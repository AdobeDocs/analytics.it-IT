---
title: Identificazione dei visitatori tramite l’estensione tag Web SDK
description: Identifica correttamente i visitatori quando si implementa l’estensione tag Web SDK.
source-git-commit: 779ba5b0a1d71467aaaf3872fd707cc323ae8af2
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 0%

---

# Identificazione dei visitatori tramite l’estensione tag Web SDK

L’estensione tag Web SDK in Adobe Experience Platform Data Collection consente alle organizzazioni di implementare Web SDK utilizzando un’interfaccia di gestione dei tag. Scenari avanzati come la condivisione di ID tra domini diversi e la migrazione del profilo visitatore possono essere facilmente configurati tramite regole e azioni di estensione. L’utilizzo di Web SDK consente di scalare l’implementazione e supporta l’aggiornamento a Customer Journey Analytics.

Poiché il Servizio ID visitatore viene inviato in modalità nativa all&#39;estensione tag, è necessario impostare **[!UICONTROL Edge Domain]** solo sul valore desiderato. Se questo campo è impostato correttamente, l’identificazione del visitatore funziona senza alcuna configurazione aggiuntiva.

>[!NOTE]
>
>Non includere l’estensione tag del servizio ID visitatore se utilizzi l’estensione tag Web SDK. L&#39;estensione tag del servizio ID visitatori è necessaria solo se si utilizza l&#39;estensione [Adobe Analytics](analytics-extension.md).
