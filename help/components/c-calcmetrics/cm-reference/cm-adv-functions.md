---
description: Accedere a queste funzioni selezionando Mostra avanzate nell'elenco a discesa Funzioni.
seo-description: Accedere a queste funzioni selezionando Mostra avanzate nell'elenco a discesa Funzioni.
seo-title: Riferimento funzioni avanzate
title: Riferimento funzioni avanzate
uuid: 7 d 1071 b 9-1737-4 b 7 c-b 318-87907 dae 5619
translation-type: tm+mt
source-git-commit: ff46935f6ec38c8981e4a1fffdbdc637bdf557db

---


# Riferimento: funzioni avanzate

<!-- 

cm_adv_functions.xml

 -->

Access these functions by checking **[!UICONTROL Show Advanced]** in the **[!UICONTROL Functions]** drop-down list.

## Table Functions versus Row Functions {#section_8977BE40A47E4ED79EB543A9703A4905}

Una funzione di tabella è una in cui l'output è uguale per ogni riga della tabella. Una funzione di riga è una in cui l'output è diverso per ogni riga della tabella.

## What does the Include-Zeros parameter mean? {#section_C7A2B05929584C65B308FD372CB8E8E3}

Indica se includere gli zeri nel calcolo. A volte zero indica "niente", ma a volte è importante.

Ad esempio, se hai una metrica Revenue (Entrate) e quindi aggiungi una metrica Page Views (Visualizzazioni pagina) al rapporto, per i ricavi che sono tutti zero vengono visualizzate più righe. Probabilmente non si desidera che questo influisca su MEDIA, MIN, QUARTILE ecc. i calcoli presenti nella colonna delle entrate. In questo caso, controllate il parametro includi-zeri.

D'altra parte, in presenza di due metriche a cui siete interessati, potrebbe non essere più facile dire che una delle righe è più alta o minima perché alcune delle righe erano zero, pertanto non dovrete controllare il parametro per includere gli zeri.

## AND {#concept_E14513FE464F4491AD0D4130D4EE621C}

Restituisce il valore del relativo argomento. Utilizzate NOT per evitare che un valore sia uguale a un valore particolare.

>[!NOTE]
>
>0 (zero) indica Falso e qualsiasi altro valore è True.

```
AND(logical_test1,[logical_test2],...)
```

| Argomento | Descrizione |
|---|---|
| *logical_ test 1* | Obbligatorio. Qualsiasi valore o espressione che può essere valutata su TRUE o FALSE. |
| *logical_ test 2* | Facoltativo. Condizioni ulteriori da valutare come TRUE o FALSE |

## Approximate Count Distinct (dimension) {#concept_000776E4FA66461EBA79910B7558D5D7}

Restituisce il numero approssimativo di elementi dimensionali per la dimensione selezionata. La funzione utilizza il metodo hypegglog (HLL) per approssimare i conteggi diversi.È configurato per garantire che il valore sia compreso entro il 5% del valore effettivo dell'ora.

```
Approximate Count Distinct (dimension)
```

| Argomento |  |
|---|---|
| *dimension* | La dimensione per la quale desiderate approssimare il conteggio degli elementi distinto. |

## Example Use Case {#section_424E3FC5092948F0A9D655F6CCBA0312}

Approximate Count Distinct (Customer ID evar) è un caso d'uso comune per questa funzione.

Definizione per una nuova metrica Calculated Ate Customers (Punteggio approssimativo):

![](assets/approx-count-distinct.png)

Questo è il modo in cui la metrica "Approssimati clienti" può essere utilizzata nei rapporti:

![](assets/approx-customers.png)

## Uniques Exceeded {#section_9C583858A9F94FF7BA054D1043194BAA}

