---
title: Implementare Adobe Analytics utilizzando l’SDK di Adobe Experience Platform Mobile
description: Utilizzare l’estensione Mobile SDK in Adobe Experience Platform Data Collection per inviare dati ad Adobe Analytics.
exl-id: 516e9a1e-caa7-4f8a-ab8c-6404e9242ccb
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 89%

---

# Implementare Adobe Analytics utilizzando l’SDK di Adobe Experience Platform Mobile

L’Adobe Experience Platform Mobile SDK aiuta ad alimentare soluzioni e servizi di Adobe Experience Cloud nelle app mobile. È disponibile per Android, iOS e vari framework di sviluppo multipiattaforma. La configurazione viene gestita tramite la raccolta dati di Adobe Experience Platform.

Per inviare dati ad Adobe Experience Edge utilizzando l’SDK di Mobile:

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection).
2. Seleziona la proprietà desiderata dall’elenco, oppure [imposta una proprietà mobile](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property).
3. Apri la scheda Estensioni e installa l’estensione [Identità per Edge Network](https://aep-sdks.gitbook.io/docs/foundation-extensions/identity-for-edge-network).
4. Installa [Adobe Experience Platform Edge Network](https://aep-sdks.gitbook.io/docs/foundation-extensions/experience-platform-extension).
5. [Configura un datastream](https://aep-sdks.gitbook.io/docs/getting-started/configure-datastreams), aggiungendo Adobe Analytics come servizio che punta alla suite di rapporti desiderata.
6. [Installa l’SDK](https://aep-sdks.gitbook.io/docs/getting-started/get-the-sdk) nella tua app mobile.

>[!IMPORTANT]
>
>Un’estensione Adobe Analytics è disponibile anche in Adobe Experience Platform Data Collection. Se installi questa estensione, non sfrutti XDM o la rete Edge.
