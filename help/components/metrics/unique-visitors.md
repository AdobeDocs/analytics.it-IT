---
title: Visitatori univoci
description: Il numero di ID visitatore univoci.
feature: Metrics
exl-id: 56e7bad4-4802-49ac-a0f1-ae77441fc016
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 9%

---

# Visitatori univoci

La metrica &quot;Visitatori unici&quot; mostra il numero di ID visitatore per l’elemento dimensione. Si tratta di una delle metriche più comuni utilizzate per determinare il traffico, in quanto offre una panoramica di alto livello della popolarità di un elemento dimensionale. Ad esempio, un visitatore può visitare il tuo sito ogni giorno per un mese, ma continua a conteggiare come un singolo visitatore univoco.

Se utilizzi [Analisi multidispositivo](../cda/overview.md), questa metrica viene sostituita con la [Dispositivi univoci](unique-devices.md) metrica.

## Visitatori univoci giornalieri, settimanali, mensili, trimestrali e annuali

Reports &amp; Analytics offre opzioni per i visitatori univoci giornalieri, settimanali, mensili, trimestrali e annuali. Invece di contare un singolo visitatore univoco per l’intero periodo di tempo, i visitatori univoci contano in base alla metrica selezionata. Ad esempio, vuoi cercare i visitatori unici giornalieri del tuo sito. Se un visitatore accede al tuo sito la mattina e di nuovo di notte, lo considera come un singolo visitatore univoco giornaliero. Se un visitatore accede al sito il lunedì e il martedì, viene conteggiato come due visitatori unici giornalieri.

Analysis Workspace tratta i visitatori unici in base alla granularità del rapporto. Ad esempio, se utilizzi il [Giorno](../dimensions/day.md) vedrai visitatori univoci giornalieri per ogni elemento dimensione. Tuttavia, per il totale del rapporto, vengono deduplicati i visitatori univoci per l’intervallo di date della tabella a forma libera.

## Calcolo di questa metrica

Questa metrica conta il numero di ID visitatore univoci per un dato elemento dimensione. Utilizza più meccanismi avanzati per identificare i visitatori unici, in quanto esistono diversi modi per identificarli. Nella tabella seguente sono elencati i modi in cui un visitatore viene identificato insieme alla sua priorità. Alcuni hit possono avere più metodi di identificazione dei visitatori; in questi casi viene utilizzato il metodo di priorità più elevata.

| Ordine utilizzato | Parametro query (metodo di raccolta) | Presente quando |
| --- | --- | --- |
| 1 | `vid` | La [`visitorID`](/help/implement/vars/config-vars/visitorid.md) è impostata. |
| 2 | `aid` | Il visitatore ha un [`s_vi`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=it) cookie. Imposta sulle implementazioni senza o prima di implementare il servizio ID visitatore. |
| 3 | `mid` | Il visitatore ha un [`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html) cookie. Imposta sulle implementazioni tramite la [Servizio Adobe Experience Cloud Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it). |
| 4 | `fid` | Il visitatore ha un [`s_fid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html) cookie o se `aid` e `mid` non può essere impostato per alcun motivo. |
| 5 | Indirizzo IP, agente utente, indirizzo IP gateway | Ultima risorsa per identificare un visitatore univoco se il browser del visitatore non accetta i cookie. |

>[!NOTE]
>
>Ogni ID visitatore di Analytics è associato a un profilo sui server di Adobe. Questi profili dei visitatori vengono eliminati dopo almeno 13 mesi di inattività, a prescindere dalla scadenza del cookie ID visitatore.

## Comportamento che influisce sul conteggio di visitatori univoci

Gli identificatori visitatore univoci vengono generalmente memorizzati in un cookie del browser. Viene conteggiato un nuovo visitatore univoco se esegue una delle seguenti operazioni:

* Elimina la cache in qualsiasi momento
* Apre un browser diverso sullo stesso computer. Viene conteggiato un visitatore univoco per browser.
* La stessa persona che naviga sul tuo sito su diversi dispositivi. Un visitatore univoco separato viene conteggiato per dispositivo. È possibile utilizzare [Analisi multidispositivo](../cda/overview.md) per combinare i visitatori utilizzando [Persone](people.md) metrica.
* Apre una sessione di navigazione privata (ad esempio la scheda in incognito di Chrome).

Un nuovo visitatore univoco è *not* conteggiato, purché l’identificatore del cookie sia mantenuto:

* Chiude il browser per un periodo prolungato
* Aggiorna il browser alla versione più recente
