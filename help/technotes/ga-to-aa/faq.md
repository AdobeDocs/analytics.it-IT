---
title: Domande frequenti sulla migrazione ad Adobe Analytics
description: Risposte alle domande frequenti riguardanti il passaggio da una piattaforma di terze parti ad Adobe.
feature: Third-party Integration
exl-id: 1201909e-b20c-48c5-b287-393da8e22d78
source-git-commit: 6de20d2fbbab6ded6c92f0c6f3536671f4b2ae46
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 73%

---

# Domande frequenti sulla migrazione ad Adobe Analytics

**Come posso eseguire la migrazione dei dati storici dalla piattaforma di terze parti ad Adobe Analytics?**

Ogni piattaforma Analytics offre diversi modi per raccogliere, gestire e archiviare i dati. Al posto della migrazione dei dati storici, Adobe consiglia di stabilire una data di interruzione precisa per iniziare a raccogliere e utilizzare i dati in Adobe Analytics. Le date di interruzione più frequenti sono l’inizio dell’anno fiscale, l’inizio dell’anno solare o l’inizio del mese. Se gli utenti desiderano visualizzare i dati storici, possono accedere alla piattaforma di terze parti per soddisfare eventuali esigenze specifiche di reporting storico.

Se la tua organizzazione desidera che i dati storici vengano trasferiti ad Adobe, contatta il team del tuo account Adobe. Un consulente per l’implementazione può collaborare con l’organizzazione per tradurre un’esportazione di dati Google Analytics in un’origine dati che può essere ingerita dai server di raccolta dati Adobe.

Per trasferire i dati storici consigliamo di utilizzare [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=it) che può acquisire qualsiasi origine dati omnicanale.

**Ho l&#39;abitudine di usare in molti rapporti un elenco a discesa di segmentazione. Come è possibile ricrearlo in [!UICONTROL Analysis Workspace]?**

I filtri a discesa sono una funzionalità flessibile e affidabile in [!UICONTROL Analysis Workspace] che consente un elenco a discesa di segmentazione. In un progetto Workspace:

1. Utilizza i comandi Ctrl-clic (Windows) o Comando-clic (Mac) sui componenti che desideri includere nel filtro a discesa. Non sei limitato a soli segmenti; qualsiasi componente può essere incluso in un filtro a discesa.
2. Trascina il gruppo di componenti nella sezione di Workspace con l’etichetta “Drop a segment here” (Rilascia un segmento qui). Prima di rilasciare, tieni premuto Maiusc.

Gli utenti che accedono a questo progetto [!UICONTROL Workspace] ora possono utilizzare questo filtro a discesa per applicare segmenti o altri componenti al progetto. Per ulteriori informazioni, consulta la [Panoramica dei pannelli](/help/analyze/analysis-workspace/c-panels/panels.md) nella guida Strumenti di Adobe Analytics.

**Ho l’abitudine di fare clic su un elemento di dimensione per visualizzare un approfondimento. Come posso replicare questo semplice flusso di lavoro in Analysis Workspace?**

Anche gli elementi Dimensione in [!UICONTROL Analysis Workspace] dispongono di un semplice flusso di lavoro basato su raggruppamenti. Per accedervi, fai clic con il pulsante destro del mouse invece che con il pulsante sinistro. Fai clic con il pulsante destro su un elemento di dimensione, fai clic su [!UICONTROL Breakdown] e seleziona il componente desiderato. Per applicare lo stesso raggruppamento a più elementi di dimensione, usa i comandi Ctrl-clic (Windows) o Comando-clic (Mac) su ciascun valore.
