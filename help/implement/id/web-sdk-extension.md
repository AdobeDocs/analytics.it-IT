---
title: Identificazione dei visitatori tramite l’estensione tag Web SDK
description: Identifica correttamente i visitatori quando si implementa l’estensione tag Web SDK.
source-git-commit: 98e9dc4932bd23d3e0b632705945f56c243750c5
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 0%

---

# Identificazione dei visitatori tramite l’estensione tag Web SDK

L’estensione tag Web SDK in Adobe Experience Platform Data Collection consente alle organizzazioni di implementare Web SDK utilizzando un’interfaccia di gestione dei tag. Scenari avanzati come la condivisione di ID tra domini diversi e la migrazione del profilo visitatore possono essere facilmente configurati tramite regole e azioni di estensione. L’utilizzo di Web SDK consente di scalare l’implementazione e supporta l’aggiornamento a Customer Journey Analytics.

I dati di identità possono essere estesi per supportare ID personalizzati e più spazi dei nomi utilizzando XDM `identityMap`. Adobe consiglia di utilizzare il servizio Adobe Experience Cloud ID come identificatore primario per Analytics, utilizzando altre opzioni di gestione delle identità per scenari avanzati.

Poiché il Servizio ID visitatore viene inviato in modalità nativa all&#39;estensione tag, è necessario impostare **[!UICONTROL Edge Domain]** solo sul valore desiderato. Se questo campo è impostato correttamente, l’identificazione del visitatore funziona senza alcuna configurazione aggiuntiva.

>[!NOTE]
>
>Non includere l’estensione tag del servizio ID visitatore se utilizzi l’estensione tag Web SDK. L&#39;estensione tag del servizio ID visitatori è necessaria solo se si utilizza l&#39;estensione [Adobe Analytics](analytics-extension.md).
