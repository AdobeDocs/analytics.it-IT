---
title: Implementare Adobe Analytics utilizzando Adobe Experience Platform Web SDK
description: Utilizza l’estensione Web SDK in Adobe Experience Platform Data Collection per inviare dati ad Adobe Analytics.
source-git-commit: 6979736e1849d25af2141e0ab76a143605a90620
workflow-type: ht
source-wordcount: '142'
ht-degree: 100%

---


# Implementare Adobe Analytics utilizzando Adobe Experience Platform Web SDK

Puoi utilizzare [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html?lang=it) per inviare dati ad Adobe Analytics. Questo metodo di implementazione funziona traducendo il [Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=it) in un formato utilizzato da Analytics.

## Configurazione

Per impostare Analytics per la ricezione di dati XDM:

1. Installa e [configura](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=it) [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=it).

1. Assicurati che le suite di rapporti applicabili siano mappate ai dati desiderati. I dati XDM arrivano automaticamente alla suite di rapporti da Adobe Experience Edge.
