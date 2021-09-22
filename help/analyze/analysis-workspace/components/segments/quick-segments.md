---
description: Utilizzare segmenti rapidi in Analysis Workspace.
title: Segmenti rapidi
feature: Workspace Basics
role: User, Admin
source-git-commit: 31507092e659fa08a50e00f91bd36411e354cb21
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 0%

---


# Segmenti rapidi

Puoi creare segmenti rapidi all&#39;interno di un progetto per bypassare la complessità del generatore di segmenti [completo](/help/components/segmentation/segmentation-workflow/seg-build.md). Per un confronto tra le attività dei segmenti veloci e quelle dei segmenti a livello di componente completi, visita [qui](/help/analyze/analysis-workspace/components/segments/t-freeform-project-segment.md).

>[!IMPORTANT]
> I segmenti rapidi sono attualmente in fase di test limitati e non sono ancora generalmente disponibili.

## Creare segmenti rapidi

1. In una tabella a forma libera, fai clic sull’icona del filtro+ nell’intestazione del pannello:

   ![](assets/quick-seg1.png)

   Tieni presente che:

   - Esiste un solo contenitore di segmenti che consente di includere una dimensione/metrica/intervallo di date nel segmento (o escluderlo da).
   - Puoi impostare il contenitore a livello di Hit, Visita o Visitatore. Il valore predefinito è Hit.

1. Aggiungi una dimensione/metrica/intervallo di date in uno dei tre modi seguenti:

   - Inizia a digitare e il [!UICONTROL Quick Segment builder] trova automaticamente il componente appropriato.
   - Utilizza l’elenco a discesa per trovare il componente.
   - Trascina i componenti dalla barra a sinistra.

1. Specifica la prima regola, ad esempio `Page equals workspace`. Puoi avere fino a tre regole nelle definizioni di un segmento. Fai clic sul segno &quot;+&quot; per aggiungere un’altra regola. Puoi aggiungere i qualificatori &quot;AND&quot; o &quot;OR&quot; alle regole, ma non puoi combinare &quot;AND&quot; e &quot;OR&quot; in una singola definizione di segmento.

   Ecco un esempio di segmento che combina dimensioni e metriche:

   ![](assets/quick-seg2.png)

1. Fai clic su **[!UICONTROL Apply]** per applicare questo segmento al pannello.
Il segmento viene visualizzato nella parte superiore. Osserva la relativa barra laterale grigia, a differenza della barra laterale blu per i segmenti a livello di componente nella libreria dei segmenti a sinistra.

   ![](assets/quick-seg3.png)

## Modificare segmenti rapidi

1. Passa il puntatore del mouse sul segmento rapido e seleziona l’icona a forma di matita .
1. Modifica la definizione del segmento o il nome del segmento.

## Salvare segmenti rapidi

Puoi scegliere di salvare i segmenti rapidi seguendo questi passaggi.

>[!IMPORTANT]
>Una volta salvato il segmento, non sarà più possibile modificarlo nel Generatore di segmenti rapidi, solo nel Generatore di segmenti regolare.

1. Passa il puntatore del mouse sul segmento rapido e seleziona l’icona Info (&quot;i&quot;).
1. Select **[!UICONTROL Save segment]**

   ![](assets/save-quick-seg.png)

1. Lascia il nome così com’è o rinomina il segmento.

1. Torna a Workspace e osserva come il segmento ora ha una barra laterale blu che indica che fa parte della libreria dei componenti.

   ![](assets/quick-seg4.png)

## Rendere i segmenti disponibili per tutti i tuoi progetti

Dopo aver salvato il segmento, puoi scegliere di aggiungerlo all’elenco dei componenti del segmento e renderlo disponibile per tutti i tuoi progetti.

1. Passa il puntatore del mouse sul segmento salvato e seleziona l’icona a forma di matita .

1. Nella parte superiore del Generatore di segmenti, osserva questa finestra di dialogo:

   ![](assets/project-only.png)

1. Seleziona la casella di controllo accanto a **[!UICONTROL Make this segment available to all your projects and add it to your component list.]**
1. Fai clic su **[!UICONTROL Save]**.
1. Il segmento verrà ora visualizzato nell’elenco dei componenti del segmento per tutti i progetti.
1. Puoi anche [condividere il segmento](/help/components/segmentation/segmentation-workflow/t-seg-share.md).

## Trasforma un segmento rapido in un segmento ad hoc

1. Passa il puntatore del mouse sul segmento salvato e seleziona l’icona a forma di matita .

1. Nella parte superiore del Generatore di segmenti, fai clic su **[!UICONTROL Apply]**.

Per ulteriori informazioni sui segmenti ad hoc, visita [qui](/help/analyze/analysis-workspace/components/segments/ad-hoc-segments.md)
