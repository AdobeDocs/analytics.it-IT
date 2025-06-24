---
title: events
description: Imposta la variabile degli eventi, che governa la maggior parte delle metriche sul sito.
feature: Appmeasurement Implementation
exl-id: 6ef99ee5-40c3-4ff2-a75d-c97f2e8ec1f8
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '833'
ht-degree: 5%

---

# events

Dimensioni e metriche sono componenti vitali per i rapporti. La variabile `events` è responsabile della raccolta dei dati di molte metriche sul sito. In genere, gli eventi incrementano [metriche](/help/components/metrics/overview.md) nei rapporti.

Prima di implementare gli eventi, assicurati di crearli e configurarli in [Eventi di successo](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) nelle impostazioni della suite di rapporti. Se prevedi di utilizzare eventi personalizzati negli hit di tracciamento dei collegamenti, assicurati che [`linkTrackVars`](../../config-vars/linktrackvars.md) e [`linkTrackEvents`](../../config-vars/linktrackevents.md) siano impostati correttamente.

## Eventi che utilizzano il Web SDK

Se utilizzi l&#39;[oggetto XDM](/help/implement/aep-edge/xdm-var-mapping.md), gli eventi personalizzati utilizzano i campi XDM seguenti:

* Gli eventi personalizzati 1-100 sono mappati a `xdm._experience.analytics.event1to100.event1` - `xdm._experience.analytics.event1to100.event100`.
* Gli eventi personalizzati 101-200 sono mappati a `xdm._experience.analytics.event101to200.event100` - `xdm._experience.analytics.event101to200.event200`.
* Questo modello si ripete ogni 100 eventi in `xdm._experience.analytics.event901to1000.event901` - `xdm._experience.analytics.event901to1000.event1000`. `eventx.value` viene utilizzato per specificare l&#39;importo da incrementare. `eventx.id` è utilizzato per la [serializzazione](event-serialization.md).
* Gli ordini sono mappati a `xdm.commerce.purchases.value`.
* Le unità sono mappate alla somma di tutti i campi `productListItems[].quantity`.
* Ricavi mappati alla somma di tutti i campi `productListItems[].priceTotal`.
* Le visualizzazioni prodotto sono mappate a `xdm.commerce.productViews.value`.
* I carrelli sono mappati a `xdm.commerce.productListOpens.value`.
* Le aggiunte al carrello sono mappate a `xdm.commerce.productListAdds.value`.
* Le rimozioni dal carrello sono mappate a `xdm.commerce.productListRemovals.value`.
* Le visualizzazioni del carrello sono mappate a `xdm.commerce.productListViews.value`.
* Le casse sono mappate a `xdm.commerce.checkouts.value`.

>[!NOTE]
>
>Se un evento è impostato in `productListItems` (ad esempio, `productListItems._experience.analytics.event1.value`) e tale evento non è ancora presente in questo campo, l&#39;evento viene aggiunto automaticamente a questo campo.

Se si utilizza l&#39;[**oggetto dati**](/help/implement/aep-edge/data-var-mapping.md), tutti gli eventi utilizzano `data.__adobe.analytics.events`, seguendo la sintassi stringa di AppMeasurement. Se imposti questo campo, tutti gli eventi impostati nell’oggetto XDM vengono sovrascritti e non inviati ad Adobe Analytics.

## Eventi che utilizzano l’estensione Adobe Analytics

Puoi impostare gli eventi sia durante la configurazione dell’estensione Analytics (variabili globali) sia nelle regole.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata (o crea una regola).
4. Nella sezione [!UICONTROL Actions], fai clic su un’azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull’icona “+”.
5. Impostare l&#39;elenco a discesa [!UICONTROL Extension] su Adobe Analytics e [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individua la sezione [!UICONTROL Events].

Sono disponibili diverse funzioni:

* Elenco a discesa che consente di selezionare l’evento da includere
* Campo di testo facoltativo per la serializzazione. Per ulteriori informazioni, vedere [serializzazione eventi](event-serialization.md).
* Campo di testo facoltativo per un valore evento. È possibile includere la valuta per gli eventi di valuta oppure un numero intero per gli eventi non di valuta per incrementarla più volte. Selezionando ad esempio `event1` nell&#39;elenco a discesa e includendo `10` in questo campo, nella generazione rapporti `event1` viene incrementato di 10.
* Un pulsante per aggiungere un altro evento. Puoi aggiungere tutti gli eventi che desideri a una singola regola entro il motivo desiderato.

