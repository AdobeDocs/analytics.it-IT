---
title: Serializzazione degli eventi
description: Consente di deduplicare le metriche sul sito.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 1%

---


# Serializzazione ID evento

La serializzazione degli eventi è il processo di implementazione delle misure per impedire che gli eventi duplicati vengano immessi  rapporti Analytics. La deduplicazione degli eventi è importante nei casi in cui non si desidera che le metriche vengano ingrandite dai visitatori che aggiornano la pagina.

>[!NOTE]
>
>Origini dati non supporta la serializzazione o la deduplicazione degli eventi.

## Impostazione della serializzazione dell&#39;evento

È innanzitutto necessario impostare un evento [!UICONTROL Unique Event Recording] [!UICONTROL Use Event ID] nelle impostazioni della suite di rapporti. Consultate Eventi [di](/help/admin/admin/c-success-events/success-event.md) successo nella guida utente di amministrazione.

Quando si utilizzano gli ID evento, la deduplicazione avviene ai seguenti livelli:

* Ogni variabile utilizza una propria tabella per la deduplicazione. Ad esempio, `event1:ABC` e `event2:ABC` sono entrambi conteggiati nel reporting.
* La deduplicazione avviene a livello globale tra tutti i visitatori. Se il visitatore A invia `event1:ABC` `event1:ABC`e anche il visitatore B lo invia, Adobe ignora la seconda istanza dal visitatore B.
* La deduplicazione non scade. Se un visitatore invia `event1:ABC` quindi torna indietro di due anni e invia di nuovo `event1:ABC` l&#39;evento, Adobe ignora la seconda istanza.

>[!TIP]
>
>Per deduplicare l’ [`purchase`](event-purchase.md) evento, utilizzate invece la [`purchaseID`](../purchaseid.md) variabile.

## Usa ID evento in  lancio Adobe Experience Platform

Potete impostare il campo ID evento sia durante la configurazione dell&#39;estensione Analytics  (variabili globali), sia come azione in una regola.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Passate alla [!UICONTROL Rules] scheda, quindi fate clic sulla regola desiderata (o create una regola).
4. In [!UICONTROL Actions], fare clic su un&#39;azione esistente [!UICONTROL Adobe Analytics - Set Variables] o fare clic sull&#39;icona &quot;+&quot;.
5. Impostate il [!UICONTROL Extension] menu a discesa su Adobe  Analytics e [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individuate la sezione, in cui ogni evento contiene un [!UICONTROL Events] [!UICONTROL Event ID] campo.

I valori validi sono caratteri alfanumerici di lunghezza massima di 20 byte.

## Utilizzare gli ID evento in AppMeasurement e Launch editor di codice personalizzato

La serializzazione degli eventi fa parte della `s.events` variabile. Assegnate un ID a ogni evento utilizzando due punti nella stringa.

```js
// Assign custom ID serialization to a single value
s.events = "event1:ABC123";

// Assign custom ID serialization to multiple values
s.events = "event1:ABC123,event2:ABC123";
```

Se la serializzazione di un evento è abilitata ma non contiene un ID di serializzazione, l&#39;evento viene sempre conteggiato.
