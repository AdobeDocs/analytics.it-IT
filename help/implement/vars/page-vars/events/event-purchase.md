---
title: Evento di acquisto
description: Utilizza l’evento di acquisto per raccogliere i dati per le metriche "Ordini", "Unità" e "Entrate".
exl-id: 5ad148d6-cf45-4dea-846a-255004300bc2
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 1%

---

# Evento di acquisto

L&#39;evento di acquisto è un valore nella variabile `events` . Questo valore è utile per le organizzazioni che desiderano raccogliere dati sui ricavi generati dal sito. Dipende fortemente dalle variabili [`products`](../products.md) e [`purchaseID`](../purchaseid.md) .

Quando imposti un evento di acquisto, questo influisce sulle metriche seguenti:

* La metrica &quot;Ordini&quot; incrementa di 1
* La metrica &quot;Unità&quot; incrementa il numero di prodotti nella variabile `products`
* La metrica &quot;Entrate&quot; aumenta della somma dei parametri di prezzo nella variabile `products`

>[!NOTE]
>
>Le entrate non vengono moltiplicate per il campo della quantità. Ad esempio, `s.products="Womens;Socks;5;4.50"` non passa $ 22,50 ai ricavi; supera $ 4,50. Assicurati che l&#39;implementazione superi i ricavi totali per la quantità indicata. Ad esempio,`s.products="Womens;Socks;5;22.50"`.

## Impostare l’evento di acquisto utilizzando i tag in Adobe Experience Platform

1. Accedi all&#39; [Interfaccia di raccolta dati](https://experience.adobe.com/data-collection) utilizzando le tue credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai alla scheda [!UICONTROL Rules] , quindi fai clic sulla regola desiderata (o crea una regola).
4. In [!UICONTROL Actions], fai clic su un&#39;azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull&#39;icona &quot;+&quot;.
5. Imposta il menu a discesa [!UICONTROL Extension] su Adobe Analytics e [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individua la sezione [!UICONTROL Events] e imposta il menu a discesa degli eventi su [!UICONTROL purchase].

Altre variabili dipendenti come `products` e `purchaseID` non dispongono di campi dedicati nell’interfaccia utente di raccolta dati. Utilizza l’editor di codice personalizzato seguendo la sintassi AppMeasurement per queste variabili.

## Imposta l’evento di acquisto in AppMeasurement e nell’editor di codice personalizzato

L&#39;evento di acquisto è una stringa impostata come parte della variabile degli eventi.

```js
// Set the purchase event by itself
s.events = "purchase";

// Set the purchase event alongside other events
s.events = "purchase,event1,event2";
```

## Deduplicazione degli eventi di acquisto

Quando si attiva un evento di acquisto, in Adobe vengono controllati i seguenti elementi:

* L’hit contiene la variabile `purchaseID`? In caso contrario, Adobe utilizza le informazioni dell’hit per creare un &quot;ID acquisto temporaneo&quot;. Questo ID acquisto temporaneo si applica solo al visitatore dell’hit. I precedenti 5 ID acquisto temporaneo sono memorizzati per ogni ID visitatore per suite di rapporti.
* L’ID acquisto temporaneo corrisponde a uno degli ultimi cinque ID acquisto temporanei memorizzati? In tal caso, la richiesta di immagine viene considerata un acquisto duplicato. Tutte le variabili di conversione, incluso l’evento di acquisto, non vengono visualizzate nel rapporto.
* Se la variabile `purchaseID` è definita, corrisponde a qualsiasi valore già raccolto nella suite di rapporti per tutti i visitatori? In tal caso, la richiesta di immagine viene considerata un acquisto duplicato. Tutte le variabili di conversione, incluso l’evento di acquisto, non vengono visualizzate nel rapporto.
