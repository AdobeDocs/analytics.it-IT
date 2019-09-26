---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Implementazione di Analytics
seo-description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
solution: null
title: Variabili dinamiche
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.dynamicAccountMatch

La variabile utilizza l'oggetto DOM per recuperare la sezione dell'URL a cui vengono applicate tutte le regole in.

Questa variabile è valida solo se *`dynamicAccountSelection`* è impostata su 'True'. Poiché il valore predefinito è [!DNL window.location.host], questa variabile non è necessaria per [!UICONTROL Dynamic Account Selection] funzionare. Per ulteriori informazioni, vedere [dynamicAccountList](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).

Le regole riportate in `dynamicAccountList` vengono applicate al valore di `dynamicAccountMatch`. Se `dynamicAccountMatch` contiene solo [!DNL window.location.host] (impostazione predefinita), le regole in `dynamicAccountList` questione si applicano solo al dominio della pagina.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | N/D | window.location.host |

## Sintassi e valori possibili

La `dynamicAccountMatch` variabile viene generalmente compilata dal consulente Adobe che fornisce AppMeasurement per il file JavaScript. Tuttavia, i valori elencati di seguito possono essere applicati in qualsiasi momento.

```js
s.dynamicAccountMatch=[DOM object]
```

| Descrizione | Valore |
|---|---|
| Dominio (predefinito) | window.location.host |
| Percorso | window.location.pathname |
| Stringa di query | (window.location.search?window.location.search:"?") |
| Dominio e percorso | window.location.host+window.location.pathname |
| Percorso e stringa query | window.location.pathname+(window.location.search?window.location.search:"?") |
| URL completo | window.location.href |

## Esempi

```js
s.dynamicAccountMatch=window.location.pathname
```

```js
s.dynamicAccountMatch=window.location.host+window.location.pathname
```

## Impostazioni di configurazione

Nessuno

## Insidie, domande e suggerimenti

* La selezione di account dinamici non è supportata da [AppMeasurement per JavaScript](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).

* Quando le pagine vengono salvate su un disco rigido, [!DNL window.location.host] è vuota e tali visualizzazioni di pagina vengono inviate alla suite di rapporti predefinita (in `s_account`).

* Quando una pagina viene tradotta tramite un motore di traduzione basato sul Web, come Google, [!UICONTROL Dynamic Account Selection] non funziona correttamente. Per un tracciamento più preciso, compila la [!UICONTROL s_account]variabile lato server.
