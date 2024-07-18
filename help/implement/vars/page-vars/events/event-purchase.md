---
title: Evento di acquisto
description: Utilizza l’evento di acquisto per raccogliere i dati per le metriche "Ordini", "Unità" e "Entrate".
feature: Variables
exl-id: 5ad148d6-cf45-4dea-846a-255004300bc2
role: Admin, Developer
source-git-commit: 7c8ffe8f4ccf0577136e4d7ee96340224897d2a4
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 10%

---

# Evento di acquisto

L&#39;evento di acquisto è un valore nella variabile `events`. Questo valore è utile per le organizzazioni che desiderano raccogliere dati sui ricavi generati dal sito. Dipende fortemente dalle variabili [`products`](../products.md) e [`purchaseID`](../purchaseid.md).

L’impostazione di un evento di acquisto influisce sulle metriche seguenti:

* La metrica &quot;Ordini&quot; aumenta di 1
* La metrica &quot;Unità&quot; viene incrementata del numero di prodotti nella variabile `products`
* La metrica &quot;Entrate&quot; aumenta della somma dei parametri di prezzo nella variabile `products`

>[!NOTE]
>
>I ricavi non vengono moltiplicati per il campo della quantità. Ad esempio, `s.products="Womens;Socks;5;4.50"` non trasferisce 22,50 $ in ricavi; ne trasmette 4,50 $. Assicurati che l’implementazione superi i ricavi totali per la quantità indicata. Esempio: `s.products="Womens;Socks;5;22.50"`.

## Impostare l’evento di acquisto tramite Web SDK

Se si utilizza l&#39;[**oggetto XDM**](/help/implement/aep-edge/xdm-var-mapping.md), l&#39;evento di acquisto utilizza i campi XDM seguenti:

* Gli ordini sono mappati a `xdm.commerce.purchases.value`.
* Le unità sono mappate alla somma di tutti i campi `xdm.productListItems[].quantity`. Per ulteriori informazioni, vedere [`products`](../products.md).
* Ricavi mappati alla somma di tutti i campi `xdm.productListItems[].priceTotal`.

```json
{
  "xdm": {
    "commerce": {
      "purchases": {
        "value": 1
      }
    }
  }
}
```

Se si utilizza l&#39;[**oggetto dati**](/help/implement/aep-edge/data-var-mapping.md), l&#39;evento di acquisto utilizza `data.__adobe.analytics.events`, seguendo la sintassi stringa di AppMeasurement.

```json
{
  "data": {
    "__adobe": {
      "analytics": {
        "events": "purchase"
      }
    }
  }
}
```

## Impostare l’evento di acquisto tramite l’estensione Adobe Analytics

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata (o crea una regola).
4. Nella sezione [!UICONTROL Actions], fai clic su un’azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull’icona “+”.
5. Impostare l&#39;elenco a discesa [!UICONTROL Extension] su Adobe Analytics e [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individuare la sezione [!UICONTROL Events] e impostare l&#39;elenco a discesa [!UICONTROL Events] su [!UICONTROL purchase].

Altre variabili dipendenti come `products` e `purchaseID` non dispongono di campi dedicati nell&#39;estensione Analytics all&#39;interno di Adobe Experience Platform Data Collection. Utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement per queste variabili.

## Imposta l’evento di acquisto in AppMeasurement e l’editor di codice personalizzato dell’estensione Analytics

L’evento di acquisto è una stringa impostata come parte della variabile degli eventi.

```js
// Set the purchase event by itself
s.events = "purchase";

// Set the purchase event alongside other events
s.events = "purchase,event1,event2";
```

## Deduplicazione degli eventi di acquisto

Quando si attiva un evento di acquisto, Adobe verifica quanto segue:

* L&#39;hit contiene la variabile `purchaseID`? In caso contrario, Adobe utilizza le informazioni dell’hit per creare un &quot;ID acquisto temporaneo&quot;. Questo ID acquisto temporaneo si applica solo al visitatore dell’hit. I precedenti 5 ID di acquisto temporanei vengono memorizzati per ogni ID visitatore per suite di rapporti.
* L’ID acquisto temporaneo corrisponde a uno degli ultimi cinque ID acquisto temporanei memorizzati? In tal caso, la richiesta di immagine viene considerata un acquisto duplicato. Tutte le variabili di conversione, incluso l’evento di acquisto, non vengono visualizzate nel reporting.
* Se la variabile `purchaseID` è definita, corrisponde a qualsiasi valore già raccolto nella suite di rapporti per tutti i visitatori? In tal caso, la richiesta di immagine viene considerata un acquisto duplicato. Tutte le variabili di conversione, incluso l’evento di acquisto, non vengono visualizzate nel reporting.
