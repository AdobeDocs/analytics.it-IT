---
description: nulle
keywords: Implementazione di Analytics
seo-description: nulle
seo-title: Implementare rinunce Adobe
solution: Analytics
title: Implementare rinunce Adobe
topic: Sviluppatore e implementazione
uuid: fc3a411c-8476-409d-99de-05b34ace5019
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Implementare rinunce Adobe

Alcuni visitatori del tuo sito Web potrebbero preferire che le loro informazioni di navigazione non siano aggregate e analizzate dai prodotti e dai servizi Adobe Experience Cloud o utilizzate per fornire contenuti e pubblicità rilevanti. Adobe offre agli utenti la possibilità di fornire ai visitatori del sito Web un mezzo per rinunciare alla raccolta delle informazioni da parte dei seguenti prodotti Adobe:

* Adobe Analytics
* Adobe Target
* Adobe Audience Targeting Creative
* Adobe AudienceManager
* Adobe AdLens
* Adobe Experience Manager

## Raccomandazioni sulla privacy {#section_BBDEE21C259842F7881642E31FB3D9B7}

Adobe consiglia di fornire ai visitatori del sito Web informazioni facili da trovare e di facile comprensione sulla possibilità di scegliere di non utilizzare le informazioni di navigazione raccolte da prodotti o servizi Adobe.

I visitatori possono scoprire come Adobe utilizza generalmente le informazioni raccolte in relazione alla fornitura di prodotti e servizi ai clienti tramite l' [Adobe Privacy Center](https://www.adobe.com/privacy.html). Tuttavia, poiché controlli esclusivamente come implementare i nostri servizi sui tuoi siti Web, spetta a te descrivere ai visitatori del tuo sito web i modi specifici in cui utilizzano i nostri prodotti e servizi. L'Utente è responsabile della creazione della propria informativa sulla privacy, del rispetto della propria informativa sulla privacy, del rispetto del contratto di servizio con Adobe e del rispetto di tutte le leggi applicabili.

## Rifiuti per Adobe Analytics (inclusi Reporting e analisi, Data Warehouse e Analisi ad hoc) {#section_8089B80CDA4043C9BC2DED49E484E8D7}

Adobe offre tre tipi di optedout per Adobe Analytics (inclusi [!UICONTROL Reports & Analytics], [!UICONTROL Data Warehouse], [!UICONTROL Ad Hoc Analysis]):

* Se implementate i prodotti Adobe Analytics con un cookie di prima parte, dovete [sviluppare un collegamento](../../../implement/js-implementation/data-collection/opt-out-link.md#concept_C2C4F19811A445EF9E9BEAC709B568A9) di rinuncia personalizzato per i visitatori del sito Web.
* I clienti hanno la possibilità di abilitare l'opzione di rifiuto utilizzando le impostazioni dei cookie del browser. See [Enable privacy settings for browser cookies](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/browser_cookie_settings.html).

Indipendentemente dal meccanismo di rifiuto scelto, Adobe consiglia di descrivere chiaramente la disponibilità del meccanismo di rifiuto nell'informativa sulla privacy o come altrimenti richiesto dalla legge o consigliato in base alle best practice correnti.
