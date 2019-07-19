---
description: Il Generatore di metriche calcolate consente di applicare funzioni statistiche e matematiche per creare metriche calcolate avanzate.
seo-description: Il Generatore di metriche calcolate consente di applicare funzioni statistiche e matematiche per creare metriche calcolate avanzate.
seo-title: Funzioni di base di riferimento
title: Funzioni di base di riferimento
uuid: 5 c 2 b 4 a 0 e -613 c -4 b 27-95 b 8-01 d 480 aeab 78
translation-type: tm+mt
source-git-commit: a4ccd3503d9d8e5e5367bb1ebd149262c5cb925a

---


# Riferimento: funzioni di base

<!-- 

cm_functions.xml

 -->

Il Generatore di metriche calcolate consente di applicare funzioni statistiche e matematiche per creare metriche calcolate avanzate.

Elenco alfabetico delle funzioni e delle relative definizioni.

>[!NOTE]
>
>Where [!DNL metric] is identified as an argument in a function, other expressions of metrics are also allowed. For example, [!DNL MAXV(metrics)] also allows for [!DNL MAXV(PageViews + Visits).]

## Table Functions versus Row Functions {#section_8977BE40A47E4ED79EB543A9703A4905}

Una funzione di tabella è una in cui l'output è uguale per ogni riga della tabella. Una funzione di riga è una in cui l'output è diverso per ogni riga della tabella.

## Absolute Value (Row) {#concept_4CC47884F7CA49D5B84AC898EA596673}

Restituisce il valore assoluto di un numero. Il valore assoluto di un numero è il numero con un valore positivo.

