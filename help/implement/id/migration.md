---
title: Considerazioni sulla migrazione al servizio ID visitatori per Adobe Analytics
description: Panoramica dell’interfaccia di Adobe Analytics con il servizio ID visitatori.
exl-id: da1f9917-5254-41fb-9e2c-c94f66a22360
TQID: https://experienceleague.adobe.com/NnZ-Vv2M5cWkfekbVX1B-dFesdtxy50fMdTlwPYviYQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: c8add8f2-4250-4fd9-9cde-9707036c567d
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 671
ht-degree: 0%

---

# Considerazioni sulla migrazione al servizio ID visitatori per Adobe Analytics

Se la tua organizzazione prevede di passare al servizio ID visitatori con un’implementazione di Analytics esistente, ci sono alcuni argomenti importanti da considerare. Queste considerazioni consentono di mantenere l&#39;integrità nell&#39;identificazione dei visitatori e di comprendere come funziona il servizio ID in presenza di un&#39;implementazione di Analytics esistente.

>[!TIP]
>
>Questa pagina si applica solo alle implementazioni di estensioni AppMeasurement o Analytics esistenti e consiste nell’aggiunta del servizio ID visitatore o nell’aggiornamento a un’implementazione Web SDK. In altre parole, l&#39;implementazione utilizza un ID Analytics legacy (`aid`) e sta per utilizzare un ID Experience Cloud (`mid`). Per impostazione predefinita, tutte le implementazioni di Web SDK utilizzano già un Experience Cloud ID (`mid`).

## Interfaccia del servizio ID visitatore con i cookie visitatore legacy di Analytics

Poiché AppMeasurement ha un proprio metodo per identificare i visitatori, alcuni visitatori potrebbero avere cookie legacy di Analytics quando un’organizzazione distribuisce il servizio ID visitatore. L’elenco seguente illustra come un visitatore viene identificato in diverse circostanze.

* **Nessun cookie visitatore presente**: il servizio ID assegna un Experience Cloud ID (`mid`).
* **Esiste un cookie `s_vi`**: il servizio ID scrive l&#39;ID legacy di Analytics esistente (`aid`) nel cookie `AMCV` oltre a un ID di Experience Cloud (`mid`). Poiché `aid` è più alto nell&#39;[Ordine delle operazioni](overview.md), l&#39;ID legacy di Analytics è l&#39;identificatore del visitatore fino alla scadenza o all&#39;eliminazione del cookie `AMCV`. Quando è abilitato un periodo di tolleranza, il servizio ID include nella risposta sia `mid` che `aid`.
* **Esiste un cookie di fallback**: il servizio ID non scrive il cookie di fallback (`fid`) nel cookie `AMCV`. Al contrario, i visitatori ricevono un Experience Cloud ID (`mid`) come se fossero un nuovo visitatore.

## Periodo di tolleranza per il servizio ID visitatore

Se hai più implementazioni che inviano dati alla stessa suite di rapporti e puoi implementare il servizio ID visitatore solo su alcune implementazioni, Adobe consiglia di configurare un periodo di tolleranza. Ad esempio, se la sezione di assistenza del sito è gestita da una soluzione di assegnazione tag separata, è possibile che il Servizio ID visitatore sia stato distribuito sul resto del sito prima della sezione di assistenza. Senza un periodo di tolleranza, i nuovi visitatori che visualizzano la sezione di supporto ricevono un ID visitatore Analytics legacy, facendo in modo che vengano conteggiati due visitatori separati. Con un periodo di tolleranza, il servizio ID visitatore emette sia un ID Experience Cloud (`mid`) che un ID visitatore Analytics legacy (`aid`) in modo che le aree del sito senza il servizio ID rimangano coerenti nell&#39;identificazione dei visitatori.

Se coordini la distribuzione del Servizio ID visitatore in tutte le aree del sito, non è necessario un periodo di tolleranza. Per configurare un periodo di tolleranza, contatta l&#39;[Assistenza clienti Adobe](https://helpx.adobe.com/it/marketing-cloud/contact-support.html). I periodi di tolleranza possono essere configurati per un massimo di 180 giorni e possono essere rinnovati. Adobe consiglia di interrompere il periodo di tolleranza una volta che l&#39;intera proprietà è configurata per l&#39;utilizzo del servizio ID.

## Tracciamento tra più domini

Alcune implementazioni legacy degli ID visitatore di Analytics potrebbero utilizzare &quot;cookie di terze parti descrittivi&quot;, in cui due domini condividono lo stesso cookie visitatore su un dominio comune come `data.example.com`. Poiché i cookie di terze parti descrittivi sono ancora cookie di terze parti, molti browser moderni li rifiutano, facendo in modo che Analytics si basi su un ID di fallback (`fid`) per l&#39;identificazione dei visitatori. Il passaggio al servizio ID consente a tutti i domini di impostare il cookie `AMCV` in un contesto di prime parti, aumentando la possibilità di mantenere un ID visitatore.

Il servizio ID visitatori tenta di impostare un cookie di terze parti per il monitoraggio tra più domini (il cookie [`demdex`](https://experienceleague.adobe.com/en/docs/id-service/using/intro/cookies)), ma viene spesso rifiutato dai browser moderni. Prendere in considerazione l&#39;utilizzo del metodo [`appendVisitorIDsTo`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/appendvisitorid) per passare l&#39;ID Experience Cloud di un visitatore (`mid`) tra i domini di cui si è proprietari.

## Tracciamento lato server

È possibile chiamare [`getMarketingCloudVisitorID`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/getmcvid) per ottenere l&#39;ID Experience Cloud (`mid`) e [`getAnalyticsVisitorID`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/getanalyticsvisitorid) per ottenere l&#39;ID Analytics legacy (`aid`). Adobe consiglia di controllare entrambi per preservare la logica di identificazione dei visitatori.
