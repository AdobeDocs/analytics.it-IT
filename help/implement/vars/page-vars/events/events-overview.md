---
title: events
description: Imposta la variabile degli eventi, che regola la maggior parte delle metriche sul sito.
feature: Variables
exl-id: 6ef99ee5-40c3-4ff2-a75d-c97f2e8ec1f8
source-git-commit: 34ba0e09cd909951a777b0ad3da080958633f97e
workflow-type: tm+mt
source-wordcount: '797'
ht-degree: 8%

---

# events

I Dimension e le metriche sono componenti vitali per i rapporti. La `events` è responsabile della raccolta dati di molte metriche sul sito. Generalmente gli eventi si incrementano [metriche](/help/components/metrics/overview.md) nei rapporti.

Prima di implementare gli eventi, assicurati di crearli e configurarli in [Eventi di successo](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) nelle impostazioni della suite di rapporti. Se prevedi di utilizzare eventi personalizzati negli hit di tracciamento dei collegamenti, assicurati che [`linkTrackVars`](../../config-vars/linktrackvars.md) e [`linkTrackEvents`](../../config-vars/linktrackevents.md) sono impostati correttamente.

## Eventi che utilizzano l’SDK per web

Gli eventi personalizzati sono [mappato per Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=it) nei seguenti campi XDM:

* Gli eventi personalizzati 1-100 sono mappati su `_experience.analytics.event1to100.event1` - `_experience.analytics.event1to100.event100`.
* Gli eventi personalizzati 101-200 sono mappati su `_experience.analytics.event101to200.event100` - `_experience.analytics.event101to200.event200`.
* Questo modello ripete ogni 100 eventi in `_experience.analytics.event901to1000.event901` - `_experience.analytics.event901to1000.event1000`. `eventx.value` viene utilizzato per specificare la quantità da incrementare. `eventx.id` viene utilizzato per [serializzazione](event-serialization.md).
* Gli ordini sono mappati su `commerce.purchases.value`.
* Le unità sono mappate alla somma di tutte `productListItems[].quantity` campi.
* Le entrate sono mappate alla somma di tutte `productListItems[].priceTotal` campi.
* Le visualizzazioni prodotto sono mappate su `commerce.productListViews.value`.
* I carrelli sono mappati su `commerce.productListOpens.value`.
* Le aggiunte al carrello sono mappate su `commerce.productListAdds.value`.
* Le rimozione del carrello sono mappate su `commerce.productListRemovals.value`.
* Le visualizzazioni del carrello sono mappate su `commerce.productListViews.value`.
* Pagamenti mappati su `commerce.checkouts.value`.

>[!NOTE]
>
>Se un evento è impostato in `productListItems` (ad esempio, `productListItems._experience.analytics.event1.value`) e tale evento non è ancora in questo campo, viene aggiunto automaticamente a questo campo.

## Eventi che utilizzano l’estensione Adobe Analytics

