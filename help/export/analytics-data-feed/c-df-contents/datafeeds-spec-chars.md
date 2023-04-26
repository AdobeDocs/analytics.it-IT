---
description: Informazioni sui caratteri speciali utilizzati nel feed di dati.
keywords: Feed di dati;processo;caratteri speciali;dati_hit;variabili con più valori;elenco_eventi;elenco_prodotti;mvar
subtopic: data feeds
title: Caratteri speciali nei feed di dati
feature: Data Feeds
exl-id: b816ebc5-0b23-4420-aa8c-b88953d031e6
source-git-commit: 6e59ee3cb3eb59b025053603cd1357c5a2709d00
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 2%

---

# Caratteri speciali nei feed di dati

Ad Adobe, utilizza la logica escape per assicurarti che i valori inviati ai server di raccolta dati non danneggino o danneggiino i file di feed di dati. I seguenti caratteri sono riservati per Adobe ai seguenti scopi in `hit_data.tsv`.

## Caratteri speciali in qualsiasi colonna

| Carattere | Descrizione |
|--- |--- |
| `\t` | Rappresenta una scheda. Contrassegna la fine di una colonna o di un campo di dati. |
| `\n` | Rappresenta una nuova riga. Segna la fine di una riga o di un hit. |
| `\` | Barra rovesciata. Ignora i caratteri quando inviati come parte della raccolta dati. |

Quando questi valori riservati sono preceduti da una barra inversa, sono stati inviati come parte della raccolta di dati.

| Carattere | Descrizione |
|--- |--- |
| `\\t` | Valore &#39;`\t`&quot; è stato inviato durante la raccolta dei dati, con escape per Adobe. |
| `\\n` | Valore &#39;`\n`&quot; è stato inviato durante la raccolta dei dati, con escape per Adobe. |
| `\\` | Valore &#39;`\`&quot; è stato inviato durante la raccolta dei dati, con escape per Adobe. |

Ad esempio, un visitatore del sito utilizza la ricerca interna e cerca `"search\nstring"`. Compilare eVar1 con `"search\nstring"`e invia tale valore ad Adobe. Adobe riceve questo hit ed evita la nuova riga inclusa nella stringa. Il valore effettivo inserito nei dati non elaborati è `"search\\nstring"`.

## Caratteri speciali nelle variabili con più valori (events_list, products_list, mvvar)

I seguenti caratteri hanno un significato speciale nelle colonne che possono contenere più valori.

| Carattere | Descrizione |
|--- |--- |
| `,` | Virgola. Rappresenta la fine di un singolo valore. Separa le stringhe di prodotto, gli ID evento o altri valori. |
| `;` | Punto e virgola. Rappresenta la fine di un singolo valore in `product_list`. Separa i campi all’interno di una singola stringa di prodotto. |
| `=` | Segno uguale. Assegna un valore a un evento in `product_list`. |
| `^` | Accento circonflesso. Ignora i caratteri quando inviati come parte della raccolta dati. |

Quando questi valori riservati sono preceduti da un accento circonflesso, sono stati inviati come parte della raccolta di dati.

| Carattere | Descrizione |
|--- |--- |
| `^,` | Valore &#39;`,`&quot; è stato inviato durante la raccolta dei dati, con escape per Adobe. |
| `^;` | Valore &#39;`;`&quot; è stato inviato durante la raccolta dei dati, con escape per Adobe. |
| `^=` | Valore &#39;`=`&quot; è stato inviato durante la raccolta dei dati, con escape per Adobe. |
| `^^` | Valore &#39;`^`&quot; è stato inviato durante la raccolta dei dati, con escape per Adobe. |
