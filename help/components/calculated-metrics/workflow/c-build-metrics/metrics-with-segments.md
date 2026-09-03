---
description: Scopri come segmentare singole metriche per effettuare confronti di metriche all’interno della stessa visualizzazione.
title: Metriche segmentate
feature: Calculated Metrics
exl-id: 1e7e048b-9d90-49aa-adcc-15876c864e04
TQID: https://experienceleague.adobe.com/t1HtjinGP02YSBQk1Z95t6wIQ0OhuFb14GKfpd8Y9Eg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: a544b409-2610-410d-a842-474ac1d0d54e
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 456
ht-degree: 1%

---

# Metriche segmentate

Nel [Generatore di metriche calcolate](cm-build-metrics.md#definition-builder), puoi applicare segmenti all&#39;interno della definizione della metrica. L’applicazione di segmenti è utile se desideri utilizzare nell’analisi le metriche per un sottoinsieme di dati.

>[!NOTE]
>
>Le definizioni dei segmenti vengono aggiornate tramite il [Generatore di segmenti](/help/components/segmentation/segmentation-workflow/seg-build.md). Se apporti una modifica a un segmento, questo viene aggiornato automaticamente ovunque venga utilizzato, incluso se il segmento fa parte di una definizione di metrica calcolata.
>

Vuoi confrontare le metriche per i tedeschi che interagiscono con il tuo marchio con quelle di persone al di fuori della Germania. Quindi puoi rispondere a domande come:

1. Quante persone tedesche e internazionali visitano le [pagine più popolari](#popular-pages).
1. Quante persone tedesche e internazionali in [totale](#totals) hanno interagito online con il tuo marchio questo mese.
1. Quali sono le [percentuali](#percentages) di tedeschi e di persone internazionali che hanno visitato le tue pagine popolari?

Consulta le sezioni seguenti per illustrare come le metriche segmentate possono aiutarti a rispondere a queste domande. Se del caso, si fa riferimento alla documentazione più dettagliata.

## Pagine popolari

1. [Creare una metrica calcolata](../cm-workflow.md) da un progetto Workspace, denominato `Germany`.
1. Dall&#39;interno del [Generatore di metriche calcolate](cm-build-metrics.md), [crea un segmento](/help/components/segmentation/segmentation-workflow/seg-build.md), denominato `Germany`, che utilizza il campo Paesi.

   >[!TIP]
   >
   >Nel generatore di metriche calcolate, puoi creare un segmento direttamente utilizzando il pannello Componenti.
   >   

   Il segmento potrebbe essere simile a.

   ![Segmento Germania](assets/segment-germany.png)

1. Nel generatore di metriche calcolate, utilizza il segmento per aggiornare la metrica calcolata.

   ![Metrica calcolata - Germania](assets/germany-visits.png)

Ripeti i passaggi precedenti per la versione internazionale della metrica calcolata.

1. Creare una metrica calcolata dal progetto Workspace, denominata `Non Germany visits`.
1. Dall&#39;interno del generatore di metriche calcolate, creare un segmento, denominato `Not Germany`, che utilizza il campo Paese CRM dai dati del sistema di gestione delle relazioni con i clienti per determinare la provenienza di una persona.

   Il segmento dovrebbe essere simile a.

   ![Segmento Germania](assets/segment-not-germany.png)

1. Nel generatore di metriche calcolate, utilizza il segmento per aggiornare la metrica calcolata.

   ![Metrica calcolata - Germania](assets/non-germany-visits.png)


1. Crea un progetto in Analysis Workspace, dove puoi vedere le pagine visitate da visitatori tedeschi e non tedeschi.

   ![Visualizzazione della tabella a forma libera di Workspace che mostra le persone tedesche rispetto a quelle internazionali](assets/workspace-german-vs-international.png)


## Totali

1. Crea due nuove metriche calcolate basate sul totale complessivo. Aprire ciascuno dei segmenti creati in precedenza, rinominare il segmento, impostare **[!UICONTROL Metric type]** per **[!UICONTROL People]** su **[!UICONTROL Grand Total]** e utilizzare **[!UICONTROL Save As]** per salvare il segmento utilizzando il nuovo nome. Ad esempio:

   ![Metrica totale per la Germania](assets/calculated-metric-germany-total.png)

1. Aggiungi al progetto Workspace una nuova visualizzazione a forma libera che mostra il totale delle pagine per l’anno in corso.

   ![Visualizzazione della tabella a forma libera di Workspace con tedesco rispetto al totale internazionale](assets/workspace-german-vs-international-totals.png)


## Percentuali

1. Crea due nuove metriche calcolate che calcolano una percentuale dalle metriche calcolate create in precedenza.

   ![Visualizzazione della tabella a forma libera di Workspace che mostra la percentuale di tedesco rispetto al totale internazionale delle persone](assets/calculated-metric-germany-total-percentage.png)


1. Aggiorna il progetto Workspace.

   ![Visualizzazione della tabella a forma libera di Workspace con tedesco rispetto al totale internazionale](assets/workspace-german-vs-international-totals-percentage.png)

