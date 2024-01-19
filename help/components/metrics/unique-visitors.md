---
title: Visitatori univoci
description: Il numero di ID visitatore univoci.
feature: Metrics
exl-id: 56e7bad4-4802-49ac-a0f1-ae77441fc016
source-git-commit: 93099d36a65ca2bf16fbd6342f01bfecdc8c798e
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 100%

---

# Visitatori univoci

La [metrica](overview.md) “Visitatori univoci” mostra il numero di ID visitatore per l’elemento dimensione. È una delle metriche più comuni utilizzate per determinare il traffico, in quanto offre una panoramica di alto livello della popolarità di un elemento dimensione. Ad esempio, un visitatore può visitare il tuo sito ogni giorno per un mese, ma continua a contare come un singolo visitatore univoco.

Se usi la funzione [Cross-Device Analytics](../cda/overview.md), questa metrica viene sostituita dalla metrica [Dispositivi univoci](unique-devices.md).

## Visitatori univoci orari, giornalieri, settimanali, mensili, trimestrali, annuali

Analysis Workspace tratta i visitatori univoci in base alla granularità del rapporto. Ad esempio, se utilizzi la dimensione [Giorno](../dimensions/day.md) , vedrai visitatori univoci giornalieri per ogni elemento dimensione. Tuttavia, per il totale del rapporto, vengono deduplicati i visitatori univoci per l’intervallo di date della tabella a forma libera.

## Come è calcolata questa metrica

Questa metrica conta il numero di ID visitatore univoci per un dato elemento dimensione. Utilizza diversi meccanismi avanzati per identificare i visitatori univoci, in quanto esistono diversi modi per identificarli. Nella tabella seguente sono elencati i modi in cui viene identificato un visitatore, e il relativo livello di priorità. Alcuni hit possono avere più metodi di identificazione dei visitatori; in questi casi viene utilizzato il metodo con priorità più elevata.

| Ordine utilizzato | Parametro query (metodo di raccolta) | Presente quando |
| --- | --- | --- |
| 1 | `vid` | La variabile [`visitorID`](/help/implement/vars/config-vars/visitorid.md) è impostata. |
| 2 | `aid` | Il visitatore ha un cookie [`s_vi`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=it) esistente. Impostato sulle implementazioni senza o antecedenti all’implementazione del servizio ID visitatore. |
| 3 | `mid` | Il visitatore ha un cookie [`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=it) esistente. Impostato sulle implementazioni tramite il [servizio Adobe Experience Cloud Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it). |
| 4 | `fid` | Il visitatore ha un cookie [`s_fid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=it) esistente, oppure per qualche ragione non è stato possibile impostare `aid` e `mid`. |
| 5 | Indirizzo IP, agente utente, indirizzo IP gateway | Ultima possibilità per identificare un visitatore univoco se il browser del visitatore non accetta i cookie. |

>[!NOTE]
>
>Ogni ID visitatore di Analytics è associato a un profilo sui server di Adobe. I profili dei visitatori vengono eliminati dopo almeno 13 mesi di inattività, a prescindere dalla scadenza del cookie ID visitatore.

## Comportamento che influisce sul numero di visitatori univoci

Gli identificatori dei visitatori univoci vengono generalmente memorizzati in un cookie del browser. Se il visitatore esegue una delle seguenti operazioni, viene conteggiato come nuovo visitatore univoco:

* Cancellazione della cache in qualsiasi momento
* Apertura di un browser diverso sullo stesso computer. Viene conteggiato un visitatore univoco per browser.
* Navigazione sul sito da dispositivi diversi. Per ogni dispositivo viene conteggiato un visitatore univoco distinto. È possibile utilizzare [Cross-Device Analytics](../cda/overview.md) per combinare i visitatori tramite la metrica [Persone](people.md).
* Apertura di una sessione di navigazione privata (come la scheda In incognito di Chrome).

Quande si verifica una delle seguenti operazioni, un visitatore *non* viene conteggiato come nuovo visitatore univoco, purché venga mantenuto l’identificatore del cookie:

* Chiusura del browser per un periodo prolungato
* Aggiornamento del browser alla versione più recente
