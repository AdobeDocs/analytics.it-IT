---
title: Identificazione dei visitatori tramite l’estensione tag Adobe Analytics
description: Identifica correttamente i visitatori quando implementi l’estensione tag Adobe Analytics.
exl-id: de534c69-0f43-45eb-86da-20d3cd3f363d
TQID: https://experienceleague.adobe.com/bdm2phkscnH9bSiQqK9K--ySTLguGaf-WLgEc3TL6H8
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 9e2c89f4188c723b4623a6e7859b74ede15e155b
workflow-type: tm+mt
source-wordcount: 469
ht-degree: 0%

---

# Identificazione dei visitatori tramite l’estensione tag Adobe Analytics

L’estensione tag Adobe Analytics fornisce consente di implementare AppMeasurement utilizzando un’interfaccia di gestione dei tag. Poiché questa estensione tag è essenzialmente AppMeasurement dal punto di vista tecnico, offre metodi simili per identificare i visitatori e richiede un’estensione tag separata per il servizio ID visitatore.

## Identificazione dei visitatori tramite il servizio ID visitatori (scelta consigliata)

Per utilizzare il servizio ID visitatori con l&#39;estensione tag Adobe Analytics, includi l&#39;estensione tag del servizio Experience Cloud ID nella proprietà tag.

1. Accedi a [Adobe CX Enterprise](https://experience.adobe.com) utilizzando le credenziali Adobe ID.
1. Passa a **[!UICONTROL Data Collection]** > **[!UICONTROL Tags]**.
1. Individua la proprietà tag desiderata.
1. Passa a **[!UICONTROL Extensions]**, quindi seleziona la scheda **[!UICONTROL Catalog]**.
1. Individua l&#39;estensione **[!UICONTROL Experience Cloud ID Service]**, quindi seleziona **[!UICONTROL Install]**.

L’estensione tag ottiene automaticamente il tuo ID organizzazione IMS, pertanto non è necessaria alcuna configurazione aggiuntiva.

## Identificazione dei visitatori tramite il cookie `s_vi` (scelta non consigliata)

>[!IMPORTANT]
>
>Adobe consiglia di non utilizzare questo metodo per identificare i visitatori.

Se la tua organizzazione non utilizza l’estensione tag del servizio Visitor ID, l’estensione tag Adobe Analytics utilizza la propria forma di identificazione dei visitatori. Quando un visitatore arriva al tuo sito per la prima volta, l&#39;estensione verifica la presenza di un cookie [`s_vi`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics). Questo cookie è impostato nel dominio corrispondente a **[!UICONTROL SSL Tracking Server]** (per HTTPS) o a **[!UICONTROL Tracking Server]** (per HTTP) durante la [configurazione dell&#39;estensione tag](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/analytics/overview).

* Se partecipi al [programma di certificazione gestito](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/adobe-managed-cert), il server di tracciamento sarà in genere un dominio di prime parti, rendendo `s_vi` cookie di prime parti.
* Se non partecipi al programma Managed Certificate, il server di tracciamento è in genere un sottodominio di `adobedc.net`, `omtrdc.net` o `2o7.net`, rendendo il cookie `s_vi` un cookie di terze parti. A causa dei moderni standard di privacy del browser, i cookie di terze parti vengono rifiutati dalla maggior parte dei browser. Una volta rifiutato, AppMeasurement tenta di impostare un cookie di fallback di prime parti (`fid`).

Se [!UICONTROL SSL Tracking Server] è impostato correttamente, non sono necessarie ulteriori misure di identificazione dei visitatori.

## Identificazione dei visitatori tramite `visitorID` (scelta non consigliata)

>[!IMPORTANT]
>
>Adobe consiglia di non utilizzare questo metodo per identificare i visitatori.

L&#39;utilizzo della variabile **[!UICONTROL Visitor ID]** consente all&#39;organizzazione di completare il controllo indipendente per identificare i visitatori. Se imposti [!UICONTROL Visitor ID] utilizzando un elemento dati, tieni presente le seguenti limitazioni:

* Ogni hit deve contenere lo stesso valore [!UICONTROL Visitor ID] per essere conteggiato come un singolo visitatore.
   * Gli hit che omettono l&#39;elemento dati [!UICONTROL Visitor ID] tentano automaticamente di utilizzare un altro metodo di identificazione visitatore, considerandoli come un visitatore separato.
   * Tutti gli hit che contengono un valore [!UICONTROL Visitor ID] diverso da un hit precedente vengono trattati come un visitatore separato.
   * Adobe non offre un modo per unire gli hit utilizzando ID visitatore diversi in Adobe Analytics.
* I tipi di pubblico condivisi, Analytics for Target e gli attributi del cliente non sono supportati con i visitatori identificati tramite [!UICONTROL Visitor ID].

Per le istruzioni di implementazione che utilizzano questa variabile, vedere [`visitorID`](/help/implement/vars/config-vars/visitorid.md).
