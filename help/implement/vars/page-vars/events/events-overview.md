---
title: events
description: Imposta la variabile degli eventi, che governa la maggior parte delle metriche sul sito.
feature: Variables
exl-id: 6ef99ee5-40c3-4ff2-a75d-c97f2e8ec1f8
source-git-commit: d252b0e99a7d38d171eab181718fa60780489652
workflow-type: tm+mt
source-wordcount: '803'
ht-degree: 7%

---

# events

I Dimension e le metriche sono componenti vitali per i rapporti. Il `events` La variabile è responsabile della raccolta dei dati di molte metriche sul sito. Gli eventi in genere incrementano [metriche](/help/components/metrics/overview.md) nei rapporti.

Prima di implementare gli eventi, accertati di crearli e configurarli in [Eventi di successo](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) nelle impostazioni della suite di rapporti. Se prevedi di utilizzare eventi personalizzati negli hit di tracciamento dei collegamenti, assicurati che [`linkTrackVars`](../../config-vars/linktrackvars.md) e [`linkTrackEvents`](../../config-vars/linktrackevents.md) sono impostati correttamente.

## Eventi che utilizzano il Web SDK

Gli eventi personalizzati sono [mappato per Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=it) nei seguenti campi XDM:

* Gli eventi personalizzati da 1 a 100 sono mappati su `_experience.analytics.event1to100.event1` - `_experience.analytics.event1to100.event100`.
* Gli eventi personalizzati 101-200 sono mappati su `_experience.analytics.event101to200.event100` - `_experience.analytics.event101to200.event200`.
* Questo modello si ripete ogni 100 eventi in `_experience.analytics.event901to1000.event901` - `_experience.analytics.event901to1000.event1000`. `eventx.value` viene utilizzato per specificare l&#39;importo da incrementare. `eventx.id` viene utilizzato per [serializzazione](event-serialization.md).
* Gli ordini sono mappati a `commerce.purchases.value`.
* Le unità sono mappate alla somma di tutte `productListItems[].quantity` campi.
* I ricavi vengono mappati sulla somma di tutti `productListItems[].priceTotal` campi.
* Le visualizzazioni del prodotto sono mappate a `commerce.productListViews.value`.
* I carrelli sono mappati su `commerce.productListOpens.value`.
* Le aggiunte al carrello sono mappate a `commerce.productListAdds.value`.
* Le rimozioni dal carrello sono mappate a `commerce.productListRemovals.value`.
* Le visualizzazioni del carrello sono mappate a `commerce.productListViews.value`.
* Pagamenti mappati a `commerce.checkouts.value`.

>[!NOTE]
>
>Se un evento è impostato in `productListItems` (ad esempio, `productListItems._experience.analytics.event1.value`) e tale evento non è ancora presente in questo campo, l&#39;evento viene aggiunto automaticamente a questo campo.

## Eventi che utilizzano l’estensione Adobe Analytics

Puoi impostare gli eventi sia durante la configurazione dell’estensione Analytics (variabili globali) sia nelle regole.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata (o crea una regola).
4. Nella sezione [!UICONTROL Actions], fai clic su un’azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull’icona “+”.
5. Imposta il [!UICONTROL Extension] in Adobe Analytics e nella sezione [!UICONTROL Action Type] a [!UICONTROL Set Variables].
6. Individua la sezione [!UICONTROL Events].

Sono disponibili diverse funzioni:

* Elenco a discesa che consente di selezionare l’evento da includere
* Campo di testo facoltativo per la serializzazione. Consulta [serializzazione degli eventi](event-serialization.md) per ulteriori informazioni.
* Campo di testo facoltativo per un valore evento. È possibile includere la valuta per gli eventi di valuta oppure un numero intero per gli eventi non di valuta per incrementarla più volte. Ad esempio, selezionando `event1` nell’elenco a discesa e includendo `10` in questo campo incrementa `event1` 10 nella generazione rapporti.
* Un pulsante per aggiungere un altro evento. Puoi aggiungere tutti gli eventi che desideri a una singola regola entro il motivo desiderato.

## s.events in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Il `s.events` variable è una stringa che contiene un elenco delimitato da virgole di eventi da includere nell’hit. La variabile consente fino a 64.000 byte, consentendo in modo efficace il numero di eventi necessario per un hit. I valori validi includono:

