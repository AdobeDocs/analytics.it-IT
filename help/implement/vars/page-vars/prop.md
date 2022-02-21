---
title: prop
description: Variabili personalizzate che puoi utilizzare nell’implementazione.
feature: Variables
exl-id: 0d0ff8cd-1d8c-4263-866d-e51ad66148b0
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 0%

---

# prop

*Questa pagina di aiuto descrive come implementare i prop. Per informazioni sul funzionamento delle proprietà come dimensione, consulta [prop](/help/components/dimensions/prop.md) nella guida utente Componenti .*

Le proprietà sono variabili personalizzate che puoi utilizzare come desideri. Non persistono oltre il risultato impostato.

>[!TIP]
>
>Adobe consiglia di utilizzare [eVar](evar.md) nella maggior parte dei casi. Nelle versioni precedenti di Adobe Analytics, le proprietà e le eVar presentavano vantaggi e svantaggi l’una per l’altra. Tuttavia, Adobe ha migliorato le eVar in cui soddisfano quasi tutti i casi d’uso per le proprietà.

Se hai [documento di progettazione della soluzione](/help/implement/prepare/solution-design.md), puoi allocare queste dimensioni personalizzate ai valori specifici dell’organizzazione. Il numero di proprietà disponibili dipende dal contratto con Adobe. Sono disponibili fino a 75 proprietà se il contratto con Adobe lo supporta.

## Proprietà che utilizzano i tag in Adobe Experience Platform

Puoi impostare le proprietà durante la configurazione dell’estensione Analytics (variabili globali) o in regole.

1. Accedi a [Interfaccia utente per la raccolta dati](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai a [!UICONTROL Rules] , quindi fai clic sulla regola desiderata (o crea una regola).
4. Sotto [!UICONTROL Actions], fai clic su un [!UICONTROL Adobe Analytics - Set Variables] fare clic sull&#39;icona &quot;+&quot;.
5. Imposta la [!UICONTROL Extension] del menu a discesa Adobe Analytics e [!UICONTROL Action Type] a [!UICONTROL Set Variables].
6. Individua il [!UICONTROL Props] sezione .

Puoi impostare una proprietà su un valore o su un elemento dati. Puoi anche copiare il valore da un’altra variabile di Analytics.

## s.prop1 - s.prop75 in AppMeasurement e nell&#39;editor di codice personalizzato

Ogni variabile di proprietà è una stringa che contiene valori personalizzati specifici dell’organizzazione. La loro lunghezza massima è di 100 byte; i valori superiori a 100 byte vengono troncati automaticamente quando inviati ad Adobe.

```js
s.prop1 = "Example custom value";
```

## Proprietà elenco

Le proprietà di elenco sono un’impostazione applicata alle proprietà che consentono alla variabile di contenere più valori nello stesso hit. Se questa impostazione non è abilitata o se viene utilizzato il delimitatore errato, la variabile viene trattata come un singolo valore.

### Configurare le proprietà dell’elenco

Abilitare le proprietà di elenco nelle impostazioni della suite di rapporti. Vedi [Variabili del traffico](/help/admin/admin/c-traffic-variables/traffic-var.md) nella guida utente Admin. Assicurati che il delimitatore desiderato sia configurato correttamente. Adobe non fornisce un delimitatore predefinito.

>[!TIP]
>
>I delimitatori comuni utilizzati nelle implementazioni sono una virgola (`,`), due punti (`:`), punto e virgola (`;`), o tubo (`|`). Puoi utilizzare qualsiasi delimitatore adatto alla tua implementazione.

### Imposta proprietà elenco

Una volta configurate le proprietà di elenco nelle impostazioni della suite di rapporti con il delimitatore desiderato, non vi sono differenze di implementazione diverse dall’utilizzo del delimitatore.

```js
// List prop delimited with a comma
s.prop1 = "value1,value2,value3";
```

>[!IMPORTANT]
>
>Le proprietà di elenco sono ancora soggette alla lunghezza massima di 100 byte. Le proprietà di elenco sono più facili da raggiungere e troncare, poiché possono contenere più valori. Considera l’utilizzo di abbreviazioni o valori di abbreviazione se potresti raggiungere questo limite di 100 byte.

Se imposti lo stesso valore più di una volta in un elenco di proprietà, questi vengono deduplicati nel reporting. Analysis Workspace conta il numero di hit in cui viene visualizzato un valore e non il numero di volte in cui un valore esiste nei dati.
