---
description: L’identificazione dei visitatori tra dispositivi consente di collegare i visitatori tra più dispositivi. L’identificazione dei visitatori su più dispositivi utilizza la variabile ID visitatore, s.visitorID, per associare un utente a più dispositivi.
keywords: Implementazione di Analytics
seo-description: L’identificazione dei visitatori tra dispositivi consente di collegare i visitatori tra più dispositivi. L’identificazione dei visitatori su più dispositivi utilizza la variabile ID visitatore, s.visitorID, per associare un utente a più dispositivi.
seo-title: Connettere gli utenti tra i dispositivi
solution: Analytics
subtopic: Visitatori
title: Connettere gli utenti tra i dispositivi
topic: Sviluppatore e implementazione
uuid: 6243957b-5cc1-49ef-aa94-5b5ec4eac313
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Connettere gli utenti tra i dispositivi

>[!IMPORTANT]
>
>Questo metodo di identificazione dei visitatori tra dispositivi non è più consigliato. Fai riferimento alla documentazione [di](https://marketing.adobe.com/resources/help/en_US/mcdc/)Adobe Experience Cloud Device Co-op.

L’identificazione dei visitatori tra dispositivi consente di collegare i visitatori tra più dispositivi. L’identificazione dei visitatori su più dispositivi utilizza la variabile ID visitatore, s.visitorID, per associare un utente a più dispositivi.

Quando fornisci una [!UICONTROL visitor ID] variabile con un hit, il sistema verifica la presenza di qualsiasi altro profilo visitatore con una corrispondenza [!UICONTROL visitor ID]. Se ne esiste uno, il profilo visitatore già presente nel sistema viene utilizzato da quel momento in poi e il profilo visitatore precedente non viene più utilizzato.

In genere [!UICONTROL visitor ID] viene impostato dopo l’autenticazione, o dopo che un visitatore esegue altre azioni che consentono di identificarli in modo univoco indipendentemente dal dispositivo utilizzato. È consigliabile creare un hash del nome utente o un ID interno che non contenga alcuna informazione personale.

Nell'esempio [precedente](/help/implement/js-implementation/xdevice-visid/xdevice-connecting.md), dopo che il cliente ha effettuato l'accesso da ciascun dispositivo, tutti i componenti sono associati allo stesso profilo utente. Se il visitatore si disconnette successivamente su un dispositivo, l'unione continua a funzionare poiché [!UICONTROL visitor ID]gli elementi memorizzati in un cookie su ciascun dispositivo sono già associati allo stesso profilo visitatore. È consigliabile compilare la [!UICONTROL s.visitorID] variabile quando possibile nel caso in cui il [!UICONTROL visitor ID] cookie venga eliminato.

## Conteggio unico visitatori e visite {#section_70330AB6724C4E419A4BD0BDD54641AC}

Considerare la seguente sequenza di connessione per due dispositivi:

![](assets/xdevice-counts.png)

**Sulla prima connessione dati**

* La deduplicazione dei visitatori non è retroattiva.

Dopo l'autenticazione sul laptop, gli hit con ID visitatore ( `nv1` o `cust1`) saranno considerati come lo stesso individuo da Adobe Analytics. Tuttavia, la deduplicazione dei visitatori non è retroattiva, quindi vengono conteggiati due visitatori unici.

Sulla prima connessione dati sul dispositivo mobile, il cliente non viene riconosciuto, quindi viene conteggiato un nuovo visitatore univoco. Una volta che l'utente è autenticato ( `cust1`) sul dispositivo mobile, Adobe Analytics `cust1` torna all'ID visitatore fornito sul sito principale, per cui non vengono incrementate ulteriori visite univoche.

Ogni nuovo dispositivo o browser autenticato aggiungerà 1 visitatore univoco.

**Nelle successive connessioni dati**

Nelle successive connessioni dati a dispositivi autenticati, i visitatori univoci non vengono incrementati.
