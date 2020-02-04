---
title: Implementazione con la panoramica di Launch
description: Scopri come implementare Adobe Analytics tramite Adobe Experience Platform Launch
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# Implementazione con la panoramica di Launch

Nel corso della vita di Adobe Analytics, Adobe ha offerto diversi metodi per implementare il codice sul sito per la raccolta dei dati. Il metodo di raccomandazione corrente di Adobe è disponibile tramite Adobe Experience Platform Launch.

Launch è una soluzione di gestione tag che consente di distribuire il codice Analytics insieme ad altri requisiti di tag. Adobe offre integrazioni con altre soluzioni e prodotti e consente di distribuire codice personalizzato. Tutte queste attività possono essere eseguite senza affidarsi ad alcun team di sviluppo dell&#39;organizzazione per aggiornare il codice sul sito.

Tutti i clienti con un contratto Adobe Experience Cloud attivo possono utilizzare Launch. Se non sei sicuro di avere accesso, contatta uno degli amministratori di sistema Experience Cloud della tua organizzazione.

## Flusso di lavoro globale

Per ottenere un’implementazione in esecuzione con Launch, effettuate le seguenti operazioni:

1. **Accesso a Launch**: Puoi accedere a Launch tramite un amministratore di sistema della tua organizzazione.
2. **Creare una proprietà**: Le proprietà sono contenitori sovrapposti utilizzati per fare riferimento ai dati di gestione tag.
3. **Implementazione in un ambiente** di sviluppo: Avere un ambiente in cui poter iterare sullo sviluppo dei tag.
4. **Convalida e pubblicazione in produzione**: Accertatevi che tutto funzioni, quindi pubblicatelo dal vivo.

Per iniziare, vedi [Creare una proprietà Analytics in Adobe Experience Platform Launch](create-analytics-property.md) .

## Risorse aggiuntive

Il lancio può essere altamente personalizzato. Scopri come ottenere il massimo da Adobe Analytics inserendo i dati giusti nella tua implementazione.

* [Documentazione](https://docs.adobe.com/content/help/en/launch/using/overview.html)di avvio: Scopri come funziona l’interfaccia e quali estensioni sono disponibili.
* [Estensione](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html)Adobe Analytics: Utilizzate l&#39;estensione Analytics per inviare dati ad Adobe Analytics.
* [Variabili](../vars/overview.md)di implementazione: Determinare le variabili da inviare ai server di raccolta dati.