* `event1` - `event1000`: eventi personalizzati, impostati nel modo desiderato. Registra come utilizzi ogni evento nel [documento di progettazione della soluzione](../../../prepare/solution-design.md). Il numero di eventi disponibili dipende dal contratto Analytics della tua organizzazione. La maggior parte delle organizzazioni con contratti non legacy dispone di 1000 eventi personalizzati. Se non sai quanti eventi personalizzati sono disponibili, contatta il tuo account team di Adobi.
* `purchase`: incrementa il [&#39;Ordini&#39;](/help/components/metrics/orders.md) metrica per 1 e accetta i valori impostati nella `products` variabile da calcolare [&#39;Unità&#39;](/help/components/metrics/units.md) e [&#39;Entrate&#39;](/help/components/metrics/revenue.md). Consulta [evento di acquisto](event-purchase.md) per ulteriori informazioni.
* `prodView`: incrementa il [&#39;Visualizzazioni prodotto&#39;](/help/components/metrics/product-views.md) metrica.
* `scOpen`: incrementa il [&#39;Carrelli&#39;](/help/components/metrics/carts.md) metrica.
* `scAdd`: incrementa il [&quot;Aggiunte carrello&quot;](/help/components/metrics/cart-additions.md) metrica.
* `scRemove`: incrementa il [&#39;Rimozioni carrello&#39;](/help/components/metrics/cart-removals.md) metrica.
* `scView`: incrementa il [&#39;Visualizzazioni carrello&#39;](/help/components/metrics/cart-views.md) metrica.
* `scCheckout`: incrementa il [&#39;Pagamenti&#39;](/help/components/metrics/checkouts.md) metrica.

>[!NOTE]
>
>Questa variabile fa distinzione tra maiuscole e minuscole. Evita di capitalizzare in modo errato i valori dell’evento per garantire una raccolta accurata dei dati.

```js
// Set the events variable to a single value
s.events = "event1";

// Set the events variable to multiple values
s.events = "event1,event13,purchase";
```

### Incrementa gli eventi contatore più volte

Se necessario, puoi contare gli eventi personalizzati più di una volta. Assegna un numero intero all’evento desiderato all’interno della stringa. Per impostazione predefinita, gli eventi creati nelle impostazioni della suite di rapporti sono eventi contatore.

```js
// Count event1 ten times
s.events = "event1=10";

// Count event1 twice and event2 once
s.events = "event1=2,event2";
```

>[!NOTE]
>
>Gli eventi contatore non supportano valori di valuta o decimali. Utilizza eventi di valuta per la valuta oppure eventi numerici per i valori decimali.

### Usa eventi di valuta

È possibile modificare un evento personalizzato in modo che utilizzi la valuta anziché i numeri interi. Gli eventi di valuta vengono automaticamente convertiti nella valuta della suite di rapporti se quest’ultima e `currencyCode` non corrispondono. Sono utili per calcolare spese di spedizione, sconti o rimborsi. È possibile impostare gli eventi di valuta in `products` se desideri attribuire l’evento solo a tale prodotto.

Prima di implementare gli eventi di valuta, assicurati di impostare l’evento desiderato su &quot;Valuta&quot; in [Eventi di successo](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) nelle impostazioni della suite di rapporti.

```js
// Send $9.99 USD in event1 using the events variable. Make sure the event type for event1 is Currency in Report suite settings
s.currencyCode = "USD";
s.events = "event1=9.99";

// Send $9.99 USD in event1 using the products variable. Make sure the event type for event1 is Currency in Report suite settings
s.currencyCode = "USD";
s.events = "event1";
s.products = "Example category;Example product;1;0;event1=9.99";
```

>[!NOTE]
>
>Se si imposta un valore di valuta in entrambi i `events` variabile e `products` variabile, il valore della valuta in `events` viene utilizzato. Evita di impostare i valori di valuta in entrambi `events` e `products` variabili.

### Utilizzare eventi numerici

È possibile modificare un evento personalizzato per accettare valori decimali anziché interi. Gli eventi numerici si comportano in modo simile agli eventi di valuta, tranne per il fatto che non utilizzano la conversione di valuta. È possibile impostare eventi numerici in `products` se desideri attribuire l’evento solo a tale prodotto.

Prima di implementare eventi numerici, assicurati di impostare l’evento desiderato su &quot;Numerico&quot; in [Eventi di successo](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) nelle impostazioni della suite di rapporti.

```js
// Send 4.5 in event1 using the events variable. Make sure the event type for event1 is Numeric in Report suite settings
s.events = "event1=4.5";

// Send 4.5 in event1 using the products variable. Make sure the event type for event1 is Numeric in Report suite settings
s.events = "event1";
s.products = "Example category;Example product;1;0;event1=4.5";
```

>[!NOTE]
>
>Se si imposta un valore numerico in entrambi i `events` variabile e `products` variabile, il valore numerico in `events` viene utilizzato. Evita di impostare valori numerici in entrambi i `events` e `products` variabili.
