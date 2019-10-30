---
description: Informazioni sui caratteri speciali utilizzati nel feed di dati.
keywords: Feed dati;processo;caratteri speciali;hit_data;variabili con più valori;events_list;products_list;mvar
seo-description: Informazioni sui caratteri speciali utilizzati nel feed di dati.
seo-title: Caratteri speciali
solution: Analytics
subtopic: feed di dati
title: Caratteri speciali
topic: Reports and Analytics
uuid: 5efe019b-39e6-4226-a936-88202a02f5e6
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Caratteri speciali

Informazioni sui caratteri speciali utilizzati nel feed di dati.

* [Caratteri speciali nel file hit_data](../../../export/analytics-data-feed/c-df-contents/datafeeds-spec-chars.md#section_9759C7A6AE684EB5B4A154FB6A26B39E)
* [Caratteri speciali nelle variabili con più valori (events_list, products_list, mvvar)](../../../export/analytics-data-feed/c-df-contents/datafeeds-spec-chars.md#section_056F8D540FFC4F24A001DC74331C2AAC)
* [Flusso di lavoro di esempio](../../../export/analytics-data-feed/c-df-contents/datafeeds-spec-chars.md#section_97F8C2925A35433DA2E7E8BE60037E37)

## Caratteri speciali nel file hit_data {#section_9759C7A6AE684EB5B4A154FB6A26B39E}

I seguenti caratteri hanno un significato speciale nel file hit_data:

| Carattere | Significato | Descrizione |
|--- |--- |--- |
| \t (carattere di tabulazione) | Fine colonna | Indica la fine di un campo di dati. |
| \n (carattere nuova riga) | Fine riga | Indica la fine di una riga di dati. |
| \ (barra rovesciata) | Carattere di escape | Scheda Esc, nuova riga e barra rovesciata quando il carattere faceva parte del valore inviato durante la raccolta di dati. |

Quando uno dei caratteri speciali è preceduto da una barra rovesciata, rappresenta un carattere letterale.

| Carattere | Significato | Descrizione |
|--- |--- |--- |
| \\t | Tab | Carattere tabulazione letterale. Questo carattere faceva parte del valore inviato durante la raccolta dei dati. |
| \\n | Newline | Newline letterale. Questo carattere faceva parte del valore inviato durante la raccolta dei dati. |
| \\ | Barra rovesciata | Carattere barra rovesciata letterale. Questo carattere faceva parte del valore inviato durante la raccolta dei dati. |

## Caratteri speciali nelle variabili con più valori (events_list, products_list, mvvar) {#section_056F8D540FFC4F24A001DC74331C2AAC}

I seguenti caratteri hanno un significato speciale nelle variabili con più valori:

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
   <td colname="col2"> <p>Separa le stringhe di prodotto, gli ID evento o altri valori in variabili con più valori. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> ; </code> (punto e virgola) </td> 
   <td colname="col02"> Fine del sotto-valore all'interno di un singolo valore di prodotto </td> 
   <td colname="col2"> <p>Separa i valori associati a un singolo prodotto nel <code> product_list </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> = </code> (uguale a carattere) </td> 
   <td colname="col02"> Assegnazione valore </td> 
   <td colname="col2"> <p>Assegna un valore a un evento nel <code> event_list </code>. </p> </td> 
  </tr> 
 </tbody> 
</table>

Quando uno dei caratteri speciali è preceduto da un punto di vista, essi rappresentano un carattere letterale.

| Carattere | Significato | Descrizione |
|--- |--- |--- |
| ^, | Virgola | Carattere letterale virgola. Questo carattere faceva parte del valore inviato durante la raccolta dei dati. |
| ^; | Semicolon | Carattere punto e virgola letterale. Questo carattere faceva parte del valore inviato durante la raccolta dei dati. |
| ^= | È uguale a | Letterale uguale a carattere. Questo carattere faceva parte del valore inviato durante la raccolta dei dati. |
| ^^ | Accento circonflesso | Carattere alfabeto letterale. Questo carattere faceva parte del valore inviato durante la raccolta dei dati. |

## Flusso di lavoro di esempio {#section_97F8C2925A35433DA2E7E8BE60037E37}

Se alcune colonne del feed di dati contengono dati inviati dall'utente, è necessario verificare la presenza di caratteri speciali prima di separare i dati per colonna o riga utilizzando `split` o `readLine`, o similare.

Considerare i dati seguenti:

| Larghezza browser | Altezza browser | eVar1 | prop1 |
|---|---|---|---|
| 1680 | 1050 | search\nstring | en |
| 800 | 600 | search\tstring | en |

Durante l'esportazione, i caratteri newline e tab nei valori eVar1 sono preceduti da escape. Il feed di dati per queste righe viene visualizzato come segue:

```
1680\t1050\tsearch\\nstring\ten\n 
800\t600\tsearch\\tstring\ten\n
```

Una chiamata `readLine()` alla prima riga restituisce la seguente stringa parziale:

```
800\t600\tsearch\
```

Una chiamata `split("\t")` alla seconda riga restituisce il seguente array di stringhe:

```
800 
600 
search\ 
string 
en
```

Per evitare questo problema, utilizzate una soluzione simile a quella indicata di seguito:

1. A partire dall'inizio del file, leggere fino a individuare un carattere tabulazione, newline, barra rovesciata o punto di inserimento.
1. Eseguire un'azione in base al carattere speciale rilevato:

   * Tab - inserire la stringa su quel punto in una cella dell'archivio dati e continuare.
   * Newline: completa la riga dell'archivio dati.
   * Barra rovesciata: leggere il carattere successivo, inserire il valore letterale di stringa appropriato e continuare.
   * Caret - leggere il carattere successivo, inserire il valore letterale di stringa appropriato e continuare.

