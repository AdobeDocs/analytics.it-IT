---
description: Scopri in che modo le dimensioni suddivise in base al tempo prendono il timestamp degli eventi raccolti e suddividono questi eventi in dimensioni più significative, come Ora del giorno o Giorno della settimana.
title: Suddividere le dimensioni in base al tempo
feature: Dimensions
role: User, Admin
exl-id: 92fbcc1e-1f7f-405a-8ad1-199fb7ba505e
source-git-commit: bf8bc40e3ec325e8e70081955fb533eee66a1734
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 74%

---

# Suddividere le dimensioni in base al tempo

Con la suddivisione in base al tempo, il timestamp degli hit raccolti viene suddiviso in dimensioni più significative, ad esempio **Ora del giorno** o **Giorno della settimana**.


>[!BEGINSHADEBOX]

Per un video demo, vedi ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Dimensioni suddivise in base al tempo](https://video.tv.adobe.com/v/329410?quality=12&learn=on&captions=ita){target="_blank"}.

>[!ENDSHADEBOX]


Le dimensioni suddivise in base al tempo sono relative al fuso orario della suite di rapporti o della suite di rapporti virtuale. Sono disponibili in Analysis Workspace e sono utili per rispondere a domande di tipo:

* Su un grande intervallo di dati, qual è l’ora di maggior afflusso al sito o all’app?
* In quale ora del giorno o giorno della settimana si verifica il maggior numero di conversioni sul sito o sull’app?
* Come sono le vendite nel fine settimana rispetto ai giorni feriali?
* Una certa campagna di marketing ha generato più conversioni nelle ore della mattina o del pomeriggio?

>[!NOTE]
>
>le dimensioni suddivise in base al tempo sono disponibili solo in Analysis Workspace. Per usare le dimensioni suddivise in base al tempo in altre soluzioni Analytics, è necessario implementare il [plug-in getTimeParting](https://experienceleague.adobe.com/docs/analytics/implementation/vars/plugins/gettimeparting.html?lang=it).

In Analysis Workspace, le dimensioni suddivise in base al tempo comprendono:

| Dimensione | Valori di esempio |
| --- | --- |
| Ora del giorno | 0-23 |
| AM/PM | AM, PM |
| Giorno della settimana | Lunedì, martedì, mercoledì, giovedì, venerdì, sabato |
| Fine settimana/Giorno feriale | Fine settimana, giorno feriale |
| Giorno del mese | 1-31 |
| Mese dell’anno | Gennaio-Dicembre |
| Giorno dell’anno | 1-366 |
| Trimestre dell’anno | Q1, Q2, Q3, Q4 |
