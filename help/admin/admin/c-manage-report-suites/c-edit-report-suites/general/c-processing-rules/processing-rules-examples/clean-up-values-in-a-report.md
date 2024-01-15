---
description: Puoi cercare valori contenenti errori ortografici comuni e aggiornarli in modo da riportarli correttamente nei rapporti.
subtopic: Processing rules
title: Pulire i valori in un rapporto
feature: Admin Tools
role: Admin
exl-id: 109005a3-2ea4-4b61-a733-d1019218ec56
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 100%

---

# Pulire i valori in un rapporto

Puoi cercare valori contenenti errori ortografici comuni e aggiornarli in modo da riportarli correttamente nei rapporti.

Per evitare di agire accidentalmente su altri valori, utilizza l’opzione di corrispondenza più restrittiva disponibile. Puoi eseguire un rapporto sulla variabile (prop1 nell’esempio seguente) e cercare i termini che vuoi sostituire per evitare che vengano rilevati valori non desiderati. Nel confronto delle stringhe non viene fatta distinzione tra maiuscole e minuscole.

| Set di regole | Valore |
|---|---|
| Condizione | Se prop1 inizia con: Shoping |
| Azione | Sovrascrivi il valore di prop1 con valore personalizzato: Shopping |

Esempio:

![](assets/clean-up-values-in-report.png)
