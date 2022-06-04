---
title: Implementare Adobe Analytics utilizzando l’SDK per web di Adobe Experience Platform
description: Utilizza l’estensione SDK per web in Raccolta dati di Adobe Experience Platform per inviare dati ad Adobe Analytics.
source-git-commit: 6979736e1849d25af2141e0ab76a143605a90620
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 4%

---


# Implementare Adobe Analytics utilizzando l’SDK per web di Adobe Experience Platform

È possibile utilizzare [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html) per inviare dati ad Adobe Analytics. Questo metodo di implementazione funziona traducendo il [Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=it) in un formato utilizzato da Analytics.

## Configurazione

Per impostare Analytics per la ricezione di dati XDM:

1. Installazione e [configurare](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html) la [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html).

1. Assicurati che le suite di rapporti applicabili siano mappate ai dati desiderati. I dati XDM arrivano automaticamente alla suite di rapporti da Adobe Experience Edge.