Like Count() and RowCount(), Approximate Count Distinct() is subject to ["uniques exceeded" limits](https://marketing.adobe.com/resources/help/en_US/reference/metrics_uniques_high_numbers.html). Se viene raggiunto il limite «superato» entro un mese particolare per una dimensione, il valore viene conteggiato come elemento di dimensione 1.

## Comparing Count Functions {#section_440FB8FB44374459B2C6AE2DA504FC0B}

Approximate Count Distinct () è un miglioramento rispetto alle funzioni Count () e rowcount () perché la metrica creata può essere utilizzata in qualsiasi rapporto dimensionale per rappresentare un conteggio approssimativo di elementi per una dimensione separata. Ad esempio, un numero di ID cliente utilizzati in un rapporto Tipo dispositivo mobile.

Questa funzione sarà marginalmente meno accurata di Count () e rowcount () perché utilizza il metodo HLL, mentre Count () e rowcount () sono conteggio esatto.

## Arc Cosine (Row) {#concept_1DA3404F3DDE4C6BAF3DBDD655D79C7B}

Restituisce l'arcseno, o inverso del coseno, di una metrica. L'arccoseno è l'angolo il cui coseno è numerico. L'angolo restituito è espresso in radianti compresi tra 0 (zero) e pi. Se desiderate convertire il risultato dai radianti in gradi, moltiplicatelo di 180/PI ().

```
ACOS(metric)
```

| Argomento |  |
|---|---|
| *metrica* | Il coseno dell'angolo desiderato da -1 a 1. |

## Arc Sine (Row) {#concept_90F00DEC46BA47F8A21493647D9668CD}

Restituisce il seno d'arco, o sinudiseno inversa, di un numero. Il seno arcetto è l'angolo il cui seno è numerico. L'angolo restituito è espresso in radianti nell'intervallo -pi/2 a pi/2. Per esprimere il seno espresso in gradi, moltiplicate il risultato di 180/PI ().

```
ASIN(metric) 
```

| Argomento |  |
|---|---|
| *metrica* | Il coseno dell'angolo desiderato da -1 a 1. |

## Arc Tangent (Row) {#concept_3408520673774A10998E9BD8B909E90C}

Restituisce la tangente arctangent o inversa di un numero. L'arctangent è l'angolo la cui tangente è numerica. L'angolo restituito è espresso in radianti nell'intervallo -pi/2 a pi/2. Per esprimere l'arctingent in gradi, moltiplicate il risultato di 180/PI ().

```
ATAN(metric)
```

| Argomento |  |
|---|---|
| *metrica* | Il coseno dell'angolo desiderato da -1 a 1. |

## Exponential Regression: Predicted Y (Row) {#concept_25615693312B4A7AB09A2921083502AD}

Calcola i valori y previsti (metrica_ Y), in base ai valori x noti (metriche_ X) utilizzando il metodo «less quadrati» per calcolare la riga di adattamento ottimale in base alla proprietà.

```
ESTIMATE.EXP(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_ X* | Una metrica che desideri designare come dati dipendenti. |
| *metric_ Y* | Una metrica da designare come dati indipendenti. |

## Cdf-T {#concept_4E2F2673532A48B5AF786521DE428A66}

Restituisce la percentuale di valori nella distribuzione t-distribution dello studente con n gradi di libertà con un punteggio z minore di x.

```
cdf_t( -∞, n ) = 0 
cdf_t(  ∞, n ) = 1 
cdf_t( 3, 5 ) ? 0.99865 
cdf_t( -2, 7 ) ? 0.0227501 
cdf_t( x, ∞ ) ? cdf_z( x )
```

## Cdf-Z {#concept_99C97ACC40A94FADBCF7393A17BC2D12}

Restituisce la percentuale di valori in una distribuzione normale con un punteggio z minore di x.

```
cdf_z( -∞ ) = 0 
cdf_z( ∞ ) = 1 
cdf_z( 0 ) = 0.5 
cdf_z( 2 ) ? 0.97725 
cdf_z( -3 ) ? 0.0013499 
 
```

## Ceiling (Row) {#concept_A14CDB1E419B4AA18D335E5BA2548346}

Restituisce il numero intero più piccolo non inferiore a un valore specificato. For example, if you want to avoid reporting currency decimals for revenue and a product has $569.34, use the formula CEILING( *Revenue*) to round revenue up to the nearest dollar, or $570.

```
CEILING(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | La metrica da arrotondare. |

## Cosine (Row) {#concept_DD07AA1FB08145DC89B69D704545FD0A}

Restituisce il coseno dell'angolo specificato. Se l'angolo è in gradi, moltiplicate l'angolo per PI ()/180.

```
COS(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | Angolo in radianti per il quale desiderate il coseno. |

## Cube Root {#concept_BD93EFA45DF7447A8F839E1CA5B5F795}

Restituisce il cubo positivo positivo di un numero. Il cubo radice di un numero è il valore di quel numero elevato alla potenza di 1/3.

```
CBRT(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | La metrica per la quale vuoi la radice. |

## Cumulative {#concept_3D3347797B6344CE88B394C3E39318ED}

Restituisce la somma di x per le ultime righe N (come ordinato dalla dimensione, utilizzando valori hash per campi basati su stringa).

Se N &lt; = 0 utilizza tutte le righe precedenti. Poiché è ordinato dalla dimensione è utile solo per dimensioni che hanno un ordine naturale, come la lunghezza o la lunghezza del percorso.

```
| Date | Rev  | cumul(0,Rev) | cumul(2,Rev) | 
|------+------+--------------+--------------| 
| May  | $500 | $500         | $500         | 
| June | $200 | $700         | $700         | 
| July | $400 | $1100        | $600         | 
 
```

## Cumulative Average {#concept_ABB650962DC64FD58A79C305282D3E61}

Restituisce la media delle ultime righe N.

Se N &lt; = 0 utilizza tutte le righe precedenti. Poiché è ordinato dalla dimensione è utile solo per dimensioni che hanno un ordine naturale, come la lunghezza o la lunghezza del percorso.

>[!NOTE]
>
>Ciò non funziona come previsto con metriche rate come entrate/visitatore: calcola le medie dei tassi invece di sommare i ricavi sull'ultimo N e di sommare i visitatori attraverso l'ultimo N e quindi dividili. Utilizzate invece

```
cumul(revenue)/cumul(visitor)
```

## Equal {#concept_A3B97152B5F74E04A97018B35734BEEB}

Restituisce elementi che corrispondono esattamente a un valore numerico o stringa.

## Exponential Regression_ Correlation Coefficient (Table) {#concept_C18BBFA43C1A499293290DF49566D8D8}

Returns the correlation coefficient, *r*, between two metric columns ( *metric_A* and *metric_B*) for the regression equation .

```
CORREL.EXP(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_ X* | A metric that you would like to correlate with *metric_Y*. |
| *metric_ Y* | A metric that you would like to correlate with *metric_X*. |

## Exponential Regression: Intercept (Table) {#concept_0047206C827841AD936A3BE58EEE1514}

Returns the intercept, *b*, between two metric columns ( *metric_X* and *metric_Y*) for

```
INTERCEPT.EXP(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_ X* | Una metrica che desideri designare come dati dipendenti. |
| *metric_ Y* | Una metrica da designare come dati indipendenti. |

## Exponential Regression: Slope (Table) {#concept_230991B0371E44308C52853EFA656F04}

Returns the slope, *a*, between two metric columns ( *metric_X* and *metric_Y*) for .

```
SLOPE.EXP(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_ X* | Una metrica che desideri designare come dati dipendenti. |
| *metric_ Y* | Una metrica da designare come dati indipendenti. |

## Floor (Row) {#concept_D368150EC3684077B284EE471463FC31}

Restituisce il numero intero più grande non superiore a un valore specificato. For example, if you want to avoid reporting currency decimals for revenue and a product has $569.34, use the formula FLOOR( *Revenue*) to round revenue down to the nearest dollar, or $569.

```
FLOOR(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | La metrica da arrotondare. |

## Greater Than {#concept_A83734A0C0C14646B76D2CC5E677C644}

Restituisce elementi il cui conteggio numerico è maggiore del valore immesso.

## Greater Than or Equal {#concept_8CA6DF1F84784D50849BF1C566AE1D37}

Restituisce elementi il cui conteggio numerico è maggiore o uguale al valore immesso.

## Hyperbolic Cosine (Row) {#concept_79DD5681CE9640BDBA3C3F527343CA98}

Restituisce il coseno ipertestuale di un numero.

```
COSH(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | Angolo in radianti per il quale desiderate trovare il coseno ipertestuale. |

## Hyperbolic Sine (Row) {#concept_96230731600C45E3A4E823FE155ABA85}

Restituisce il seno ipertestuale di un numero.

```
SINH(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | Angolo in radianti per il quale desiderate trovare il sinusoidale. |

## Hyperbolic Tangent (Row) {#concept_BD249013732F462B9863629D142BCA6A}

Restituisce la tangente ipertestuale di un numero.

```
TANH(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | Angolo in radianti per il quale desiderate trovare il tanget ipertestuale. |

## IF (Row) {#concept_6BF0F3EAF3EF42C288AEC9A79806C48E}

La funzione IF restituisce un valore se una condizione specificata restituisce TRUE, e un altro valore se tale condizione restituisce FALSE.

```
IF(logical_test, [value_if_true], [value_if_false])
```

| Argomento | Descrizione |
|---|---|
| *logical_ test* | Obbligatorio. Qualsiasi valore o espressione che può essere valutata su TRUE o FALSE. |
| *[value_ if_ true]* | The value that you want to be returned if the *logical_test* argument evaluates to TRUE. (L'argomento predefinito è 0 se non incluso.) |
| *[value_ if_ false]* | The value that you want to be returned if the *logical_test* argument evaluates to FALSE. (L'argomento predefinito è 0 se non incluso.) |

## Less Than {#concept_A4A85C0FDF944AACAD4B8B55699D1B11}

Restituisce elementi il cui conteggio numerico è inferiore al valore immesso.

## Less Than or Equal {#concept_99D12154DE4848B1B0A6327C4322D288}

Restituisce elementi il cui conteggio numerico è minore o uguale al valore immesso.

## Linear regression_ Correlation Coefficient {#concept_132AC6B3A55248AA9C002C1FBEB55C60}

Y = a X + b. Restituisce il coefficiente di correlazione

## Linear regression_ Intercept {#concept_E44A8D78B802442DB855A07609FC7E99}

Y = a X + b. Restituisce b.

## Linear regression_ Predicted Y {#concept_9612B9BF106D4D278648D2DF92E98EFC}

Y = a X + b. Restituisce Y.

## Linear regression_ Slope {#concept_12352982082A4DDF824366B073B4C213}

Y = a X + b. Restituisce un valore.

## Log Base 10 (Row) {#concept_4C65DF9659164261BE52AA5A95FD6BC1}

Restituisce il logaritmo base -10 di un numero.

```
LOG10(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | Il numero reale positivo per il quale desiderate il logaritmo base -10. |

## Log regression: Correlation coefficient (Table) {#concept_F3EB35016B754E74BE41766E46FDC246}

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. Viene calcolato utilizzando l'equazione Correzione.

```
CORREL.LOG(metric_X,metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_ X* | A metric that you would like to correlate with *metric_Y*. |
| *metric_ Y* | A metric that you would like to correlate with *metric_X*. |

## Log regression: Intercept (Table) {#concept_75A3282EDF54417897063DC26D4FA363}

Returns the intercept *b* as the least squares regression between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. Viene calcolato utilizzando l'equazione INTERCETTT.

```
INTERCEPT.LOG(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_ X* | Una metrica che desideri designare come dati dipendenti. |
| *metric_ Y* | Una metrica da designare come dati indipendenti. |

## Log Regression: Predicted Y (Row) {#concept_5F3A9263BBB84E6098160A4DFB9E3607}

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the "least squares" method for calculating the line of best fit based on [!DNL Y = a ln(X) + b]. Viene calcolato utilizzando l'equazione STIMA.

In regression analysis, this function calculates the predicted [!DNL y] values (*metric_Y*), given the known [!DNL x] values (*metric_X*) using the logarithm for calculating the line of best fit for the regression equation [!DNL Y = a ln(X) + b]. [!DNL a] I valori corrispondono a ciascun valore x ed [!DNL b] è un valore costante.

```
ESTIMATE.LOG(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_ X* | Una metrica che desideri designare come dati dipendenti. |
| *metric_ Y* | Una metrica da designare come dati indipendenti. |

## Log regression: Slope (Table) {#concept_B291EFBE121446A6B3B07B262BBD4EF2}

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. Viene calcolato utilizzando l'equazione SLOPE.

```
SLOPE.LOG(metric_A, metric_B)
```

| Argomento | Descrizione |
|---|---|
| *metric_ A* | Una metrica che desideri designare come dati dipendenti. |
| *metric_ B* | Una metrica da designare come dati indipendenti. |

## Natural Log {#concept_D3BE148A9B84412F8CA61734EB35FF9E}

Restituisce il logaritmo naturale di un numero. Natural logarithms are based on the constant *e* (2.71828182845904). LN è l'inverso della funzione EXP.

```
LN(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | Il numero reale positivo per il quale vuoi il logaritmo naturale. |

## NOT {#concept_BD954C455A8148A3904A301EC4DC821E}

Restituisce 1 se il numero è 0 o restituisce 0 se un altro numero.

```
NOT(logical)
```

| Argomento | Descrizione |
|---|---|
| *loglogico* | Obbligatorio. Un valore o un'espressione che può essere valutata su TRUE o FALSE. |

L'utilizzo di NOT richiede la presenza di espressioni (&lt;, &gt;, =, &lt; &gt;, ecc.) restituisce valori 0 o 1.

## Not equal {#concept_EC010B7A9D2049099114A382D662FC16}

Restituisce tutti gli elementi che non contengono la corrispondenza esatta del valore immesso.

## Or (Row) {#concept_AF81A33A376C4849A4C14F3A380639D2}

Restituisce TRUE se un argomento è TRUE, oppure restituisce FALSE se tutti gli argomenti sono FALSE.

>[!NOTE]
>
>0 (zero) indica Falso e qualsiasi altro valore è True.

```
OR(logical_test1,[logical_test2],...)
```

| Argomento | Descrizione |
|---|---|
| *logical_ test 1* | Obbligatorio. Qualsiasi valore o espressione che può essere valutata su TRUE o FALSE. |
| *logical_ test 2* | Facoltativo. Condizioni ulteriori da valutare come TRUE o FALSE |

## Pi {#concept_41258789660D4A33B5FB86228F12ED9C}

Restituisce la costante PI, 3.14159265358979, precisa a 15 cifre.

```
PI()
```

The [!DNL PI]function has no arguments.

## Power regression: Correlation coefficient (Table) {#concept_91EC2CFB5433494F9E0F4FDD66C63766}

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
CORREL.POWER(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_ X* | A metric that you would like to correlate with *metric_Y*. |
| *metric_ Y* | A metric that you would like to correlate with *metric_X*. |

## Power regression: Intercept (Table) {#concept_7781C85597D64D578E19B212BDD1764F}

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
 INTERCEPT.POWER(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_ X* | Una metrica che desideri designare come dati dipendenti. |
| *metric_ Y* | Una metrica da designare come dati indipendenti. |

## Power regression: Predicted Y (Row) {#concept_CD652C0A921D4EFBA8F180CB8E486B18}

Calculates the predicted [!DNL y] values ( [!DNL metric_Y]), given the known [!DNL x] values ( [!DNL metric_X]) using the "least squares" method for calculating the line of best fit for [!DNL Y = b*X].

```
 ESTIMATE.POWER(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_ X* | Una metrica che desideri designare come dati dipendenti. |
| *metric_ Y* | Una metrica da designare come dati indipendenti. |

## Power regression: Slope (Table) {#concept_5B9E71B989234694BEB5EEF29148766C}

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
SLOPE.POWER(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_ X* | Una metrica che desideri designare come dati dipendenti. |
| *metric_ Y* | Una metrica da designare come dati indipendenti. |

## Quadratic regression: Correlation coefficient (Table) {#concept_9C9101A456B541E69BA29FCEAC8CD917}

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y=(a*X+b)]****.

```
CORREL.QUADRATIC(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_ X* | A metric that you would like to correlate with *metric_Y*. |
| *metric_ Y* | A metric that you would like to correlate with *metric_X*. |

## Quadratic regression: Intercept (Table) {#concept_69DC0FD6D38C40E9876F1FD08EC0E4DE}

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y=(a*X+b)]****.

```
INTERCEPT.POWER(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_ X* | Una metrica che desideri designare come dati dipendenti. |
| *metric_ Y* | Una metrica da designare come dati indipendenti. |

## Quadratic regression: Predicted Y (Row) {#concept_2F1ED70B1BDE4664A61CC09D30C39CBB}

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the least squares method for calculating the line of best fit using [!DNL Y=(a*X+b)]**** .

```
ESTIMATE.QUADRATIC(metric_A, metric_B)
```

| Argomento | Descrizione |
|---|---|
| *metric_ A* | Una metrica che desideri designare come dati dipendenti. |
| *metric_ B* | Una metrica che desideri designare come dati dipendenti. |

## Quadratic regression: Slope (Table) {#concept_0023321DA8E84E6D9BCB06883CA41645}

Returns the slope, *a*, between two metric columns (*metric_X* and metric_Y) for [!DNL Y=(a*X+b)]****.

```
SLOPE.QUADRATIC(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_ X* | Una metrica che desideri designare come dati dipendenti. |
| *metric_ Y* | Una metrica da designare come dati indipendenti. |

## Reciprocal regression: Correlation coefficient (Table) {#concept_EBEC509A19164B8AB2DBDED62F4BA2A5}

Returns the correlation coefficient, *r*, between two metric columns (*metric_X)* and *metric_Y*) for [!DNL Y = a/X+b].

```
CORREL.RECIPROCAL(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_ X* | A metric that you would like to correlate with *metric_Y*. |
| *metric_ Y* | A metric that you would like to correlate with *metric_X*. |

## Reciprocal regression: Intercept (Table) {#concept_2DA45B5C69F140EC987649D2C88F19B3}

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = a/X+b].

```
INTERCEPT.RECIPROCAL(metric_A, metric_B)
```

| Argomento | Descrizione |
|---|---|
| *metric_ X* | Una metrica che desideri designare come dati dipendenti. |
| *metric_ Y* | Una metrica da designare come dati indipendenti. |

## Reciprocal regression: Predicted Y (Row) {#concept_2CF4B8F417A84FE98050FE488E227DF8}

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the least squares method for calculating the line of best fit using [!DNL Y = a/X+b].

```
ESTIMATE.RECIPROCAL(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_ X* | Una metrica che desideri designare come dati dipendenti. |
| *metric_ Y* | Una metrica da designare come dati indipendenti. |

## Reciprocal regression: Slope (Table) {#concept_8A8B68C9728E42A6BFDC6BD5CBDCCEC5}

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = a/X+b].

```
SLOPE.RECIPROCAL(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_ X* | Una metrica che desideri designare come dati dipendenti. |
| *metric_ Y* | Una metrica da designare come dati indipendenti. |

## Sine (Row) {#concept_21C8C3AA835947A28B53A4E756A7451E}

Restituisce il seno dell'angolo specificato. Se l'angolo è in gradi, moltiplicate l'angolo per PI ()/180.

```
SIN(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | L'angolo in radianti per il quale desiderate la sinusoidale. |

## T-Score {#concept_80D2B4CED3D0426896B2412B4FC73BF7}

Alias per Z-Score, ovvero lo scarto dal significato diviso per la deviazione standard

## T-Test {#concept_A1F78F4A765348E38DBCAD2E8F638EB5}

Esegue un test t-tailing con t-score of col e n gradi di libertà.

The signature is `t_test( x, n, m )`. Underneath, it simply calls `m*cdf_t(-abs(x),n)`. (This is similar to the z-test function which runs `m*cdf_z(-abs(x))`.

Here, `m` is the number of tails, and `n` is the degrees of freedom. Devono essere numeri (costanti per l'intero rapporto, ovvero non modifica su riga per riga).

`X` is the t-test statistic, and would be a formula (ad es. zscore) based on a metric and will be evaluate on each row.

Il valore restituito è la probabilità di visualizzare la statistica di test x data i gradi di libertà e numero di tails.

**Esempi:**

1. Utilizzatelo per trovare elementi aberranti:

   ```
   t_test( zscore(bouncerate), row-count-1, 2)
   ```

1. Combine it with `if` to ignore very high or low bounce rates, and count visits on everything else:

   ```
   if ( t_test( z-score(bouncerate), row-count, 2) < 0.01, 0, visits )
   ```

## Tangent {#concept_C25E00CB17054263AB0460D9EF94A700}

Restituisce la tangente dell'angolo specificato. Se l'angolo è in gradi, moltiplicate l'angolo per PI ()/180.

```
TAN (metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | L'angolo in radianti per cui si desidera la tangente. |

## Z-Score (Row) {#concept_96BEAC79476C49B899DB7E193A5E7ADD}

Restituisce la valutazione Z, o la valutazione normale, in base a una distribuzione normale. La valutazione Z è il numero di deviazioni standard che un'osservazione deriva dal significato. Un punteggio Z pari a 0 (zero) indica che il punteggio è uguale al significato. Un punteggio Z può essere positivo o negativo, indicando se si trova sopra o sotto il significato e in base al numero di deviazioni standard.

L'equazione per Z-score è:

![](assets/z_score.png)

where [!DNL x] is the raw score, [!DNL μ] is the mean of the population, and [!DNL σ] is the standard deviation of the population.

>[!NOTE]
>
>[!DNL μ] (mu) e[!DNL σ] (sigma) vengono calcolate automaticamente dalla metrica.

Valutazione Z (metrica)

<table id="table_AEA3622A58F54EA495468A9402651E1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argomento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metrica</i> </td> 
   <td colname="col2"> <p> Restituisce il valore del primo argomento diverso da zero. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Z-Test {#concept_2A4ADD6B3AEB4A2E8465F527FAFC4C23}

Esegue un test Z-personalizzato con Z-score di A.

Restituisce la probabilità che la riga corrente venga visualizzata per casualità nella colonna.

>[!NOTE]
>
>Presuppone che i valori siano distribuiti in genere.

