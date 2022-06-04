---
title: Implementare Adobe Analytics utilizzando l’SDK di Adobe Experience Platform Mobile
description: Utilizza l’estensione Mobile SDK in Adobe Experience Platform Data Collection per inviare dati ad Adobe Analytics.
source-git-commit: 6979736e1849d25af2141e0ab76a143605a90620
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 2%

---


# Implementare Adobe Analytics utilizzando l’SDK di Adobe Experience Platform Mobile

L&#39;SDK di Adobe Experience Platform Mobile consente di sviluppare soluzioni e servizi di Experience Cloud nelle app mobili. È disponibile per Android, iOS e vari framework di sviluppo multipiattaforma. La configurazione viene gestita tramite l’interfaccia utente di raccolta dati di Adobe Experience Platform.

Per inviare dati ad Adobe Experience Edge utilizzando l’SDK di Mobile:

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection).
2. Seleziona la proprietà desiderata dall’elenco, oppure [impostare una proprietà mobile](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property).
3. Vai alla scheda Estensioni e installa il [Identità per rete Edge](https://aep-sdks.gitbook.io/docs/foundation-extensions/identity-for-edge-network) estensione.
4. Installa il [Adobe Experience Platform Edge Network](https://aep-sdks.gitbook.io/docs/foundation-extensions/experience-platform-extension).
5. [Configurare un datastream](https://aep-sdks.gitbook.io/docs/getting-started/configure-datastreams), aggiunta di Adobe Analytics come servizio che punta alla suite di rapporti desiderata.
6. [Installare l’SDK](https://aep-sdks.gitbook.io/docs/getting-started/get-the-sdk) nella tua app mobile.

>[!IMPORTANT]
>
>Un’estensione Adobe Analytics è disponibile anche nell’interfaccia utente di raccolta dati. Se installi questa estensione, non sfrutti XDM o la rete Edge.
