---
description: Il Generatore di metriche calcolate consente di applicare funzioni statistiche e matematiche per generare metriche calcolate avanzate.
title: Funzioni di base di riferimento
feature: Calculated Metrics
exl-id: 1a49435c-96d1-4617-bd1a-a5d3b74e3ebd
source-git-commit: f4032ac06c9057635dd0526ad046c4640c6350bf
workflow-type: tm+mt
source-wordcount: '1047'
ht-degree: 95%

---

# Riferimento: funzioni di base

Il Generatore di metriche calcolate consente di applicare funzioni statistiche e matematiche per generare metriche calcolate avanzate.

Di seguito è riportato un elenco alfabetico delle funzioni e delle relative definizioni.

>[!NOTE]
>
>Se [!DNL metric] è identificato come argomento in una funzione, sono consentite anche altre espressioni di metriche. Ad esempio, [!DNL MAXV(metrics)] consente anche [!DNL MAXV(PageViews + Visits)].

## Funzioni tabella e funzioni riga {#section_8977BE40A47E4ED79EB543A9703A4905}

Una funzione tabella è una funzione in cui l’output è lo stesso per ogni riga della tabella. Una funzione riga è una funzione in cui l’output è diverso per ogni riga della tabella.

## Valore assoluto (riga) {#concept_4CC47884F7CA49D5B84AC898EA596673}

Restituisce il valore assoluto di un numero. Il valore assoluto di un numero è il numero con un valore positivo.

