---
title: Panoramica account dinamici
description: Scopri il flusso di lavoro per la selezione dinamica di una suite di rapporti utilizzando il codice H.
feature: Implementation Basics
exl-id: 6f35dd71-29ad-4923-b1f7-9c7d6ca45bd8
role: Developer
TQID: https://experienceleague.adobe.com/PCeDSQpYH3wym7oG5CYbQblnXkiOQRF4YlcHU6zYfKA
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: df312454-73c4-43f6-a90e-18f5043f074c
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 243
ht-degree: 4%

---

# Panoramica account dinamici

>[!IMPORTANT]
>
>Gli account dinamici sono supportati solo utilizzando le implementazioni legacy di JavaScript (codice H). Queste variabili non sono supportate nelle librerie o nei tag AppMeasurement correnti in Adobe Experience Platform.

Gli account dinamici sono una funzione di implementazione che consente di determinare quale suite di rapporti utilizzare in base ai criteri definiti. Se la tua organizzazione richiede più di una suite di rapporti ma desidera utilizzare la stessa implementazione tra i siti, gli account dinamici rappresentano una buona soluzione.

>[!TIP]
>
>Adobe consiglia di inviare i dati a una singola suite di rapporti e, se necessario, di utilizzare suite di rapporti virtuali per separare i dati. Per ulteriori informazioni, consulta [Considerazioni globali sulla suite di rapporti](../../../prepare/global-rs.md).

3 variabili vengono utilizzate per selezionare dinamicamente una suite di rapporti.

* [`dynamicAccountSelection`](dynamicaccountselection.md): abilitare o disabilitare la selezione dinamica dell&#39;account.
* [`dynamicAccountMatch`](dynamicaccountmatch.md): determina il valore da osservare. Ad esempio, l’URL o una stringa di query.
* [`dynamicAccountList`](dynamicaccountlist.md): confronta i valori con `dynamicAccountMatch` e, se viene trovata una corrispondenza, popola la variabile `account`.

Se `dynamicAccountSelection = true`, il valore in `dynamicAccountMatch` viene confrontato con `dynamicAccountList`. Se i valori in `dynamicAccountList` corrispondono, l&#39;ID suite di rapporti viene incluso nella variabile `account`.

## Suite di rapporti predefinita

La variabile `account` può essere impostata per prima e funge da valore predefinito nel caso in cui non sia possibile trovare una delle stringhe specificate. Ad esempio:

```javascript
s_account = "examplersiddefault";
s.dynamicAccountSelection = true;
s.dynamicAccountMatch = location.hostname;
s.dynamicAccountList="examplersiddev=dev.example.com;examplersidprod=example.com";
```

Se `location.hostname` non fosse né `dev.example.com` né `example.com`, l&#39;hit verrebbe inviato a `examplersiddefault`.

## Assegnazione di tag multisuite

L’assegnazione tag multisuite può essere utilizzata con la selezione dinamica dell’account. Ad esempio:

```js
s.dynamicAccountSelection = true;
s.dynamicAccountMatch = location.hostname;
s.dynamicAccountList="examplersid1,examplersid2=example.com";
```

Se `location.hostname` contiene `example.com`, l&#39;hit viene inviato a `examplersid1` e `examplersid2`.
