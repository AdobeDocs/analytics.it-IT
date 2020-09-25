---
description: Spiega la nuova strategia per il rilascio continuo di funzioni per Adobe Analytics
title: Rilasci di funzioni di Adobe Analytics
translation-type: tm+mt
source-git-commit: bbbe6dccfee81ae5111f295906aa3a23d68ad39e
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 79%

---


# Rilasci di funzioni di Adobe Analytics

Precedentemente, i rilasci delle funzioni di Adobe Analytics seguivano una pianificazione mensile fissa. A partire da aprile 2020,  Adobe Analytics è passato a un modello di distribuzione continua che consente un approccio più scalabile e graduale alla distribuzione delle funzionalità.

## Strategia di rilascio

[!UICONTROL Analysis Workspace] utilizza i flag di funzione (noti anche come “interruttori”) per controllare la visibilità delle nuove funzioni, consentendo test su scala controllati prima del rilascio completo. Questa strategia di rilascio include le seguenti fasi:

* **Rilascio in produzione (RTP, Release to Production)**: il codice viene rilasciato in produzione con la visibilità delle funzioni disattivata in Analysis Workspace. **Nota**: al momento dell’RTP, la funzione potrebbe essere disponibile nell’API Analytics 2.0.

* **Test limitati**: un rilascio graduale inizia con il test da parte degli utenti Adobe interni. Il rilascio viene quindi scalato dallo 0% al 100% di disponibilità nel corso di un paio di mesi. Il rollout graduale avviene a livello di organizzazione Experience Cloud, in modo che tutti gli utenti autorizzati in un’organizzazione ricevano la stessa esperienza.

* **Disponibilità generale (GA, General Availability)**: la funzione è disponibile per il 100% delle organizzazioni Experience Cloud autorizzate e il rilascio è completo.

Con ogni rilascio di funzioni, la timeline da RTP a GA può variare. L’obiettivo è mantenere i rilasci brevi, in modo che entro 2 mesi dall’inizio del rilascio (RTP) una funzione sarà in GA.

## Flag di funzione

I flag di funzione vengono utilizzati per controllare la visibilità delle nuove funzioni durante il rilascio.  Adobe consiglia di aggiungere app.launchdarkly.com al elenco Consentiti [](https://docs.adobe.com/content/help/en/analytics/technotes/ip-addresses.html) del firewall per un&#39;esperienza ottimale durante il rilascio. Subito dopo il raggiungimento di GA, la bandiera viene rimossa.

Potete visualizzare i contrassegni delle funzioni attive in qualsiasi momento in **Aiuto > Informazioni su Workspace > Contrassegni** delle funzioni attive.

## Vantaggi

I rilasci graduali consentono ad Adobe di scalare meglio il processo di distribuzione del software e assicurano che le funzioni siano completamente consolidate prima della disponibilità generale. Consente inoltre di pubblicare le funzioni non appena sono disponibili, piuttosto che attenersi a un intervallo di rilascio mensile fisso.

## Domande frequenti

| Domanda | Risposta |
|---|---|
| Posso richiedere l’accesso anticipato a una funzione? | No. Non sarà concesso un accesso anticipato.<br>Se desideri testare concetti di Analytics in fase iniziale, ti invitiamo a provare [Adobe Analytics Labs](https://docs.adobe.com/content/help/it-IT/analytics/analyze/tech-previews/overview.html) per fornire feedback sulle innovazioni leader del settore. |
| Questa strategia di rilascio influisce sull’accesso alle funzioni? | No. Una volta che una funzione raggiunge la fase GA, potrai accedervi se è inclusa nel tuo pacchetto Analytics.<br>Puoi visualizzare i dettagli del tuo pacchetto Analytics in [!UICONTROL Admin] > [!UICONTROL Company Settings] > [Feature Access Levels](https://docs.adobe.com/content/help/it-IT/analytics/admin/company-settings/feature-access-levels.html). |
