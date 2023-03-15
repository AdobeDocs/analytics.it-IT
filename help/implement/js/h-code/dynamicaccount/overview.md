---
title: Panoramica account dinamici
description: Scopri il flusso di lavoro per la selezione dinamica di una suite di rapporti utilizzando il codice H.
feature: Implementation Basics
exl-id: 6f35dd71-29ad-4923-b1f7-9c7d6ca45bd8
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 5%

---

# Panoramica account dinamici

>[!IMPORTANT]
>
>Gli account dinamici sono supportati solo utilizzando implementazioni JavaScript legacy (codice H). Queste variabili non sono supportate nelle librerie o nei tag AppMeasurement correnti in Adobe Experience Platform.

Gli account dinamici sono una funzione di implementazione che consente di determinare quale suite di rapporti utilizzare in base ai criteri definiti. Se la tua organizzazione richiede più di una suite di rapporti ma desidera utilizzare la stessa implementazione tra i siti, gli account dinamici sono una buona soluzione.

>[!TIP]
>
>L’Adobe consiglia di inviare dati a una singola suite di rapporti e, se necessario, di utilizzare suite di rapporti virtuali per separare i dati. Consulta [Considerazioni globali sulla suite di rapporti](../../../prepare/global-rs.md) per ulteriori informazioni.

3 variabili vengono utilizzate per selezionare dinamicamente una suite di rapporti.

* [`dynamicAccountSelection`](dynamicaccountselection.md): attiva o disattiva la selezione dinamica dell’account.
* [`dynamicAccountMatch`](dynamicaccountmatch.md): determina il valore da osservare. Ad esempio, l’URL o una stringa di query.
* [`dynamicAccountList`](dynamicaccountlist.md): confronta i valori con `dynamicAccountMatch`e, se viene trovata una corrispondenza, compila il `account` variabile.

Se `dynamicAccountSelection = true`, il valore entro `dynamicAccountMatch` viene confrontato con `dynamicAccountList`. Se i valori in `dynamicAccountList` corrispondenza, l’ID suite di rapporti è incluso nel `account` variabile.

## Suite di rapporti predefinita

Il `account` La variabile può essere impostata per prima e funge da valore predefinito nel caso in cui non sia possibile trovare una delle stringhe specificate. Ad esempio:

```javascript
s_account = "examplersiddefault";
s.dynamicAccountSelection = true;
s.dynamicAccountMatch = location.hostname;
s.dynamicAccountList="examplersiddev=dev.example.com;examplersidprod=example.com";
```

Se `location.hostname` non era `dev.example.com` o `example.com`, l’hit viene inviato a `examplersiddefault`.

## Assegnazione di tag a più suite

L’assegnazione tag multisuite può essere utilizzata con la selezione dinamica dell’account. Ad esempio:

```js
s.dynamicAccountSelection = true;
s.dynamicAccountMatch = location.hostname;
s.dynamicAccountList="examplersid1,examplersid2=example.com";
```

Se `location.hostname` contiene `example.com`, l’hit viene inviato a entrambi `examplersid1` e `examplersid2`.