```
ABS(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | La metrica della quale desideri il valore assoluto. |

## Massimo colonna {#concept_B25518D717D24F82B65CDE49A153D3A3}

Restituisce il valore più grande in un insieme di elementi dimensionali della colonna di una metrica. MAXV valuta verticalmente all’interno di una singola colonna (metrica) tra gli elementi dimensionali.

```
MAXV(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | Una metrica che desideri valutare. |

## Minimo colonna {#concept_5B1033F8ACE9485F9AD3CDC0D146391B}

Restituisce il valore più piccolo in un insieme di elementi dimensionali della colonna di una metrica. MINV valuta verticalmente all’interno di una singola colonna (metrica) tra gli elementi dimensionali.

```
MINV(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | Una metrica che desideri valutare. |

## Somma colonna {#concept_391F04FBC3CC43368CA0C5AACE74D4B1}

Somma tutti i valori numerici di una metrica all’interno di una colonna (negli elementi di una dimensione).

```
SUM(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | La metrica della quale desideri il valore totale o la somma. |

## Conteggio (tabella) {#concept_2C6ED2B88AB74481BD130969FB071A41}

Restituisce il numero, o conteggio, di valori diversi da zero di una metrica all’interno di una colonna (il numero di elementi univoci riportati all’interno di una dimensione).

```
COUNT(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | La metrica che desideri conteggiare. |

## Esponente (riga) {#concept_17554F9D234449FB8DDEE895816B3FF1}

Restituisce *e* elevato alla potenza di un numero specificato. La costante *e* è uguale a 2,71828182845904, la base del logaritmo naturale. EXP è l’inverso di LN, il logaritmo naturale di un numero.

```
EXP(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | L’esponente applicato alla base *e*. |

## Esponenziazione {#concept_941578534F1E4583B1BEB067C8113A21}

Operatore di potenza

```
pow(x,y) = x<sup>y</sup> = x*x*x*… (y times)
```

## Media (tabella) {#concept_F4FF950580304D0B99DA7FBB5DB8730A}

Restituisce la media aritmetica, o media, di una metrica in una colonna.

```
MEAN(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | La metrica di cui desideri la media. |

## Mediana (tabella) {#concept_183EC31208524EDB8463D986DE2E895F}

Restituisce la mediana di una metrica in una colonna. La mediana è il numero nel mezzo di un insieme di numeri, ovvero metà dei numeri ha valori che sono maggiori o uguali alla mediana, e metà sono minori o uguali alla mediana.

```
MEDIAN(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | La metrica di cui desideri la mediana. |

## Modulo {#concept_DE0825D7A51643219CB01F59667EA352}

Il resto di col1 / col2, utilizzando la divisione euclidea.

Restituisce il resto dopo aver diviso x per y.

```
x = floor(x/y) + modulo(x,y)
```

Il valore restituito ha lo stesso segno dell’input (o è zero).

```
modulo(4,3) = 1 
modulo(-4,3) = -1 
modulo(-3,3) = 0
```

Per ottenere sempre un numero positivo, utilizza

```
modulo(modulo(x,y)+y,y)
```

## Percentile (tabella) {#concept_51DF57B606D14F898E5010DBA61CA979}

Restituisce il k-esimo percentile dei valori di una metrica. Puoi utilizzare questa funzione per stabilire una soglia di accettazione. Ad esempio, puoi decidere di esaminare gli elementi dimensionali con un punteggio superiore al 90 percentile.

```
PERCENTILE(metric,k)
```

| Argomento | Descrizione |
| --- | --- |
| *metrica* | La colonna della metrica che definisce la condizione relativa. |
| *k* | Il valore percentile compreso tra 0 e 100 incluso. |

## Quartile (tabella) {#concept_BFD37F0F23A24AD181407142233FA151}

Restituisce il quartile dei valori di una metrica. Ad esempio, i quartili possono essere utilizzati per trovare il 25% dei prodotti che generano maggiori ricavi. MINV, MEDIAN e MAXV restituiscono lo stesso valore di QUARTILE quando il quarto è uguale rispettivamente a 0 (zero), 2 e 4.

```
QUARTILE(metric,quart)
```

| Argomento | Descrizione |
| --- | --- |
| *metrica* | La metrica di cui desideri il valore del quartile. |
| *quarto* | Indica il valore* da restituire. |

&#42;Se *quarto* = 0, QUARTILE restituisce il valore minimo. Se *quarto* = 1, QUARTILE restituisce il primo quartile (25 percentile). Se *quarto* = 2, QUARTILE restituisce il primo quartile (50 percentile). Se *quarto* = 3, QUARTILE restituisce il primo quartile (75 percentile). Se *quarto* = 4, QUARTILE restituisce il valore massimo.

## Arrotondamento {#concept_2F12F2A6ACD445A0A8FF648AE4D4CB9E}

Restituisce il numero intero più vicino a un determinato valore. Ad esempio, se desideri evitare di riportare i decimali della valuta per le entrate e un prodotto ha 569,34 $, utilizza la formula Round(*Entrate*) per arrotondare le entrate al dollaro più vicino, cioè 569 $. Un prodotto che riporta 569,51 $ sarà arrotondato al dollaro più vicino, cioè 570 $.

```
ROUND(metric)
```

| Argomento | Descrizione |
|---|---|
| *numero* | La metrica che desideri arrotondare. |

L’arrotondamento senza un parametro di cifre è uguale all’arrotondamento con un parametro di cifre pari a 0, vale a dire arrotondato al numero intero più vicino. Con un parametro di cifre restituisce quel numero di cifre a destra del decimale. Se la cifra è negativa, restituisce quel numero di 0 a sinistra del decimale.

```
round( 314.15, 0) = 314
round( 314.15, 1) = 314.1
round( 314.15, -1) = 310
round( 314.15, -2) = 300
```

## Conteggio righe {#concept_0DBF5995881C47CF95F793125F3A0E2B}

Restituisce il numero di righe di una colonna specificata (il numero di elementi univoci riportati all’interno di una dimensione). “Univoci superati” viene conteggiato come 1.

## Massimo riga {#concept_984D045D7EDD4A1ABED454CDF2EC23C5}

Il massimo delle colonne in ogni riga.

## Minimo riga {#concept_A6FB9E72C70A43D0B31565E70B8122BD}

Il minimo delle colonne in ogni riga.

## Somma righe {#concept_E9EAB0FC5233498F907E7A078698A98E}

La somma delle colonne di ogni riga.

## Radice quadrata (riga) {#concept_6460DFA51EC24527A2317970FB76D404}

Restituisce la radice quadrata positiva di un numero. La radice quadrata di un numero è il valore di quel numero elevato alla potenza di 1/2.

```
SQRT(metric)
```

| Argomento | Descrizione |
| --- | --- |
| *numero* | La metrica della quale desideri la radice quadrata. |

## Deviazione standard (tabella) {#concept_A383A8BCC6FA42D7B73F7C83997D782A}

Restituisce la deviazione standard, o radice quadrata della varianza, in base a una popolazione di dati campione.

L’equazione per STDEV è:

![](assets/std_dev.png)

Dove *x* è il valore di ciascun campione (*metrica*), *x̄* è la popolazione media e *n* è la dimensione della popolazione.

```
STDEV(metric)
```

| Argomento | Descrizione |
| --- | --- |
| *metrica* | La metrica di cui desideri la deviazione standard. |

## Varianza (tabella) {#concept_269751EDC5A34E689112AE16E04A11B0}

Restituisce la varianza in base a una popolazione di dati campione.

L’equazione per VARIANCE è:

![](assets/variance_eq.png)

Dove *x* è il valore di ciascun campione (*metrica*), *x̄* è la popolazione media e *n* è la dimensione della popolazione.

```
VARIANCE(metric)
```

| Argomento | Descrizione |
| --- | --- |
| *metrica* | La metrica di cui desideri la varianza. |

Per calcolare una varianza, si considera un’intera colonna di numeri. Di tale elenco di numeri si calcola prima la media. Una volta ottenuta la media, si esamina ogni voce e si effettuano le seguenti operazioni:

1. Si sottrae la media dal numero.
1. Si eleva al quadrato il risultato.
1. Si aggiunge al totale.

Dopo aver ripetuto per l’intera colonna, si ottiene un singolo totale. Si divide quindi il totale per il numero di elementi nella colonna. Tale numero è la varianza della colonna. È un singolo numero. Viene tuttavia visualizzato come una colonna di numeri.

Ad esempio, supponiamo che sia presente una colonna con tre elementi:

1

2

3

La media di questa colonna è 2. La varianza per la colonna sarà ((1 - 2)<sup>2</sup> + (2 - 2)<sup>2</sup> + (3 - 2)<sup>2</sup>/3 = 2/3.
