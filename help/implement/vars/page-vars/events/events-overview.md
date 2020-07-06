---
title: events
description: Impostate la variabile degli eventi, che regola la maggior parte delle metriche sul sito.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '580'
ht-degree: 0%

---


# events

Dimensioni e metriche sono componenti essenziali per i report. La `events` variabile è responsabile della raccolta di dati di molte metriche sul sito.

## Eventi in  Adobe Experience Platform Launch

È possibile impostare gli eventi durante la configurazione dell&#39;estensione Analytics  (variabili globali) o in base alle regole.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Passate alla [!UICONTROL Rules] scheda, quindi fate clic sulla regola desiderata (o create una regola).
4. In [!UICONTROL Actions], fare clic su un&#39;azione esistente [!UICONTROL Adobe Analytics - Set Variables] o fare clic sull&#39;icona &quot;+&quot;.
5. Impostate il [!UICONTROL Extension] menu a discesa su Adobe  Analytics e [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individuare la [!UICONTROL Events] sezione.

Sono disponibili diverse funzioni:

* Un menu a discesa consente di selezionare l&#39;evento da includere
* Un campo di testo facoltativo per la serializzazione. Per ulteriori informazioni, consultate [la sezione dedicata alla serializzazione](event-serialization.md) degli eventi.
* Campo di testo facoltativo per il valore di un evento. È possibile includere la valuta per gli eventi di valuta, oppure un numero intero per gli eventi non di valuta per incrementarla più volte. Ad esempio, se si seleziona `event1` sotto il menu a discesa e si inserisce `10` in questo campo, nei rapporti gli incrementi `event1` di 10 vengono effettuati.
* Un pulsante per aggiungere un altro evento. Non esiste un limite ragionevole al numero di eventi che puoi includere in un hit.

## s.events in AppMeasurement e Launch editor di codice personalizzato

La `s.events` variabile è una stringa che contiene un elenco delimitato da virgole di eventi da includere nell’hit. Non esiste alcun limite di byte per questa variabile, pertanto non viene troncata. I valori validi includono:

* `event1` - `event1000`: Eventi personalizzati, impostati come desiderato. Registrazione dell&#39;utilizzo di ogni evento nel documento [di progettazione della](../../../prepare/solution-design.md)soluzione aziendale. Il numero di eventi disponibili dipende dal contratto Analytics  della tua organizzazione. La maggior parte delle organizzazioni per i contratti non legacy dispone di 1000 eventi personalizzati. Contatta il responsabile commerciale dell&#39;azienda se non sei sicuro di quanti eventi personalizzati sono disponibili.
* `purchase`: Aumenta la metrica [&#39;Ordini&#39;](/help/components/metrics/orders.md) di 1 e prende i valori impostati nella `products` variabile per calcolare [&#39;Unità&#39;](/help/components/metrics/units.md) &#39; e [&#39;Entrate&#39;](/help/components/metrics/revenue.md). Per ulteriori informazioni, consulta Evento [di](event-purchase.md) acquisto.
* `prodView`: Aumenta la metrica [&#39;Visite prodotto&#39;](/help/components/metrics/product-views.md) .
* `scOpen`: Incrementa la metrica [&#39;Carts&#39;](/help/components/metrics/carts.md) .
* `scAdd`: Incrementa la metrica [&#39;Incrementi carrello&#39;](/help/components/metrics/cart-additions.md) .
* `scRemove`: Aumenta la metrica [&#39;Rimozioni carrello&#39;](/help/components/metrics/cart-removals.md) .
* `scView`: Incrementa la metrica [Visualizzazioni carrello](/help/components/metrics/cart-views.md) .
* `scCheckout`: Aumenta la metrica [&#39;Checkout&#39;](/help/components/metrics/checkouts.md) .

>[!NOTE]
>
>Questa variabile fa distinzione tra maiuscole e minuscole. Evitate di usare valori di evento con maiuscole/minuscole errate per garantire una raccolta accurata dei dati.

```js
// Set the events variable to a single value
s.events = "event1";

// Set the events variable to multiple values
s.events = "event1,event13,purchase";
```

### Incrementare più volte gli eventi del contatore

Se necessario, potete contare più eventi personalizzati. Assegnare un numero intero all&#39;evento desiderato all&#39;interno della stringa. Per impostazione predefinita, gli eventi creati nelle impostazioni della suite di rapporti sono eventi contatore.

```js
// Count event1 ten times
s.events = "event1=10";

// Count event1 twice and event2 once
s.events = "event1=2,event2";
```

>[!NOTE]
>
>Gli eventi contatore non supportano valori di valuta o decimali. Utilizzare gli eventi di valuta per la valuta o gli eventi numerici per i valori decimali.

### Utilizzare gli eventi valuta

È possibile modificare un evento personalizzato per utilizzare la valuta invece dei numeri interi. Gli eventi di valuta vengono convertiti automaticamente nella valuta della suite di rapporti se la valuta della suite di rapporti e la `currencyCode` variabile non corrispondono. Sono utili per calcolare i costi di spedizione, gli sconti o i rimborsi. È possibile impostare gli eventi di valuta nella `products` variabile se si desidera attribuire l&#39;evento solo a tale prodotto.

```js
// Send $9.99 USD in event1 using the events variable. Make sure the event type for event1 is Currency in report suite settings
s.currencyCode = "USD";
s.events = "event1=9.99";

// Send $9.99 USD in event1 using the products variable. Make sure the event type for event1 is Currency in report suite settings
s.currencyCode = "USD";
s.events = "event1";
s.products = "Example category;Example product;1;0;event1=9.99";
```

>[!NOTE]
>
>Se si imposta un valore di valuta sia nella `events` variabile che nella `products` variabile, viene utilizzato il valore di valuta in `events` . Evitare di impostare i valori di valuta sia nelle `events` variabili che nelle `products` variabili.

### Uso di eventi numerici

È possibile modificare un evento personalizzato accettando valori decimali invece dei numeri interi. Gli eventi numerici si comportano in modo simile agli eventi valutari, ma non utilizzano la conversione della valuta. È possibile impostare eventi numerici nella `products` variabile se si desidera attribuire l&#39;evento solo a tale prodotto.

```js
// Send 4.5 in event1 using the events variable. Make sure the event type for event1 is Numeric in report suite settings
s.events = "event1=4.5";

// Send 4.5 in event1 using the products variable. Make sure the event type for event1 is Numeric in report suite settings
s.events = "event1";
s.products = "Example category;Example product;1;0;event1=4.5";
```

>[!NOTE]
>
>Se si imposta un valore numerico sia nella `events` variabile che nella `products` variabile, viene utilizzato il valore numerico in `events` . Evitare di impostare valori numerici sia nelle `events` variabili che nelle `products` variabili.
