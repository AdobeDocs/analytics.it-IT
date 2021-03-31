---
description: Nel passaggio 1 della Creazione guidata richieste è possibile applicare un livello di granularità alla richiesta di dati. La granularità specifica il livello di dettaglio basato sul tempo incluso nel rapporto.
title: Granularity (Granularità)
uuid: 948b3ff2-fcff-45fc-9e8c-8a025ac562b1
feature: Report Builder
role: Business Practices, amministratore
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 2%

---


# Granularity (Granularità)

Nella Creazione guidata richieste: Al passaggio 1, puoi applicare un livello di granularità alla richiesta di dati. La granularità specifica il livello di dettaglio basato sul tempo incluso nel rapporto.

I valori validi sono Ora, Giorno, Settimana, Mese, Trimestre, Anno e Aggregato.

## Elaborazione della granularità da parte del Report Builder

Supponiamo di scegliere un intervallo di date per un mese con granularità [!UICONTROL Month]. Le richieste mostrano i totali per la metrica in base esattamente al valore di un mese di dati. Se l’intervallo di date della richiesta si estende su un trimestre, il rapporto mostra tre cifre: una per ogni unità di mese o frazione di essa. Se oggi è il 18 marzo, la scelta dell&#39;ultimo trimestre restituisce una cifra per il 1° gennaio - 31 gennaio, un&#39;altra per il 1° febbraio - 28 febbraio, e una cifra finale per il 1° marzo - 17 marzo.
