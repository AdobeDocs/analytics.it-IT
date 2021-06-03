---
title: Utilizzo dei dati XDM con Analytics
description: Panoramica dell’utilizzo di dati XDM da Experience Platform in Adobe Analytics
exl-id: 6f1282fb-8d4a-4d88-9be0-1c939c22cb92
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 2%

---

# Utilizzo dei dati di Adobe Experience Platform Edge con Analytics

Puoi utilizzare l&#39; [Adobe Experience Platform (AEP) Web SDK](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html) per inviare dati ad Adobe Analytics. Questo funziona traducendo il [Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=it) in un formato utilizzato da Analytics.

Analytics raccoglie i dati XDM tramite due metodi:

* Mappatura automatica dagli schemi XDM
* Mappatura manuale dei dati contestuali

## Mappatura automatica

La mappatura automatica si basa su uno [schema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html) predefinito in XDM che popola automaticamente gli oggetti JSON inclusi nella tipica raccolta dati di Analytics. Le variabili di Analytics mappate automaticamente da XDM alle suite di rapporti configurate non richiedono alcun supporto per gli sviluppatori da incorporare.

## Mappatura manuale

[La mappatura manuale dei dati XDM su ](xdm-manual.md) Analytics si basa sulle variabili di dati contestuali di  [Analytics ](../vars/page-vars/contextdata.md) . Queste variabili vengono inserite in oggetti JSON corrispondenti agli schemi applicabili. In genere, il team di sviluppo aggiunge dati contestuali al momento dell&#39;implementazione, quindi gli amministratori impostano [regole di elaborazione](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md) per applicare tali dati a suite di rapporti specificate.

## Configurazione

Per impostare Analytics per la ricezione di dati XDM:

1. Installa e [configura](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html) l&#39; [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html).

2. Assicurati che le suite di rapporti applicabili siano mappate ai dati desiderati. I dati XDM arrivano automaticamente alla suite di rapporti da Adobe Experience Platform.
