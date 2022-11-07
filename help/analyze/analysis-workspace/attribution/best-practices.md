---
title: Best practice di attribuzione
description: Quali sono le best practice per la scelta di un modello di attribuzione?
feature: Attribution
exl-id: 92c6039c-f950-4746-8b34-ba18be258c08
source-git-commit: ac9e4934cee0178fb00e4201cc3444d333a74052
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 100%

---

# Best practice di attribuzione

La scelta del modello di attribuzione corretto per l’organizzazione dipende da una serie di considerazioni. Questo articolo esplora una metodologia e alcune best practice generali.

## Passaggio 1: analisi esplorativa

>[!NOTE]
>Questa analisi deve essere eseguita prima di scegliere un modello di attribuzione.

Questa fase consiste inizialmente nel comprendere il comportamento del cliente e definire le metriche di conversione. In base alle metriche di conversione, strumenti come [Feed dati](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=it) (per dati non elaborati) o Analysis Workspace facilitano la comprensione di

* Quanti clienti toccano diversi canali di marketing prima della conversione?
* La proporzione/distribuzione di questi comportamenti.

Ad esempio, se il 50% dei clienti tocca 3 canali prima della conversione, esiste un’interazione tra questi 3 canali?
Per comprendere meglio la situazione, puoi quindi eseguire un’analisi upper funnel o lower funnel.

### Analisi upper funnel

L’analisi upper funnel esamina i canali utilizzati per creare awareness del brand o del prodotto. Ad esempio, la maggior parte degli annunci TV hanno come obiettivo la brand awareness. Con il passare del tempo, le persone si dimenticheranno del tuo annuncio TV, e potresti quindi usare il [modello di attribuzione Time decay (Decadimento temporale)](/help/analyze/analysis-workspace/attribution/models.md).

### Analisi lower funnel

In questa analisi, il presupposto è che le persone conoscano già il tuo marchio e che il tuo obiettivo sia la conversione. Utilizza notifiche e-mail o push o annunci Facebook.

## Passaggio 2: attribuzione basata su regole

Lo scopo di questo passaggio è quello di convalidare le tue ipotesi.

**Esempio 1**

Supponiamo che l’ipotesi sia “il primo canale di contatto ha un impatto maggiore sulla conversione rispetto all’ultimo”. Per testare questa ipotesi, utilizza il [modello di attribuzione “a J inversa”](/help/analyze/analysis-workspace/attribution/models.md). Questo modello attribuisce il 60% del credito al primo punto di contatto.

**Esempio 2**

L’ipotesi potrebbe essere: “nel nostro settore (ad es., viaggi), la finestra di attribuzione è 60 o 90 giorni, non 30 giorni, perché i clienti fanno molta ricerca prima di acquistare un prodotto”. Potresti quindi cambiare l’[intervallo di lookback](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html?lang=it#lookback-windows) impostandolo su 90 giorni.

## Passaggio 3: utilizzare l’attribuzione algoritmica

Poiché è molto difficile convalidare un numerose ipotesi e combinazioni possibili, puoi utilizzare l’[attribuzione algoritmica](/help/analyze/analysis-workspace/attribution/algorithmic.md) e lasciare che siano gli algoritmi incorporati a fare i calcoli necessari. Se hai già trovato il modello di attribuzione perfetto che risponde e si adatta a tutte le domande, allora ovviamente non devi fare questo passaggio.

## Altre considerazioni

* Potrebbe essere necessario avvalersi anche di un data scientist, invece di affidarsi solo ad Analysis Workspace.
* Puoi fare affidamento sui dati non elaborati, come nei feed di dati di Adobe.
* [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=it) potrebbe essere utile, ad esempio, se desideri considerare i dati relativi alle impression.
