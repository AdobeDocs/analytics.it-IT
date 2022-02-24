---
description: Puoi cercare valori contenenti errori ortografici comuni e aggiornarli in modo da riportarli correttamente nei rapporti.
subtopic: Processing rules
title: Pulire i valori in un rapporto
feature: Admin Tools
uuid: fcd72afc-3a3c-47a9-a5e4-53389dba7d83
exl-id: 109005a3-2ea4-4b61-a733-d1019218ec56
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: ht
source-wordcount: '113'
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
