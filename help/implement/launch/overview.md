---
title: Panoramica sull’implementazione con Launch
description: Scopri come implementare Adobe Analytics utilizzando Adobe Experience Platform Launch
exl-id: 52990731-8a68-4779-ad42-6ec94b0aabd1
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 2%

---

# Panoramica sull’implementazione con Launch

Nel corso della vita di Adobe Analytics, Adobe ha offerto diversi metodi per implementare il codice sul sito per la raccolta dei dati. Il metodo attualmente consigliato da Adobe è tramite Adobe Experience Platform Launch.

Launch è una soluzione di gestione tag che consente di distribuire il codice Analytics insieme ad altri requisiti di assegnazione tag. Adobe offre integrazioni con altre soluzioni e prodotti e consente di distribuire codice personalizzato. Tutte queste attività possono essere eseguite senza affidarsi ad alcun team di sviluppo dell’organizzazione per aggiornare il codice sul sito.

Tutti i clienti con un contratto Adobe Experience Cloud attivo possono utilizzare Launch. Se non sei sicuro di avere accesso, contatta uno degli amministratori di sistema di Experience Cloud della tua organizzazione.

## Flusso di lavoro globale

Per ottenere un’implementazione in esecuzione con Launch, procedi come segue:

1. **Accedere a Launch**: Puoi ottenere l’accesso a Launch tramite un amministratore di sistema nella tua organizzazione.
2. **Crea una proprietà**: Le proprietà sono contenitori sovrapposti utilizzati per fare riferimento ai dati di gestione dei tag.
3. **Distribuire in un ambiente** di sviluppo: Avere un ambiente in cui è possibile eseguire iterazioni sullo sviluppo dei tag.
4. **Convalida e pubblicazione in produzione**: Assicurati che tutto funzioni, quindi pubblicalo in diretta.

Per iniziare, vedi [Creare una proprietà Analytics in Adobe Experience Platform Launch](create-analytics-property.md) .

## Risorse aggiuntive

Launch può essere altamente personalizzato. Ulteriori informazioni su come ottenere il massimo da Adobe Analytics includendo i dati giusti nella tua implementazione.

* [Documentazione](https://docs.adobe.com/content/help/it-IT/experience-cloud/user-guides/home.translate.html) di Launch: Scopri come funziona l’interfaccia e quali estensioni sono disponibili.
* [Estensione](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html) Adobe Analytics: Utilizza l’estensione Analytics per inviare dati ad Adobe Analytics.
* [Variabili](../vars/overview.md) di implementazione: Determina le variabili che desideri inviare ai server di raccolta dati.
