---
title: decodeLinkParameters
description: Abilita o disabilita le variabili di tracciamento dei collegamenti con doppia codifica AppMeasurement.
exl-id: 329c521a-b965-4114-93ce-f45f159d4a20
feature: Appmeasurement Implementation
role: Admin, Developer
TQID: https://experienceleague.adobe.com/YzBsuWvpzof1f8qqJO5j8wuWvHSWdPomxowisPbkg7E
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 310
ht-degree: 8%

---

# decodeLinkParameters

La variabile `decodeLinkParameters` è un valore booleano che determina se le variabili di tracciamento dei collegamenti vengono codificate una volta (se impostata su `true`) o due (se impostata su `false`). Ha effetto solo su `linkName` (parte del metodo [`tl()`](../functions/tl-method.md)) e [`linkURL`](linkurl.md). Per utilizzare questa versione è necessario disporre di AppMeasurement v2.24.0 o versione successiva. Il valore predefinito di questa variabile è `false`.

Nelle versioni di AppMeasurement precedenti alla versione 2.24.0, le variabili di tracciamento dei collegamenti erano sempre codificate in URL due volte. Anche se non è un problema per le implementazioni che in genere si basano su caratteri a byte singolo, la doppia codifica ha creato valori codificati in modo errato per i caratteri multibyte nei rapporti. Se si imposta questa variabile su `true`, i valori di tracciamento dei collegamenti vengono codificati una volta, che in genere corrisponde al comportamento desiderato.

* Se l&#39;implementazione utilizza caratteri multibyte e le variabili di tracciamento dei collegamenti sono decodificate tramite URL per compensare la doppia codifica di AppMeasurement, imposta questa variabile su `false`. Questo valore mantiene le funzionalità esistenti di AppMeasurement.
* Se la tua implementazione utilizza caratteri multibyte e non utilizzi valori di tracciamento URL decode link, Adobe consiglia di impostare questa variabile su `true`.
* Se l’implementazione non utilizza caratteri multibyte, questa variabile non è necessaria. Tuttavia, Adobe consiglia di impostare questa variabile su `true` nei casi in cui potrebbero essere inviati caratteri multibyte.

## Doppia codifica dei parametri di collegamento tramite Web SDK

Questa variabile è specifica di AppMeasurement e non è necessaria in alcun tipo di implementazione di Web SDK.

## Parametri di collegamento di doppia codifica tramite l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## s.decodeLinkParameters in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La variabile `s.decodeLinkParameters` è un valore booleano che determina se i valori di tracciamento dei collegamenti hanno doppia codifica. Se questa variabile non è definita, il suo valore predefinito è `false` per mantenere la funzionalità per le implementazioni esistenti. Adobe consiglia di impostare questo valore su `true` per tutte le nuove implementazioni, soprattutto se nei rapporti di tracciamento dei collegamenti vengono visualizzati valori codificati in URL.

```js
s.decodeLinkParameters = true;
```
