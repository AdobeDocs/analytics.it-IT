---
description: È possibile confrontare i valori con errori di ortografica comuni e aggiornarli in modo da visualizzarli correttamente nei rapporti.
subtopic: Processing rules
title: Pulizia dei valori in un rapporto
feature: Admin Tools
uuid: fcd72afc-3a3c-47a9-a5e4-53389dba7d83
exl-id: 109005a3-2ea4-4b61-a733-d1019218ec56
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '115'
ht-degree: 16%

---

# Pulizia dei valori in un rapporto

È possibile confrontare i valori con errori di ortografica comuni e aggiornarli in modo da visualizzarli correttamente nei rapporti.

Per evitare di corrispondere inavvertitamente ad altri valori, utilizza l’opzione di corrispondenza più restrittiva disponibile. Puoi eseguire un rapporto sulla variabile (prop1 nell’esempio seguente) e cercare i termini selezionati per sostituire per assicurarsi che non corrispondano ai valori non desiderati. I confronti tra stringhe non fanno distinzione tra maiuscole e minuscole.

| Set di regole | Valore |
|---|---|
| Condizione | Se prop1 inizia con lo shopping |
| Azione | Sovrascrivi il valore di prop1 a valore personalizzato Shopping |

Ad esempio:

![](assets/clean-up-values-in-report.png)
