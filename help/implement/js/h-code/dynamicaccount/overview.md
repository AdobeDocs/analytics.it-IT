---
title: Panoramica account dinamici
description: Scopri come selezionare in modo dinamico una suite di rapporti utilizzando il codice H.
exl-id: 6f35dd71-29ad-4923-b1f7-9c7d6ca45bd8
source-git-commit: 562ed0e190954b7687fa79efaf5c5c54eb202af8
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 5%

---

# Panoramica account dinamici

>[!IMPORTANT]
>
>Gli account dinamici sono supportati solo utilizzando implementazioni JavaScript legacy (H Code). Queste variabili non sono supportate nelle librerie AppMeasurement o nei tag correnti in Adobe Experience Platform.

Gli account dinamici sono una funzione di implementazione che consente di determinare quale suite di rapporti utilizzare in base ai criteri definiti. Se l’organizzazione richiede più di una suite di rapporti ma desidera utilizzare la stessa implementazione tra i siti, gli account dinamici rappresentano una buona soluzione.

>[!TIP]
>
>Adobe consiglia di inviare dati a una singola suite di rapporti, quindi di utilizzare suite di rapporti virtuali per separare i dati se necessario. Per ulteriori informazioni, consulta [Considerazioni globali sulla suite di rapporti](../../../prepare/global-rs.md) .

Per selezionare in modo dinamico una suite di rapporti vengono utilizzate 3 variabili.

* [`dynamicAccountSelection`](dynamicaccountselection.md): Attiva o disattiva la selezione degli account dinamici.
* [`dynamicAccountMatch`](dynamicaccountmatch.md): Determina il valore da osservare. Ad esempio, l’URL o una stringa di interrogazione.
* [`dynamicAccountList`](dynamicaccountlist.md): Confronta i valori con  `dynamicAccountMatch` e, se viene trovata una corrispondenza, compila la  `account` variabile.

Se `dynamicAccountSelection = true`, il valore all&#39;interno di `dynamicAccountMatch` viene confrontato con `dynamicAccountList`. Se i valori in `dynamicAccountList` corrispondono, l&#39;ID suite di rapporti è incluso nella variabile `account` .

## Suite di rapporti predefinita

La variabile `account` può essere impostata per prima e funge da valore predefinito nel caso in cui non sia possibile trovare una delle stringhe specificate. Ad esempio:

```javascript
s_account = "examplersiddefault";
s.dynamicAccountSelection = true;
s.dynamicAccountMatch = location.hostname;
s.dynamicAccountList="examplersiddev=dev.example.com;examplersidprod=example.com";
```

Se `location.hostname` non era `dev.example.com` o `example.com`, l&#39;hit verrebbe inviato a `examplersiddefault`.

## Assegnazione di tag a più suite

L’assegnazione tag a più suite può essere utilizzata con la selezione dinamica dell’account. Ad esempio:

```js
s.dynamicAccountSelection = true;
s.dynamicAccountMatch = location.hostname;
s.dynamicAccountList="examplersid1,examplersid2=example.com";
```

Se `location.hostname` contiene `example.com`, l&#39;hit viene inviato sia a `examplersid1` che a3/>.`examplersid2`
