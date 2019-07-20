---
description: L'identificazione dei visitatori su più dispositivi consente di collegare i visitatori su più dispositivi. L'identificazione dei visitatori con più dispositivi utilizza la variabile ID visitatore, s. visitorid, per associare un utente ai diversi dispositivi.
keywords: Implementazione di Analytics
seo-description: L'identificazione dei visitatori su più dispositivi consente di collegare i visitatori su più dispositivi. L'identificazione dei visitatori con più dispositivi utilizza la variabile ID visitatore, s. visitorid, per associare un utente ai diversi dispositivi.
seo-title: Utenti Connect tra dispositivi
solution: Analytics
subtopic: Visitatori
title: Utenti Connect tra dispositivi
topic: Sviluppatore e implementazione
uuid: 6243957 b -5 cc 1-49 ef-aa 94-5 b 5 ec 4 eac 313
translation-type: tm+mt
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# Utenti Connect tra dispositivi

>[!IMPORTANT]
>
>Questo metodo di identificazione dei visitatori su dispositivi non è più consigliato. Please refer to the [Adobe Experience Cloud Device Co-op Documentation](https://marketing.adobe.com/resources/help/en_US/mcdc/).

L'identificazione dei visitatori su più dispositivi consente di collegare i visitatori su più dispositivi. L'identificazione dei visitatori con più dispositivi utilizza la variabile ID visitatore, s. visitorid, per associare un utente ai diversi dispositivi.

When you provide a [!UICONTROL visitor ID] variable with a hit, the system checks for any other visitor profiles that have a matching [!UICONTROL visitor ID]. Se ne esiste uno, il profilo visitatore già presente nel sistema viene usato da quel momento in poi e il profilo visitatore precedente non viene più utilizzato.

The [!UICONTROL visitor ID] is typically set after authentication, or after a visitor performs some other action that enables you to uniquely identify them independently of the device that is used. È consigliabile creare un hash del nome utente o un ID interno che non contenga informazioni personali identificabili.

In the [previous example](../../../implement/js-implementation/xdevice-visid/xdevice-connecting.md), after the customer signs on from each device, they are all associated with the same user profile. If the visitor later signs out on a device, stitching continues to work since the [!UICONTROL visitor ID]s that are stored in a cookie on each device are already associated with the same visitor profile. We recommend populating the [!UICONTROL s.visitorID] variable whenever possible in case the [!UICONTROL visitor ID] cookie is deleted.

## Unique Visitor and Visits Counts {#section_70330AB6724C4E419A4BD0BDD54641AC}

Considerate la seguente sequenza di connessione per due dispositivi:

![](assets/xdevice-counts.png)

**Sulla prima connessione dati**

* La deduplicazione del visitatore non è retroattiva.

After authentication on the laptop, hits with either visitor ID ( `nv1` or `cust1`) will be considered the same individual by Adobe Analytics. Tuttavia, la deduplicazione dei visitatori non è retroattiva, pertanto vengono conteggiati 2 visitatori unici.

Sulla prima connessione dati sul dispositivo mobile il cliente non viene riconosciuto, pertanto viene conteggiato un nuovo visitatore univoco. Once the user is authenticated ( `cust1`) on the mobile device, Adobe Analytics maps `cust1` back to the visitor ID provided on the main site, so no more unique visits are incremented.

Ogni nuovo dispositivo o browser autenticato aggiungerà 1 visitatori univoci.

**Connessioni dati successive**

Nelle successive connessioni dati a dispositivi autenticati i visitatori univoci non vengono incrementati.
