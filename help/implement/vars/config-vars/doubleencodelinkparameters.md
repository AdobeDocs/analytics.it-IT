---
title: doubleEncodeLinkParameters
description: Abilita o disabilita le variabili di tracciamento dei collegamenti a doppia codifica di AppMeasurement.
exl-id: 7a4cea23-5ae6-4a8b-82a6-c68f9a1f9c49
feature: Variables
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 7%

---

# doubleEncodeLinkParameters

Il `doubleEncodeLinkParameters` la variabile è un valore booleano che determina se le variabili di tracciamento dei collegamenti vengono codificate una volta (se impostato su `false`) o due volte (se impostato su `true`). Ha un impatto solo `linkName` (parte del [`tl()`](../functions/tl-method.md) metodo) e [`linkURL`](linkurl.md). Per utilizzare il codice è necessario l’AppMeasurement 2.23, paragrafo 1, o una versione successiva. Il valore predefinito di questa variabile è `true`.

Nelle versioni precedenti di un AppMeasurement, le variabili di tracciamento dei collegamenti erano sempre codificate nell’URL due volte. Anche se non è un problema per le implementazioni che in genere si basano su caratteri a byte singolo, la doppia codifica ha creato valori codificati in modo errato per i caratteri multibyte nei rapporti. Impostazione di questa variabile su `false` codifica i valori di tracciamento dei collegamenti una volta, che in genere corrisponde al comportamento desiderato.

* Se la tua implementazione utilizza caratteri multibyte e le variabili di tracciamento dei collegamenti sono decodificate in URL per compensare la doppia codifica di AppMeasurement, imposta questa variabile su `true`. Questo valore conserva la funzionalità AppMeasurement esistente.
* Se la tua implementazione utilizza caratteri multibyte e non codifichi i valori di tracciamento dei collegamenti URL, l’Adobe consiglia di impostare questa variabile su `false`.
* Se l’implementazione non utilizza caratteri multibyte, questa variabile non è necessaria. Tuttavia, l’Adobe consiglia di impostare questa variabile su `false` nei casi in cui è possibile inviare caratteri multibyte.

## Doppia codifica dei parametri di collegamento tramite Web SDK

Questa variabile è specifica di AppMeasurement e non è necessaria in alcun tipo di implementazione dell’SDK web.

## Parametri di collegamento di doppia codifica tramite l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## s.doubleEncodeLinkParameters in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Il `s.doubleEncodeLinkParameters` la variabile è un valore booleano che determina se i valori di tracciamento dei collegamenti hanno doppia codifica. Se questa variabile non è definita, il suo valore predefinito è `true` per mantenere la funzionalità per le implementazioni esistenti. L’Adobe consiglia di impostare questo valore su `false` per tutte le nuove implementazioni, soprattutto se vedi valori codificati URL nei rapporti di tracciamento dei collegamenti.

```js
s.doubleEncodeLinkParameters = false;
```
