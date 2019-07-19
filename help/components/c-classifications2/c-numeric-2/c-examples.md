---
description: Esempi per fornire indicazioni per l'importazione di classificazioni numeriche 2.
seo-description: Esempi per fornire indicazioni per l'importazione di classificazioni numeriche 2.
seo-title: Esempi
solution: Analytics
subtopic: Classificazioni
title: Esempi
topic: Strumenti di amministrazione
uuid: 0553 d 07 f -87 c 1-4372-90 ce -7118 a 6393 a 01
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Esempi

Esempi per fornire indicazioni per l'importazione di classificazioni numeriche 2.

<!-- 

c_example_1__rate.xml

 -->

In this case, you created the classification on the [!UICONTROL Classification Conversion] manager and want to import the January values:

| Chiave | Mytext | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_jan_var` |  | `.2` |
| Product2 | Text2 | `Cost2_jan_var` |  | `.3` |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/01/01 - 2010/01/31 | revenue | revenue |
| 2010/01/01 - 2010/01/31 | revenue | revenue |

In January, Product1 had a cost of 20% of its revenue (shown in `~MyCost^~value~`) and Product2 had a cost of 30% of its revenue. Because you are importing a new row, `~MyCost^~id~` is blank.

## Risultato {#section_E0569289C9B34C479C7D2CD9ECBF866E}

Esempio di output del rapporto:

Periodo: Gen 2010

Report: Prodotti

| Variabile   | Ricavi | Mycost |
|---|---|---|
| Product1 | $10,000.23 | $2000.05 |
| Product2 | $9,000.04 | $2700.01 |

<!-- 

c_example_2__rate.xml

 -->

| Chiave | Mytext | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_jan_var` | 1 | 0,2 |
| Product2 | Text2 | `Cost2_jan_var` | 2 | .3 |
| Product1 | Text1 | `Cost1_feb_var` |  | .15 |
| Product2 | Text2 | `Cost2_feb_var` |  | .25 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/01/01 - 2010/01/31 | revenue | revenue |
| 2010/01/01 - 2010/01/31 | revenue | revenue |
| 2010/02/01 - 2010/02/28 | revenue | revenue |
| 2010/02/01 - 2010/02/28 | revenue | revenue |

A febbraio, il costo dell'utente per il prodotto 1 è sceso al 15% dei ricavi e il prodotto 2 è sceso al 25% delle entrate.

## Risultato {#section_23DF5353AC1B478C88647F222703352C}

Esempio di output del rapporto:

Periodo: Gen 2010

Report: Prodotti

| Variabile   | Ricavi | Mycost |
|---|---|---|
| Product1 | $10,000.23 | $2000.05 |
| Product2 | $9,000.04 | $2700.01 |

Periodo: Feb 2010

Report: Prodotti

| Variabile   | Ricavi | Mycost |
|---|---|---|
| Product1 | $15,500.75 | $2325.11 |
| Product2 | $12,300.52 | $3075.13 |

Periodo: Jan 1, 2010 - 2010 febbraio 28

Report: Prodotti

| Variabile   | Ricavi | Mycost |
|---|---|---|
| Product1 | $25,500.98 | $4325.16 |
| Product2 | $21,300.56 | $5,775.14 |

<!-- 

c_example_3__fixed.xml

 -->

Di conseguenza, importare i dati seguenti:

| Chiave | Mytext | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_mar_fixed` |  | 3000.00 |
| Product2 | Text2 | `Cost2_jan_fixed` |  | 2000.00 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | fixed | none |
| 2010/03/01 - 2010/03/31 | fixed | none |

## Risultato {#section_674B57ADB8284B878F9E670038C31464}

Esempio di output del rapporto:

Periodo: Mar 2010

Report: Prodotti

| Variabile   | Ricavi | Mycost |
|---|---|---|
| Product1 | $11,023.75 | $3000.00 |
| Product2 | $8,000.12 | $2000.00 |

<!-- 

c_example_4__(advanced)_multiple_row_per_time_period.xml

 -->

In questo esempio, è possibile aggiungere una spesa di spedizione da $ 500 a un prodotto 1 per gennaio e un costo di spedizione di $ 600 a febbraio.

| Chiave | Mytext | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_jan_var` | 1 | 0,2 |
| Product1 | Text1 | `Cost2_jan_fixed` |  | 500 |
| Product1 | Text1 | `Cost1_feb_var` | 2 | .15 |
| Product1 | Text1 | `Cost2_feb_fixed` |  | 600 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/01/01 - 2010/01/31 | revenue | revenue |
| 2010/01/01 - 2010/01/31 | fixed | none |
| 2010/02/01 - 2010/01/31 | revenue | revenue |
| 2010/02/01 - 2010/01/31 | fixed | none |

Le righe importate in precedenza dispongono di un ID, che indica che non si tratta di costi nuovi.

## Risultato {#section_2096084176614B9AA60F97D5853CB9EA}

Esempio di output del rapporto:

Periodo: Gen 2010

Report: Prodotti

| Variabile   | Ricavi | Mycost |
|---|---|---|
| Product1 | $10,000.23 | $2500.05 |

>[!NOTE]
>
>Questa funzione consente agli utenti avanzati di approssimare i valori. Le informazioni risultanti non devono essere considerate valori esatti.

<!-- 

c_example_5__identical_rate_hinge.xml

 -->

Esempio di questo esempio:

| Chiave | Mytext | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_mar_var` |  | 1 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | order | order |

## Risultato {#section_39E24ECCC3B34C9AADC25572662750E5}

Esempio di output del rapporto:

Periodo: Mar 2010

Report: Prodotti per pagina

| Prodotti per pagina | Ordini | Mycost |
|---|---|---|
| Product1 | 1000 | $1000.00 |
| Home page | 600 | $600 |
| Carrello acquisti | 400 | $400 |

<!-- 

c_example_5__fixed_no_hinge.xml

 -->

| Chiave | Mytext | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_mar_fixed` |  | 3000.00 |
| Product2 | Text2 | `Cost2_mar_fixed` |  | 2000.00 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | fixed | none |
| 2010/03/01 - 2010/03/31 | fixed | none |

## Risultato {#section_7F5F5970077D4E14A5DC91495E23540D}

Esempio di output del rapporto:

Periodo: Mar 2010

Report: Prodotti per pagina

| Prodotti per pagina | Ordini | Mycost |
|---|---|---|
| Product1 | 1000 | $3000.00 |
| Home page | 600 | 0 |
| Carrello acquisti | 400 | 0 |

<!-- 

c_example_7__fixed_hinge.xml

 -->

In tal caso, importare i dati seguenti:

| Chiave | Mytext | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_mar_fixed` |  | 3000.00 |
| Product2 | Text2 | `Cost2_mar_fixed` |  | 2000.00 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | fixed | revenue |
| 2010/03/01 - 2010/03/31 | fixed | revenue |

## Risultato {#section_5953BB6FD0CE4EF69D1D60B8B1203431}

Esempio di output del rapporto:

Periodo: Mar 2010

Report: Prodotti per pagina

| Prodotti per pagina | Ordini | Mycost |
|---|---|---|
| Product1 | 1000 | $3000.00 |
| Home page | 600 | $1800.00 |
| Carrello acquisti | 400 | $1200.00 |

<!-- 

c_example_7_continued__different_rate_hinge.xml

 -->

In questo caso, si importano i seguenti dati del file:

| Chiave | Mytext | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | Cost 1_ mar_ fixed |  | 3 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | order | revenue |

## Risultato {#section_6E2604D9A3B0455585EFF0F80FF54127}

Esempio di output del rapporto:

Periodo: Mar 2010

Report: Prodotti per pagina

| Prodotti per pagina | Ordini | Mycost |
|---|---|---|
| Product1 | 1000 | $3000.00 |
| Home page | 600 | $1,000.00 |
| Carrello acquisti | 400 | $2,000.00 |

