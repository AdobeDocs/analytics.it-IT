---
description: Esempi per fornire indicazioni per l'importazione di classificazioni numeriche 2.
subtopic: Classifications
title: Esempi
topic: Admin tools
uuid: 0553d07f-87c1-4372-90ce-7118a6393a01
translation-type: tm+mt
source-git-commit: 6778dd290424651dc959224daa0eef8ebd8196e5
workflow-type: tm+mt
source-wordcount: '551'
ht-degree: 32%

---


# Esempi

Esempi per fornire indicazioni per l&#39;importazione di classificazioni numeriche 2.

<!-- 

c_example_1__rate.xml

 -->

In questo caso, hai creato la classificazione nel [!UICONTROL Classification Conversion] manager e vuoi importare i valori di gennaio:

| Chiave | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_jan_var` |  | `.2` |
| Product2 | Text2 | `Cost2_jan_var` |  | `.3` |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/01/01 - 2010/01/31 | ricavo | ricavo |
| 2010/01/01 - 2010/01/31 | ricavo | ricavo |

A gennaio, Product1 aveva un costo del 20% delle entrate (come mostrato in `~MyCost^~value~`) e Product2 aveva un costo del 30% delle entrate. Poiché si sta importando una nuova riga, `~MyCost^~id~` è vuota.

## Risultato {#section_E0569289C9B34C479C7D2CD9ECBF866E}

Un esempio di output del rapporto è illustrato di seguito:

Periodo: Gen 2010

Rapporto: Prodotti

| Prodotti | Ricavi | MyCost |
|---|---|---|
| Product1 | $10,000.23 | $2000.05 |
| Product2 | $9,000.04 | $2700.01 |

<!-- 

c_example_2__rate.xml

 -->

| Chiave | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_jan_var` | 1 | .2 |
| Product2 | Text2 | `Cost2_jan_var` | 2 | .3 |
| Product1 | Text1 | `Cost1_feb_var` |  | .15 |
| Product2 | Text2 | `Cost2_feb_var` |  | .25 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/01/01 - 2010/01/31 | ricavo | ricavo |
| 2010/01/01 - 2010/01/31 | ricavo | ricavo |
| 2010/02/01 - 2010/02/28 | ricavo | ricavo |
| 2010/02/01 - 2010/02/28 | ricavo | ricavo |

A febbraio, il costo dell&#39;utente per Product1 è sceso al 15% delle entrate, e Product2 è sceso al 25% delle entrate.

## Risultato {#section_23DF5353AC1B478C88647F222703352C}

Un esempio di output del rapporto è illustrato di seguito:

Periodo: Gen 2010

Rapporto: Prodotti

| Prodotti | Ricavi | MyCost |
|---|---|---|
| Product1 | $10,000.23 | $2000.05 |
| Product2 | $9,000.04 | $2700.01 |

Periodo: Feb 2010

Rapporto: Prodotti

| Prodotti | Ricavi | MyCost |
|---|---|---|
| Product1 | $15,500.75 | $2325.11 |
| Product2 | $12,300.52 | $3075.13 |

Periodo: 1 gennaio 2010 - 28 febbraio 2010

Rapporto: Prodotti

| Prodotti | Ricavi | MyCost |
|---|---|---|
| Product1 | $25,500.98 | $4325.16 |
| Product2 | $21,300.56 | $5,775.14 |

<!-- 

c_example_3__fixed.xml

 -->

È quindi necessario importare i dati seguenti:

