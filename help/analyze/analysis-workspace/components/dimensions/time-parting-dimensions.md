---
description: Con la suddivisione in base al tempo, viene considerato il timestamp degli hit raccolti che vengono quindi suddivisi in dimensioni più significative, quali “Ora del giorno” o “Giorno della settimana”.
seo-description: Con la suddivisione in base al tempo, viene considerato il timestamp degli hit raccolti che vengono quindi suddivisi in dimensioni più significative, quali “Ora del giorno” o “Giorno della settimana”.
seo-title: Suddividere le dimensioni in base al tempo
title: Suddividere le dimensioni in base al tempo
uuid: c 9 fa 7921-aa 57-483 c-b 2 f 9-da 55013 ada 17
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Suddividere le dimensioni in base al tempo

Con la suddivisione in base al tempo, viene considerato il timestamp degli hit raccolti che vengono quindi suddivisi in dimensioni più significative, quali “Ora del giorno” o “Giorno della settimana”.

Le dimensioni suddivise in base al tempo sono relative al fuso orario della suite di rapporti o della suite di rapporti virtuale. Sono disponibili in Analysis Workspace e sono utili per rispondere a domande di tipo:

* Su un grande intervallo di dati, qual è l’ora di maggior afflusso al sito o all’app?
* In quale ora del giorno o giorno della settimana si verifica il maggior numero di conversioni sul sito o sull’app?
* Come sono le vendite nel fine settimana rispetto ai giorni feriali?
* Una certa campagna di marketing ha generato più conversioni nelle ore della mattina o del pomeriggio?

>[!NOTE]
>
>le dimensioni suddivise in base al tempo sono disponibili solo in Analysis Workspace. Per usare le dimensioni suddivise in base al tempo in altre soluzioni Analytics, è necessario implementare il plug-in [getTimeParting](https://marketing.adobe.com/resources/help/en_US/sc/implement/getTimeParting.html).

In Analysis Workspace, le dimensioni suddivise in base al tempo comprendono:

| Dimensione | Valori di esempio |
|--- |--- |
| Ora del giorno | 0-23 |
| AM/PM | AM, PM |
| Giorno della settimana | Lunedì, martedì, mercoledì, giovedì, venerdì, sabato |
| Fine settimana/Giorno feriale | Fine settimana, giorno feriale |
| Giorno del mese | 1-31 |
| Mese dell’anno | Gennaio-Dicembre |
| Giorno dell’anno | 1-366 |
| Trimestre dell’anno | Q1, Q2, Q3, Q4 |
