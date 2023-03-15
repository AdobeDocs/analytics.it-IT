---
title: Serializzazione degli eventi
description: Aiuta a deduplicare le metriche sul tuo sito.
feature: Variables
exl-id: 54de0fd7-9056-44af-bd59-b8eb55fc816e
source-git-commit: 68389772dec0420a66767bb0af9dea3122e1cb0f
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 15%

---

# Serializzazione degli ID evento

La serializzazione degli eventi è il processo di implementazione delle misure per impedire che eventi duplicati vengano inseriti nei rapporti di Analytics. La deduplicazione degli eventi è importante nei casi in cui non si desidera che le metriche vengano gonfiate dai visitatori che aggiornano la pagina.

>[!NOTE]
>
>Origini dati non supporta la serializzazione degli eventi o la deduplicazione.

## Impostare la serializzazione degli eventi

Devi prima impostare il [!UICONTROL Unique Event Recording] a [!UICONTROL Use Event ID] nelle impostazioni della suite di rapporti. Consulta [Eventi di successo](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) nella guida utente Admin.

Quando si utilizzano gli ID evento, la deduplicazione si verifica sui seguenti livelli:

* Ogni variabile utilizza una propria tabella per la deduplicazione. Ad esempio: `event1:ABC` e `event2:ABC` sono entrambi conteggiati nella generazione rapporti.
* La deduplicazione avviene a livello globale per tutti i visitatori. Se il visitatore A invia `event1:ABC` quindi invia anche il visitatore B `event1:ABC`, Adobe ignora la seconda istanza dal visitatore B.
* La deduplicazione non scade. Se un visitatore invia `event1:ABC` quindi ritorna 2 anni dopo e invia `event1:ABC` di nuovo, Adobe ignora la seconda istanza.

>[!TIP]
>
>Se si desidera deduplicare [`purchase`](event-purchase.md) evento, utilizza [`purchaseID`](../purchaseid.md) variabile.

## Utilizzare gli ID evento con Web SDK

La serializzazione degli eventi è [mappato per Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=it) nel campo XDM dell’evento desiderato `id`. Il percorso XDM completo dipende dall’evento da serializzare.

Ad esempio, per serializzare la metrica Aggiunte carrello, imposta il `commerce.productListAdds.id` Campo XDM al valore di serializzazione desiderato. Se desideri serializzare l&#39;evento personalizzato 20, imposta `_experience.analytics.event1to100.event20` Campo XDM al valore di serializzazione desiderato.

## Utilizzare gli ID evento tramite l’estensione Adobe Analytics

Puoi impostare il campo ID evento sia durante la configurazione dell’estensione Analytics (variabili globali) sia come azione in una regola.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata (o crea una regola).
4. Nella sezione [!UICONTROL Actions], fai clic su un’azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull’icona “+”.
5. Scegli Adobe Analytics nel menu a discesa [!UICONTROL Extension] e imposta [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individua il [!UICONTROL Events] sezione, in cui ogni evento contiene un [!UICONTROL Event ID] campo.

I valori validi sono caratteri alfanumerici della lunghezza massima di 20 byte. Se si immette un valore più lungo di 20 byte, il sistema lo troncerà ai primi 20 byte.

## Utilizzare gli ID evento in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La serializzazione degli eventi fa parte del `s.events` variabile. Assegna un ID a ogni evento utilizzando i due punti nella stringa.

```js
// Assign custom ID serialization to a single value
s.events = "event1:ABC123";

// Assign custom ID serialization to multiple values
s.events = "event1:ABC123,event2:ABC123";
```

Se la serializzazione di un evento è abilitata ma non contiene un ID di serializzazione, l’evento viene sempre conteggiato.
