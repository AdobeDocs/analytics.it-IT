---
title: Identificazione dei visitatori tramite l’estensione tag Web SDK
description: Identifica correttamente i visitatori quando si implementa l’estensione tag Web SDK.
exl-id: 65de7fc3-a344-4f04-b523-1f5edf681d2f
TQID: 'https://experienceleague.adobe.com/4PVDioBDa-1VXg9Fpy0wA8-RZZYSXzVijj-b2kdEALQ'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
subfeature_v2:
  - id: b3e5f43e-2e2f-43c0-810a-044a5f91e31a
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a947d2d7f45d4155a61cbfe0f8110851cca32e60
workflow-type: tm+mt
source-wordcount: 195
ht-degree: 0%

---

# Identificazione dei visitatori tramite l’estensione tag Web SDK

L’estensione tag Web SDK in Adobe Experience Platform Data Collection consente alle organizzazioni di implementare Web SDK utilizzando un’interfaccia di gestione dei tag. Scenari avanzati come la condivisione di ID tra domini diversi e la migrazione del profilo visitatore possono essere facilmente configurati tramite regole e azioni di estensione. L’utilizzo di Web SDK consente di scalare l’implementazione e supporta l’aggiornamento a Customer Journey Analytics.

I dati di identità possono essere estesi per supportare ID personalizzati e più spazi dei nomi utilizzando XDM [`identityMap`](https://experienceleague.adobe.com/en/docs/experience-platform/collection/identity/identity-map). Adobe consiglia di utilizzare ECID come identificatore primario per Analytics, utilizzando altre opzioni di gestione delle identità per scenari avanzati.

Poiché il Servizio ID visitatore viene inviato in modalità nativa all&#39;estensione tag, è necessario impostare **[!UICONTROL Edge Domain]** solo sul valore desiderato. Se questo campo è impostato correttamente, l’identificazione del visitatore funziona senza alcuna configurazione aggiuntiva.

>[!NOTE]
>
>Non includere l’estensione tag del servizio ID visitatore se utilizzi l’estensione tag Web SDK. L&#39;estensione tag del servizio ID visitatori è necessaria solo se si utilizza l&#39;estensione [Adobe Analytics](analytics-extension.md).
