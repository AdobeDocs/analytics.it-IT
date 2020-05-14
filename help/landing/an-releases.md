---
description: Spiega la nuova strategia per il rilascio continuo di funzionalità per Adobe Analytics
title: Adobe Analytics - Strategia per il rilascio delle funzioni
translation-type: tm+mt
source-git-commit: 0b00405e9e27a427a85b0f4a0d970671ada4aa67
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 4%

---


# Adobe Analytics - Strategia per il rilascio delle funzioni

Precedentemente, le versioni delle funzioni di Adobe Analytics seguivano una pianificazione mensile fissa. A partire da aprile 2020, Adobe Analytics passa a un modello di distribuzione continua che consente un approccio più scalabile e graduale alla distribuzione delle funzionalità.

## Strategia di rilascio

[!UICONTROL Analysis Workspace] utilizza i flag di funzione (noti anche come &quot;interruttori&quot;) per controllare la visibilità delle nuove funzioni, consentendo test di scala controllati prima del rilascio completo. Questa strategia di rilascio include le seguenti fasi:

* **Rilascio alla produzione (RTP)**: Il codice viene rilasciato in produzione e la visibilità delle funzioni viene disattivata in Analysis Workspace. **Nota**: Al momento, la funzione potrebbe essere disponibile nell&#39;API Analytics 2.0.

* **Test** limitati: Una versione in fase inizia con il test da parte degli utenti Adobe interni. Il rilascio viene quindi ridimensionato dallo 0% al 100% di disponibilità nel corso di un paio di mesi. L&#39;implementazione graduale avviene a livello di organizzazione Experience Cloud, in modo che tutti gli utenti autorizzati in un&#39;organizzazione ricevano la stessa esperienza.

* **Disponibilità generale (GA)**: La funzione è disponibile al 100% delle organizzazioni Experience Cloud a cui si ha diritto e la release della funzione è completa.

Con ogni release di funzionalità, la timeline da RTP a GA può variare. L&#39;obiettivo è di mantenere le versioni brevi, in modo che entro 2 mesi dall&#39;inizio del rilascio (RTP), una funzione sarà in GA.

## Vantaggi

Le versioni in fasi consentono ad Adobe di ridimensionare meglio il processo di distribuzione del software e assicurano che le funzioni siano completamente indurite prima della disponibilità generale. Consente inoltre di pubblicare le funzionalità non appena disponibili, ma di aderire a una finestra di rilascio mensile fissa.

## Domande frequenti

| Domanda | Risposta |
|---|---|
| Posso richiedere l&#39;accesso anticipato a una funzione? | No. Non sarà concesso un accesso anticipato.<br>Se desideri testare i concetti di Analytics iniziali, ti invitiamo a provare [Adobe Analytics Labs](https://docs.adobe.com/content/help/it-IT/analytics/analyze/tech-previews/overview.html) per fornire feedback sulle nostre innovazioni leader di settore. |
| Questa strategia di rilascio influisce sull’accesso alle funzioni? | No. Una volta raggiunta una funzione GA, sarà possibile accedere alla funzione se inclusa nel pacchetto Analytics.<br>Puoi visualizzare i dettagli del pacchetto Analytics in [!UICONTROL Admin] > [!UICONTROL Company Settings] > Livelli [di accesso alle](https://docs.adobe.com/content/help/en/analytics/admin/company-settings/feature-access-levels.html)funzioni. |