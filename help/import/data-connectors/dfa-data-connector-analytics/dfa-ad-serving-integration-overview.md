---
description: 'In questa integrazione sono disponibili diversi modi per acquisire dati sul visitatore basato su annunci. La prima modalità consiste nel fare clic su un annuncio e in arrivo su una pagina di destinazione con tag, tramite un click-through '
keywords: DFA
seo-description: 'In questa integrazione sono disponibili diversi modi per acquisire dati sul visitatore basato su annunci. La prima modalità consiste nel fare clic su un annuncio e in arrivo su una pagina di destinazione con tag, tramite un click-through '
seo-title: Panoramica sull'integrazione di annunci pubblicitari
solution: Analytics
title: Panoramica sull'integrazione di annunci pubblicitari
topic: Connettori dati
uuid: e 286 f 61 e -4 b 09-48 b 5-b 1 e 9-3 c 07 b 6 face 24
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Panoramica sull'integrazione di annunci pubblicitari{#ad-serving-integration-overview}

In questa integrazione sono disponibili diversi modi per acquisire dati sul visitatore basato su annunci. Il primo metodo consiste nel fare clic su un annuncio e in arrivo su una pagina di destinazione con tag, tramite:

![](assets/Diagram1.png)

Il visitatore arriva sul sito di un editore, che ospita l'annuncio. Questo annuncio ha un identificatore univoco, denominato ID annuncio. Ads include un posizionamento più un Creative, che descrive dove si trova Ad si trova sul sito Editore e quale contenuto è stato mostrato al visitatore. Quando il visitatore recupera questa pubblicità, placement o creative dai server di contenuto DFA, tiene traccia di un'impression ai server DFA Floodlight per questo visitatore (1).

Se il visitatore fa clic sull'annuncio (2), viene interrogato il server Floodlight, che conta un clic, quindi 302 reindirizzerà il visitatore alla pagina di destinazione (3). Quando il visitatore arriva sulla pagina di destinazione, viene visualizzato un click-through. This page contains Adobe tracking code which query data from the DFA Floodlight Server.

Se il visitatore non arriva effettivamente sulla pagina di destinazione dopo aver tracciato un click, non viene visualizzato alcun click-through. Alcuni annunci e implementazioni potrebbero non far sì che il browser del visitatore abbia a che fare con il reindirizzamento 302. Per ulteriori discussioni su questo argomento, consultate [Riconciliazione delle discrepanze metriche](../dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies/dfa-reconciling-metric-discrepancies.md#concept-8c31ebe761ca4b3fab1e3a18ef5d098f).

La metrica successiva acquisita da questa integrazione si verifica quando il visitatore riceve l'impression ad impression, non fa clic, ma più tardi in futuro sulla pagina di destinazione in un altro mezzo.

![](assets/Viewthrough.png)

Questo scenario viene visualizzato come visualizzazione. La differenza in questo scenario con lo scenario click-through è che il visitatore non fa clic su Ad, ma continua ad altre attività prima di entrare nella pagina di destinazione (2). Nel caso più semplice, i tipi di visitatori nell'URL della pagina di destinazione nel browser. In altri casi, il visitatore continua a navigare, ma successivamente utilizza un motore di ricerca che porta il visitatore alla pagina di destinazione. In ogni caso, l'utente arriva alla pagina di destinazione.
