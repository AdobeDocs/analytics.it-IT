---
description: L'elenco delle informazioni sui percorsi potrebbe non essere registrato e visualizzato nei report.
keywords: Implementazione di Analytics
seo-description: L'elenco delle informazioni sui percorsi potrebbe non essere registrato e visualizzato nei report.
seo-title: I percorsi dei motivi potrebbero non essere registrati
solution: Analytics
title: I percorsi dei motivi potrebbero non essere registrati
topic: Sviluppatore e implementazione
uuid: 9985 b 7 f 7-75 ea -4 c 94-97 a 3-520 f 92630989
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# I percorsi dei motivi potrebbero non essere registrati

L'elenco delle informazioni sui percorsi potrebbe non essere registrato e visualizzato nei report.

* Il percorso non è stato abilitato per quel prop in quella suite di rapporti. Questa abilitazione è specifica per la suite di rapporti.
* I dati non vengono passati nella prop corretta.
* I percorsi sono stati abilitati e i dati sono nel prop, ma non sono visualizzati nei report. Though the [!UICONTROL sprop] data may show up within 10 minutes, the pathing data will not show up until the visitor's session has ended. Termina dopo 30 minuti di inattività. Analytics quindi dura altri 10 minuti per completare l'elaborazione dei dati percorso per la presentazione finale nei report.

Se hai selezionato tutti questi e i dati non sono ancora visibili, consulta l'Assistenza clienti per eseguire un ulteriore debug.
