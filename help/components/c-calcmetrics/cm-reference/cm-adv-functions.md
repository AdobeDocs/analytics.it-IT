---
description: Per accedere a queste funzioni, seleziona Show Advanced (Mostra avanzate) dall’elenco a discesa Functions (Funzioni).
title: Funzioni avanzate di riferimento
uuid: 7d1071b9-1737-4b7c-b318-87907dae5619
exl-id: a6d0c2ad-864d-4cab-84e0-dd6ce0a4c6b1
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '2906'
ht-degree: 99%

---

# Riferimento: funzioni avanzate

Accedi a queste funzioni selezionando **[!UICONTROL Show Advanced]** nell’elenco a discesa **[!UICONTROL Functions]**.

## Funzioni tabella e Funzioni riga {#section_8977BE40A47E4ED79EB543A9703A4905}

Una funzione tabella è una funzione in cui l’output è lo stesso per ogni riga della tabella. Una funzione riga contiene un output diverso per ogni riga della tabella.

## Che cosa significa il parametro Include-Zeros? {#section_C7A2B05929584C65B308FD372CB8E8E3}

Il parametro indica se includere gli zeri all’interno del calcolo. Talvolta lo zero non ha alcun significato, ma in determinate occasioni può risultare importante.

Ad esempio, se hai una metrica Revenue (Entrate) e ne aggiungi al report una del tipo Page Views (Visualizzazioni pagina), improvvisamente saranno presenti più righe per le entrate che sono pari a zero. È probabile che non vorrai estendere questo risultato ai calcoli MEAN, MIN, QUARTILE e così via, che sono presenti nella colonna Revenue (Entrate). In questo caso, dovrai controllare il parametro include-zeros.

D’altra parte, se disponi di due metriche di tuo interesse, potrebbe non essere giusto affermare che una presenti una media o un minimo più alto in virtù di alcune righe pari a zero, quindi non controlleresti il parametro in modo da includere gli zeri.

## AND {#concept_E14513FE464F4491AD0D4130D4EE621C}

Restituisce il valore del relativo argomento. Per assicurarti che un valore non sia uguale a un valore particolare, utilizza la funzione NOT.

>[!NOTE]
>
>0 (zero) significa False, mentre qualsiasi altro valore corrisponde a True.

```
AND(logical_test1,[logical_test2],...)
```

| Argomento | Descrizione |
|---|---|
| *logical_test1* | Obbligatorio. Qualsiasi valore o espressione che può essere valutato come TRUE o FALSE. |
| *logical_test2* | Facoltativo. Condizioni aggiuntive da valutare come TRUE o FALSE. |

## Approximate Count Distinct (dimension) (Conteggio valori univoci approssimativo (dimensione)) {#concept_000776E4FA66461EBA79910B7558D5D7}

Restituisce il conteggio valori univoci approssimativo degli elementi dimensione per la dimensione selezionata. La funzione sfrutta il metodo HyperLogLog (HLL) per approssimare i conteggi valori univoci ed è configurata per garantire che il valore sia compreso entro il 5% del valore effettivo per il 95% del tempo.

```
Approximate Count Distinct (dimension)
```

| Argomento |  |
|---|---|
| *dimension* | La dimensione per la quale vuoi ottenere il conteggio dei valori univoci approssimativo degli elementi. |

### Caso d’uso di esempio {#section_424E3FC5092948F0A9D655F6CCBA0312}

Approximate Count Distinct (customer ID eVar) (Conteggio valori univoci approssimativo (eVar ID cliente)) rappresenta un caso d’uso comune per questa funzione.

Definizione di una nuova metrica calcolata “Approximate Customers” (Clienti approssimativi):

![](assets/approx-count-distinct.png)

Questo è il modo in cui la metrica “Approximate Customers” (Clienti approssimativi) potrebbe essere utilizzata nel reporting:

![](assets/approx-customers.png)

### Uniques Exceeded (Univoci superati) {#section_9C583858A9F94FF7BA054D1043194BAA}

