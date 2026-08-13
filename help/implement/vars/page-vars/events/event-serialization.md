---
title: Serializzazione degli eventi
description: Aiuta a deduplicare le metriche sul tuo sito.
feature: Appmeasurement Implementation
exl-id: 54de0fd7-9056-44af-bd59-b8eb55fc816e
role: Admin, Developer
TQID: https://experienceleague.adobe.com/43YfbDVjSH7ZJ8kqlXwAnb8UsIEoG3Ei-NRnkLLW63Q
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 416
ht-degree: 10%

---

# Serializzazione degli ID evento

La serializzazione degli eventi è il processo di implementazione delle misure per impedire che eventi duplicati vengano inseriti nei rapporti di Analytics. La deduplicazione degli eventi è importante nei casi in cui non si desidera che le metriche vengano gonfiate dai visitatori che aggiornano la pagina.

>[!NOTE]
>
>Origini dati non supporta la serializzazione degli eventi o la deduplicazione.

## Impostare la serializzazione degli eventi

Devi prima impostare [!UICONTROL Unique Event Recording] di un evento su [!UICONTROL Use Event ID] nelle impostazioni della suite di rapporti. Vedi [Eventi di successo](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/c-success-events/success-event.md) nella guida utente dell&#39;amministratore.

Quando si utilizzano gli ID evento, la deduplicazione si verifica sui seguenti livelli:

* Ogni variabile utilizza una propria tabella per la deduplicazione. Ad esempio, `event1:ABC` e `event2:ABC` sono entrambi conteggiati nel reporting.
* La deduplicazione avviene a livello globale per tutti i visitatori. Se il visitatore A invia `event1:ABC` e poi il visitatore B invia anche `event1:ABC`, Adobe ignora la seconda istanza dal visitatore B.
* La deduplicazione non scade. Se un visitatore invia `event1:ABC` e poi ritorna 2 anni dopo, inviando nuovamente `event1:ABC`, Adobe ignora la seconda istanza.

>[!TIP]
>
>Per deduplicare l&#39;evento [`purchase`](event-purchase.md), utilizzare la variabile [`purchaseID`](../purchaseid.md).

## Utilizzare gli ID evento tramite Web SDK

Se si utilizza l&#39;[**oggetto XDM**](/help/implement/aep-edge/xdm-var-mapping.md), la serializzazione degli eventi utilizza il campo XDM dell&#39;evento desiderato `id`. Il percorso XDM completo dipende dall’evento da serializzare.

Ad esempio, se desideri serializzare la metrica Aggiunte al carrello, imposta `xdm.commerce.productListAdds.id` sul valore di serializzazione desiderato. Per serializzare l&#39;evento personalizzato 20, impostare `xdm._experience.analytics.event1to100.event20.id` sul valore di serializzazione desiderato.

Se si utilizza l&#39;[**oggetto dati**](/help/implement/aep-edge/data-var-mapping.md), la serializzazione degli eventi utilizza `data.__adobe.analytics.events`, seguendo la sintassi stringa di AppMeasurement.

## Utilizzare gli ID evento tramite l’estensione Adobe Analytics

Puoi impostare il campo ID evento sia durante la configurazione dell’estensione Analytics (variabili globali) sia come azione in una regola.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata (o crea una regola).
4. Nella sezione [!UICONTROL Actions], fai clic su un’azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull’icona “+”.
5. Impostare l&#39;elenco a discesa [!UICONTROL Extension] su Adobe Analytics e [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individuare la sezione [!UICONTROL Events], in cui ogni evento contiene un campo [!UICONTROL Event ID].

I valori validi sono caratteri alfanumerici della lunghezza massima di 20 byte. Se si immette un valore più lungo di 20 byte, il sistema lo troncerà ai primi 20 byte.

## Utilizzare gli ID evento in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La serializzazione degli eventi fa parte della variabile `s.events`. Assegna un ID a ogni evento utilizzando i due punti nella stringa.

```js
// Assign custom ID serialization to a single value
s.events = "event1:ABC123";

// Assign custom ID serialization to multiple values
s.events = "event1:ABC123,event2:ABC123";
```

Se la serializzazione di un evento è abilitata ma non contiene un ID di serializzazione, l’evento viene sempre conteggiato.
