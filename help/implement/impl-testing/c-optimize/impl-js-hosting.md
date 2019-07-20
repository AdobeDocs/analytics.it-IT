---
description: L'inserimento della chiamata al file libreria javascript nella parte superiore della pagina assicura che l'immagine sia tra i primi elementi da scaricare.
keywords: Implementazione di Analytics
seo-description: L'inserimento della chiamata al file libreria javascript nella parte superiore della pagina assicura che l'immagine sia tra i primi elementi da scaricare.
seo-title: Posizione file javascript e relativi argomenti
solution: Analytics
subtopic: 'Risoluzione dei problemi   '
title: Posizione file javascript e relativi argomenti
topic: Sviluppatore e implementazione
uuid: ed 5118 a 8-b 142-4 fab -8 aa 1-92 d 931 cc 1439
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Posizione file javascript e relativi argomenti

L'inserimento della chiamata al file libreria javascript nella parte superiore della pagina assicura che l'immagine sia tra i primi elementi da scaricare.

La maggior parte dei browser Web scaricano le immagini simultaneamente. In genere possono essere scaricate da tre a quattro immagini.

Poiché la maggior parte dei browser Web scaricano gli elementi contemporaneamente, la barra di stato di molti browser comuni (inclusa Internet Explorer) non rispecchia con precisione l'elemento che il browser sta tentando di caricare. Ad esempio, la barra di stato potrebbe indicare che il browser è in attesa di un'immagine da scaricare 1. I test dei pacchetti di rete mostrano che il browser ha già ricevuto l'immagine 1 ed è attualmente in attesa di immagine 2.

>[!NOTE]
>
>Poiché i fornitori di controllo delle prestazioni Internet (ad esempio, Sistemi Keynote) scaricano gli elementi delle immagini di pagina in sequenza, non in contemporanea, non simulano la tipica esperienza utente.

