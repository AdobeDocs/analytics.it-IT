---
description: Scopri in che modo le dimensioni suddivise in base al tempo prendono il timestamp degli eventi raccolti e suddividono questi eventi in dimensioni più significative, come Ora del giorno o Giorno della settimana.
title: Suddivisione delle dimensioni in base al tempo
feature: Dimensions
role: User, Admin
exl-id: 92fbcc1e-1f7f-405a-8ad1-199fb7ba505e
source-git-commit: 8b1e25b9633b6db3e49da079f7014e6b7b595474
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 25%

---

# Suddividere le dimensioni in base al tempo

Con la suddivisione in base al tempo, il timestamp degli hit raccolti viene suddiviso in dimensioni più significative, ad esempio **Ora del giorno** o **Giorno della settimana**.


>[!BEGINSHADEBOX]

Per un video demo, vedi ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Dimensioni suddivise in base al tempo](https://experienceleague.adobe.com/it/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/time-parting-dimensions-in-analysis-workspace){target="_blank"}.

>[!ENDSHADEBOX]


Le dimensioni suddivise in base al tempo si basano sul fuso orario della suite di rapporti o della suite di rapporti virtuali. Queste dimensioni sono disponibili in Analysis Workspace e possono essere utili per rispondere alle seguenti domande:

* In un ampio intervallo di date, qual è l’ora del giorno più comune per i visitatori per accedere al sito o all’app?
* Esistono giorni della settimana o ore del giorno in cui la conversione è più elevata sul sito o nell’app?
* Come si confrontano le vendite del fine settimana con le vendite del giorno feriale?
* Una determinata campagna di marketing genera conversioni più elevate al mattino o nel pomeriggio?

>[!NOTE]
>
>le dimensioni suddivise in base al tempo sono disponibili solo in Analysis Workspace. Per usare le dimensioni suddivise in base al tempo in altre soluzioni Analytics, è necessario implementare il [plug-in getTimeParting](/help/implement/vars/plugins/gettimeparting.md).

Le dimensioni suddivise in base al tempo in Analysis Workspace includono:

| Dimensione | Valori di esempio |
| --- | --- |
| Ora del giorno | 0-23 |
| AM/PM | AM, PM |
| Giorno della settimana | Lunedì, martedì, mercoledì, giovedì, venerdì, sabato |
| Fine settimana/Giorno feriale | Fine settimana, Giorno feriale |
| Giorno del mese | 1-31 |
| Mese dell’anno | Gennaio-Dicembre |
| Giorno dell’anno | 1-366 |
| Trimestre dell’anno | Q1, Q2, Q3, Q4 |
