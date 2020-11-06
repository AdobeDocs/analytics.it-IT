---
title: Utilizzo di dati XDM con Analytics
description: 'Panoramica dell''utilizzo di dati XDM da  Experience Platform in  Adobe Analytics '
translation-type: tm+mt
source-git-commit: 01e9a456dece2a7c3f96bb2c6c9625f654a05059
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 4%

---


# Utilizzo di dati Adobe Experience Platform Edge con Analytics

Puoi usare l’SDK [Web](https://docs.adobe.com/content/help/it-IT/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html) Adobe Experience Platform (AEP) per inviare dati a  Adobe Analytics. Questo funziona traducendo il modello dati [esperienza (XDM)](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html) in un formato utilizzato da Analytics.

Analytics raccoglie i dati XDM tramite due metodi:

* Mappatura automatica dagli schemi XDM
* Mappatura manuale ai dati contestuali

## Mappatura automatica

La mappatura automatica si basa su uno [schema](https://docs.adobe.com/content/help/en/experience-platform/xdm/schema/composition.html) predefinito in XDM che popola automaticamente gli oggetti JSON inclusi nella raccolta dati Analytics tipica. Le variabili di Analytics mappate automaticamente da XDM alle suite di rapporti configurate non richiedono il supporto per gli sviluppatori.

## Mappatura manuale

[La mappatura manuale dei dati XDM su Analytics](xdm-manual.md) si basa sulle variabili dei dati [contestuali di](../vars/page-vars/contextdata.md) Analytics. Queste variabili vengono inserite in oggetti JSON che corrispondono agli schemi applicabili. In genere, il team di sviluppo aggiunge i dati contestuali al momento dell’implementazione, quindi gli amministratori impostano le regole [di](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md) elaborazione per applicare tali dati a specifiche suite di rapporti.

## Configurazione

Per impostare Analytics per la ricezione di dati XDM:

1. Installate e [configurate](https://docs.adobe.com/content/help/en/experience-platform/edge/fundamentals/configuring-the-sdk.html) l&#39;SDK [Web di](https://docs.adobe.com/content/help/en/experience-platform/edge/fundamentals/installing-the-sdk.html)Adobe Experience Platform.

2. Assicurati che le suite di rapporti applicabili siano mappate sui dati desiderati. I dati XDM scorrono automaticamente nella suite di rapporti dalla piattaforma Adobe Experience.
