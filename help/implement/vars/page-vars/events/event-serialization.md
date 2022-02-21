---
title: Serializzazione degli eventi
description: Consente di deduplicare le metriche sul sito.
feature: Variables
exl-id: 54de0fd7-9056-44af-bd59-b8eb55fc816e
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '321'
ht-degree: 0%

---

# Serializzazione degli ID evento

La serializzazione degli eventi è il processo di implementazione delle misure per impedire l’inserimento di eventi duplicati nel reporting di Analytics. La deduplicazione degli eventi è importante nei casi in cui non desideri che le metriche vengano gonfiate dai visitatori che aggiornano la pagina.

>[!NOTE]
>
>Origini dati non supporta la serializzazione o la deduplicazione degli eventi.

## Imposta la serializzazione degli eventi

È innanzitutto necessario impostare il valore di [!UICONTROL Unique Event Recording] a [!UICONTROL Use Event ID] nelle impostazioni della suite di rapporti. Vedi [Eventi di successo](/help/admin/admin/c-success-events/success-event.md) nella guida utente Admin.

Quando si utilizzano gli ID evento, la deduplicazione avviene ai seguenti livelli:

* Ogni variabile utilizza una propria tabella per la deduplicazione. Ad esempio: `event1:ABC` e `event2:ABC` sono entrambi conteggiati nel reporting.
* La deduplicazione avviene a livello globale per tutti i visitatori. Se il visitatore A invia `event1:ABC` poi il visitatore B invia anche `event1:ABC`, Adobe ignora la seconda istanza dal visitatore B.
* La deduplicazione non scade. Se un visitatore invia `event1:ABC` poi torna indietro 2 anni dopo e invia `event1:ABC` ancora una volta, l&#39;Adobe ignora la seconda istanza.

>[!TIP]
>
>Se desideri deduplicare il [`purchase`](event-purchase.md) , utilizza [`purchaseID`](../purchaseid.md) invece.

## Utilizzare gli ID evento utilizzando i tag in Adobe Experience Platform

Puoi impostare il campo ID evento sia durante la configurazione dell&#39;estensione Analytics (variabili globali) sia come azione in una regola.

1. Accedi a [Interfaccia utente per la raccolta dati](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai a [!UICONTROL Rules] , quindi fai clic sulla regola desiderata (o crea una regola).
4. Sotto [!UICONTROL Actions], fai clic su un [!UICONTROL Adobe Analytics - Set Variables] fare clic sull&#39;icona &quot;+&quot;.
5. Imposta la [!UICONTROL Extension] del menu a discesa Adobe Analytics e [!UICONTROL Action Type] a [!UICONTROL Set Variables].
6. Individua il [!UICONTROL Events] sezione , dove ogni evento contiene un [!UICONTROL Event ID] campo .

I valori validi sono caratteri alfanumerici di lunghezza massima di 20 byte. Se si immette un valore superiore a 20 byte, il sistema lo troncherà ai primi 20 byte.

## Utilizzare gli ID evento in AppMeasurement e nell’editor di codice personalizzato

La serializzazione degli eventi fa parte del `s.events` variabile. Assegna un ID a ogni evento utilizzando due punti nella stringa.

```js
// Assign custom ID serialization to a single value
s.events = "event1:ABC123";

// Assign custom ID serialization to multiple values
s.events = "event1:ABC123,event2:ABC123";
```

Se la serializzazione di un evento è abilitata ma non contiene un ID di serializzazione, l’evento viene sempre conteggiato.
