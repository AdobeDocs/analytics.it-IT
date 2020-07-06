---
title: Panoramica account dinamici
description: Scopri come selezionare in modo dinamico una suite di rapporti utilizzando il codice H.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 5%

---


# Panoramica account dinamici

>[!IMPORTANT]
>
>Gli account dinamici sono supportati solo utilizzando implementazioni JavaScript precedenti (H Code). Queste variabili non sono supportate nelle librerie AppMeasurement correnti né  lancio del Adobe Experience Platform.

Gli account dinamici è una funzione di implementazione che consente di determinare quale suite di rapporti utilizzare in base ai criteri definiti dall&#39;utente. Se la tua organizzazione richiede più suite di rapporti ma desidera utilizzare la stessa implementazione tra i tuoi siti, gli account dinamici sono una buona soluzione.

>[!TIP]
>
>Adobe consiglia di inviare dati a una singola suite di rapporti, quindi di utilizzare suite di rapporti virtuali per separare i dati, se necessario. Per ulteriori informazioni, consulta Considerazioni [](../../../prepare/global-rs.md) globali sulla suite di rapporti.

3 variabili vengono utilizzate per selezionare in modo dinamico una suite di rapporti.

* [`dynamicAccountSelection`](dynamicaccountselection.md): Attiva o disattiva la selezione dinamica dell&#39;account.
* [`dynamicAccountMatch`](dynamicaccountmatch.md): Determina il valore da osservare. Ad esempio, l’URL o una stringa di query.
* [`dynamicAccountList`](dynamicaccountlist.md): Confronta i valori con `dynamicAccountMatch`, e se viene trovata una corrispondenza, compila la `account` variabile.

Se `dynamicAccountSelection = true`necessario, il valore all&#39;interno `dynamicAccountMatch` viene confrontato con `dynamicAccountList`. Se i valori in `dynamicAccountList` corrispondono, l&#39;ID suite di rapporti viene incluso nella `account` variabile.

## Suite di rapporti predefinita

La `account` variabile può essere impostata per prima e funge da valore predefinito nel caso in cui non sia possibile trovare una delle stringhe specificate. Ad esempio:

```javascript
s_account = "examplersiddefault";
s.dynamicAccountSelection = true;
s.dynamicAccountMatch = location.hostname;
s.dynamicAccountList="examplersiddev=dev.example.com;examplersidprod=example.com";
```

Se non `location.hostname` fosse stato né `dev.example.com` né `example.com`, l’hit sarebbe stato inviato a `examplersiddefault`.

## Assegnazione di tag a più suite

I tag per più suite possono essere utilizzati con la selezione dinamica dell&#39;account. Ad esempio:

```js
s.dynamicAccountSelection = true;
s.dynamicAccountMatch = location.hostname;
s.dynamicAccountList="examplersid1,examplersid2=example.com";
```

Se `location.hostname` contiene `example.com`, l’hit viene inviato sia a `examplersid1` che a `examplersid2`.