| Chiave | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_mar_fixed` |  | 3000.00 |
| Product2 | Text2 | `Cost2_jan_fixed` |  | 2000.00 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | fixed | none |
| 2010/03/01 - 2010/03/31 | fixed | none |

## Risultato {#section_674B57ADB8284B878F9E670038C31464}

Un esempio di output del rapporto è illustrato di seguito:

Periodo: Mar 2010

Rapporto: Prodotti

| Prodotti | Ricavi | MyCost |
|---|---|---|
| Product1 | $11,023.75 | $3000.00 |
| Product2 | $8,000.12 | $2000.00 |

<!-- 

c_example_4__(advanced)_multiple_row_per_time_period.xml

 -->

In questo esempio, si aggiunge una spesa di spedizione di $500 al Prodotto1 per gennaio e una spesa di spedizione di $600 a febbraio.

| Chiave | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_jan_var` | 1 | .2 |
| Product1 | Text1 | `Cost2_jan_fixed` |  | 500 |
| Product1 | Text1 | `Cost1_feb_var` | 2 | .15 |
| Product1 | Text1 | `Cost2_feb_fixed` |  | 600 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/01/01 - 2010/01/31 | ricavo | ricavo |
| 2010/01/01 - 2010/01/31 | fixed | none |
| 2010/02/01 - 2010/01/31 | ricavo | ricavo |
| 2010/02/01 - 2010/01/31 | fixed | none |

Le righe precedentemente importate dispongono di un ID che indica che non sono nuovi costi.

## Risultato {#section_2096084176614B9AA60F97D5853CB9EA}

Un esempio di output del rapporto è illustrato di seguito:

Periodo: Gen 2010

Rapporto: Prodotti

| Prodotti | Ricavi | MyCost |
|---|---|---|
| Product1 | $10,000.23 | $2500.05 |

>[!NOTE]
>
>Questa funzione consente agli utenti avanzati di approssimare i valori. Le informazioni risultanti non devono essere trattate come valori esatti.

<!-- 

c_example_5__identical_rate_hinge.xml

 -->

L&#39;esempio seguente illustra quanto segue:

| Chiave | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_mar_var` |  | 1 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | order | order |

## Risultato {#section_39E24ECCC3B34C9AADC25572662750E5}

Un esempio di output del rapporto è illustrato di seguito:

Periodo: Mar 2010

Rapporto: Prodotti per pagina

| Prodotti per pagina | Ordini | MyCost |
|---|---|---|
| Product1 | 1000 | $1000.00 |
| Home page | 600 | $600 |
| Carrello | 400 | $400 |

<!-- 

c_example_5__fixed_no_hinge.xml

 -->

| Chiave | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_mar_fixed` |  | 3000.00 |
| Product2 | Text2 | `Cost2_mar_fixed` |  | 2000.00 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | fixed | none |
| 2010/03/01 - 2010/03/31 | fixed | none |

## Risultato {#section_7F5F5970077D4E14A5DC91495E23540D}

Un esempio di output del rapporto è illustrato di seguito:

Periodo: Mar 2010

Rapporto: Prodotti per pagina

| Prodotti per pagina | Ordini | MyCost |
|---|---|---|
| Product1 | 1000 | $3000.00 |
| Home page | 600 | 0 |
| Carrello | 400 | 0 |

<!-- 

c_example_7__fixed_hinge.xml

 -->

In questo caso, è necessario importare i dati seguenti:

| Chiave | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_mar_fixed` |  | 3000.00 |
| Product2 | Text2 | `Cost2_mar_fixed` |  | 2000.00 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | fixed | ricavo |
| 2010/03/01 - 2010/03/31 | fixed | ricavo |

## Risultato {#section_5953BB6FD0CE4EF69D1D60B8B1203431}

Un esempio di output del rapporto è illustrato di seguito:

Periodo: Mar 2010

Rapporto: Prodotti per pagina

| Prodotti per pagina | Ordini | MyCost |
|---|---|---|
| Product1 | 1000 | $3000.00 |
| Home page | 600 | $1800.00 |
| Carrello | 400 | $1200.00 |

<!-- 

c_example_7_continued__different_rate_hinge.xml

 -->

In questo caso, potete importare i seguenti dati del file:

| Chiave | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | Cost1_mar_fixed |  | 3 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | order | ricavo |

## Risultato {#section_6E2604D9A3B0455585EFF0F80FF54127}

Un esempio di output del rapporto è illustrato di seguito:

Periodo: Mar 2010

Rapporto: Prodotti per pagina

| Prodotti per pagina | Ordini | MyCost |
|---|---|---|
| Product1 | 1000 | $3000.00 |
| Home page | 600 | $1,000.00 |
| Carrello | 400 | $2,000.00 |

