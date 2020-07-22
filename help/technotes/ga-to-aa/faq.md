---
title: Domande frequenti
description: Risposte alle domande frequenti riguardanti il passaggio da una piattaforma di terze parti ad Adobe.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 68%

---


# Domande frequenti

**Come posso trasferire i miei dati storici dalla piattaforma di terze parti ad Adobe  Analytics?**

Ogni piattaforma Analytics offre diversi modi per raccogliere, gestire e archiviare i dati. Al posto della migrazione dei dati storici, Adobe consiglia di stabilire una data di interruzione precisa per iniziare a raccogliere e utilizzare i dati in Adobe Analytics. Le date di interruzione più frequenti sono l’inizio dell’anno fiscale, l’inizio dell’anno solare o l’inizio del mese. Se gli utenti desiderano visualizzare i dati storici, possono accedere alla piattaforma di terze parti per soddisfare eventuali esigenze specifiche di reporting storico.

Se l’organizzazione desidera che i dati storici vengano trasferiti ad Adobe, contatta il loro Account Manager. Un consulente per l’implementazione può collaborare con l’organizzazione per tradurre un’esportazione di dati Google Analytics in un’origine dati che può essere ingerita dai server di raccolta dati Adobe.

Adobe non consiglia di trasferire i dati storici, in quanto si tratta di un processo complesso ed eccessivamente costoso per l’organizzazione. Inoltre è impossibile trasferire direttamente ad Adobe l’identificazione dei visitatori, in quanto le informazioni sui visitatori vengono memorizzate in cookie e in formati diversi tra le piattaforme.

**Ho l’abitudine di usare in molti rapporti un elenco a discesa di segmentazione. How can I recreate that in[!UICONTROL Analysis Workspace]?**

Dropdown filters are a flexible and robust feature in [!UICONTROL Analysis Workspace] that allows a segmentation dropdown. In un progetto Workspace:

1. Usa i comandi Ctrl-clic (Windows) o Cmd-clic (Mac) sui componenti che desideri includere nell’elenco a discesa. Oltre ai segmenti, puoi includere qualsiasi componente nei filtri a discesa.
2. Trascina il gruppo di componenti nella sezione di Workspace con l’etichetta “Drop a segment here” (Rilascia un segmento qui). Prima di rilasciare, tieni premuto Maiusc.

Users accessing this [!UICONTROL Workspace] project can now use this dropdown to apply segments or other components to the project. See [Panels Overview](/help/analyze/analysis-workspace/c-panels/panels.md) in the Adobe Analytics Tools guide for more information.

**Sono abituato a fare clic su un elemento dimensione per visualizzare un&#39;espansione. Come posso replicare questo flusso di lavoro agevole in Analysis Workspace?**

Gli elementi dimensionali in [!UICONTROL Analysis Workspace] dispongono inoltre di un flusso di lavoro di suddivisione semplice. Per accedervi, fate clic con il pulsante destro del mouse invece di fare clic con il pulsante sinistro del mouse. Right-click on a dimension item, click **[!UICONTROL Breakdown], then select the desired component. Potete applicare la stessa suddivisione a più elementi dimensionali utilizzando Ctrl+clic (Windows) o Comando+clic (Mac) su ciascun valore.