## s.events in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La variabile `s.events` è una stringa che contiene un elenco delimitato da virgole di eventi da includere nell&#39;hit. La variabile consente fino a 64.000 byte, consentendo in modo efficace il numero di eventi necessario per un hit. I valori validi includono:

* `event1` - `event1000`: eventi personalizzati, impostati come desiderato. Registra come utilizzi ogni evento nel [documento di progettazione della soluzione](../../../prepare/solution-design.md) della tua organizzazione. Il numero di eventi disponibili dipende dal contratto Analytics della tua organizzazione. La maggior parte delle organizzazioni con contratti non legacy dispone di 1000 eventi personalizzati. Se non sai quanti eventi personalizzati sono disponibili, contatta il tuo Adobe Account Team.
* `purchase`: incrementa di 1 la metrica [&#39;Orders&#39;](/help/components/metrics/orders.md) e considera i valori impostati nella variabile `products` per calcolare [&#39;Units&#39;](/help/components/metrics/units.md) e [&#39;Revenue&#39;](/help/components/metrics/revenue.md). Per ulteriori informazioni, consulta [evento di acquisto](event-purchase.md).
* `prodView`: incrementa la metrica [&#39;Visualizzazioni prodotto&#39;](/help/components/metrics/product-views.md).
* `scOpen`: incrementa la metrica [&#39;Carrelli&#39;](/help/components/metrics/carts.md).
* `scAdd`: incrementa la metrica [&#39;Aggiunte carrello&#39;](/help/components/metrics/cart-additions.md).
* `scRemove`: incrementa la metrica [&#39;Rimozioni carrello&#39;](/help/components/metrics/cart-removals.md).
* `scView`: incrementa la metrica [&#39;Visualizzazioni carrello&#39;](/help/components/metrics/cart-views.md).
* `scCheckout`: incrementa la metrica [&#39;Casse&#39;](/help/components/metrics/checkouts.md).

>[!NOTE]
>
>Questa variabile fa distinzione tra maiuscole e minuscole. Evita di capitalizzare in modo errato i valori degli eventi per garantire una raccolta accurata dei dati.

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

È possibile modificare un evento personalizzato in modo che utilizzi la valuta anziché i numeri interi. Gli eventi di valuta vengono convertiti automaticamente nella valuta della suite di rapporti se la valuta della suite di rapporti e la variabile `currencyCode` non corrispondono. Sono utili per calcolare spese di spedizione, sconti o rimborsi. È possibile impostare gli eventi di valuta nella variabile `products` se si desidera attribuire l&#39;evento solo a tale prodotto.

Prima di implementare gli eventi di valuta, assicurati di impostare l&#39;evento desiderato su &quot;Valuta&quot; in [Eventi di successo](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) nelle impostazioni della suite di rapporti.

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
>Se si imposta un valore di valuta sia nella variabile `events` che nella variabile `products`, verrà utilizzato il valore di valuta in `events`. Evitare di impostare valori di valuta nelle variabili `events` e `products`.

### Utilizzare eventi numerici

È possibile modificare un evento personalizzato per accettare valori decimali anziché interi. Gli eventi numerici si comportano in modo simile agli eventi di valuta, tranne per il fatto che non utilizzano la conversione di valuta. È possibile impostare eventi numerici nella variabile `products` se si desidera attribuire l&#39;evento solo a tale prodotto.

Prima di implementare eventi numerici, assicurati di impostare l&#39;evento desiderato su &quot;Numerico&quot; in [Eventi di successo](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) nelle impostazioni della suite di rapporti.

```js
// Send 4.5 in event1 using the events variable. Make sure the event type for event1 is Numeric in Report suite settings
s.events = "event1=4.5";

// Send 4.5 in event1 using the products variable. Make sure the event type for event1 is Numeric in Report suite settings
s.events = "event1";
s.products = "Example category;Example product;1;0;event1=4.5";
```

>[!NOTE]
>
>Se si imposta un valore numerico sia nella variabile `events` che nella variabile `products`, verrà utilizzato il valore numerico in `events`. Evitare di impostare valori numerici nelle variabili `events` e `products`.
