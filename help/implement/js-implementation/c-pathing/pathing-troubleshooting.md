---
description: Elenco di motivi per cui le informazioni di percorso potrebbero non essere registrate e visualizzate nel reporting.
keywords: Analytics Implementation
solution: Analytics
title: Motivi per cui la tracciatura percorso potrebbe non essere registrata
topic: Developer and implementation
uuid: 9985b7f7-75ea-4c94-97a3-520f92630989
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Motivi per cui la tracciatura percorso potrebbe non essere registrata

Elenco di motivi per cui le informazioni di percorso potrebbero non essere registrate e visualizzate nel reporting.

* Il percorso non è stato abilitato per la proprietà nella suite di rapporti. Questa abilitazione è specifica per la suite di rapporti.
* I dati non vengono passati nella proprietà corretta.
* Il percorso è stato abilitato e i dati sono nella proprietà, ma non è stato visualizzato nei report. Anche se i [!UICONTROL sprop] dati possono essere visualizzati entro 10 minuti, i dati del percorso non verranno visualizzati fino alla fine della sessione del visitatore. Si conclude dopo 30 minuti di inattività. Analytics impiega altri 10 minuti per completare l'elaborazione dei dati del percorso per la presentazione finale nei report.

Se hai controllato tutti questi e i dati non sono ancora visualizzati, consulta l'Assistenza clienti per ulteriori attività di debug.
