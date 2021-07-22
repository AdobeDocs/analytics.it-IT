---
title: Implementazione con i tag in Adobe Experience Platform
description: Scopri come implementare Adobe Analytics utilizzando i tag
exl-id: 52990731-8a68-4779-ad42-6ec94b0aabd1
source-git-commit: 5368e808a862a3e320f5d079433db96ab79b45c8
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 4%

---

# Implementazione con i tag in Adobe Experience Platform

>[!NOTE]
>Adobe Experience Platform Launch è stato riclassificato come una suite di tecnologie di raccolta dati nell’Experience Platform. Di conseguenza, sono state introdotte diverse modifiche terminologiche nella documentazione del prodotto. Consulta questo [documento](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en) come riferimento consolidato delle modifiche terminologiche.

Nel corso della vita di Adobe Analytics, Adobe ha offerto diversi metodi per implementare il codice sul sito per la raccolta dei dati. Il metodo attualmente consigliato da Adobe è tramite i tag in Adobe Experience Platform.

I tag in Adobe Experience Platform è una soluzione di gestione tag che consente di distribuire il codice Analytics insieme ad altri requisiti di assegnazione tag. Adobe offre integrazioni con altre soluzioni e prodotti e consente di distribuire codice personalizzato. Tutte queste attività possono essere eseguite senza affidarsi ad alcun team di sviluppo dell’organizzazione per aggiornare il codice sul sito.

Tutti i clienti con un contratto Adobe Experience Cloud attivo possono utilizzare i tag . Se non sei sicuro di avere accesso, contatta uno degli amministratori di sistema di Experience Cloud della tua organizzazione.

## Flusso di lavoro globale

Per ottenere un&#39;implementazione in esecuzione utilizzando i tag, procedi come segue:

1. **Accedere ai tag**: Puoi ottenere l’accesso ai tag Platform tramite un amministratore di sistema nella tua organizzazione.
2. **Creare una proprietà** tag: Le proprietà sono contenitori sovrapposti utilizzati per fare riferimento ai dati di gestione dei tag.
3. **Distribuire in un ambiente** di sviluppo: Avere un ambiente in cui è possibile eseguire iterazioni sullo sviluppo dei tag.
4. **Convalida e pubblicazione in produzione**: Assicurati che tutto funzioni, quindi pubblicalo in diretta.

Per iniziare, consulta [Creare una proprietà tag di Analytics](create-analytics-property.md) .

## Risorse aggiuntive

I tag possono essere altamente personalizzati. Ulteriori informazioni su come ottenere il massimo da Adobe Analytics includendo i dati giusti nella tua implementazione.

* [Documentazione](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=en#) sui tag: Scopri come funziona l’interfaccia e quali estensioni sono disponibili.
* [Estensione](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=en) Adobe Analytics: Utilizza l’estensione Analytics per inviare dati ad Adobe Analytics.
* [Variabili](../vars/overview.md) di implementazione: Determina le variabili che desideri inviare ai server di raccolta dati.
