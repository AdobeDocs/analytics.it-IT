---
description: Nel passaggio 1 della Creazione guidata richieste è possibile applicare un livello di granularità alla richiesta di dati. Granularità specifica il livello di dettaglio basato sul tempo incluso nel rapporto.
title: Granularità
uuid: 948b3ff2-fcff-45fc-9e8c-8a025ac562b1
feature: Report Builder
role: User, Admin
exl-id: 96c3b93a-9adf-4993-b6fc-9146ee5be4bd
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '159'
ht-degree: 1%

---

# Granularità

Nel passaggio 1 della Creazione guidata richieste è possibile applicare un livello di granularità alla richiesta di dati. Granularità specifica il livello di dettaglio basato sul tempo incluso nel rapporto.

I valori validi sono Ora, Giorno, Settimana, Mese, Trimestre, Anno e Aggregato.

## Come il Report Builder elabora la granularità

Supponiamo di scegliere un intervallo di date per un mese con granularità [!UICONTROL Month]. Le richieste mostrano i totali per la metrica in base ai dati relativi a un mese esatto. Se l’intervallo di date della richiesta si estende su un trimestre, il rapporto mostra tre cifre: una per ogni unità di mese o frazione di unità. Se oggi è il 18 marzo, scegliendo l’ultimo trimestre si restituisce un dato per il 1° gennaio - 31 gennaio, un altro per il 1° febbraio - 28 febbraio e un dato finale per il 1° marzo - 17 marzo.
