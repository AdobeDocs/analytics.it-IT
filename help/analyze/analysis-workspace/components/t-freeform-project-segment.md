---
description: Utilizzare i segmenti in Analysis Workspace.
title: Segmenti
uuid: 677f6030-5b3e-4dfa-bb79-9f27f3382fb1
translation-type: tm+mt
source-git-commit: 5d8032a9806836e7d0ecbd7fa3652ed1fd137e89
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 93%

---


# Segmenti {#topic_DC2917A2E8FD4B62816572F3F6EDA58A}

## Barra dei segmenti {#section_3B07D458C43E42FDAF242BB3ACAF3E90}

La barra dei segmenti nel menu Components (Componenti) mostra i segmenti e i modelli di segmenti, come indicato da queste icone:

![](assets/segment_icons.png)

[Utilizzo dei segmenti in Analysis Workspace](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/applying-segments/using-segments-in-analysis-workspace.html) (6:46)

## Creare un segmento {#section_693CFADA668B4542B982446C2B4CF0F5}

Puoi creare all’istante dei segmenti rilasciando qualsiasi tipo di componente (dimensione, elemento dimensione, evento, metrica, segmento, modello di segmento, intervallo di date) nella zona di rilascio dei segmenti, nella parte superiore di un pannello.

I tipi di componente vengono automaticamente convertiti in segmenti. In alternativa, puoi fare clic sul simbolo “+” nella casella di riepilogo Aggiungi segmento.

Nota bene:

* Nella zona dei segmenti **non è possibile** rilasciare i tipi di componenti seguenti: metriche calcolate e dimensioni/metriche da cui non è possibile creare i segmenti.
* Per eventi e dimensioni intere, Analysis Workspace crea dei segmenti di hit di tipo “esiste”. Esempi: “Hit dove esiste eVar1” oppure “Hit dove esiste event1”.
* Se nella zona di rilascio dei segmenti viene rilasciato “Non specificato” o “Nessuno”, vengono automaticamente convertiti in un segmento di tipo “non esiste” in modo da essere trattati correttamente nella segmentazione.

![](assets/segment-dropzone.png)

>[!NOTE]
>
>I segmenti creati in questo modo sono interni al progetto.

Puoi scegliere di rendere questi segmenti pubblici (globali), seguendo questi passaggi:

1. Passa il mouse sul segmento nella zona di rilascio e fai clic sull’icona “i”.
1. Nel pannello informazioni visualizzato, fai clic su **[!UICONTROL Make public]**.

   ![](assets/segment-info.png)

## Altri metodi per applicare segmenti {#section_10FF2E309BA84618990EA5B473015894}

Esistono molti altri metodi per applicare i segmenti a un pannello a forma libera.

| Azione | Descrizione |
|--- |--- |
| Crea segmenti dalla selezione | Crea un segmento in linea. Seleziona le righe, fai clic con il pulsante destro del mouse sulla selezione e crea un segmento in linea. Questo tipo di segmento si applica solo al progetto aperto e non viene salvato come segmento di Analytics. 1. Seleziona le righe.  2. Fai clic con il pulsante destro del mouse sulla selezione.  3. Fai clic su *Create Segment from selection* (Crea segmenti da selezione). |
| Components (Componenti) > New Segment (Nuovo segmento) | Visualizza il Segment Builder (Generatore di segmenti). Per ulteriori informazioni sulla segmentazione, consulta l’articolo su come [generare i segmenti](https://docs.adobe.com/content/help/it-IT/analytics/components/segmentation/segmentation-workflow/seg-build.html). |
| Share (Condividi) > Share Project (Condividi progetto) or Share (Condividi) > Curate Project Data (Cura dati progetto) | In [Cura e condivisione](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/curate-share/curate.html#concept_4A9726927E7C44AFA260E2BB2721AFC6), scopri come i segmenti applicati al progetto sono disponibili al destinatario nelle analisi condivise. |
| Uso dei segmenti come dimensioni | Video: [Uso dei segmenti come dimensioni in Analysis Workspace](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/components/segmentation/using-segments-as-dimensions-in-analysis-workspace.html) |
