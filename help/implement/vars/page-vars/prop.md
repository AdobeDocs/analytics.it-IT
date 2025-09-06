---
title: prop
description: Variabili personalizzate che puoi utilizzare nell’implementazione.
feature: Appmeasurement Implementation
exl-id: 0d0ff8cd-1d8c-4263-866d-e51ad66148b0
role: Admin, Developer
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '603'
ht-degree: 13%

---

# prop

*Questa pagina della guida descrive come implementare prop. Per informazioni sul funzionamento di prop come dimensione, vedere [prop](/help/components/dimensions/prop.md) nella guida utente Componenti.*

Le proprietà sono variabili personalizzate che puoi utilizzare come desideri. Non persistono oltre l’hit impostato.

>[!TIP]
>
>Adobe consiglia di utilizzare [eVar](evar.md) nella maggior parte dei casi. Nelle versioni precedenti di Adobe Analytics, prop e eVar presentavano vantaggi e svantaggi l’uno per l’altro. Tuttavia, Adobe ha migliorato le eVar al punto che ora soddisfano quasi tutti i casi d’uso per prop.

Se hai un [documento di progettazione della soluzione](/help/implement/prepare/solution-design.md), puoi allocare queste dimensioni personalizzate a valori specifici della tua organizzazione. Il numero di prop disponibili dipende dal contratto con Adobe. Se il contratto con Adobe lo supporta, sono disponibili fino a 75 proprietà.

## Proprietà che utilizzano il Web SDK

Le proprietà sono mappate alle seguenti variabili:

* [Oggetto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `xdm._experience.analytics.customDimensions.props.prop1` - `xdm._experience.analytics.customDimensions.props.prop75` - le prop elenco sono specificate in [un set separato di campi](#list-props-web-sdk).
* [Oggetto dati](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.prop1` - `data.__adobe.analytics.prop75`; o `data.__adobe.analytics.c1` - `data.__adobe.analytics.c75` - prop elenco inclusi in questi campi.

## Proprietà tramite l’estensione Adobe Analytics

Puoi impostare le proprietà sia durante la configurazione dell’estensione Analytics (variabili globali) sia nelle regole.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata (o crea una regola).
4. Nella sezione [!UICONTROL Actions], fai clic su un’azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull’icona “+”.
5. Impostare l&#39;elenco a discesa [!UICONTROL Extension] su Adobe Analytics e [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individua la sezione [!UICONTROL Props].

Puoi impostare una proprietà su un valore o su un elemento dati. Puoi anche copiare il valore da un’altra variabile di Analytics.

## s.prop1 - s.prop75 in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Ogni variabile prop è una stringa che contiene valori personalizzati specifici dell’organizzazione. La loro lunghezza massima è di 100 byte; i valori superiori a 100 byte vengono troncati automaticamente quando sono inviati ad Adobe.

```js
s.prop1 = "Example custom value";
```

## Prop elenco

Le prop elenco sono un’impostazione applicata alle prop che consente alla variabile di contenere più valori nello stesso hit. Se questa impostazione non è abilitata o se si utilizza un delimitatore errato, la variabile viene trattata come un singolo valore.

### Configurare le prop elenco

Abilita le prop elenco in [Variabili traffico](/help/admin/tools/manage-rs/edit-settings/c-traffic-variables/traffic-var.md) nelle impostazioni della suite di rapporti. Assicurati che il delimitatore desiderato sia configurato correttamente. Adobe non fornisce un delimitatore predefinito.

>[!TIP]
>
>I delimitatori comuni utilizzati nelle implementazioni sono virgola (`,`), due punti (`:`), punto e virgola (`;`) o barra verticale (`|`). Puoi utilizzare qualsiasi delimitatore ASCII non esteso che meglio si adatta alla tua implementazione.

### Impostare le prop elenco tramite Web SDK {#list-props-web-sdk}

Se si utilizza l&#39;[**oggetto XDM**](/help/implement/aep-edge/xdm-var-mapping.md), le prop elenco sono mappate a `xdm._experience.analytics.customDimensions.listProps.prop1.values[]` - `xdm._experience.analytics.customDimensions.listProps.prop75.values[]`. Il Web SDK utilizza automaticamente il delimitatore corretto elencato nelle impostazioni della suite di rapporti. Se imposti il delimitatore nel campo XDM (ad esempio, `xdm._experience.analytics.customDimensions.props.prop1.delimiter`), questo sovrascrive il delimitatore recuperato automaticamente dalle impostazioni della suite di rapporti e può causare un&#39;analisi errata della stringa prop dell&#39;elenco.

Se utilizzi l&#39;[**oggetto dati**](/help/implement/aep-edge/data-var-mapping.md), le prop elenco utilizzano gli stessi campi delle prop standard e seguono la sintassi AppMeasurement.

### Impostare le prop elenco tramite l’estensione Adobe Analytics e AppMeasurement

Una volta configurate le prop elenco nelle impostazioni della suite di rapporti con il delimitatore desiderato, non ci sono differenze di implementazione se non utilizzando il delimitatore.

```js
// List prop delimited with a comma
s.prop1 = "value1,value2,value3";
```

>[!IMPORTANT]
>
>Le prop elenco sono ancora soggette alla lunghezza massima di 100 byte. Le prop elenco sono più facili da raggiungere e da troncare, in quanto possono contenere più valori. Valuta l’utilizzo di abbreviazioni o valori abbreviati se potresti raggiungere questo limite di 100 byte.

Se imposti lo stesso valore più di una volta in una prop elenco, vengono deduplicati nel reporting. Analysis Workspace conta il numero di hit in cui viene visualizzato un valore e non il numero di volte in cui un valore esiste nei dati.
