---
title: hier
description: Implementa le variabili gerarchiche in Adobe Analytics.
translation-type: tm+mt
source-git-commit: 751d19227d74d66f3ce57888132514cf8bd6f7fc

---


# hier

Le variabili gerarchiche sono variabili personalizzate che consentono di visualizzare la struttura del sito.

Questa variabile è particolarmente utile per i siti con più di tre livelli nella struttura del sito. Ad esempio, un sito multimediale può avere 4 livelli nella sezione Sport: Sport, sport locali, baseball e Red Sox. Se qualcuno visita la pagina di baseball, Sport, Sport e Baseball, tutti i livelli riflettono quella visita.

Sono disponibili cinque [!UICONTROL hierarchy] variabili, che devono essere abilitate dall&#39;Assistenza clienti Adobe. Quando la gerarchia è abilitata, è necessario definire un delimitatore per la variabile e il numero massimo di livelli per la gerarchia. Ad esempio, se il delimitatore è una virgola, la gerarchia sportiva potrebbe essere visualizzata come segue.

```js
s.hier1="Sports,Local Sports,Baseball"
```

Accertatevi che nessuno dei nomi di sezione contenga il delimitatore. Ad esempio, se una delle sezioni è denominata &quot;Coach Griffin, Jim&quot;, è consigliabile scegliere un carattere di delimitazione diverso dalla virgola. Ciascuna sezione gerarchica è limitata a 255 byte, mentre il limite totale della variabile è di 255 byte. Dopo aver selezionato un delimitatore (al momento della creazione della gerarchia), questo non viene facilmente modificato.

Contatta l’Assistenza clienti Adobe per modificare il delimitatore di una gerarchia esistente. I delimitatori possono anche essere costituiti da più caratteri, come|| o /|\, che hanno meno probabilità di apparire in una sezione gerarchica.

## Sintassi e valori possibili

Non inserite uno spazio tra ciascun delimitatore. Nell&#39;esempio seguente, N è un numero compreso tra uno e cinque.

```js
s.hierN="Level 1[<delimiter>Level 2[<delimiter>Level 3[...]]]"
```

Non utilizzate il carattere di delimitazione tranne per delimitare i livelli della gerarchia. Il carattere di delimitazione può essere uno o più caratteri di vostra scelta.

## Esempi

```js
s.hier1="Toys|Boys 6+|Legos|Super Block Tub"
```

```js
s.hier4="Sports/Local Sports/Baseball"
```

## Insidie, domande e suggerimenti

* Il delimitatore non può essere modificato dopo la configurazione della gerarchia. Se il carattere di delimitazione della gerarchia deve essere modificato, contatta l’Assistenza clienti Adobe.
* Il numero di livelli potrebbe non essere modificato dopo la configurazione della gerarchia.

> [!NOTE] Le modifiche alle gerarchie possono determinare un costo di servizio.
