---
title: Serializzazione degli eventi
description: Consente di deduplicare le metriche sul sito.
feature: Variables
exl-id: 54de0fd7-9056-44af-bd59-b8eb55fc816e
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '401'
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

## Utilizzare gli ID evento utilizzando l’SDK per web

La serializzazione degli eventi è [mappato per Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) nel campo XDM dell&#39;evento desiderato `id`. Il percorso XDM completo dipende dall’evento da serializzare.

Ad esempio, se desideri serializzare la metrica Aggiunte carrello, imposta la `commerce.productListAdds.id` Campo XDM al valore di serializzazione desiderato. Se desideri serializzare l&#39;evento personalizzato 20, imposta la variabile `_experience.analytics.event1to100.event20` Campo XDM al valore di serializzazione desiderato.

## Utilizzare gli ID evento utilizzando l’estensione Adobe Analytics

Puoi impostare il campo ID evento sia durante la configurazione dell&#39;estensione Analytics (variabili globali) sia come azione in una regola.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
2. Fai clic sulla proprietà tag desiderata.
3. Vai a [!UICONTROL Rules] , quindi fai clic sulla regola desiderata (o crea una regola).
4. Sotto [!UICONTROL Actions], fai clic su un [!UICONTROL Adobe Analytics - Set Variables] fare clic sull&#39;icona &quot;+&quot;.
5. Imposta la [!UICONTROL Extension] del menu a discesa Adobe Analytics e [!UICONTROL Action Type] a [!UICONTROL Set Variables].
6. Individua il [!UICONTROL Events] sezione , dove ogni evento contiene un [!UICONTROL Event ID] campo .

I valori validi sono caratteri alfanumerici di lunghezza massima di 20 byte. Se si immette un valore superiore a 20 byte, il sistema lo troncherà ai primi 20 byte.

## Utilizza gli ID evento in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La serializzazione degli eventi fa parte del `s.events` variabile. Assegna un ID a ogni evento utilizzando due punti nella stringa.

```js
// Assign custom ID serialization to a single value
s.events = "event1:ABC123";

// Assign custom ID serialization to multiple values
s.events = "event1:ABC123,event2:ABC123";
```

Se la serializzazione di un evento è abilitata ma non contiene un ID di serializzazione, l’evento viene sempre conteggiato.
