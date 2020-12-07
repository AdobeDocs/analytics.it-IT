---
title: dc
description: Variabile ritirata che consente di determinare quale centro dati utilizzare.
translation-type: tm+mt
source-git-commit: dfe2b09b2ee287219d18099c51b6fbd7c86bab21
workflow-type: tm+mt
source-wordcount: '71'
ht-degree: 2%

---


# dc

>[!IMPORTANT]
>
>Questa variabile è ritirata. Usa [`trackingServer`](trackingserver.md) invece.

Nelle versioni precedenti di  Adobe Analytics,  Adobe richiedeva di specificare a quale data center si desidera inviare i dati. L&#39;invio di hit al centro dati errato causava la perdita di dati.

 Adobe ha migliorato questa esperienza consentendo a qualsiasi implementazione di inviare hit `sc.adobedc.net`. La specifica del data center non è più necessaria.
