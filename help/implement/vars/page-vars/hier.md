---
title: hier
description: Implementa le variabili gerarchiche in Adobe Analytics.
feature: Variables
exl-id: 72bdab8f-a001-4ada-b5e2-453a8e3f24a6
source-git-commit: a71db2fac9333b70a55da91fe9a94b0cc8434b42
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 1%

---

# hier

Le variabili gerarchiche sono variabili personalizzate che consentono di visualizzare la struttura di un sito.

>[!TIP]
>
>Questa variabile era più comune nelle versioni precedenti di Adobe Analytics. Adobe consiglia di utilizzare [eVar](evar.md) e classificazioni.

>[!IMPORTANT]
>
>La gerarchia non è supportata nella raccolta dati che utilizza XDM per Experience Edge.

Questa variabile è utile per i siti con più di tre livelli nella struttura del sito. Ad esempio, un sito multimediale può avere 4 livelli nella sezione Sport: `Sports`, `Local Sports`, `Baseball`e `Team name`. Se qualcuno visita la pagina di baseball, Sport, Sport locali e Baseball, tutti i livelli riflettono quella visita.

Adobe supporta fino a 5 variabili gerarchiche nell’implementazione. Quando la gerarchia è abilitata, decide un delimitatore per la variabile e il numero massimo di livelli per la gerarchia. Ad esempio, se il delimitatore è una virgola, la gerarchia sarà simile alla seguente:

```js
s.hier1 = "Sports,Local Sports,Baseball";
```

Assicurati che nessuno dei nomi di sezione contenga il delimitatore. Ad esempio, se viene chiamata una delle sezioni `Coach Griffin, Jim`, scegli un delimitatore diverso da una virgola. Il limite totale della variabile è di 255 byte. I delimitatori possono essere costituiti da più caratteri, ad esempio `||` o `/|\`, che hanno meno probabilità di apparire nei valori delle variabili.

## Esempi

```js
s.hier1="Toys|Boys 6+|Legos|Super Block Tub";
```

```js
s.hier4="Sports/Local Sports/Baseball";
```
