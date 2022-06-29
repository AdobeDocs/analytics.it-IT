---
title: Domande frequenti sulla migrazione ad Adobe Analytics
description: Risposte alle domande frequenti riguardanti il passaggio da una piattaforma di terze parti ad Adobe.
feature: Third-party Integration
exl-id: 1201909e-b20c-48c5-b287-393da8e22d78
source-git-commit: 1192a6a1e14e43aa2b434ac0b2675c73d249214a
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 58%

---

# Domande frequenti sulla migrazione ad Adobe Analytics

**Come posso eseguire la migrazione dei dati storici dalla piattaforma di terze parti ad Adobe Analytics?**

Ogni piattaforma Analytics offre diversi modi per raccogliere, gestire e archiviare i dati. Al posto della migrazione dei dati storici, Adobe consiglia di stabilire una data di interruzione precisa per iniziare a raccogliere e utilizzare i dati in Adobe Analytics. Le date di interruzione più frequenti sono l’inizio dell’anno fiscale, l’inizio dell’anno solare o l’inizio del mese. Se gli utenti desiderano visualizzare i dati storici, possono accedere alla piattaforma di terze parti per soddisfare eventuali esigenze specifiche di reporting storico.

Se l’organizzazione desidera che i dati storici vengano trasferiti ad Adobe, contatta il loro Account Manager. Un consulente per l’implementazione può collaborare con l’organizzazione per tradurre un’esportazione di dati Google Analytics in un’origine dati che può essere ingerita dai server di raccolta dati Adobe.

Per spostarsi sui dati storici consigliamo di utilizzare [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=it) che può importare qualsiasi origine dati omni-channel.

**Ho l’abitudine di usare in molti rapporti un elenco a discesa di segmentazione. Come posso ricrearlo in [!UICONTROL Analysis Workspace]?**

I filtri a discesa sono una funzione flessibile e affidabile in [!UICONTROL Analysis Workspace] consente di visualizzare un elenco a discesa di segmentazione. In un progetto Workspace:

1. Usa i comandi Ctrl-clic (Windows) o Cmd-clic (Mac) sui componenti che desideri includere nell’elenco a discesa. Oltre ai segmenti, puoi includere qualsiasi componente nei filtri a discesa.
2. Trascina il gruppo di componenti nella sezione di Workspace con l’etichetta “Drop a segment here” (Rilascia un segmento qui). Prima di rilasciare, tieni premuto Maiusc.

Utenti che accedono a questo [!UICONTROL Workspace] ora puoi utilizzare questo menu a discesa per applicare segmenti o altri componenti al progetto. Vedi [Panoramica dei pannelli](/help/analyze/analysis-workspace/c-panels/panels.md) nella guida Strumenti di Adobe Analytics per ulteriori informazioni.

**Ho l’abitudine di fare clic su un elemento di dimensione per visualizzare un drill-down. Come posso replicare questo flusso di lavoro agevole in Analysis Workspace?**

Dimension elementi in [!UICONTROL Analysis Workspace] dispongono anche di un flusso di lavoro di suddivisione semplice. Per accedervi, fai clic con il pulsante destro del mouse invece di scegliere il pulsante sinistro del mouse. Fai clic con il pulsante destro del mouse su un elemento di dimensione e fai clic su **[!UICONTROL Breakdown], quindi seleziona il componente desiderato. Puoi applicare lo stesso raggruppamento a più elementi dimensionali utilizzando i comandi Ctrl+clic (Windows) o Comando+clic (Mac) su ciascun valore.
