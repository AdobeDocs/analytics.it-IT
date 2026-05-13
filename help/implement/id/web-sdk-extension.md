---
title: Identificazione dei visitatori tramite l’estensione tag Web SDK
description: Identifica correttamente i visitatori quando si implementa l’estensione tag Web SDK.
exl-id: 65de7fc3-a344-4f04-b523-1f5edf681d2f
TQID: https://experienceleague.adobe.com/W42VkHT5yCW0yO-FbiAFHHKM8dF5NgCveZYGFOs7sYk
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 190
ht-degree: 0%

---

# Identificazione dei visitatori tramite l’estensione tag Web SDK

L’estensione tag Web SDK in Adobe Experience Platform Data Collection consente alle organizzazioni di implementare Web SDK utilizzando un’interfaccia di gestione dei tag. Scenari avanzati come la condivisione di ID tra domini diversi e la migrazione del profilo visitatore possono essere facilmente configurati tramite regole e azioni di estensione. L’utilizzo di Web SDK consente di scalare l’implementazione e supporta l’aggiornamento a Customer Journey Analytics.

I dati di identità possono essere estesi per supportare ID personalizzati e più spazi dei nomi utilizzando XDM `identityMap`. Adobe consiglia di utilizzare il servizio Adobe Experience Cloud ID come identificatore primario per Analytics, utilizzando altre opzioni di gestione delle identità per scenari avanzati.

Poiché il Servizio ID visitatore viene inviato in modalità nativa all&#39;estensione tag, è necessario impostare **[!UICONTROL Edge Domain]** solo sul valore desiderato. Se questo campo è impostato correttamente, l’identificazione del visitatore funziona senza alcuna configurazione aggiuntiva.

>[!NOTE]
>
>Non includere l’estensione tag del servizio ID visitatore se utilizzi l’estensione tag Web SDK. L&#39;estensione tag del servizio ID visitatori è necessaria solo se si utilizza l&#39;estensione [Adobe Analytics](analytics-extension.md).
