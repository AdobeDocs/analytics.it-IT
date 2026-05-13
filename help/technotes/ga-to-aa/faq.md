---
title: Domande frequenti sulla migrazione ad Adobe Analytics
description: Risposte alle domande frequenti riguardanti il passaggio da una piattaforma di terze parti ad Adobe.
feature: Third-party Integration
exl-id: 1201909e-b20c-48c5-b287-393da8e22d78
TQID: https://experienceleague.adobe.com/NJPnGHUG-9krAfzRZiNbMd7DS9q5gRGTm-1KM3DMXag
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: e38cbddc-1633-4cd5-bed5-9f289f2a6029
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 409
ht-degree: 54%

---

# Domande frequenti sulla migrazione ad Adobe Analytics

**Come posso eseguire la migrazione dei dati storici dalla piattaforma di terze parti ad Adobe Analytics?**

Ogni piattaforma Analytics offre diversi modi per raccogliere, gestire e archiviare i dati. Al posto della migrazione dei dati storici, Adobe consiglia di stabilire una data di interruzione precisa per iniziare a raccogliere e utilizzare i dati in Adobe Analytics. Le date di interruzione più frequenti sono l’inizio dell’anno fiscale, l’inizio dell’anno solare o l’inizio del mese. Se gli utenti desiderano visualizzare i dati storici, possono accedere alla piattaforma di terze parti per soddisfare eventuali esigenze specifiche di reporting storico.

Se la tua organizzazione desidera che i dati storici vengano trasferiti ad Adobe, contatta il team del tuo account Adobe. Un consulente per l’implementazione può collaborare con l’organizzazione per tradurre un’esportazione di dati Google Analytics in un’origine dati che può essere ingerita dai server di raccolta dati Adobe.

Per trasferire i dati storici, si consiglia di utilizzare [Customer Journey Analytics](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-overview) che può importare qualsiasi origine dati omni-channel.

**Ho l&#39;abitudine di usare in molti rapporti un elenco a discesa di segmentazione. Come è possibile ricrearlo in [!UICONTROL Analysis Workspace]?**

I filtri a discesa sono una funzionalità flessibile e affidabile in [!UICONTROL Analysis Workspace] che consente un elenco a discesa di segmentazione. In un progetto Workspace:

1. Utilizza ***ctrl***+***clic*** (Windows) o ***cmd***+***clic*** (Mac) sui componenti che desideri includere nel filtro a discesa. Non sei limitato a soli segmenti. Qualsiasi componente può essere incluso in un filtro a discesa.
2. Trascina il gruppo di componenti nell&#39;area di lavoro con l&#39;etichetta *Rilascia qui un segmento*. Prima di rilasciare, tieni premuto **[!UICONTROL shift]**.

Gli utenti che accedono a questo progetto [!UICONTROL Workspace] ora possono utilizzare questo filtro a discesa per applicare segmenti o altri componenti al progetto. Per ulteriori informazioni, consulta la [Panoramica dei pannelli](/help/analyze/analysis-workspace/c-panels/panels.md) nella guida Strumenti di Adobe Analytics.

**Ho l’abitudine di fare clic su un elemento di dimensione per visualizzare un approfondimento. Come posso replicare questo semplice flusso di lavoro in Analysis Workspace?**

Anche gli elementi Dimensione in [!UICONTROL Analysis Workspace] dispongono di un semplice flusso di lavoro basato su raggruppamenti. Accedi al raggruppamento utilizzando il menu di scelta rapida su un elemento dimensione. Quindi selezionare **[!UICONTROL Breakdown]** e il componente desiderato. Puoi applicare lo stesso raggruppamento a più elementi dimensionali utilizzando ***ctrl***+***seleziona*** (Windows) o ***cmd***+***seleziona*** (Mac) per ogni valore.
