---
title: events
description: Imposta la variabile degli eventi, che regola la maggior parte delle metriche sul sito.
exl-id: 6ef99ee5-40c3-4ff2-a75d-c97f2e8ec1f8
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '668'
ht-degree: 0%

---

# events

I Dimension e le metriche sono componenti vitali per i rapporti. La variabile `events` è responsabile della raccolta di dati di molte metriche sul sito. Gli eventi in genere incrementano [metriche](/help/components/metrics/overview.md) nei rapporti.

Prima di implementare gli eventi, assicurati di crearli e configurarli in [Eventi di successo](/help/admin/admin/c-success-events/success-event.md) nelle impostazioni della suite di rapporti. Se prevedi di utilizzare eventi personalizzati negli hit di tracciamento dei collegamenti, assicurati che [`linkTrackVars`](../../config-vars/linktrackvars.md) e [`linkTrackEvents`](../../config-vars/linktrackevents.md) siano impostati correttamente.

## Eventi che utilizzano i tag in Adobe Experience Platform

Puoi impostare gli eventi sia durante la configurazione dell’estensione Analytics (variabili globali) che in regole.

1. Accedi all&#39; [Interfaccia di raccolta dati](https://experience.adobe.com/data-collection) utilizzando le tue credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai alla scheda [!UICONTROL Rules] , quindi fai clic sulla regola desiderata (o crea una regola).
4. In [!UICONTROL Actions], fai clic su un&#39;azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull&#39;icona &quot;+&quot;.
5. Imposta il menu a discesa [!UICONTROL Extension] su Adobe Analytics e [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individua la sezione [!UICONTROL Events] .

Sono disponibili diverse funzioni:

* Un menu a discesa consente di selezionare l’evento da includere
* Campo di testo facoltativo per la serializzazione. Per ulteriori informazioni, consulta [serializzazione degli eventi](event-serialization.md) .
* Campo di testo facoltativo per un valore evento. È possibile includere la valuta per gli eventi di valuta o un numero intero per gli eventi non di valuta per incrementarla più volte. Ad esempio, selezionando `event1` nel menu a discesa e includendo `10` in questo campo, il rapporto incrementa di `event1` di 10.
* Un pulsante per aggiungere un altro evento. Non esiste un limite ragionevole al numero di eventi che puoi includere in un hit.

## s.events in AppMeasurement e nell&#39;editor di codice personalizzato

La variabile `s.events` è una stringa che contiene un elenco delimitato da virgole di eventi da includere nell&#39;hit. Non esiste un limite di byte per questa variabile, quindi non viene troncata. I valori validi includono:

* `event1` -  `event1000`: Eventi personalizzati, impostati come desiderato. Registra come utilizzi ogni evento nel documento di progettazione della soluzione [della tua organizzazione](../../../prepare/solution-design.md). Il numero di eventi disponibili dipende dal contratto Analytics della tua organizzazione. La maggior parte delle organizzazioni con contratti non legacy dispone di 1000 eventi personalizzati. Contatta l’account manager della tua organizzazione se non sei sicuro di quanti eventi personalizzati sono disponibili.
* `purchase`: Incrementa la  [&#39;](/help/components/metrics/orders.md) metrica Ordini&#39; di 1 e prende i valori impostati nella  `products` variabile per calcolare  [&#39;Unità&#39; ](/help/components/metrics/units.md) e  [&#39;Entrate&#39;](/help/components/metrics/revenue.md). Per ulteriori informazioni, consulta [evento di acquisto](event-purchase.md) .
* `prodView`: Incrementa la metrica  [&quot;Visualizzazioni prodotto&quot;](/help/components/metrics/product-views.md) .
* `scOpen`: Incrementa la  [metrica ](/help/components/metrics/carts.md) &quot;Carts&quot;.
* `scAdd`: Incrementa la  [metrica ](/help/components/metrics/cart-additions.md) &quot;Aggiunte carrello&quot;.
* `scRemove`: Incrementa la  [metrica ](/help/components/metrics/cart-removals.md) &quot;Rimozioni dal carrello&quot;.
* `scView`: Incrementa la  [metrica ](/help/components/metrics/cart-views.md) &quot;Visualizzazioni carrello&quot;.
* `scCheckout`: Incrementa la  [metrica ](/help/components/metrics/checkouts.md) &quot;Checkout&quot;.

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

È possibile modificare un evento personalizzato per utilizzare la valuta anziché i numeri interi. Gli eventi di valuta vengono convertiti automaticamente nella valuta della suite di rapporti se la valuta della suite di rapporti e la variabile `currencyCode` non corrispondono. Sono utili per calcolare i costi di spedizione, gli sconti o i rimborsi. È possibile impostare gli eventi di valuta nella variabile `products` se si desidera attribuire l&#39;evento solo a quel prodotto.

Prima di implementare gli eventi relativi alla valuta, accertati di impostare l’evento desiderato su &quot;Valuta&quot; in [Eventi di successo](/help/admin/admin/c-success-events/success-event.md) nelle impostazioni della suite di rapporti.

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
>Se si imposta un valore di valuta sia nella variabile `events` che nella variabile `products`, viene utilizzato il valore di valuta in `events`. Evita di impostare i valori di valuta nelle variabili `events` e `products`.

### Utilizzare eventi numerici

È possibile modificare un evento personalizzato accettando valori decimali anziché numeri interi. Gli eventi numerici si comportano in modo simile agli eventi di valuta, ma non utilizzano la conversione di valuta. È possibile impostare eventi numerici nella variabile `products` se si desidera attribuire l’evento solo a quel prodotto.

Prima di implementare eventi numerici, accertati di impostare l’evento desiderato su &quot;Numerico&quot; in [Eventi di successo](/help/admin/admin/c-success-events/success-event.md) nelle impostazioni della suite di rapporti.

```js
// Send 4.5 in event1 using the events variable. Make sure the event type for event1 is Numeric in Report suite settings
s.events = "event1=4.5";

// Send 4.5 in event1 using the products variable. Make sure the event type for event1 is Numeric in Report suite settings
s.events = "event1";
s.products = "Example category;Example product;1;0;event1=4.5";
```

>[!NOTE]
>
>Se si imposta un valore numerico sia nella variabile `events` che nella variabile `products`, viene utilizzato il valore numerico in `events`. Evita di impostare valori numerici nelle variabili `events` e `products` .
