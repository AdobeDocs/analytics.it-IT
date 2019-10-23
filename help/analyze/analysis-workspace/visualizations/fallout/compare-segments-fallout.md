---
description: Puoi creare segmenti da un punto di contatto, aggiungere segmenti come punto di contatto e confrontare flussi di lavoro chiave tra vari segmenti in Analysis Workspace.
keywords: abbandono e segmentazione;segmenti nell’analisi dell’abbandono;confrontare segmenti nell’abbandono
seo-description: Puoi creare segmenti da un punto di contatto, aggiungere segmenti come punto di contatto e confrontare flussi di lavoro chiave tra vari segmenti in Analysis Workspace.
seo-title: Applicare i segmenti nell’analisi dell’abbandono
title: Applicare i segmenti nell’analisi dell’abbandono
uuid: e87a33df-160e-4943-8d02-4d6609ae3bb1
translation-type: tm+mt
source-git-commit: ca9f1ed00295b556250894ae4e7fa377ef8a593d

---


# Applicare i segmenti nell’analisi dell’abbandono

Puoi creare segmenti da un punto di contatto, aggiungere segmenti come punto di contatto e confrontare flussi di lavoro chiave tra vari segmenti in Analysis Workspace.

> [!IMPORTANT] I segmenti utilizzati come punti di controllo in Abbandono devono utilizzare un contenitore di livello inferiore rispetto al contesto generale della visualizzazione Abbandono. Con un abbandono del contesto del visitatore, i segmenti utilizzati come punti di controllo devono essere segmenti basati su visite o hit. Con un abbandono del contesto delle visite, i segmenti utilizzati come punto di controllo devono essere segmenti basati sugli hit. Se utilizzate una combinazione non valida, l'abbandono sarà 100%. Abbiamo aggiunto un avviso alla visualizzazione Abbandono che verrà visualizzata quando aggiungi un segmento incompatibile come punto di contatto. Alcune combinazioni di contenitori di segmenti non valide genereranno diagrammi di abbandono non validi, ad esempio:

* Utilizzo di un segmento basato su visitatore come punto di contatto all’interno di una visualizzazione Abbandono in un contesto Visitatore
* Utilizzo di un segmento basato su visitatore come punto di contatto all’interno di una visualizzazione Abbandono in un contesto Visita
* Utilizzo di un segmento basato su visite come punto di contatto all’interno di una visualizzazione Abbandono in un contesto Visita

## Create a segment from a touchpoint {#section_915E8FBF35CD4F34828F860C1CCC2272}

1. Crea un segmento da un punto di contatto specifico che ti interessa e che potrebbe essere utile da applicare ad altri rapporti. Fai clic con il pulsante destro del mouse sul punto di contatto e seleziona **[!UICONTROL Create segment from touchpoint]**.

   ![](assets/segment-from-touchpoint.png)

   Viene aperto il Generatore di segmenti, precompilato con il segmento sequenziale pregenerato che corrisponde al punto di contatto selezionato:

   ![](assets/segment-builder.png)

1. Assegna al segmento un titolo e una descrizione e salvalo.

   Ora puoi usare questo segmento in qualsiasi rapporto.

## Add a segment as a touchpoint {#section_17611C1A07444BE891DC21EE8FC03EFC}

Per vedere ad esempio come gli utenti USA influenzano le metriche di abbandono, trascina il segmento degli utenti USA nella sezione Abbandono:

![](assets/segment-touchpoint.png)

Oppure puoi creare un punto di contatto AND trascinando il segmento degli utenti USA su un altro punto di controllo.

## Compare segments in fallout {#section_E0B761A69B1545908B52E05379277B56}

Puoi confrontare un numero illimitato di segmenti nella visualizzazione Abbandono.

1. Select the segments you want to compare from the [!UICONTROL Segments] rail on the left. Nel nostro esempio, abbiamo selezionato 2 segmenti: Utenti USA e Utenti non USA.
1. Trascinali nella zona di rilascio Segmento, in alto.

   ![](assets/segment-drop.png)

1. Facoltativo: puoi mantenere il contenitore predefinito “Tutte le visite”, o eliminarlo.

   ![](assets/seg-compare.png)

1. Ora puoi confrontare i dati di abbandono tra i due segmenti, ad esempio dove un segmento ha prestazioni migliori dell’altro.
