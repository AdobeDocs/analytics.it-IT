---
title: Versione JavaScript
description: La versione di JavaScript supportata dal browser del visitatore.
feature: Dimensions
source-git-commit: a68e13c9232ef8d975fd1256168a0addf677f5ac
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 5%
---
# Versione JavaScript

La &#39;versione JavaScript&#39; [dimension](overview.md) riporta la versione di JavaScript supportata dal browser del visitatore. Non riporta la versione della libreria AppMeasurement.

>[!IMPORTANT]
>
>Questa dimensione è disponibile solo in Data Warehouse. Se desideri utilizzare la versione di JavaScript in altre soluzioni Analytics, prova a copiare il valore in un [eVar](evar.md) per ogni hit.

## Popolare questa dimensione con i dati

AppMeasurement rileva automaticamente le funzionalità di JavaScript nel browser e invia un valore di versione nel parametro della stringa di query `j`. Nessuna variabile di implementazione da impostare. Questo rilevamento utilizza le etichette di versione legacy di JavaScript; non è una misura completa del supporto delle funzioni ECMAScript moderne.

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | Nessuno (raccolta automatica) |
| **Campo Web SDK / XDM** | [`environment.browserDetails.javaScriptVersion`](/help/implement/aep-edge/xdm-var-mapping.md) |
| **Parametro query** | [`j`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Tag XML** | [`<javaScriptVersion>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Colonna API di inserimento dati in blocco** | [`javaScriptVersion`](https://developer.adobe.com/analytics-collection-apis/methods/bulk-data-insertion/column-reference) |
| **Limite di byte** | 5 byte |
| **Persistenza** | Hit |

## Elementi dimensionali

Gli elementi Dimension includono i valori di versione di JavaScript raccolti dai browser dei visitatori, ad esempio `1.5` e `1.6`.
