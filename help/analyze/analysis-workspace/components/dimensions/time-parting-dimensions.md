---
description: Scopri in che modo le dimensioni suddivise in base al tempo prendono il timestamp degli eventi raccolti e suddividono questi eventi in dimensioni più significative, come Ora del giorno o Giorno della settimana.
title: Suddivisione delle dimensioni in base al tempo
feature: Dimensions
role: User, Admin
exl-id: 92fbcc1e-1f7f-405a-8ad1-199fb7ba505e
TQID: https://experienceleague.adobe.com/bQVBmv3KhaDZtmUXSOY3UsustpCZKAwJ8rH9Qv49Rfw
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 266
ht-degree: 24%

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
