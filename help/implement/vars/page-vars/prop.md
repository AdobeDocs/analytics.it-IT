---
title: prop
description: Variabili personalizzate che puoi utilizzare nell’implementazione.
feature: Variables
exl-id: 0d0ff8cd-1d8c-4263-866d-e51ad66148b0
source-git-commit: 17b5185e5358d661157c20a2504cacdbd4a2cc3d
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 18%

---

# prop

*Questa pagina della guida descrive come implementare prop. Per informazioni sul funzionamento delle proprietà come dimensione, consulta [prop](/help/components/dimensions/prop.md) nella guida utente Componenti.*

Le proprietà sono variabili personalizzate che puoi utilizzare come desideri. Non persistono oltre l’hit impostato.

>[!TIP]
>
>L’Adobe consiglia di utilizzare [eVar](evar.md) nella maggior parte dei casi. Nelle versioni precedenti di Adobe Analytics, prop e eVar presentavano vantaggi e svantaggi l’uno per l’altro. Tuttavia, Adobe ha migliorato le eVar in modo da soddisfare quasi tutti i casi d’uso per prop.

Se si dispone di [documento di progettazione della soluzione](/help/implement/prepare/solution-design.md), puoi allocare queste dimensioni personalizzate a valori specifici dell’organizzazione. Il numero di prop disponibili dipende dal contratto con Adobe. Se il contratto con Adobe lo supporta, sono disponibili fino a 75 proprietà.

## Proprietà che utilizzano l’SDK web

Le proprietà sono [mappato per Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=it) nei campi XDM `_experience.analytics.customDimensions.props.prop1` a `_experience.analytics.customDimensions.props.prop75`. Le prop elenco vengono specificate in un set separato di campi.

## Proprietà tramite l’estensione Adobe Analytics

Puoi impostare le proprietà sia durante la configurazione dell’estensione Analytics (variabili globali) sia nelle regole.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata (o crea una regola).
4. Nella sezione [!UICONTROL Actions], fai clic su un’azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull’icona “+”.
5. Scegli Adobe Analytics nel menu a discesa [!UICONTROL Extension] e imposta [!UICONTROL Action Type] su [!UICONTROL Set Variables].
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

Abilita prop elenco in [Variabili traffico](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md) in impostazioni suite di rapporti. Assicurati che il delimitatore desiderato sia configurato correttamente. L&#39;Adobe non fornisce un delimitatore predefinito.

>[!TIP]
>
>I delimitatori comuni utilizzati nelle implementazioni sono una virgola (`,`), due punti (`:`), punto e virgola (`;`) o pipe (`|`). Puoi utilizzare qualsiasi delimitatore ASCII non esteso che meglio si adatta alla tua implementazione.

### Impostare le prop elenco tramite Web SDK

Dopo aver configurato le prop elenco nelle impostazioni della suite di rapporti con il delimitatore desiderato, le prop elenco vengono mappate per Adobe Analytics in `_experience.analytics.customDimensions.listProps.prop1.values[]` a `_experience.analytics.customDimensions.listProps.prop75.values[]`. L’SDK per web utilizza automaticamente il delimitatore corretto elencato in Impostazioni della suite di rapporti. Se imposti il delimitatore nel campo XDM (ad esempio, `_experience.analytics.customDimensions.props.prop1.delimiter`), che sostituisce il delimitatore recuperato automaticamente dalle impostazioni della suite di rapporti e può causare un’analisi errata della stringa prop dell’elenco.

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
