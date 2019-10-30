---
description: nulle
seo-description: nulle
seo-title: Segmenti
title: Segmenti
uuid: 677f6030-5b3e-4dfa-bb79-9f27f3382fb1
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Segmenti {#topic_DC2917A2E8FD4B62816572F3F6EDA58A}

## Segment rail {#section_3B07D458C43E42FDAF242BB3ACAF3E90}

La barra dei segmenti nel menu Components (Componenti) mostra i segmenti e i modelli di segmenti, come indicato da queste icone:

![](assets/segment_icons.png)

[Utilizzo dei segmenti in Analysis Workspace su YouTube](https://www.youtube.com/watch?v=QlUCdQDnni4)(6:46)

## Creare un segmento {#section_693CFADA668B4542B982446C2B4CF0F5}

Puoi creare all’istante dei segmenti rilasciando qualsiasi tipo di componente (dimensione, elemento dimensione, evento, metrica, segmento, modello di segmento, intervallo di date) nella zona di rilascio dei segmenti, nella parte superiore di un pannello.

I tipi di componente vengono automaticamente convertiti in segmenti. In alternativa, puoi fare clic sul segno "+" nella casella di riepilogo Aggiungi segmento.

Nota bene:

* Nella zona dei segmenti **non è possibile** rilasciare i tipi di componenti seguenti: metriche calcolate e dimensioni/metriche da cui non è possibile creare i segmenti.
* Per eventi e dimensioni intere, Analysis Workspace crea dei segmenti di hit di tipo “esiste”. Esempi: “Hit dove esiste eVar1” oppure “Hit dove esiste event1”.
* Se nella zona di rilascio del segmento viene omessa l’impostazione "unspecified" o "none", viene automaticamente convertita in un segmento "non esiste" in modo che venga trattato correttamente nella segmentazione.

![](assets/segment-dropzone.png)

> [!NOTE] I segmenti creati in questo modo sono interni al progetto.

Puoi scegliere di rendere questi segmenti pubblici (globali), seguendo questi passaggi:

1. Passa il mouse sul segmento nella zona di rilascio e fai clic sull’icona “i”.
1. In the information panel that displays, click **[!UICONTROL Make public]**.

   ![](assets/segment-info.png)

## Other methods for applying segments {#section_10FF2E309BA84618990EA5B473015894}

Esistono molti altri metodi per applicare i segmenti a un pannello a forma libera.

| Azione | Descrizione |
|--- |--- |
| Crea segmenti dalla selezione | Crea un segmento in linea. Seleziona le righe, fai clic con il pulsante destro del mouse sulla selezione e crea un segmento in linea. Questo tipo di segmento si applica solo al progetto aperto e non viene salvato come segmento di Analytics. 1. Selezionare le righe.  2. Fare clic con il pulsante destro del mouse sulla selezione.  3. Click *Create segment from selection*. |
| Componenti &gt; Nuovo segmento | Visualizza il Generatore di segmenti. See [Segment Builder](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-build.html) for more information about segmentation. |
| Condividi &gt; Condividi progetto o Condividi &gt; Cura dati progetto | In [Curate and Share](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate.html#concept_4A9726927E7C44AFA260E2BB2721AFC6), learn how segments that you apply to the project are available in shared analysis for the recipient. |
| Uso dei segmenti come dimensioni | Video: [Uso dei segmenti come dimensioni in Analysis Workspace](https://www.youtube.com/watch?v=WmSdReKTWto&list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS&index=39) |
