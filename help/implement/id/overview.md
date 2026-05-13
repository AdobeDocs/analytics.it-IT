---
title: Identificazione dei visitatori in Adobe Analytics
description: Scopri come identificare i visitatori in Adobe Analytics utilizzando le best practice più recenti.
exl-id: 8d26a556-84fe-4fb5-98d6-a16b69423e5b
TQID: https://experienceleague.adobe.com/uwEv9cl3234uiWhZEZLqgAVo42b-9L-9YEIGD97Pw-Q
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c8add8f2-4250-4fd9-9cde-9707036c567did: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 617
ht-degree: 12%

---

# Identificazione dei visitatori in Adobe Analytics

L’identificazione dei visitatori è fondamentale per il valore che Adobe Analytics fornisce per comprendere il comportamento degli utenti online. Comporta il collegamento di hit alla stessa persona nel tempo utilizzando un identificatore comune. Un’identificazione accurata dei visitatori garantisce metriche affidabili e supporta una strategia di implementazione efficace. Adobe consiglia alle organizzazioni di dare priorità ai servizi di identità moderni per garantire coerenza e integrità dei dati tra le piattaforme.

L’identificazione dei visitatori in Adobe Analytics è costituita dai seguenti componenti:

* Identificatore lato client: in genere memorizzato in un cookie di prime parti. Le implementazioni che si basano su cookie di terze parti sono meno coerenti con l’identificazione dei visitatori, a causa dei moderni standard di privacy del browser.
* Identificatore lato server: ogni ID visitatore di Analytics è associato a un profilo sui server di Adobe. Questi profili di visitatori sono ciò che consente la persistenza su variabili come [eVar](/help/components/dimensions/evar.md). I profili vengono eliminati dopo almeno 13 mesi di inattività, indipendentemente dalla scadenza del cookie ID visitatore.

## Ordine delle operazioni di identificazione Adobe Analytics

Quando Adobe riceve un hit, vengono eseguiti i seguenti controlli in ordine. Se è presente una determinata proprietà, Adobe utilizza tale identificatore per l’hit. Se in un hit sono presenti più identificatori, viene utilizzato solo il primo metodo. L’ordine delle operazioni non riflette l’ordine consigliato da Adobe per l’identificazione dei visitatori.

| Ordine utilizzato | Parametri query | Presente quando |
|---|---|---|
| **1<sup>st</sup>** | `vid` | La variabile [`visitorID`](/help/implement/vars/config-vars/visitorid.md) è impostata. |
| **2<sup>nd</sup>** | `aid` | Il visitatore ha un cookie [`s_vi`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics) esistente. Impostato sulle implementazioni senza o antecedenti all’implementazione del servizio ID visitatore. |
| **3<sup>rd</sup>** | `mid` | Il visitatore ha un cookie [`s_ecid`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics) esistente. Impostato sulle implementazioni tramite il servizio [Adobe Experience Cloud Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it). Adobe consiglia di utilizzare il servizio ID per tutte le implementazioni, ove possibile. |
| **4<sup>th</sup>** | `fid` | Il visitatore ha un cookie [`s_fid`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics) esistente. AppMeasurement genera automaticamente un ID di fallback se `aid` e `mid` non possono essere impostati per alcun motivo. |
| **5<sup>th</sup>** | Indirizzo IP + agente utente | Utilizzato come ultima risorsa per identificare un visitatore univoco se il browser del visitatore non accetta i cookie. Un ID visitatore con hash viene generato prima dell&#39;[offuscamento dell&#39;IP](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md). Se l&#39;indirizzo IP non è disponibile, vengono utilizzati altri dettagli IP (ad esempio l&#39;IP del gateway). |

L’ID visitatore selezionato viene quindi sottoposto a hashing e diventa il suo identificatore lato server. Questo identificatore lato server è disponibile come `visid_high` + `visid_low` in [Feed dati](/help/export/analytics-data-feed/data-feed-overview.md).

## Comportamento che influisce sul numero di visitatori univoci

Gli identificatori dei visitatori univoci vengono generalmente memorizzati in un cookie del browser. Un nuovo visitatore univoco viene conteggiato se esegue una delle seguenti azioni:

* Cancella i cookie in qualsiasi momento. Un visitatore univoco viene conteggiato per un hit dopo ogni volta che la sua cache viene cancellata.
* I cookie ID visitatore scadono a causa delle impostazioni di privacy del browser. Alcuni browser includono metodi di prevenzione del tracciamento che limitano la durata dei cookie.
* Apertura di un browser diverso sullo stesso computer. Viene conteggiato un visitatore univoco per browser.
* Apre una sessione di navigazione privata (come la scheda Incognito di Chrome). Viene conteggiato un visitatore univoco per sessione di navigazione dopo che tutte le schede sono state chiuse.
* Visita il tuo sito su diversi dispositivi. Viene conteggiato un visitatore univoco per dispositivo.
* Visita il tuo sito dopo più di 13 mesi di inattività.

È consigliabile utilizzare [Stitching](https://experienceleague.adobe.com/it/docs/analytics-platform/using/stitching/overview) in Customer Journey Analytics per identificare la stessa persona che utilizza più browser o dispositivi.

## Comportamento che non influisce sul conteggio di visitatori univoci

Un nuovo visitatore univoco è *non* conteggiato, purché l&#39;identificatore del visitatore sia mantenuto:

* Chiude il browser (per meno di 13 mesi)
* Aggiornamento del browser alla versione più recente
* Riavvia il computer
