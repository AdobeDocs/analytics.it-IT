---
title: Evento di acquisto
description: Utilizza l’evento di acquisto per raccogliere i dati per le metriche "Ordini", "Unità" e "Entrate".
feature: Variables
exl-id: 5ad148d6-cf45-4dea-846a-255004300bc2
role: Admin, Developer
source-git-commit: 12347957a7a51dc1f8dfb46d489b59a450c2745a
workflow-type: tm+mt
source-wordcount: '450'
ht-degree: 10%

---

# Evento di acquisto

L’evento di acquisto è un valore in `events` variabile. Questo valore è utile per le organizzazioni che desiderano raccogliere dati sui ricavi generati dal sito. Dipende in larga misura dalla [`products`](../products.md) e [`purchaseID`](../purchaseid.md) variabili.

L’impostazione di un evento di acquisto influisce sulle metriche seguenti:

* La metrica &quot;Ordini&quot; aumenta di 1
* La metrica &quot;Unità&quot; viene incrementata del numero di prodotti nel `products` variabile
* La metrica &quot;Entrate&quot; aumenta della somma dei parametri di prezzo nel `products` variabile

>[!NOTE]
>
>I ricavi non vengono moltiplicati per il campo della quantità. Ad esempio: `s.products="Womens;Socks;5;4.50"` non trasferisce $ 22,50 nei ricavi; trasferisce $ 4,50. Assicurati che l’implementazione superi i ricavi totali per la quantità indicata. Esempio: `s.products="Womens;Socks;5;22.50"`.

## Impostare l’evento di acquisto tramite Web SDK

Se utilizzi il [**Oggetto XDM**](/help/implement/aep-edge/xdm-var-mapping.md), l’evento di acquisto utilizza i seguenti campi XDM:

* Gli ordini sono mappati a `xdm.commerce.purchases.value`.
* Le unità sono mappate alla somma di tutte `xdm.productListItems[].quantity` campi.
* I ricavi vengono mappati sulla somma di tutti `xdm.productListItems[].priceTotal` campi.

Se utilizzi il [**oggetto dati**](/help/implement/aep-edge/data-var-mapping.md), l’evento di acquisto utilizza `data.__adobe.analytics.events`, seguendo l&#39;AppMeasurement di sintassi delle stringhe.

## Impostare l’evento di acquisto tramite l’estensione Adobe Analytics

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata (o crea una regola).
4. Nella sezione [!UICONTROL Actions], fai clic su un’azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull’icona “+”.
5. Imposta il [!UICONTROL Extension] in Adobe Analytics e nella sezione [!UICONTROL Action Type] a [!UICONTROL Set Variables].
6. Individua il [!UICONTROL Events] e impostare [!UICONTROL Events] elenco a discesa per [!UICONTROL purchase].

Altre variabili dipendenti come `products` e `purchaseID` non sono presenti campi dedicati nell’estensione Analytics all’interno di Adobe Experience Platform Data Collection. Utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement per queste variabili.

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

* L’hit contiene `purchaseID` variabile? In caso contrario, Adobe utilizza le informazioni dell’hit per creare un &quot;ID acquisto temporaneo&quot;. Questo ID acquisto temporaneo si applica solo al visitatore dell’hit. I precedenti 5 ID di acquisto temporanei vengono memorizzati per ogni ID visitatore per suite di rapporti.
* L’ID acquisto temporaneo corrisponde a uno degli ultimi cinque ID acquisto temporanei memorizzati? In tal caso, la richiesta di immagine viene considerata un acquisto duplicato. Tutte le variabili di conversione, incluso l’evento di acquisto, non vengono visualizzate nel reporting.
* Se il `purchaseID` è definita una variabile, corrisponde a qualsiasi valore già raccolto nella suite di rapporti per tutti i visitatori? In tal caso, la richiesta di immagine viene considerata un acquisto duplicato. Tutte le variabili di conversione, incluso l’evento di acquisto, non vengono visualizzate nel reporting.
