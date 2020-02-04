---
title: prop
description: Variabili personalizzate utilizzabili nell’implementazione.
translation-type: tm+mt
source-git-commit: ddab63a4fe3b8f1a3187893eba1ac3a1eda3bc41

---


# prop

Le proprietà sono variabili personalizzate che potete utilizzare come desiderate.

> [!TIP] Nella maggior parte dei casi, Adobe consiglia di utilizzare le eVar. Nelle versioni precedenti di Adobe Analytics, le proprietà e le eVar presentavano vantaggi e svantaggi l&#39;una per l&#39;altra. Tuttavia, Adobe ha migliorato le eVar dove soddisfano quasi tutti i casi di utilizzo per le prop. Per un confronto delle funzioni tra questi due tipi di variabili personalizzate, vedere [eVar](evar.md) .

Se l&#39;azienda utilizza le proprietà, accertatevi di registrarne l&#39;uso e la logica nel documento [di progettazione della](../../prepare/solution-design.md)soluzione.

## Prop in Adobe Experience Platform Launch

Potete impostare le proprietà sia durante la configurazione dell&#39;estensione Analytics (variabili globali) che in base alle regole.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Passate alla [!UICONTROL Rules] scheda, quindi fate clic sulla regola desiderata (o create una regola).
4. In [!UICONTROL Actions], fare clic su un&#39;azione esistente [!UICONTROL Adobe Analytics - Set Variables] o fare clic sull&#39;icona &quot;+&quot;.
5. Impostate il [!UICONTROL Extension] menu a discesa su Adobe Analytics e [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individuare la [!UICONTROL Props] sezione.

È possibile selezionare una proprietà per impostare un valore o un elemento dati. Puoi anche copiare il valore da un’altra variabile di Analytics.

## s.prop1 - s.prop75 in AppMeasurement e Launch editor di codice personalizzato

Ogni variabile prop è una stringa che contiene valori personalizzati specifici dell&#39;organizzazione. La loro lunghezza massima è di 100 byte; i valori superiori a 100 byte vengono troncati automaticamente quando inviati ad Adobe.

```js
s.prop1 = "Example custom value";
```

## Proprietà elenco

Le proprietà elenco sono un&#39;impostazione applicata alle proprietà che consentono alla variabile di contenere più valori nello stesso hit. Se questa impostazione non è abilitata o se viene utilizzato il delimitatore sbagliato, la variabile viene trattata come un singolo valore.

### Configurare le proprietà dell&#39;elenco

Abilitare le proprietà elenco nelle impostazioni della suite di rapporti. Consultate Variabili [di](/help/admin/admin/c-traffic-variables/traffic-var.md) traffico nella guida utente di amministrazione. Accertatevi che il delimitatore desiderato sia configurato correttamente. Adobe non fornisce un delimitatore predefinito.

> [!TIP] I delimitatori comuni utilizzati nelle implementazioni sono virgole (`,`), due punti (`:`), un punto e virgola (`;`) o una barra verticale (`|`). Potete utilizzare un carattere di delimitazione adatto alla vostra implementazione.

### Imposta proprietà elenco

Una volta configurate le proprietà dell&#39;elenco nelle impostazioni della suite di rapporti con il delimitatore desiderato, non vi sono differenze di implementazione diverse dall&#39;utilizzo del delimitatore.

```js
// List prop delimited with a comma
s.prop1 = "value1,value2,value3";
```

> [!IMPORTANT] Le proprietà elenco sono ancora soggette alla lunghezza massima di 100 byte. Le proprietà elenco sono più facili da raggiungere e troncare, poiché possono contenere più valori. Se raggiungete questo limite di 100 byte, prendete in considerazione l&#39;uso di abbreviazioni o valori abbreviati.
