---
title: linkType
description: Utilizzate la variabile linkType per determinare a quale dimensione di tracciamento dei collegamenti appartiene l’hit.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 2%

---


# linkType

Gli hit di tracciamento dei collegamenti possono compilare una delle tre dimensioni seguenti:

* Collegamenti personalizzati
* Collegamenti di uscita
* Collegamenti di download

Utilizzare la `linkType` variabile per determinare quale dimensione si desidera compilare quando si esegue la [`tl()`](../functions/tl-method.md) funzione successiva.

## Tipo di collegamento in  lancio Adobe Experience Platform

Impostate il tipo di collegamento al momento della configurazione di una regola per l&#39;invio di un beacon.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Passate alla [!UICONTROL Rules] scheda, quindi fate clic sulla regola desiderata (o create una regola).
4. In [!UICONTROL Actions], fare clic sull&#39;icona &quot;+&quot;
5. Impostate il [!UICONTROL Extension] menu a discesa su Adobe  Analytics e su [!UICONTROL Action Type] Invia beacon.
6. Fare clic sul `s.tl()` pulsante di scelta per visualizzare il [!UICONTROL Link Type] menu a discesa.

È possibile impostare questo menu a discesa su [!UICONTROL Custom Link], [!UICONTROL Download Link]o [!UICONTROL Exit Link].

## s.linkType nell&#39;editor di codice personalizzato AppMeasurement e Launch

La `s.linkType` variabile è una stringa che accetta uno dei tre valori a carattere singolo: `o`, `d`o `e`. Se un `tl()` metodo viene chiamato senza un tipo di collegamento, per impostazione predefinita viene utilizzato il collegamento Personalizzato.

* `o` - Collegamenti personalizzati
* `d` - Collegamenti di download
* `e` - Collegamenti di uscita

>[!TIP]
>
>Questa variabile è il secondo parametro del `tl()` metodo e in genere non deve essere impostata come variabile standalone. Tuttavia, è possibile utilizzare la `linkType` variabile se non si desidera impostare i valori come argomenti nel `tl()` metodo.

```js
s.linkType = "e";
```

## Esempio

Le due seguenti chiamate di tracciamento dei collegamenti di esempio sono funzionalmente identiche. Sono metodi diversi per ottenere lo stesso hit di tracciamento dei collegamenti.

```js
// Set link tracking arguments as individual variables
s.linkType = "d";
s.linkName = "Example download link";
s.tl();

// Set link tracking arguments directly in the tl() function
s.tl(this,"d","Example download link");
```
