---
description: Nel passaggio 1 della Richiesta guidata è possibile applicare un livello di granularità alla richiesta di dati. La granularità specifica il livello di dettaglio basato sul tempo incluso nel rapporto.
solution: Analytics
title: Granularity (Granularità)
topic: Report builder
uuid: 948b3ff2-fcff-45fc-9e8c-8a025ac562b1
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Granularity (Granularità)

Nella Richiesta guidata: Passaggio 1, è possibile applicare un livello di granularità alla richiesta di dati. La granularità specifica il livello di dettaglio basato sul tempo incluso nel rapporto.

I valori validi sono ora, giorno, settimana, mese, trimestre, anno e aggregato.

## Elaborazione della granularità con Generatore di report

Si supponga di scegliere un intervallo di date per un mese con [!UICONTROL Month] granularità. Le richieste mostrano i totali per la metrica in base esattamente al valore di un mese di dati. Se l'intervallo di date della richiesta si estende per un trimestre, il rapporto mostra tre cifre: uno per ogni unità mensile, o frazione di essa. Se oggi è il 18 marzo, scegliendo l'ultimo trimestre restituisce un dato per il 1 gennaio - 31 gennaio, un altro dato per il 1 febbraio - 28 febbraio, e un dato finale per il 1 - 17 marzo.
