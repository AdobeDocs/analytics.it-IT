---
description: Utilizzare segmenti rapidi in Analysis Workspace.
title: Segmenti rapidi
feature: Workspace Basics
role: User, Admin
source-git-commit: ef232d1227430bb2430ca1da09756f5dd5106b1f
workflow-type: tm+mt
source-wordcount: '716'
ht-degree: 1%

---


# Segmenti rapidi

Puoi creare segmenti rapidi all&#39;interno di un progetto per bypassare la complessità del generatore di segmenti [completo](/help/components/segmentation/segmentation-workflow/seg-build.md). Per un confronto tra le attività dei segmenti veloci e quelle dei segmenti elenco di componenti completi, visita [qui](/help/analyze/analysis-workspace/components/segments/t-freeform-project-segment.md). I segmenti rapidi consentono fino a 3 regole e non contengono contenitori nidificati o segmenti sequenziali.

>[!IMPORTANT]
> I segmenti rapidi sono attualmente in fase di test limitati e non sono ancora generalmente disponibili.

## Creare segmenti rapidi

In una tabella a forma libera, fai clic sull’icona del filtro+ nell’intestazione del pannello:

![](assets/quick-seg1.png)

| Impostazione | Descrizione |
| --- | --- |
| Nome | Il nome predefinito di un segmento è una combinazione delle regole nel segmento. È possibile rinominare il segmento. |
| Includi/escludi | Puoi includere o escludere componenti nella definizione del segmento, ma non entrambi. |
| Contenitore Hit/Visita/Visitatore | I segmenti rapidi includono un [contenitore di segmenti](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-overview.html?lang=en#section_AF2A28BE92474DB386AE85743C71B2D6) solo che consente di includere una dimensione/metrica/intervallo di date nel segmento (o escluderlo da). [!UICONTROL Visitor] contiene i dati generali specifici del visitatore per visite e visualizzazioni di pagina. Un contenitore [!UICONTROL Visit] consente di impostare regole per suddividere i dati del visitatore in base alle visite e un contenitore [!UICONTROL Hit] consente di suddividere le informazioni del visitatore in base alle singole visualizzazioni di pagina. Il contenitore predefinito è [!UICONTROL Hit]. |
| Componenti (Dimension/metrica/intervallo di date) | Definisci fino a 3 regole aggiungendo dimensioni e/o metriche dei componenti e/o intervalli di date. Ci sono 3 modi per trovare il componente giusto:<ul><li>Inizia a digitare e il generatore [!UICONTROL Quick Segment] trova automaticamente il componente appropriato.</li><li>Utilizza l’elenco a discesa per trovare il componente.</li><li>Trascina i componenti dalla barra a sinistra.</li></ul> |
| Operatore | Utilizza il menu a discesa per trovare gli operatori standard come `contains` e [!UICONTROL Distinct Count] . |
| Segno più (+) | Aggiungi un&#39;altra regola |
| E/O Qualificatori | Puoi aggiungere i qualificatori &quot;AND&quot; o &quot;OR&quot; alle regole, ma non puoi combinare &quot;AND&quot; e &quot;OR&quot; in una singola definizione di segmento. |
| Applica | Applica questo segmento al pannello. |
| Open builder | Apre il Generatore di segmenti. |
| Annulla | Annulla questo segmento rapido - non applicarlo. |
| Intervallo date | La convalida utilizza l&#39;intervallo di date del pannello per la ricerca dei dati. Tuttavia, qualsiasi intervallo di date applicato in un segmento rapido sostituisce l’intervallo di date del pannello nella parte superiore del pannello. |
| Anteprima (in alto a destra) | Ti consente di verificare se disponi di un segmento valido e la sua ampiezza. Rappresenta il raggruppamento del set di dati che si prevede di visualizzare quando si applica questo segmento. |

Ecco un esempio di segmento che combina dimensioni e metriche:

![](assets/quick-seg2.png)

Il segmento viene visualizzato nella parte superiore. Osserva la relativa barra laterale grigia, a differenza della barra laterale blu per i segmenti a livello di componente nella libreria dei segmenti a sinistra.

![](assets/quick-seg3.png)

## Modificare segmenti rapidi

1. Passa il puntatore del mouse sul segmento rapido e seleziona l’icona a forma di matita .
1. Modifica la definizione del segmento o il nome del segmento.

## Salvare segmenti rapidi

Puoi scegliere di salvare i segmenti rapidi nel generatore Segmenti rapidi o seguendo questi passaggi.

>[!IMPORTANT]
>Una volta salvato o applicato il segmento, non è più possibile modificarlo nel Generatore di segmenti rapidi, solo nel Generatore di segmenti regolare.

1. Passa il puntatore del mouse sul segmento rapido e seleziona l’icona Info (&quot;i&quot;).
1. Select **[!UICONTROL Save segment]**

   ![](assets/save-quick-seg.png)

1. Lascia il nome così com’è o rinomina il segmento.

   Torna a Workspace e osserva come il segmento ora ha una barra laterale blu. Questo indica che non è più possibile modificarlo o aprirlo nel Generatore di segmenti rapidi. E salvandolo, diventa parte dell&#39;elenco dei componenti.

   ![](assets/quick-seg4.png)

Dopo aver applicato il segmento, puoi scegliere di aggiungerlo all’elenco dei componenti del segmento e renderlo disponibile per tutti i tuoi progetti.

1. Passa il puntatore del mouse sul segmento salvato e seleziona l’icona a forma di matita .

1. Nella parte superiore del Generatore di segmenti, osserva questa finestra di dialogo:

   ![](assets/project-only.png)

1. Seleziona la casella di controllo accanto a **[!UICONTROL Make this segment available to all your projects and add it to your component list.]**
1. Fai clic su **[!UICONTROL Save]**.
1. Il segmento viene ora visualizzato nell’elenco dei componenti del segmento per tutti i progetti.
1. Puoi anche [condividere il segmento](/help/components/segmentation/segmentation-workflow/t-seg-share.md) con altre persone all&#39;interno della tua organizzazione.

## Cosa sono i segmenti solo per progetto?

I segmenti solo progetto sono segmenti rapidi o segmenti di progetto ad hoc Workspace. Quando li modifica/aprono nel generatore di segmenti, viene visualizzata la casella solo progetto. Se si applica un segmento rapido nel generatore ma non si seleziona la casella rendi disponibile, si tratta comunque di un segmento solo progetto, ma non può più essere aperto nel generatore QS. Se selezionano la casella e salvano, ora è un segmento dell’elenco di componenti.