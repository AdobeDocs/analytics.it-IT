---
description: È possibile stabilire una corrispondenza tra i valori e gli errori ortografici più comuni e aggiornarli in modo che vengano visualizzati correttamente nei rapporti.
seo-description: È possibile stabilire una corrispondenza tra i valori e gli errori ortografici più comuni e aggiornarli in modo che vengano visualizzati correttamente nei rapporti.
seo-title: Pulizia dei valori in un rapporto
solution: Analytics
subtopic: Regole di elaborazione
title: Pulizia dei valori in un rapporto
topic: Strumenti di amministrazione
uuid: fcd72afc-3a3c-47a9-a5e4-53389dba7d83
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

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