```
ABS(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | La metrica per la quale vuoi il valore assoluto. |

## Column Maximum {#concept_B25518D717D24F82B65CDE49A153D3A3}

Restituisce il valore più elevato in un set di elementi dimensionali per una colonna di metrica. MAXV valuta verticalmente in una singola colonna (metrica) tra gli elementi dimensionali.

```
MAXV(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | Una metrica che vorresti valutare. |

## Column Minimum {#concept_5B1033F8ACE9485F9AD3CDC0D146391B}

Restituisce il valore più piccolo in un set di elementi dimensionali per una colonna di metrica. MINV valuta verticalmente in una singola colonna (metrica) tra gli elementi dimensionali.

```
MINV(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | Una metrica che vorresti valutare. |

## Column Sum {#concept_391F04FBC3CC43368CA0C5AACE74D4B1}

Aggiunge tutti i valori numerici di una metrica all'interno di una colonna (tra gli elementi di una dimensione).

```
SUM(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | La metrica per la quale vuoi il valore totale o la somma. |

## Count (Table) {#concept_2C6ED2B88AB74481BD130969FB071A41}

Restituisce il numero, o il conteggio, di valori non-zero per una metrica all'interno di una colonna (il numero di elementi univoci segnalati all'interno di una dimensione).

```
COUNT(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | La metrica che desideri conteggiare. |

## Exponent (Row) {#concept_17554F9D234449FB8DDEE895816B3FF1}

Returns *e* raised to the power of a given number. The constant *e* equals 2.71828182845904, the base of the natural logarithm. EXP è l'inverso di LN, il logaritmo naturale di un numero.

```
EXP(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | The exponent applied to the base *e*. |

## Exponentiation {#concept_941578534F1E4583B1BEB067C8113A21}

Power Operator

<pre>
pow(x,y) = x<sup>y</sup> = x*x*x*… (y times)
</pre>

## Mean (Table) {#concept_F4FF950580304D0B99DA7FBB5DB8730A}

Restituisce la media aritmetica, o media, per una metrica in una colonna.

```
MEAN(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | La metrica per la quale vuoi la media. |

## Median (Table) {#concept_183EC31208524EDB8463D986DE2E895F}

Restituisce il median per una metrica in una colonna. Il median è il numero nel centro di un insieme di numeri, ovvero metà dei numeri hanno valori maggiore o uguale alla mediana, e metà è minore o uguale al median.

```
MEDIAN(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | La metrica per la quale desideri la mediana. |

## Modulo {#concept_DE0825D7A51643219CB01F59667EA352}

Il resto di col 1/col 2, utilizzando la divisione Euclidea.

Restituisce il resto dopo la divisione x x y.

```
x = floor(x/y) + modulo(x,y)
```

Il valore restituito ha lo stesso segno dell'input (o è zero).

```
modulo(4,3) = 1 
modulo(-4,3) = -1 
modulo(-3,3) = 0
```

Per ottenere sempre un numero positivo, usa

```
modulo(modulo(x,y)+y,y)
```

## Percentile (Table) {#concept_51DF57B606D14F898E5010DBA61CA979}

Restituisce il numero k-esimo percentile di valori per una metrica. Potete utilizzare questa funzione per stabilire una soglia di accettazione. Ad esempio, potete decidere di esaminare gli elementi dimensionali che hanno un punteggio superiore al 90 percentile.

```
PERCENTILE(metric,k)
```

<table id="table_35CD840ACFB44CD9979881DB8823CC53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argomento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metrica</i> </td> 
   <td colname="col2"> La colonna della metrica che definisce la posizione relativa. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>k </p> </td> 
   <td colname="col2"> Il valore percentile compreso tra 0 e 100 incluso. </td> 
  </tr> 
 </tbody> 
</table>

## Quartile (Table) {#concept_BFD37F0F23A24AD181407142233FA151}

Restituisce la porzione quartile di valori per una metrica. Ad esempio, le quariture possono essere utilizzate per trovare i primi 25% prodotti che generano maggior fatturato. MINV, MEDIAN e MAXV restituiscono lo stesso valore di QUARTILE quando quart è uguale a 0 (zero), 2 e 4, rispettivamente.

```
QUARTILE(metric,quart)
```

<table id="table_64EA3DAAE77541439D59FAF0353F83A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argomento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metrica</i> </td> 
   <td colname="col2"> La metrica per la quale vuoi il valore quartile. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>quart </p> </td> 
   <td colname="col2"> Indica quale valore * restituisce. </td> 
  </tr> 
 </tbody> 
</table>

*If *quart* = 0, QUARTILE returns the minimum value. If *quart* = 1, QUARTILE returns the first quartile (25 percentile). If *quart* = 2, QUARTILE returns the first quartile (50 percentile). If *quart* = 3, QUARTILE returns the first quartile (75 percentile). If *quart* = 4, QUARTILE returns the maximum value.

## Turno {#concept_2F12F2A6ACD445A0A8FF648AE4D4CB9E}

Restituisce il numero intero più vicino per un valore specificato. For example, if you want to avoid reporting currency decimals for revenue and a product has $569.34, use the formula Round( *Revenue*) to round revenue to the nearest dollar, or $569. Un rapporto di prodotto $ 569.51 sarà arrotondato al dollaro più vicino, oppure $ 570.

```
ROUND(metric)
```

| Argomento | Descrizione |
|---|---|
| *numero* | La metrica da arrotondare. |

Round senza parametro cifre è uguale a round con un parametro di cifre pari a 0, ovvero arrotondato al numero intero più vicino. Con un parametro cifre, restituisce il numero di cifre a destra del decimale. Se le cifre sono negative, restituisce 0 a sinistra del decimale.

```
round( 314.15, 0) = 314 
round( 314.15, 1) = 314.1 
round( 314.15, -1) = 310 
round( 314.15, -2) = 300
```

## Row Count {#concept_0DBF5995881C47CF95F793125F3A0E2B}

Restituisce il numero di righe per una determinata colonna (il numero di elementi univoci segnalati all'interno di una dimensione). «Monoques superato» viene conteggiato come 1.

## Row Max {#concept_984D045D7EDD4A1ABED454CDF2EC23C5}

Il massimo delle colonne di ciascuna riga.

## Row Min {#concept_A6FB9E72C70A43D0B31565E70B8122BD}

Il minimo delle colonne in ciascuna riga.

## Row Sum {#concept_E9EAB0FC5233498F907E7A078698A98E}

La somma delle colonne di ciascuna riga.

## Square Root (Row) {#concept_6460DFA51EC24527A2317970FB76D404}

Restituisce la radice quadrata positiva di un numero. La radice quadrata di un numero è il valore di quel numero elevato alla potenza di 1/2.

```
SQRT(metric)
```

| Argomento | Descrizione |
|---|---|
| *numero* | La metrica per la quale vuoi la radice quadrata. |

## Standard Deviation (Table) {#concept_A383A8BCC6FA42D7B73F7C83997D782A}

Restituisce la deviazione standard, o radice quadrata della varianza, in base a una popolazione di dati di esempio.

L'equazione per STDEV è:

![](assets/std_dev.png)

where x is the sample mean (*metric*) and *n* is the sample size.

```
STDEV(metric)
```

<table id="table_8BCF2E4B02434AABAAD026FB3C4E8B2F"> 
 <tbody> 
  <tr> 
   <td> <b> Argomento</b> </td> 
   <td> <b> Descrizione</b> </td> 
  </tr> 
  <tr> 
   <td> <b><i> metrica</i></b> </td> 
   <td> <p> Metrica per la deviazione standard. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variance (Table) {#concept_269751EDC5A34E689112AE16E04A11B0}

Restituisce la varianza in base a una popolazione di dati di esempio.

L'equazione per VARIANCE è:

![](assets/variance_eq.png)

where x is the sample mean, MEAN(*metric*), and *n* is the sample size.

```
VARIANCE(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | La metrica per la quale vuoi la varianza. |

Per calcolare una varianza si osserva un'intera colonna di numeri. Da tale elenco di numeri viene calcolato per la prima volta la media. Una volta raggiunta la media, eseguite ogni voce ed effettuate le seguenti operazioni:

1. Sottrae la media dal numero.

2. Quadrato il risultato.

3. Aggiungetelo al totale.

Una volta effettuato l'iterazione sull'intera colonna, si ottiene un totale. La dividete in base al numero di elementi nella colonna. Tale numero corrisponde alla varianza della colonna. È un numero unico. Viene invece visualizzata come una colonna di numeri.

Ad esempio, supponiamo che sia presente una colonna di tre elementi:

1

2

3

La media di questa colonna è 2. La varianza della colonna sarà ((1 - 2) ² + (2 - 2) ² + (3 - 2) ²/3 = 2/3. In Analisi ad hoc questo aspetto sarà simile al seguente:

1 2/3

2 2/3

3 2/3
