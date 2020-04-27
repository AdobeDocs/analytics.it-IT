---
description: Nel passaggio 1 della Richiesta guidata è possibile applicare un livello di granularità alla richiesta di dati. La granularità specifica il livello di dettaglio basato sul tempo incluso nel rapporto.
title: Granularity (Granularità)
topic: Report builder
uuid: 948b3ff2-fcff-45fc-9e8c-8a025ac562b1
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Granularity (Granularità)

Nella Richiesta guidata: Passaggio 1, è possibile applicare un livello di granularità alla richiesta di dati. La granularità specifica il livello di dettaglio basato sul tempo incluso nel rapporto.

I valori validi sono Ora, Giorno, Settimana, Mese, Trimestre, Anno e Aggregato.

## Elaborazione della granularità con Generatore di report

Si supponga di scegliere un intervallo di date per un mese con [!UICONTROL Month] granularità. Le richieste mostrano i totali per la metrica in base esattamente al valore di un mese di dati. Se l&#39;intervallo di date della richiesta si estende per un trimestre, il rapporto mostra tre cifre: uno per ogni unità mensile, o frazione di essa. Se oggi è il 18 marzo, scegliendo l&#39;ultimo trimestre restituisce un dato per il 1 gennaio - 31 gennaio, un altro dato per il 1 febbraio - 28 febbraio, e un dato finale per il 1 - 17 marzo.
