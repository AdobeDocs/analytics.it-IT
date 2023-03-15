---
title: Best practice di attribuzione
description: Quali sono le best practice per la scelta di un modello di attribuzione?
feature: Attribution
exl-id: 92c6039c-f950-4746-8b34-ba18be258c08
source-git-commit: ce7f953b8f7f1f7d0616074454e4401937fcc0c7
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 59%

---

# Best practice di attribuzione

La scelta del modello di attribuzione corretto per l’organizzazione dipende da una serie di considerazioni. Questo articolo esplora una metodologia e alcune best practice generali.

## Passaggio 1: analisi esplorativa

>[!NOTE]
>Questa analisi deve essere eseguita prima di scegliere un modello di attribuzione.

Questa fase consiste inizialmente nel comprendere il comportamento del cliente e definire le metriche di conversione. In base alle metriche di conversione, strumenti come [Feed dati](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=it) (per dati non elaborati) o Analysis Workspace facilitano la comprensione di

* Il numero di clienti che toccano diversi canali di marketing prima della conversione
* La proporzione/distribuzione di questi comportamenti

Ad esempio, se il 50% dei clienti tocca 3 canali prima della conversione, esiste un’interazione tra questi 3 canali?
Per comprendere meglio la situazione, puoi quindi eseguire un’analisi upper funnel o lower funnel.

### Analisi upper funnel

I canali di analisi upper funnel vengono utilizzati per creare awareness del brand o del prodotto. Ad esempio, la maggior parte degli annunci TV hanno come obiettivo la brand awareness. Con il passare del tempo, le persone si dimenticheranno del tuo annuncio TV, e potresti quindi usare il [modello di attribuzione Time decay (Decadimento temporale)](/help/analyze/analysis-workspace/attribution/models.md).

### Analisi lower funnel

Nell’analisi lower funnel, il presupposto è che le persone conoscano già il tuo marchio e che desideri che vengano convertite. Utilizza e-mail, notifiche push o annunci Facebook.

## Passaggio 2: attribuzione basata su regole

Lo scopo di questo passaggio è quello di convalidare le tue ipotesi.

**Esempio 1**

Supponiamo che l’ipotesi sia: &quot;Il mio canale di primo contatto ha un impatto maggiore sulla conversione rispetto al mio canale di ultimo contatto&quot;.

In questo caso, puoi quindi utilizzare [Modello di attribuzione &quot;a J inversa&quot;](/help/analyze/analysis-workspace/attribution/models.md) per testare questa ipotesi. Questo modello attribuisce il 60% del credito al primo punto di contatto.

**Esempio 2**

Supponiamo che l’ipotesi sia: &quot;nel nostro settore (ad esempio, viaggi), la finestra di attribuzione è di 60 o 90 giorni, non di 30 giorni, perché i clienti fanno molta ricerca prima di acquistare un prodotto&quot;.

In questo caso, è necessario modificare [intervallo di lookback](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html?lang=it#lookback-windows) a 90 giorni.

## Passaggio 3: utilizzare l’attribuzione algoritmica

Se non disponi ancora di un modello di attribuzione che fornisca risposte soddisfacenti a tutte le domande, puoi utilizzare [attribuzione algoritmica](/help/analyze/analysis-workspace/attribution/algorithmic.md). Poiché è molto difficile convalidare un numero elevato di ipotesi e combinazioni possibili, l’attribuzione algoritmica utilizza algoritmi incorporati per allocare credito tra gli elementi dimensionali.

## Altre considerazioni

* Potrebbe essere necessario avvalersi anche di un data scientist, invece di affidarsi solo ad Analysis Workspace.
* Puoi fare affidamento sui dati non elaborati, come nei feed di dati di Adobe.
* [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=it) potrebbe essere utile, ad esempio, se desideri considerare i dati relativi alle impression.