Puoi impostare gli eventi sia durante la configurazione dell’estensione Analytics (variabili globali) che in regole.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata (o crea una regola).
4. Nella sezione [!UICONTROL Actions], fai clic su un’azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull’icona “+”.
5. Scegli Adobe Analytics nel menu a discesa [!UICONTROL Extension] e imposta [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individua la sezione [!UICONTROL Events].

Sono disponibili diverse funzioni:

* Un menu a discesa consente di selezionare l’evento da includere
* Campo di testo facoltativo per la serializzazione. Vedi [serializzazione degli eventi](event-serialization.md) per ulteriori informazioni.
* Campo di testo facoltativo per un valore evento. È possibile includere la valuta per gli eventi di valuta o un numero intero per gli eventi non di valuta per incrementarla più volte. Ad esempio, selezionando `event1` nel menu a discesa e include `10` in questo campo incrementali `event1` entro 10 nei rapporti.
* Un pulsante per aggiungere un altro evento. Puoi aggiungere tutti gli eventi desiderati a una singola regola per un motivo.

## s.events in AppMeasurement e nell&#39;editor di codice personalizzato dell&#39;estensione Analytics

La `s.events` variabile è una stringa che contiene un elenco delimitato da virgole di eventi da includere nell&#39;hit. Non esiste un limite di byte per questa variabile, quindi non viene troncata. I valori validi includono:

* `event1` - `event1000`: Eventi personalizzati, impostati come desiderato. Registra come utilizzi ogni evento nell&#39;organizzazione [documento di progettazione della soluzione](../../../prepare/solution-design.md). Il numero di eventi disponibili dipende dal contratto Analytics della tua organizzazione. La maggior parte delle organizzazioni con contratti non legacy dispone di 1000 eventi personalizzati. Contatta il team dell’account di Adobe se non sei sicuro di quanti eventi personalizzati sono disponibili.
* `purchase`: Incrementa la [&quot;Ordini&quot;](/help/components/metrics/orders.md) metrica per 1 e prende i valori impostati nel `products` variabile da calcolare [&quot;Unità&quot;](/help/components/metrics/units.md) e [&quot;Entrate&quot;](/help/components/metrics/revenue.md). Vedi [evento di acquisto](event-purchase.md) per ulteriori informazioni.
* `prodView`: Incrementa la [&quot;Visualizzazioni prodotto&quot;](/help/components/metrics/product-views.md) metrica.
* `scOpen`: Incrementa la [&#39;Carts&#39;](/help/components/metrics/carts.md) metrica.
* `scAdd`: Incrementa la [&quot;Aggiunte carrello&quot;](/help/components/metrics/cart-additions.md) metrica.
* `scRemove`: Incrementa la [&#39;Rimozioni carrello&#39;](/help/components/metrics/cart-removals.md) metrica.
* `scView`: Incrementa la [Visualizzazioni carrello](/help/components/metrics/cart-views.md) metrica.
* `scCheckout`: Incrementa la [&#39;Pagamenti&#39;](/help/components/metrics/checkouts.md) metrica.

>[!NOTE]
>
>Questa variabile distingue tra maiuscole e minuscole. Evita di capitalizzare male i valori degli eventi per garantire una raccolta accurata dei dati.

```js
// Set the events variable to a single value
s.events = "event1";

// Set the events variable to multiple values
s.events = "event1,event13,purchase";
```

### Incrementa più volte gli eventi dei contatori

Se lo desideri, puoi contare eventi personalizzati più di una volta. Assegna un numero intero all’evento desiderato all’interno della stringa. Per impostazione predefinita, gli eventi creati nelle impostazioni della suite di rapporti sono eventi contatore.

```js
// Count event1 ten times
s.events = "event1=10";

// Count event1 twice and event2 once
s.events = "event1=2,event2";
```

>[!NOTE]
>
>Gli eventi contatore non supportano la valuta o i valori decimali. Utilizzare gli eventi valuta per la valuta o gli eventi numerici per i valori decimali.

### Usa eventi valuta

È possibile modificare un evento personalizzato per utilizzare la valuta anziché i numeri interi. Gli eventi di valuta si convertono automaticamente nella valuta della suite di rapporti se la valuta della suite di rapporti e `currencyCode` La variabile non corrisponde. Sono utili per calcolare i costi di spedizione, gli sconti o i rimborsi. È possibile impostare gli eventi di valuta nella `products` se desideri attribuire l&#39;evento solo a quel prodotto.

Prima di implementare gli eventi di valuta, accertati di impostare l’evento desiderato su &quot;Valuta&quot; in [Eventi di successo](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) nelle impostazioni della suite di rapporti.

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
>Se si imposta un valore di valuta in entrambi i `events` e la variabile `products` variabile, il valore della valuta in `events` viene utilizzato. Evita di impostare i valori di valuta in entrambe le `events` e `products` variabili.

### Utilizzare eventi numerici

È possibile modificare un evento personalizzato accettando valori decimali anziché numeri interi. Gli eventi numerici si comportano in modo simile agli eventi di valuta, ma non utilizzano la conversione di valuta. È possibile impostare eventi numerici nella `products` se desideri attribuire l&#39;evento solo a quel prodotto.

Prima di implementare eventi numerici, accertati di impostare l’evento desiderato su &quot;Numerico&quot; in [Eventi di successo](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) nelle impostazioni della suite di rapporti.

```js
// Send 4.5 in event1 using the events variable. Make sure the event type for event1 is Numeric in Report suite settings
s.events = "event1=4.5";

// Send 4.5 in event1 using the products variable. Make sure the event type for event1 is Numeric in Report suite settings
s.events = "event1";
s.products = "Example category;Example product;1;0;event1=4.5";
```

>[!NOTE]
>
>Se imposti un valore numerico in entrambe le `events` e la variabile `products` il valore numerico in `events` viene utilizzato. Evitare di impostare valori numerici in entrambe le `events` e `products` variabili.
