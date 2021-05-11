---
title: Serializzazione degli eventi
description: Consente di deduplicare le metriche sul sito.
exl-id: 54de0fd7-9056-44af-bd59-b8eb55fc816e
translation-type: tm+mt
source-git-commit: 71581f49eb7ef13577a05c05daee737eeb9e6218
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# Serializzazione degli ID evento

La serializzazione degli eventi è il processo di implementazione delle misure per impedire l’inserimento di eventi duplicati nel reporting di Analytics. La deduplicazione degli eventi è importante nei casi in cui non desideri che le metriche vengano gonfiate dai visitatori che aggiornano la pagina.

>[!NOTE]
>
>Origini dati non supporta la serializzazione o la deduplicazione degli eventi.

## Imposta la serializzazione degli eventi

Devi innanzitutto impostare l’evento [!UICONTROL Unique Event Recording] su [!UICONTROL Use Event ID] nelle impostazioni della suite di rapporti. Consulta [Eventi di successo](/help/admin/admin/c-success-events/success-event.md) nella guida utente Admin.

Quando si utilizzano gli ID evento, la deduplicazione avviene ai seguenti livelli:

* Ogni variabile utilizza una propria tabella per la deduplicazione. Ad esempio, `event1:ABC` e `event2:ABC` vengono entrambi conteggiati nei rapporti.
* La deduplicazione avviene a livello globale per tutti i visitatori. Se il visitatore A invia `event1:ABC` e anche il visitatore B invia `event1:ABC`, Adobe ignora la seconda istanza dal visitatore B.
* La deduplicazione non scade. Se un visitatore invia `event1:ABC` , torna indietro di 2 anni e invia di nuovo `event1:ABC` , Adobe ignora la seconda istanza.

>[!TIP]
>
>Se desideri deduplicare l’evento [`purchase`](event-purchase.md), utilizza invece la variabile [`purchaseID`](../purchaseid.md) .

## Utilizzare gli ID evento in Adobe Experience Platform Launch

Puoi impostare il campo ID evento sia durante la configurazione dell&#39;estensione Analytics (variabili globali) sia come azione in una regola.

1. Accedi a [launch.adobe.com](https://launch.adobe.com) utilizzando le tue credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai alla scheda [!UICONTROL Rules] , quindi fai clic sulla regola desiderata (o crea una regola).
4. In [!UICONTROL Actions], fai clic su un&#39;azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull&#39;icona &quot;+&quot;.
5. Imposta il menu a discesa [!UICONTROL Extension] su Adobe Analytics e [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individua la sezione [!UICONTROL Events], in cui ogni evento contiene un campo [!UICONTROL Event ID] .

I valori validi sono caratteri alfanumerici di lunghezza massima di 20 byte. Se si immette un valore superiore a 20 byte, il sistema lo troncherà ai primi 20 byte.

## Utilizzare gli ID evento nell’editor di codice personalizzato AppMeasurement e Launch

La serializzazione degli eventi fa parte della variabile `s.events` . Assegna un ID a ogni evento utilizzando due punti nella stringa.

```js
// Assign custom ID serialization to a single value
s.events = "event1:ABC123";

// Assign custom ID serialization to multiple values
s.events = "event1:ABC123,event2:ABC123";
```

Se la serializzazione di un evento è abilitata ma non contiene un ID di serializzazione, l’evento viene sempre conteggiato.
