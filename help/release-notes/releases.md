---
description: Descrive la strategia di rilascio continuo di funzioni per Adobe Analytics
title: Rilasci di funzioni di Adobe Analytics
feature: Release Notes
exl-id: 1e403bef-4aab-4a9a-a358-62449ce801ff
TQID: https://experienceleague.adobe.com/gDUf5ZiM-DUiG52nlMIFMbXc4NPNTI7bLrugWGicjgI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 7d733a6375f6c6009563bc53f5a3ff090dbc48ed
workflow-type: tm+mt
source-wordcount: 393
ht-degree: 90%

---

# Rilasci di funzioni di Adobe Analytics

I rilasci di Adobe Analytics funzionano secondo un modello di distribuzione continua che consente un approccio più scalabile e graduale all’implementazione delle funzioni.

## Strategia di rilascio

[!UICONTROL Analysis Workspace] utilizza i flag di funzione (noti anche come “pulsanti di attivazione”) per controllare la visibilità delle nuove funzioni, consentendo test su scala controllati prima del rilascio completo. Questa strategia di rilascio include le seguenti fasi:

* **Test limitati**: un rilascio graduale inizia con il test da parte di utenti Adobe interni. Viene quindi reso disponibile a un piccolo gruppo di account cliente per garantire che la funzione soddisfi le loro esigenze e aspettative.

* **Inizio del rollout**: il rollout di un rilascio graduale inizia con la fase di test limitato. La versione viene quindi scalata dallo 0% al 100% di disponibilità ai clienti nel corso di un paio di mesi. Il rollout graduale avviene a livello dell&#39;organizzazione CX Enterprise, in modo che tutti gli utenti autorizzati all&#39;interno di un&#39;organizzazione ricevano la stessa esperienza.

* **Disponibilità generale (GA)**: la funzionalità è disponibile per il 100% delle organizzazioni CX Enterprise autorizzate e il rilascio è completo.

Con ogni rilascio di funzioni, la timeline dall’inizio del rollout a GA può variare. L’obiettivo è mantenere i rilasci brevi, in modo che una funzione sia in GA entro 2 mesi dall’inizio del rollout.

## Flag di funzioni

I flag di funzioni consentono di controllare la visibilità delle nuove funzioni durante la fase di rilascio. Adobe consiglia di aggiungere `app.launchdarkly.com` all’[elenco di indirizzi consentiti](/help/technotes/ip-addresses.md) del firewall, per garantire un’esperienza ottimale durante la fase di rilascio. Una volta che la versione definitiva viene rilasciata al pubblico, il flag viene rimosso.

Puoi visualizzare i flag di funzioni attivi in qualsiasi momento, da **Aiuto > Informazioni su Workspace > Flag di funzioni attivi**.

## Vantaggi

I rilasci graduali consentono ad Adobe di scalare meglio il processo di distribuzione del software e assicurano che le funzioni siano completamente consolidate prima della disponibilità generale. Consente inoltre di pubblicare le funzioni non appena sono disponibili, piuttosto che attenersi a un intervallo di rilascio mensile fisso.

## Domande frequenti

| Domanda | Risposta |
| --- | --- |
| Posso richiedere l’accesso anticipato a una funzione? | No. Non sarà concesso un accesso anticipato.<br>Se desideri testare concetti di Analytics in fase iniziale, ti invitiamo a provare [Adobe Analytics Labs](/help/analyze/labs.md) per fornire feedback sulle innovazioni leader del settore. |
| Questa strategia di rilascio influisce sull’accesso alle funzioni? | No. Una volta che una funzione raggiunge la fase GA, potrai accedervi se è inclusa nel tuo pacchetto Analytics.<br>Puoi visualizzare i dettagli del tuo pacchetto Analytics in [Feature Access Levels](/help/admin/tools/company/feature-access-levels.md) (Livelli di accesso alle funzioni). |
