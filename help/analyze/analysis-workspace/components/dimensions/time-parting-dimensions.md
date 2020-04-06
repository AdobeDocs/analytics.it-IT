---
description: Con la suddivisione in base al tempo, viene considerato il timestamp degli hit raccolti che viene quindi suddiviso in dimensioni più significative, quali “Ora del giorno” o “Giorno della settimana”.
title: Suddividere le dimensioni in base al tempo
uuid: c9fa7921-aa57-483c-b2f9-da55013ada17
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Suddividere le dimensioni in base al tempo

Con la suddivisione in base al tempo, viene considerato il timestamp degli hit raccolti che viene quindi suddiviso in dimensioni più significative, quali “Ora del giorno” o “Giorno della settimana”.

Le dimensioni suddivise in base al tempo si basano sul fuso orario della suite di rapporti o della suite di rapporti virtuale. Queste dimensioni sono disponibili in Analysis Workspace e possono essere utili per rispondere alle seguenti domande:

* In un intervallo di date ampio, qual è l’ora più popolare in cui i visitatori possono accedere al sito o all’app?
* Are there days of the week, or hours of the day, on which conversion is higher on my site or app?
* Come sono le vendite nel fine settimana rispetto ai giorni feriali?
* Una certa campagna di marketing genera maggiori conversioni al mattino o nel pomeriggio?

>[!NOTE] le dimensioni suddivise in base al tempo sono disponibili solo in Analysis Workspace. Per usare le dimensioni suddivise in base al tempo in altre soluzioni Analytics, è necessario implementare il [plug-in getTimeParting](https://marketing.adobe.com/resources/help/it_IT/sc/implement/getTimeParting.html).

Le dimensioni suddivise in base al tempo in Analysis Workspace includono:

| Dimensione | Valori di esempio |
|--- |--- |
| Ora del giorno | 0-23 |
| AM/PM | AM, PM |
| Giorno della settimana | Lunedì, martedì, mercoledì, giovedì, venerdì, sabato |
| Fine settimana/Giorno feriale | Fine settimana, Giorno feriale |
| Giorno del mese | 1-31 |
| Mese dell&#39;anno | Gennaio-Dicembre |
| Giorno dell&#39;anno | 1-366 |
| Trimestre dell&#39;anno | Q1, Q2, Q3, Q4 |
