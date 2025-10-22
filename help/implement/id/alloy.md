---
title: Identificazione dei visitatori tramite la libreria JavaScript di Web SDK
description: Identifica correttamente i visitatori quando si implementa la libreria JavaScript di Web SDK.
source-git-commit: 98e9dc4932bd23d3e0b632705945f56c243750c5
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 0%

---

# Identificazione dei visitatori tramite la libreria JavaScript di Web SDK

La libreria JavaScript di Adobe Experience Platform Web SDK (`alloy.js`) offre un approccio unificato e moderno alla raccolta dei dati per tutte le applicazioni Adobe Experience Cloud, incluso Adobe Analytics. Mentre la maggior parte dei clienti implementa in genere l&#39;estensione tag [Web SDK](web-sdk-extension.md), è possibile utilizzare la libreria Web SDK JavaScript in modo autonomo o all&#39;interno di un sistema di gestione tag di terze parti. Consulta [Alloy](https://github.com/adobe/alloy) su GitHub per scaricare la versione più recente della libreria.

I dati di identità possono essere estesi per supportare ID personalizzati e più spazi dei nomi utilizzando XDM `identityMap`. Adobe consiglia di utilizzare il servizio Adobe Experience Cloud ID come identificatore primario per Analytics, utilizzando altre opzioni di gestione delle identità per scenari avanzati.

Se la tua organizzazione utilizza la libreria JavaScript di Web SDK per inviare dati ad Adobe Analytics, è necessaria una configurazione minima per l’identificazione dei visitatori. Il servizio ID visitatore viene inviato in modalità nativa alla libreria, richiedendo solo l&#39;impostazione di **[!UICONTROL Edge Domain]** nel comando `configure`. Se questo campo è impostato sul valore desiderato, l’identificazione del visitatore funziona senza alcuna configurazione aggiuntiva.
