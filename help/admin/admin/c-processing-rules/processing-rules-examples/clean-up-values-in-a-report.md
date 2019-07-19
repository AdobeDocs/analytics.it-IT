---
description: È possibile associare valori ai più comuni errori di ortografia e aggiornarli in modo corretto nei rapporti.
seo-description: È possibile associare valori ai più comuni errori di ortografia e aggiornarli in modo corretto nei rapporti.
seo-title: Pulizia dei valori in un rapporto
solution: Analytics
subtopic: Regole di elaborazione
title: Pulizia dei valori in un rapporto
topic: Strumenti di amministrazione
uuid: fcd 72 afc -3 a 3 c -47 a 9-a 5 e 4-53389 dba 7 d 83
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Pulizia dei valori in un rapporto

È possibile associare valori ai più comuni errori di ortografia e aggiornarli in modo corretto nei rapporti.

Per evitare di corrispondere inavvertitamente ad altri valori, utilizzare l'opzione corrispondente più restrittiva disponibile. Potete eseguire un rapporto sulla variabile (prop 1 nell'esempio di seguito) e cercare i termini che selezionate per sostituire, in modo che non corrispondano ai valori indesiderati. Il confronto delle stringhe non fa distinzione tra maiuscole e minuscole.

| Set di regole | Valore |
|---|---|
| Condizione | Se prop 1 inizia con shopping |
| Azione | Valore sovrascritto da prop 1 a personalizza acquisto |

Ad esempio:

![](assets/clean-up-values-in-report.png)

