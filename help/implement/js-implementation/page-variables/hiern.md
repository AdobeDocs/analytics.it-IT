---
description: Le variabili di pagina popolano direttamente un report, ad esempio pageName, List Props, List Variables e così via.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variabili di pagina
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 45642bdbe18627caa20b1def6443f1e596a41f52

---



# hierN

La [!UICONTROL hierarchy] variabile determina la posizione di una pagina nella gerarchia del sito.

<!-- 

hierN.xml

 -->

Questa variabile è particolarmente utile per i siti con più di tre livelli nella struttura del sito. Ad esempio, un sito multimediale può avere 4 livelli nella sezione Sport: Sport, sport locali, baseball e Red Sox. Se qualcuno visita la pagina di baseball, Sport, Sport e Baseball, tutti i livelli riflettono quella visita.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| 255 byte | H1-H5 | Gerarchia | "" |

Sono disponibili cinque [!UICONTROL hierarchy] variabili, che devono essere abilitate dall'Assistenza clienti Adobe. Quando la gerarchia è abilitata, è necessario definire un delimitatore per la variabile e il numero massimo di livelli per la gerarchia. Ad esempio, se il delimitatore è una virgola, la gerarchia sportiva potrebbe essere visualizzata come segue.

```js
s.hier1="Sports,Local Sports,Baseball"
```

Accertatevi che nessuno dei nomi di sezione contenga il delimitatore. Ad esempio, se una delle sezioni è denominata "Coach Griffin, Jim", è consigliabile scegliere un carattere di delimitazione diverso dalla virgola. Ciascuna sezione gerarchica è limitata a 255 byte, mentre il limite totale della variabile è di 255 byte. Dopo aver selezionato un delimitatore (al momento della creazione della gerarchia), questo non viene facilmente modificato.

Contatta l’Assistenza clienti Adobe per modificare il delimitatore di una gerarchia esistente. I delimitatori possono anche essere costituiti da più caratteri, come|| o /|\, che hanno meno probabilità di apparire in una sezione gerarchica.

**Sintassi e valori** possibili {#section_0739948A68A2420DAB1CBEA3115A5A66}

Non inserite uno spazio tra ciascun delimitatore. Nell'esempio seguente, N è un numero compreso tra uno e cinque.

```js
s.hierN="Level 1[<delimiter>Level 2[<delimiter>Level 3[...]]]"
```

Non utilizzate il carattere di delimitazione tranne per delimitare i livelli della gerarchia. Il carattere di delimitazione può essere uno o più caratteri di vostra scelta.

**Esempi** {#section_38E0929F88DD45B6ACDF473DF155971D}

```js
s.hier1="Toys|Boys 6+|Legos|Super Block Tub"
```

```js
s.hier4="Sports/Local Sports/Baseball"
```

**Impostazioni** di configurazione {#section_E823FB3CAD744D2480EBCE2DF9B134CC}

Nessuno

**Insidie, domande e suggerimenti**{#section_104E5BD320764BDEA5FA8D13A70C78E3}

* Il delimitatore non può essere modificato dopo la configurazione della gerarchia. Se il carattere di delimitazione della gerarchia deve essere modificato, contatta l’Assistenza clienti Adobe.
* Il numero di livelli potrebbe non essere modificato dopo la configurazione della gerarchia.

> [!NOTE] Le modifiche alle gerarchie possono determinare un costo di servizio.