Analogamente a Count() e RowCount(), Approximate Count Distinct() è soggetto ai [limiti di “uniques exceeded” (univoci superati)](https://experienceleague.adobe.com/docs/analytics/technotes/low-traffic.html). Se in un determinato mese si raggiunge il limite “uniques exceeded” per una dimensione, il valore viene conteggiato come 1 elemento dimensione.

### Confronto delle funzioni di conteggio {#section_440FB8FB44374459B2C6AE2DA504FC0B}

Approximate Count Distinct() rappresenta un miglioramento rispetto alle funzioni Count() e RowCount(), perché la metrica creata può essere utilizzata in qualsiasi report dimensionale per rappresentare un conteggio approssimativo di elementi per una dimensione separata. Ad esempio, un conteggio degli ID cliente utilizzati all’interno di un report Mobile Device Type (Tipo dispositivo mobile).

Questa funzione risulterà leggermente meno precisa rispetto a Count() e RowCount() perché sfrutta il metodo HLL, mentre Count() e RowCount() rappresentano conteggi esatti.

## Arcocoseno (riga) {#concept_1DA3404F3DDE4C6BAF3DBDD655D79C7B}

Restituisce l’arcocoseno di una metrica, detto anche inverso del coseno. L’arcocoseno è l’angolo di cui è numero il coseno. L’angolo restituito è espresso in radianti compresi nell’intervallo tra 0 (zero) e pi. Per convertire il risultato dai radianti ai gradi, moltiplicalo per 180/PI( ).

```
ACOS(metric)
```

| Argomento |  |
|---|---|
| *metric* | Il coseno dell’angolo desiderato da -1 a 1. |

## Arcoseno (riga) {#concept_90F00DEC46BA47F8A21493647D9668CD}

Restituisce l’arcoseno, o seno inverso, di un numero. L’arcoseno è l’angolo di cui è numero il seno. L’angolo restituito è espresso in radianti compresi nell’intervallo tra -pi/2 e pi/2. Per esprimere l’arcoseno in gradi, moltiplica il risultato per 180/PI( ).

```
ASIN(metric) 
```

| Argomento |  |
|---|---|
| *metrica* | Il coseno dell’angolo desiderato da -1 a 1. |

## Arcotangente (riga) {#concept_3408520673774A10998E9BD8B909E90C}

Restituisce l’arcotangente, o tangente inversa, di un numero. L’arcotangente è l’angolo di cui è numero la tangente. L’angolo restituito è espresso in radianti compresi nell’intervallo tra -pi/2 e pi/2. Per esprimere l’arcotangente in gradi, moltiplica il risultato per 180/PI( ).

```
ATAN(metric)
```

| Argomento |  |
|---|---|
| *metrica* | Il coseno dell’angolo desiderato da -1 a 1. |

## Regressione esponenziale: valore Y previsto (riga) {#concept_25615693312B4A7AB09A2921083502AD}

Calcola i valori y previsti (metric_Y), in base ai valori x noti (metric_X) utilizzando il metodo dei minimi quadrati per calcolare la riga di adattamento ottimale in base a.

```
ESTIMATE.EXP(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_X* | Una metrica da designare come dati indipendenti. |
| *metric_Y* | Una metrica da designare come dati dipendenti. |

## Cdf-T {#concept_4E2F2673532A48B5AF786521DE428A66}

Restituisce la percentuale di valori nella distribuzione t di uno studente con n gradi di libertà che presenta un punteggio z inferiore a x.

```
cdf_t( -∞, n ) = 0 
cdf_t(  ∞, n ) = 1 
cdf_t( 3, 5 ) ? 0.99865 
cdf_t( -2, 7 ) ? 0.0227501 
cdf_t( x, ∞ ) ? cdf_z( x )
```

## Cdf-Z {#concept_99C97ACC40A94FADBCF7393A17BC2D12}

Restituisce la percentuale di valori in una distribuzione normale che presenta un punteggio z inferiore a x.

```
cdf_z( -∞ ) = 0 
cdf_z( ∞ ) = 1 
cdf_z( 0 ) = 0.5 
cdf_z( 2 ) ? 0.97725 
cdf_z( -3 ) ? 0.0013499 
 
```

## Eccesso (riga) {#concept_A14CDB1E419B4AA18D335E5BA2548346}

Restituisce l’integer più piccolo, non inferiore a un valore specificato. Ad esempio, se vuoi evitare di riportare i decimali della valuta per le entrate e il prezzo di un prodotto è pari a 569,34 $, utilizza la formula CEILING(*Revenue*) per arrotondare le entrate al dollaro più vicino o 570 $.

```
CEILING(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | La metrica da arrotondare. |

## Coseno (riga) {#concept_DD07AA1FB08145DC89B69D704545FD0A}

Restituisce il coseno dell’angolo specificato. Se l’angolo è in gradi, moltiplicalo per PI( )/180.

```
COS(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | L’angolo in radianti di cui vuoi ottenere il coseno. |

## Radice cubica {#concept_BD93EFA45DF7447A8F839E1CA5B5F795}

Restituisce la radice cubica positiva di un numero. La radice cubica di un numero corrisponde al valore di quel numero elevato alla potenza di 1/3.

```
CBRT(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | La metrica per la quale vuoi ottenere la radice cubica. |

## Cumulativo {#concept_3D3347797B6344CE88B394C3E39318ED}

Restituisce la somma di x per le ultime N righe secondo quanto ordinato dalla dimensione, utilizzando valori hash per i campi basati su stringhe.

Se N &lt;= 0 vengono usate tutte le righe precedenti. Poiché questa funzione è ordinata dalla dimensione, risulta utile solo per le dimensioni con ordine naturale, come data o lunghezza del percorso.

```
| Date | Rev  | cumul(0,Rev) | cumul(2,Rev) | 
|------+------+--------------+--------------| 
| May  | $500 | $500         | $500         | 
| June | $200 | $700         | $700         | 
| July | $400 | $1100        | $600         | 
 
```

## Media cumulativa {#concept_ABB650962DC64FD58A79C305282D3E61}

Restituisce la media delle ultime N righe.

Se N &lt;= 0 vengono usate tutte le righe precedenti. Poiché questa funzione è ordinata dalla dimensione, risulta utile solo per le dimensioni con ordine naturale, come data o lunghezza del percorso.

>[!NOTE]
>
>Questa funzione non opera come previsto con metriche di tasso come entrate/visitatore: essa calcola la media dei tassi, anziché sommare le entrate rispetto all’ultima N, quindi sommare i visitatori rispetto all’ultima N e infine dividere i due valori ottenuti. Invece, utilizza

```
cumul(revenue)/cumul(visitor)
```

## Uguale {#concept_A3B97152B5F74E04A97018B35734BEEB}

Restituisce elementi che corrispondono esattamente a un valore numerico o stringa.

## Regressione esponenziale: coefficiente di correlazione (tabella) {#concept_C18BBFA43C1A499293290DF49566D8D8}

Restituisce il coefficiente di correlazione, *r*, tra due colonne di metrica ( *metric_A* e *metric_B*) per l’equazione di regressione.

```
CORREL.EXP(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_X* | Metrica da correlare con *metric_Y*. |
| *metric_Y* | Metrica da correlare con *metric_X*. |

## Regressione esponenziale: intersezione (tabella) {#concept_0047206C827841AD936A3BE58EEE1514}

Restituisce l’intersezione, *b*, tra due colonne di metrica ( *metric_X* e *metric_Y*) per

```
INTERCEPT.EXP(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_X* | Una metrica da designare come dati indipendenti. |
| *metric_Y* | Una metrica da designare come dati dipendenti. |

## Regressione esponenziale: pendenza (tabella) {#concept_230991B0371E44308C52853EFA656F04}

Restituisce la pendenza, *a*, tra due colonne di metrica ( *metric_X* e *metric_Y*) per

```
SLOPE.EXP(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_X* | Una metrica da designare come dati indipendenti. |
| *metric_Y* | Una metrica da designare come dati dipendenti. |

## Base (riga) {#concept_D368150EC3684077B284EE471463FC31}

Restituisce l’integer più grande, non superiore a un valore specificato. Ad esempio, se vuoi evitare di riportare i decimali della valuta per le entrate e il prezzo di un prodotto è pari a 569,34 $, utilizza la formula FLOOR(*Revenue*) per arrotondare le entrate al dollaro più vicino o 569$.

```
FLOOR(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | La metrica da arrotondare. |

## Maggiore di {#concept_A83734A0C0C14646B76D2CC5E677C644}

Restituisce elementi il cui conteggio numerico è maggiore del valore immesso.

## Maggiore di o uguale a {#concept_8CA6DF1F84784D50849BF1C566AE1D37}

Restituisce elementi il cui conteggio numerico è maggiore di o uguale al valore immesso.

## Coseno iperbolico (riga) {#concept_79DD5681CE9640BDBA3C3F527343CA98}

Restituisce il coseno iperbolico di un numero.

```
COSH(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | L’angolo in radianti di cui vuoi ottenere il coseno iperbolico. |

## Seno iperbolico (riga) {#concept_96230731600C45E3A4E823FE155ABA85}

Restituisce il seno iperbolico di un numero.

```
SINH(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | L’angolo in radianti di cui vuoi ottenere il seno iperbolico. |

## Tangente iperbolica (riga) {#concept_BD249013732F462B9863629D142BCA6A}

Restituisce la tangente iperbolica di un numero.

```
TANH(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | L’angolo in radianti di cui vuoi ottenere la tangente iperbolica. |

## IF (riga) {#concept_6BF0F3EAF3EF42C288AEC9A79806C48E}

La funzione IF restituisce un valore se una condizione specificata restituisce TRUE, mentre consente di ottenere un altro valore se tale condizione restituisce FALSE.

```
IF(logical_test, [value_if_true], [value_if_false])
```

| Argomento | Descrizione |
|---|---|
| *logical_test* | Obbligatorio. Qualsiasi valore o espressione che può essere valutato come TRUE o FALSE. |
| *[value_if_true]* | Il valore che vuoi ottenere se l’argomento *logical_test* restituisce TRUE. Se non è incluso, questo argomento sarà pari a 0 per impostazione predefinita. |
| *[value_if_false]* | Il valore che vuoi ottenere se l’argomento *logical_test* restituisce FALSE. Se non è incluso, questo argomento sarà pari a 0 per impostazione predefinita. |

## Minore di {#concept_A4A85C0FDF944AACAD4B8B55699D1B11}

Restituisce elementi il cui conteggio numerico è inferiore al valore immesso.

## Minore o uguale a {#concept_99D12154DE4848B1B0A6327C4322D288}

Restituisce elementi il cui conteggio numerico è minore o uguale al valore immesso.

## Regressione lineare: coefficiente di correlazione {#concept_132AC6B3A55248AA9C002C1FBEB55C60}

Y = a X + b. Restituisce il coefficiente di correlazione.

## Regressione lineare: intersezione {#concept_E44A8D78B802442DB855A07609FC7E99}

Y = a X + b. Restituisce b.

## Regressione lineare: valore Y previsto {#concept_9612B9BF106D4D278648D2DF92E98EFC}

Y = a X + b. Restituisce Y.

## Regressione lineare: pendenza {#concept_12352982082A4DDF824366B073B4C213}

Y = a X + b. Restituisce a.

## Base logaritmo 10 (riga) {#concept_4C65DF9659164261BE52AA5A95FD6BC1}

Restituisce il logaritmo base 10 di un numero.

```
LOG10(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | Numero reale positivo di cui vuoi ottenere il logaritmo base 10. |

## Regressione logaritmo: coefficiente di correlazione (tabella) {#concept_F3EB35016B754E74BE41766E46FDC246}

Restituisce il coefficiente di correlazione, *r*, tra due colonne di metrica (*metric_X* e *metric_Y*) per l’equazione di regressione [!DNL Y = a ln(X) + b]. Viene calcolato utilizzando l’equazione CORREL.

```
CORREL.LOG(metric_X,metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_X* | Metrica da correlare con *metric_Y*. |
| *metric_Y* | Metrica da correlare con *metric_X*. |

## Regressione logaritmo: intersezione (tabella) {#concept_75A3282EDF54417897063DC26D4FA363}

Restituisce l’intersezione *b* come regressione dei minimi quadrati tra due colonne di metrica (*metric_X* e *metric_Y*) per l’equazione di regressione [!DNL Y = a ln(X) + b]. Viene calcolata utilizzando l’equazione INTERCEPT.

```
INTERCEPT.LOG(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_X* | Una metrica da designare come dati indipendenti. |
| *metric_Y* | Una metrica da designare come dati dipendenti. |

## Regressione logaritmo: valore Y previsto (riga) {#concept_5F3A9263BBB84E6098160A4DFB9E3607}

Calcola i [!DNL y] valori previsti (metric_Y), in base ai [!DNL x] valori noti (metric_X) utilizzando il metodo dei minimi quadrati per calcolare la riga di adattamento ottimale in base a [!DNL Y = a ln(X) + b]. Viene calcolata utilizzando l’equazione ESTIMATE.

Nell’analisi di regressione, questa funzione calcola i [!DNL y] valori previsti (*metric_Y*), dati i [!DNL x] valori noti (*metric_X*) utilizzando il logaritmo per calcolare la linea più adatta all’equazione di regressione [!DNL Y = a ln(X) + b]. I [!DNL a] valori corrispondono a ciascun valore x e [!DNL b] è un valore costante.

```
ESTIMATE.LOG(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_X* | Una metrica da designare come dati indipendenti. |
| *metric_Y* | Una metrica da designare come dati dipendenti. |

## Regressione logaritmo: pendenza (tabella) {#concept_B291EFBE121446A6B3B07B262BBD4EF2}

Restituisce la pendenza, *a*, tra due colonne di metrica (*metric_X* e *metric_Y*) per l’equazione di regressione [!DNL Y = a ln(X) + b]. Viene calcolata utilizzando l’equazione SLOPE.

```
SLOPE.LOG(metric_A, metric_B)
```

| Argomento | Descrizione |
|---|---|
| *metric_A* | Una metrica da designare come dati indipendenti. |
| *metric_B* | Una metrica da designare come dati dipendenti. |

## Logaritmo naturale {#concept_D3BE148A9B84412F8CA61734EB35FF9E}

Restituisce il logaritmo naturale di un numero. I logaritmi naturali si basano sulla costante *e* (2,71828182845904). LN è l’inverso della funzione EXP.

```
LN(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | Numero reale positivo di cui vuoi ottenere il logaritmo naturale. |

## NOT {#concept_BD954C455A8148A3904A301EC4DC821E}

Restituisce 1 se il numero è 0 o restituisce 0 se è presente un altro numero.

```
NOT(logical)
```

| Argomento | Descrizione |
|---|---|
| *logical* | Obbligatorio. Un valore o espressione che può essere valutato come TRUE o FALSE. |

Per utilizzare NOT è necessario verificare se le espressioni (&lt;, >, =, &lt;>, ecc.) restituiscono i valori 0 o 1.

## Non uguale {#concept_EC010B7A9D2049099114A382D662FC16}

Restituisce tutti gli elementi che non contengono la corrispondenza esatta del valore immesso.

## O (riga) {#concept_AF81A33A376C4849A4C14F3A380639D2}

Restituisce TRUE se un qualsiasi argomento è TRUE oppure FALSE se tutti gli argomenti sono FALSE.

>[!NOTE]
>
>0 (zero) significa False, mentre qualsiasi altro valore corrisponde a True.

```
OR(logical_test1,[logical_test2],...)
```

| Argomento | Descrizione |
|---|---|
| *logical_test1* | Obbligatorio. Qualsiasi valore o espressione che può essere valutato come TRUE o FALSE. |
| *logical_test2* | Facoltativo. Condizioni aggiuntive da valutare come TRUE o FALSE. |

## Pi {#concept_41258789660D4A33B5FB86228F12ED9C}

Restituisce la costante PI, 3,14159265358979, con una precisione di 15 cifre.

```
PI()
```

La funzione [!DNL PI]non ha argomenti.

## Regressione di potenza: coefficiente di correlazione (tabella) {#concept_91EC2CFB5433494F9E0F4FDD66C63766}

Restituisce il coefficiente di correlazione, *r*, tra due colonne di metrica (*metric_X* e *metric_Y*) per [!DNL Y = b*X].

```
CORREL.POWER(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_X* | Metrica da correlare con *metric_Y*. |
| *metric_Y* | Metrica da correlare con *metric_X*. |

## Regressione di potenza: intersezione (tabella) {#concept_7781C85597D64D578E19B212BDD1764F}

Restituisce l’intersezione, *b*, tra due colonne di metrica (*metric_X* e *metric_Y*) per [!DNL Y = b*X].

```
 INTERCEPT.POWER(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_X* | Una metrica da designare come dati indipendenti. |
| *metric_Y* | Una metrica da designare come dati dipendenti. |

## Regressione di potenza: valore Y previsto (riga) {#concept_CD652C0A921D4EFBA8F180CB8E486B18}

Calcola i [!DNL y] valori previsti ( [!DNL metric_Y]), in base ai [!DNL x] valori noti ( [!DNL metric_X]) utilizzando il metodo dei minimi quadrati per calcolare la riga di adattamento ottimale per [!DNL Y = b*X].

```
 ESTIMATE.POWER(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_X* | Una metrica da designare come dati indipendenti. |
| *metric_Y* | Una metrica da designare come dati dipendenti. |

## Regressione di potenza: pendenza (tabella) {#concept_5B9E71B989234694BEB5EEF29148766C}

Restituisce la pendenza, *a*, tra due colonne di metrica (*metric_X* e *metric_Y*) per [!DNL Y = b*X].

```
SLOPE.POWER(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_X* | Una metrica da designare come dati indipendenti. |
| *metric_Y* | Una metrica da designare come dati dipendenti. |

## Regressione quadratica: coefficiente di correlazione (tabella) {#concept_9C9101A456B541E69BA29FCEAC8CD917}

Restituisce il coefficiente di correlazione, *r*, tra due colonne di metrica (*metric_X* e *metric_Y*) per [!DNL Y=(a*X+b)]****.

```
CORREL.QUADRATIC(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_X* | Metrica da correlare con *metric_Y*. |
| *metric_Y* | Metrica da correlare con *metric_X*. |

## Regressione quadratica: intersezione (tabella) {#concept_69DC0FD6D38C40E9876F1FD08EC0E4DE}

Restituisce l’intersezione, *b*, tra due colonne di metrica (*metric_X* e *metric_Y*) per [!DNL Y=(a*X+b)]****.

```
INTERCEPT.POWER(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_X* | Una metrica da designare come dati indipendenti. |
| *metric_Y* | Una metrica da designare come dati dipendenti. |

## Regressione quadratica: valore Y previsto (riga) {#concept_2F1ED70B1BDE4664A61CC09D30C39CBB}

Calcola i [!DNL y] valori previsti (metric_Y), in base ai [!DNL x] valori noti (metric_X) utilizzando il metodo dei minimi quadrati per calcolare la riga di adattamento ottimale tramite [!DNL Y=(a*X+b)]****.

```
ESTIMATE.QUADRATIC(metric_A, metric_B)
```

| Argomento | Descrizione |
|---|---|
| *metric_A* | Una metrica da designare come dati indipendenti. |
| *metric_B* | Una metrica da designare come dati dipendenti. |

## Regressione quadratica: pendenza (tabella) {#concept_0023321DA8E84E6D9BCB06883CA41645}

Restituisce la pendenza, *a*, tra due colonne di metrica (*metric_X* e metric_Y) per [!DNL Y=(a*X+b)]****.

```
SLOPE.QUADRATIC(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_X* | Una metrica da designare come dati indipendenti. |
| *metric_Y* | Una metrica da designare come dati dipendenti. |

## Regressione reciproca: coefficiente di correlazione (tabella) {#concept_EBEC509A19164B8AB2DBDED62F4BA2A5}

Restituisce il coefficiente di correlazione, *r*, tra due colonne di metrica (*metric_X)* e *metric_Y*) per [!DNL Y = a/X+b].

```
CORREL.RECIPROCAL(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_X* | Metrica da correlare con *metric_Y*. |
| *metric_Y* | Metrica da correlare con *metric_X*. |

## Regressione reciproca: intersezione (tabella) {#concept_2DA45B5C69F140EC987649D2C88F19B3}

Restituisce l’intersezione, *b*, tra due colonne di metrica (*metric_X* e *metric_Y*) per [!DNL Y = a/X+b].

```
INTERCEPT.RECIPROCAL(metric_A, metric_B)
```

| Argomento | Descrizione |
|---|---|
| *metric_X* | Una metrica da designare come dati indipendenti. |
| *metric_Y* | Una metrica da designare come dati dipendenti. |

## Regressione reciproca: valore Y previsto (riga) {#concept_2CF4B8F417A84FE98050FE488E227DF8}

Calcola i [!DNL y] valori previsti (metric_Y), in base ai [!DNL x] valori noti (metric_X) utilizzando il metodo dei minimi quadrati per calcolare la riga di adattamento ottimale tramite [!DNL Y = a/X+b].

```
ESTIMATE.RECIPROCAL(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_X* | Una metrica da designare come dati indipendenti. |
| *metric_Y* | Una metrica da designare come dati dipendenti. |

## Regressione reciproca: pendenza (tabella) {#concept_8A8B68C9728E42A6BFDC6BD5CBDCCEC5}

Restituisce la pendenza, *a*, tra due colonne di metrica (*metric_X* e *metric_Y*) per [!DNL Y = a/X+b].

```
SLOPE.RECIPROCAL(metric_X, metric_Y)
```

| Argomento | Descrizione |
|---|---|
| *metric_X* | Una metrica da designare come dati indipendenti. |
| *metric_Y* | Una metrica da designare come dati dipendenti. |

## Seno (riga) {#concept_21C8C3AA835947A28B53A4E756A7451E}

Restituisce il seno dell’angolo specificato. Se l’angolo è in gradi, moltiplicalo per PI( )/180.

```
SIN(metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | L’angolo in radianti di cui vuoi ottenere il seno. |

## Punteggio T {#concept_80D2B4CED3D0426896B2412B4FC73BF7}

Alias per punteggio Z, vale a dire la deviazione dalla media divisa per la deviazione standard.

## Test T {#concept_A1F78F4A765348E38DBCAD2E8F638EB5}

Esegue un test t a coda m con un punteggio t di col e n gradi di libertà.

La firma è `t_test( x, n, m )`. Sotto, effettua semplicemente la chiamata `m*cdf_t(-abs(x),n)`. È simile alla funzione di test z che esegue `m*cdf_z(-abs(x))`.

Qui `m` indica il numero di code e `n` corrisponde ai gradi di libertà. Devono essere numeri costanti per l’intero report, ovvero senza subire modifiche per riga.

`X` è la statistica del test t e spesso è una formula (ad es., zscore) basata su una metrica, che sarà valutata su ogni riga.

Il valore restituito è la probabilità di visualizzare la statistica x del test in base ai gradi di libertà e al numero di code.

**Esempi:**

1. Utilizza questo valore per individuare gli outlier:

   ```
   t_test( zscore(bouncerate), row-count-1, 2)
   ```

1. Combinalo con `if` per ignorare tassi non raggiunti molto elevati o bassi e per contare le visite degli altri elementi:

   ```
   if ( t_test( z-score(bouncerate), row-count, 2) < 0.01, 0, visits )
   ```

## Tangente {#concept_C25E00CB17054263AB0460D9EF94A700}

Restituisce la tangente dell’angolo specificato. Se l’angolo è in gradi, moltiplicalo per PI( )/180.

```
TAN (metric)
```

| Argomento | Descrizione |
|---|---|
| *metrica* | L’angolo in radianti di cui vuoi ottenere la tangente. |

## Punteggio Z (riga) {#concept_96BEAC79476C49B899DB7E193A5E7ADD}

Restituisce il punteggio Z, o punteggio normale, in base a una distribuzione normale. Il punteggio Z è il numero di deviazioni standard di un’osservazione dalla media. Un punteggio Z pari a 0 (zero) indica che il punteggio è uguale alla media. Un punteggio Z può essere positivo o negativo, il che significa se è superiore o inferiore alla media, oltre al numero di deviazioni standard.

L’equazione per il punteggio Z è:

![](assets/z_score.png)

dove [!DNL x] è il punteggio non elaborato, [!DNL μ] corrisponde alla media della popolazione e [!DNL σ] indica la deviazione standard della popolazione.

>[!NOTE]
>
>[!DNL μ] (mu) e[!DNL σ] (sigma) vengono calcolati automaticamente dalla metrica.

Punteggio Z (metrica)

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

## Test Z {#concept_2A4ADD6B3AEB4A2E8465F527FAFC4C23}

Effettua un test Z con coda n con punteggio Z di A.

Restituisce la probabilità che la riga corrente possa essere vista casualmente nella colonna.

>[!NOTE]
>
>Presuppone che i valori siano distribuiti normalmente.
