---
title: Evento di acquisto
description: Utilizza l’evento di acquisto per raccogliere i dati per le metriche "Ordini", "Unità" e "Entrate".
feature: Variables
exl-id: 5ad148d6-cf45-4dea-846a-255004300bc2
source-git-commit: 6de20d2fbbab6ded6c92f0c6f3536671f4b2ae46
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 12%

---

# Evento di acquisto

L&#39;evento di acquisto è un valore nel `events` variabile. Questo valore è utile per le organizzazioni che desiderano raccogliere dati sui ricavi generati dal sito. Dipende fortemente dalla [`products`](../products.md) e [`purchaseID`](../purchaseid.md) variabili.

Quando imposti un evento di acquisto, questo influisce sulle metriche seguenti:

* La metrica &quot;Ordini&quot; incrementa di 1
* La metrica &quot;Unità&quot; incrementa per il numero di prodotti nel `products` variable
* La metrica &quot;Entrate&quot; aumenta della somma dei parametri di prezzo nel `products` variable

>[!NOTE]
>
>Le entrate non vengono moltiplicate per il campo della quantità. Ad esempio: `s.products="Womens;Socks;5;4.50"` non trasferisce 22,50 dollari in entrate; supera $ 4,50. Assicurati che l&#39;implementazione superi i ricavi totali per la quantità indicata. Esempio: `s.products="Womens;Socks;5;22.50"`.

## Impostare l&#39;evento di acquisto utilizzando l&#39;SDK per web

L&#39;evento di acquisto è [mappato per Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=it) in diversi campi XDM:

* Gli ordini sono mappati su `commerce.purchases.value`.
* Le unità sono mappate alla somma di tutte `productListItems[].quantity` campi.
* Le entrate sono mappate alla somma di tutte `productListItems[].priceTotal` campi.

## Impostare l’evento di acquisto utilizzando l’estensione Adobe Analytics

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata (o crea una regola).
4. Nella sezione [!UICONTROL Actions], fai clic su un’azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull’icona “+”.
5. Imposta la [!UICONTROL Extension] elenco a discesa in Adobe Analytics e [!UICONTROL Action Type] a [!UICONTROL Set Variables].
6. Individua il [!UICONTROL Events] e imposta la [!UICONTROL Events] elenco a discesa in [!UICONTROL purchase].

Altre variabili dipendenti come `products` e `purchaseID` non dispongono di campi dedicati nell’estensione Analytics all’interno di Raccolta dati di Adobe Experience Platform. Utilizza l’editor di codice personalizzato seguendo la sintassi AppMeasurement per queste variabili.

## Imposta l’evento di acquisto in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

L&#39;evento di acquisto è una stringa impostata come parte della variabile degli eventi.

```js
// Set the purchase event by itself
s.events = "purchase";

// Set the purchase event alongside other events
s.events = "purchase,event1,event2";
```

## Deduplicazione degli eventi di acquisto

Quando si attiva un evento di acquisto, in Adobe vengono controllati i seguenti elementi:

* L’hit contiene il `purchaseID` variabile? In caso contrario, Adobe utilizza le informazioni dell’hit per creare un &quot;ID acquisto temporaneo&quot;. Questo ID acquisto temporaneo si applica solo al visitatore dell’hit. I precedenti 5 ID acquisto temporaneo sono memorizzati per ogni ID visitatore per suite di rapporti.
* L’ID acquisto temporaneo corrisponde a uno degli ultimi cinque ID acquisto temporanei memorizzati? In tal caso, la richiesta di immagine viene considerata un acquisto duplicato. Tutte le variabili di conversione, incluso l’evento di acquisto, non vengono visualizzate nel rapporto.
* Se la `purchaseID` viene definita una variabile , corrisponde a qualsiasi valore già raccolto nella suite di rapporti per tutti i visitatori? In tal caso, la richiesta di immagine viene considerata un acquisto duplicato. Tutte le variabili di conversione, incluso l’evento di acquisto, non vengono visualizzate nel rapporto.
