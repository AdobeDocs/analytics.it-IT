---
description: Informazioni sui caratteri speciali utilizzati nel feed di dati.
keywords: Feed dati; processo; caratteri speciali; hit_ data; variabili con valori multipli; events_ list; products_ list; mvvar
seo-description: Informazioni sui caratteri speciali utilizzati nel feed di dati.
seo-title: Caratteri speciali
solution: Analytics
subtopic: feed dati
title: Caratteri speciali
topic: Reports & Analytics
uuid: 5 efe 019 b -39 e 6-4226-a 936-88202 a 02 f 5 e 6
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Caratteri speciali

Informazioni sui caratteri speciali utilizzati nel feed di dati.

* [Caratteri speciali nel file hit_ data](../../../export/analytics-data-feed/c-df-contents/datafeeds-spec-chars.md#section_9759C7A6AE684EB5B4A154FB6A26B39E)
* [Caratteri speciali in variabili con più valori (eventi_ list, products_ list, mvvar)](../../../export/analytics-data-feed/c-df-contents/datafeeds-spec-chars.md#section_056F8D540FFC4F24A001DC74331C2AAC)
* [Flusso di lavoro di esempio](../../../export/analytics-data-feed/c-df-contents/datafeeds-spec-chars.md#section_97F8C2925A35433DA2E7E8BE60037E37)

## Special characters in the hit_data file {#section_9759C7A6AE684EB5B4A154FB6A26B39E}

I seguenti caratteri hanno un significato speciale nel file hit_ data:

| Carattere | Significato | Descrizione |
|--- |--- |--- |
| \ t (carattere tab) | Fine colonna | Segna la fine di un campo dati. |
| \ n (carattere newline) | Fine riga | Indica la fine di una riga dati. |
| \ (carattere barra rovesciata) | Carattere escape | Passa a tabulazione, newline e barra rovesciata quando il carattere era parte del valore inviato durante la raccolta dati. |

Se uno dei caratteri speciali è preceduto da una barra rovesciata, rappresenta un carattere letterale.

| Carattere | Significato | Descrizione |
|--- |--- |--- |
| \\ t | Tab | Carattere di tabulazione letterale. Questo carattere faceva parte del valore inviato durante la raccolta di dati. |
| \\ n | Newline | Newline letterale. Questo carattere faceva parte del valore inviato durante la raccolta di dati. |
| \\ | Barra rovesciata | Carattere barra rovesciata. Questo carattere faceva parte del valore inviato durante la raccolta di dati. |

## Special characters in multi-valued variables (events_list, products_list, mvvars) {#section_056F8D540FFC4F24A001DC74331C2AAC}

I caratteri seguenti hanno un significato speciale nelle variabili con più valori:

<table id="table_FDA13DE05A784ED4972C2955BD2642C7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Carattere </th> 
   <th colname="col02" class="entry"> Significato </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> , </code> (virgola) </td> 
   <td colname="col02"> Fine del valore </td> 
   <td colname="col2"> <p>Separa stringhe di prodotto, ID evento o altri valori in variabili con più valori. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> ; </code> (carattere punto e virgola) </td> 
   <td colname="col02"> Fine del valore secondario all'interno di un singolo valore di prodotto </td> 
   <td colname="col2"> <p>Separates values associated with an individual product in the <code> product_list </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> = </code> (uguale a carattere) </td> 
   <td colname="col02"> Assegnazione valore </td> 
   <td colname="col2"> <p>Assigns a value to an event in the <code> event_list </code>. </p> </td> 
  </tr> 
 </tbody> 
</table>

Se uno qualsiasi dei caratteri speciali è preceduto da un accento circonflesso, rappresenta un carattere letterale.

| Carattere | Significato | Descrizione |
|--- |--- |--- |
| ^, | Virgola | Carattere virgola letterale. Questo carattere faceva parte del valore inviato durante la raccolta di dati. |
| ^; | Punto e virgola | Carattere punto e virgola letterale. Questo carattere faceva parte del valore inviato durante la raccolta di dati. |
| ^= | È uguale a | Il letterale corrisponde al carattere. Questo carattere faceva parte del valore inviato durante la raccolta di dati. |
| ^^ | Accento circonflesso | Carattere caret letterale. Questo carattere faceva parte del valore inviato durante la raccolta di dati. |

## Sample workflow {#section_97F8C2925A35433DA2E7E8BE60037E37}

If some of the columns in your data feed contain user-submitted data, you should check for special characters before separating the data by column or row using `split` or `readLine`, or similar.

Considerate i dati seguenti:

| Larghezza browser | Altezza browser | eVar1 | prop1 |
|---|---|---|---|
| 1680 | 1050 | search\ nstring | en |
| 800 | 600 | search\ tstring | en |

Durante l'esportazione, i caratteri newline e tab nei valori evar 1 sono soggetti a escape. Il feed di dati per queste righe viene visualizzato come segue:

```
1680\t1050\tsearch\\nstring\ten\n 
800\t600\tsearch\\tstring\ten\n
```

Calling `readLine()` on the first row returns the following partial string:

```
800\t600\tsearch\
```

Calling `split("\t")` on the second row returns the following string array:

```
800 
600 
search\ 
string 
en
```

Per evitare questa situazione, usa una soluzione simile a quella di seguito:

1. A partire dall'inizio del file, leggere fino a individuare un carattere tabet, newline, backslash o caret.
1. Eseguire un'azione in base al carattere speciale rilevato:

   * Tabulazione: inserite la stringa verso l'alto che si trova in una cella di archivio dati e continua.
   * Newline - Completa la riga di archivio dati.
   * Barra rovesciata: leggere il carattere successivo, inserire il carattere letterale appropriato e continuare.
   * Accento circonflesso: leggere il carattere successivo, inserire la stringa letterale appropriata e continuare.

