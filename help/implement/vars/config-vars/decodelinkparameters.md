---
title: decodeLinkParameters
description: Abilita o disabilita le variabili di tracciamento dei collegamenti a doppia codifica di AppMeasurement.
exl-id: 329c521a-b965-4114-93ce-f45f159d4a20
feature: Variables
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 7%

---

# decodeLinkParameters

Il `decodeLinkParameters` la variabile è un valore booleano che determina se le variabili di tracciamento dei collegamenti vengono codificate una volta (se impostato su `true`) o due volte (se impostato su `false`). Ha un impatto solo `linkName` (parte del [`tl()`](../functions/tl-method.md) metodo) e [`linkURL`](linkurl.md). Per utilizzare, è necessario disporre della versione 2.24.0 o successiva di AppMeasurement. Il valore predefinito di questa variabile è `false`.

Nelle versioni dell’AppMeasurement precedenti alla versione 2.24.0, le variabili di tracciamento dei collegamenti erano sempre codificate in URL due volte. Anche se non è un problema per le implementazioni che in genere si basano su caratteri a byte singolo, la doppia codifica ha creato valori codificati in modo errato per i caratteri multibyte nei rapporti. Impostazione di questa variabile su `true` codifica i valori di tracciamento dei collegamenti una volta, che in genere corrisponde al comportamento desiderato.

* Se la tua implementazione utilizza caratteri multibyte e le variabili di tracciamento dei collegamenti sono decodificate in URL per compensare la doppia codifica di AppMeasurement, imposta questa variabile su `false`. Questo valore conserva la funzionalità AppMeasurement esistente.
* Se la tua implementazione utilizza caratteri multibyte e non codifichi i valori di tracciamento dei collegamenti URL, l’Adobe consiglia di impostare questa variabile su `true`.
* Se l’implementazione non utilizza caratteri multibyte, questa variabile non è necessaria. Tuttavia, l’Adobe consiglia di impostare questa variabile su `true` nei casi in cui è possibile inviare caratteri multibyte.

## Doppia codifica dei parametri di collegamento tramite Web SDK

Questa variabile è specifica di AppMeasurement e non è necessaria in alcun tipo di implementazione dell’SDK web.

## Parametri di collegamento di doppia codifica tramite l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## s.decodeLinkParameters in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Il `s.decodeLinkParameters` la variabile è un valore booleano che determina se i valori di tracciamento dei collegamenti hanno doppia codifica. Se questa variabile non è definita, il suo valore predefinito è `false` per mantenere la funzionalità per le implementazioni esistenti. L’Adobe consiglia di impostare questo valore su `true` per tutte le nuove implementazioni, soprattutto se vedi valori codificati URL nei rapporti di tracciamento dei collegamenti.

```js
s.decodeLinkParameters = true;
```
