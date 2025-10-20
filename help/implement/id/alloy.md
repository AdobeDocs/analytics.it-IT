---
title: Identificazione dei visitatori tramite la libreria JavaScript di Web SDK
description: Identifica correttamente i visitatori quando si implementa la libreria JavaScript di Web SDK.
source-git-commit: 779ba5b0a1d71467aaaf3872fd707cc323ae8af2
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 0%

---

# Identificazione dei visitatori tramite la libreria JavaScript di Web SDK

Adobe Experience Platform Web SDK (`alloy.js`) offre un approccio unificato e moderno alla raccolta dei dati per tutte le applicazioni Adobe Experience Cloud, incluso Adobe Analytics. I dati di identità possono essere estesi per supportare ID personalizzati e più spazi dei nomi utilizzando XDM `identityMap`. Adobe consiglia di utilizzare il servizio Adobe Experience Cloud ID come identificatore primario per Analytics, utilizzando altre opzioni di gestione delle identità per scenari avanzati.

Se la tua organizzazione utilizza la libreria JavaScript di Web SDK per inviare dati ad Adobe Analytics, è necessaria una configurazione minima per l’identificazione dei visitatori. Il servizio ID visitatore viene inviato in modalità nativa alla libreria, richiedendo solo l&#39;impostazione di **[!UICONTROL Edge Domain]** nel comando `configure`. Se questo campo è impostato sul valore desiderato, l’identificazione del visitatore funziona senza alcuna configurazione aggiuntiva.
