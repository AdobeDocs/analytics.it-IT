---
title: hier
description: Implementa le variabili gerarchiche in Adobe Analytics.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# hier

Le variabili gerarchiche sono variabili personalizzate che consentono di visualizzare la struttura del sito.

>[!TIP] Questa variabile era più comune nelle versioni precedenti di Adobe Analytics. Adobe consiglia di utilizzare [eVar](evar.md) e classificazioni.

Questa variabile è utile per i siti con più di tre livelli nella struttura del sito. Ad esempio, un sito multimediale può avere 4 livelli nella sezione Sport: `Sports`, `Local Sports`, `Baseball`e `Team name`. Se qualcuno visita la pagina di baseball, Sport, Sport e Baseball, tutti i livelli riflettono quella visita.

Adobe supporta fino a 5 variabili gerarchiche nell’implementazione. Al momento dell&#39;abilitazione della gerarchia, scegliere un delimitatore per la variabile e il numero massimo di livelli per la gerarchia. Ad esempio, se il carattere di delimitazione è una virgola, la gerarchia sarà simile a quella riportata di seguito:

```js
s.hier1 = "Sports,Local Sports,Baseball";
```

Accertatevi che nessuno dei nomi di sezione contenga il carattere di delimitazione. Ad esempio, se una delle sezioni è denominata `Coach Griffin, Jim`, scegliete un carattere di delimitazione diverso da una virgola. Il limite totale della variabile è di 255 byte. I delimitatori possono essere costituiti da più caratteri, ad esempio `||` o `/|\`, con minore probabilità visualizzati nei valori delle variabili.

## Esempi

```js
s.hier1="Toys|Boys 6+|Legos|Super Block Tub";
```

```js
s.hier4="Sports/Local Sports/Baseball";
```
