---
title: Evento di acquisto
description: Utilizzare l'evento di acquisto per raccogliere i dati per le metriche 'Ordini', 'Unità' e 'Entrate'.
translation-type: tm+mt
source-git-commit: 87d0c7e20594e2e39f55284e8d50d425cc1cdacf
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 2%

---


# Evento di acquisto

L&#39;evento acquisto è un valore nella `events` variabile. Questo valore è utile per le organizzazioni che desiderano raccogliere dati sulle entrate generate dal loro sito. Dipende fortemente dalle [`products`](../products.md) e dalle [`purchaseID`](../purchaseid.md) variabili.

Quando imposti un evento di acquisto, questo incide sulle metriche seguenti:

* La metrica &quot;Ordini&quot; aumenta di 1
* La metrica &quot;Unità&quot; aumenta per il numero di prodotti nella `products` variabile
* La metrica &quot;Revenue&quot; (Entrate) aumenta per la somma dei parametri di prezzo nella `products` variabile

>[!NOTE] Le entrate non vengono moltiplicate per il campo quantità. Ad esempio, `s.products="Womens;Socks;5;4.50"` non trasferisce $22,50 nelle entrate; passa $4,50. Assicurarsi che l&#39;implementazione superi le entrate totali per la quantità indicata. Ad esempio,`s.products="Womens;Socks;5;22.50"`.

## Imposta l’evento di acquisto in Adobe Experience Platform Launch

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Passate alla [!UICONTROL Rules] scheda, quindi fate clic sulla regola desiderata (o create una regola).
4. In [!UICONTROL Actions], fare clic su un&#39;azione esistente [!UICONTROL Adobe Analytics - Set Variables] o fare clic sull&#39;icona &quot;+&quot;.
5. Impostate il [!UICONTROL Extension] menu a discesa su Adobe Analytics e [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individuate la [!UICONTROL Events] sezione e impostate il menu a discesa degli eventi su [!UICONTROL purchase].

Altre variabili dipendenti come `products` e `purchaseID` non hanno campi dedicati in Launch. Utilizzate l&#39;editor di codice personalizzato che segue la sintassi AppMeasurement per queste variabili.

## Imposta l’evento di acquisto nell’editor di codice personalizzato AppMeasurement e Launch

L&#39;evento purchase è una stringa impostata come parte della variabile events.

```js
// Set the purchase event by itself
s.events = "purchase";

// Set the purchase event alongside other events
s.events = "purchase,event1,event2";
```

## Deduplicazione degli eventi di acquisto

Quando si attiva un evento di acquisto, Adobe verifica quanto segue:

* L’hit contiene la `purchaseID` variabile? In caso contrario, Adobe utilizza le informazioni dell’hit per creare un &quot;ID acquisto temporaneo&quot;. Questo ID acquisto temporaneo si applica solo al visitatore dell’hit. I 5 ID acquisto temporaneo precedenti sono memorizzati per ogni ID visitatore per ogni suite di rapporti.
* L&#39;ID acquisto temporaneo corrisponde a uno degli ultimi cinque ID acquisto temporaneo memorizzati? In tal caso, la richiesta di immagine viene considerata un acquisto duplicato. Tutte le variabili di conversione, incluso l&#39;evento di acquisto, non vengono visualizzate nel reporting.
* Se la `purchaseID` variabile è definita, corrisponde a qualsiasi valore già raccolto nella suite di rapporti tra tutti i visitatori? In tal caso, la richiesta di immagine viene considerata un acquisto duplicato. Tutte le variabili di conversione, incluso l&#39;evento di acquisto, non vengono visualizzate nel reporting.
