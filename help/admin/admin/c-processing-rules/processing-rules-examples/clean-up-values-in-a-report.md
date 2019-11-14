---
description: È possibile stabilire una corrispondenza tra i valori e gli errori ortografici più comuni e aggiornarli in modo che vengano visualizzati correttamente nei rapporti.
solution: Analytics
subtopic: Processing rules
title: Pulizia dei valori in un rapporto
topic: Admin tools
uuid: fcd72afc-3a3c-47a9-a5e4-53389dba7d83
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Pulizia dei valori in un rapporto

È possibile stabilire una corrispondenza tra i valori e gli errori ortografici più comuni e aggiornarli in modo che vengano visualizzati correttamente nei rapporti.

Per evitare di corrispondere inavvertitamente ad altri valori, utilizzate l'opzione di corrispondenza più restrittiva disponibile. È possibile eseguire un rapporto sulla variabile (prop1 nell'esempio seguente) e cercare i termini selezionati per sostituire per assicurarsi che non corrisponda a valori non desiderati. I confronti tra stringhe non fanno distinzione tra maiuscole e minuscole.

| Set di regole | Valore |
|---|---|
| Condizione | Se prop1 inizia con Shopping |
| Azione | Sovrascrivi valore di prop1 a valore personalizzato Shopping |

Ad esempio:

![](assets/clean-up-values-in-report.png)

