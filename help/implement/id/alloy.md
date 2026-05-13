---
title: Identificazione dei visitatori tramite la libreria JavaScript di Web SDK
description: Identifica correttamente i visitatori quando si implementa la libreria JavaScript di Web SDK.
exl-id: e650d6b1-6e29-4a9c-98dd-8482f50968d1
TQID: https://experienceleague.adobe.com/R6O--qqR7SzlArrIDFCWunUEAduzmAS2Skm6BKyREnw
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 190
ht-degree: 2%

---

# Identificazione dei visitatori tramite la libreria JavaScript di Web SDK

La libreria JavaScript di Adobe Experience Platform Web SDK (`alloy.js`) offre un approccio unificato e moderno alla raccolta dei dati per tutte le applicazioni Adobe Experience Cloud, incluso Adobe Analytics. Mentre la maggior parte dei clienti implementa in genere l&#39;estensione tag [Web SDK](web-sdk-extension.md), è possibile utilizzare la libreria Web SDK JavaScript in modo autonomo o all&#39;interno di un sistema di gestione tag di terze parti. Consulta [Alloy](https://github.com/adobe/alloy) su GitHub per scaricare la versione più recente della libreria.

I dati di identità possono essere estesi per supportare ID personalizzati e più spazi dei nomi utilizzando XDM `identityMap`. Adobe consiglia di utilizzare il servizio Adobe Experience Cloud ID come identificatore primario per Analytics, utilizzando altre opzioni di gestione delle identità per scenari avanzati.

Se la tua organizzazione utilizza la libreria JavaScript di Web SDK per inviare dati ad Adobe Analytics, è necessaria una configurazione minima per l’identificazione dei visitatori. Il servizio ID visitatore viene inviato in modalità nativa alla libreria, richiedendo solo l&#39;impostazione di **[!UICONTROL Edge Domain]** nel comando `configure`. Se questo campo è impostato sul valore desiderato, l’identificazione del visitatore funziona senza alcuna configurazione aggiuntiva.
