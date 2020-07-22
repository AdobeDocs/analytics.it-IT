---
title: Visitatori unici
description: Numero di singoli (o dispositivi) univoci.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '563'
ht-degree: 10%

---


# Visitatori unici

La metrica &quot;Visitatori unici&quot; mostra il numero di ID visitatore per l’elemento dimensione. Si tratta di una delle metriche più comuni utilizzate per determinare il traffico, in quanto offre una panoramica di alto livello della popolarità di un elemento dimensione. Ad esempio, un visitatore può visitare il sito ogni giorno per un mese, ma continua a essere un singolo visitatore.

Se utilizzate l&#39;analisi [](../cda/overview.md)cross-device, questa metrica viene rinominata in &quot;Unique Devices&quot;.

## Visitatori unici giornalieri, settimanali, mensili, trimestrali e annuali

Reporting e  Analytics offre opzioni per i visitatori unici giornalieri, settimanali, mensili, trimestrali e annuali. Invece di contare un singolo visitatore univoco per l&#39;intero periodo di tempo, i visitatori univoci contano in base alla metrica selezionata. Ad esempio, potete osservare i visitatori unici giornalieri per il sito. Se un visitatore accede al sito al mattino e di nuovo di notte, viene considerato come un singolo visitatore al giorno. Se un visitatore accede al sito il lunedì e il martedì, viene conteggiato come due visitatori unici al giorno.

 Analysis Workspace gestisce i visitatori univoci in base alla granularità del rapporto. Ad esempio, se utilizzi la dimensione [Giorno](../dimensions/day.md) , vedrai visitatori unici giornalieri per ogni elemento dimensione. Tuttavia, per il totale del rapporto, vengono deduplicati visitatori univoci per l&#39;intervallo di date della tabella a forma libera.

## Modalità di calcolo di questa metrica

Questa metrica conta il numero di ID visitatore univoci per un dato elemento dimensione. Utilizza diversi meccanismi avanzati per identificare i visitatori univoci, in quanto esistono diversi modi per identificarli. Nella tabella seguente sono elencati i modi in cui un visitatore viene identificato, insieme alla sua priorità. Alcuni hit possono avere più metodi di identificazione dei visitatori; in questi casi viene utilizzato il metodo della priorità più alta.

| Ordine utilizzato | Parametro query (metodo di raccolta) | Presente quando |
| --- | --- | --- |
| 1 | `vid` | La [`visitorID`](/help/implement/vars/config-vars/visitorid.md) variabile è impostata. |
| 2 | `aid` | Il visitatore ha un [`s_vi`](https://docs.adobe.com/content/help/it-IT/core-services/interface/ec-cookies/cookies-analytics.html) cookie esistente. Configurati sulle implementazioni senza o prima di implementare il servizio Visitor ID. |
| 3 | `mid` | Il visitatore ha un [`s_ecid`](https://docs.adobe.com/content/help/it-IT/core-services/interface/ec-cookies/cookies-analytics.html) cookie esistente. Configurare le implementazioni tramite il servizio [](https://docs.adobe.com/content/help/it-IT/id-service/using/home.html)Adobe Experience Cloud Identity. |
| 4 | `fid` | Il visitatore ha un [`s_fid`](https://docs.adobe.com/content/help/it-IT/core-services/interface/ec-cookies/cookies-analytics.html) cookie esistente, oppure se `aid` e non `mid` è stato possibile impostarlo per nessun motivo. |
| 5 | Indirizzo IP, agente utente, indirizzo IP gateway | Ultimo ricorso per identificare un visitatore univoco se il browser del visitatore non accetta i cookie. |

>[!NOTE]
>
>Ogni ID visitatore Analytics  è associato a un profilo sui server Adobe. Questi profili dei visitatori vengono eliminati dopo almeno 13 mesi di inattività, indipendentemente dalla scadenza dei cookie dell’ID visitatore.

## Comportamento che influisce sul conteggio dei visitatori univoci

Gli identificatori visitatore univoci vengono generalmente memorizzati in un cookie del browser. Un nuovo visitatore univoco viene conteggiato se esegue una delle seguenti operazioni:

* Cancella la cache in qualsiasi momento
* Apre un altro browser sullo stesso computer. Un visitatore univoco viene conteggiato per browser.
* La stessa persona che naviga sul sito su diversi dispositivi. Un visitatore univoco separato viene conteggiato per dispositivo. Potete utilizzare l&#39;analisi [](../cda/overview.md) cross-device per combinare i visitatori utilizzando la metrica [Persone](people.md) .
* Apre una sessione di navigazione privata (ad esempio la scheda Incognito di Chrome).

Un nuovo visitatore univoco *non* viene conteggiato, purché sia mantenuto l’identificatore del cookie:

* Chiude il browser per un periodo prolungato
* Aggiorna il browser alla versione più recente
