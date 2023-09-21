---
title: Visitatori univoci
description: Il numero di ID visitatore univoci.
feature: Metrics
exl-id: 56e7bad4-4802-49ac-a0f1-ae77441fc016
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 11%

---

# Visitatori univoci

&quot;Visitatori univoci&quot; [metrica](overview.md) mostra il numero di ID visitatore per l’elemento dimensione. È una delle metriche più comuni utilizzate per determinare il traffico, in quanto offre una panoramica di alto livello della popolarità di un elemento dimensione. Ad esempio, un visitatore può visitare il tuo sito ogni giorno per un mese, ma continua a contare come un singolo visitatore univoco.

Se usa [Analisi cross-device](../cda/overview.md), questa metrica viene sostituita con [Dispositivi univoci](unique-devices.md) metrica.

## Visitatori univoci giornalieri, settimanali, mensili, trimestrali e annuali

Reports &amp; Analytics offre opzioni per visitatori univoci giornalieri, settimanali, mensili, trimestrali e annuali. Invece di contare un singolo visitatore univoco per l’intero periodo di tempo, i visitatori univoci vengono conteggiati in base alla metrica selezionata. Ad esempio, desideri esaminare i visitatori univoci giornalieri del tuo sito. Se un visitatore accede al tuo sito al mattino e di nuovo alla notte, viene conteggiato come un singolo visitatore univoco giornaliero. Se un visitatore accede al sito lunedì e di nuovo martedì, vengono conteggiati come due visitatori univoci giornalieri.

Analysis Workspace tratta i visitatori univoci in base alla granularità del rapporto. Ad esempio, se utilizzi il [Giorno](../dimensions/day.md) dimensione, vedrai visitatori univoci giornalieri per ogni elemento dimensione. Tuttavia, per il totale del rapporto, vengono deduplicati i visitatori univoci per l’intervallo di date della tabella a forma libera.

## Come è calcolata questa metrica

Questa metrica conta il numero di ID visitatore univoci per un dato elemento dimensione. Utilizza diversi meccanismi avanzati per identificare i visitatori univoci, in quanto esistono diversi modi per identificarli. Nella tabella seguente sono elencati i modi in cui un visitatore viene identificato e la sua priorità. Alcuni hit possono avere più metodi di identificazione dei visitatori; in questi casi viene utilizzato il metodo di priorità più elevata.

| Ordine utilizzato | Parametro query (metodo di raccolta) | Presente quando |
| --- | --- | --- |
| 1 | `vid` | Il [`visitorID`](/help/implement/vars/config-vars/visitorid.md) è impostata. |
| 2 | `aid` | Il visitatore ha un [`s_vi`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=it) cookie. Impostato sulle implementazioni senza o prima dell&#39;implementazione del servizio ID visitatore. |
| 3 | `mid` | Il visitatore ha un [`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=it) cookie. Impostato sulle implementazioni utilizzando [Servizio Adobe Experience Cloud Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it). |
| 4 | `fid` | Il visitatore ha un [`s_fid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=it) cookie, o se `aid` e `mid` impossibile impostare per qualsiasi motivo. |
| 5 | Indirizzo IP, agente utente, indirizzo IP gateway | Ultima risorsa per identificare un visitatore univoco se il browser del visitatore non accetta i cookie. |

>[!NOTE]
>
>Ogni ID visitatore di Analytics è associato a un profilo sui server di Adobe. Questi profili visitatore vengono eliminati dopo almeno 13 mesi di inattività, indipendentemente dalla scadenza del cookie ID visitatore.

## Comportamento che influisce sul conteggio di visitatori univoci

Gli identificatori univoci dei visitatori vengono generalmente memorizzati in un cookie del browser. Viene conteggiato un nuovo visitatore univoco se esegue una delle seguenti operazioni:

* Cancella la cache in qualsiasi momento
* Apre un browser diverso sullo stesso computer. Viene conteggiato un visitatore univoco per browser.
* naviga sul sito da dispositivi diversi. Un visitatore univoco separato viene conteggiato per dispositivo. È possibile utilizzare [Analisi cross-device](../cda/overview.md) per combinare i visitatori utilizzando [Persone](people.md) metrica.
* Apre una sessione di navigazione privata (come la scheda in incognito di Chrome).

Un nuovo visitatore univoco è *non* conteggiato, purché l’identificatore del cookie sia mantenuto:

* Chiude il browser per un periodo prolungato
* Aggiorna il browser alla versione più recente
