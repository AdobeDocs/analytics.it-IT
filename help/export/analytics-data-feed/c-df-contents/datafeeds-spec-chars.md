---
description: Informazioni sui caratteri speciali utilizzati nel feed di dati.
keywords: Data Feed;job;special characters;hit_data;multi-valued variables;events_list;products_list;mvvars
subtopic: data feeds
title: Caratteri speciali nei feed di dati
topic: Reports and analytics
uuid: 5efe019b-39e6-4226-a936-88202a02f5e6
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Caratteri speciali nei feed di dati

Adobe utilizza la logica di escape per assicurarsi che i valori inviati ai server di raccolta dati non corrompa o non danneggi i file di feed di dati. I seguenti caratteri sono riservati da Adobe ai seguenti scopi in `hit_data.tsv`.

## Caratteri speciali in qualsiasi colonna

| Carattere | Descrizione |
|--- |--- |
| `\t` | Rappresenta una scheda. Indica la fine di una colonna o di un campo di dati. |
| `\n` | Rappresenta una nuova riga. Indica la fine di una riga o di un hit. |
| `\` | Barra rovesciata. Rimuove i caratteri quando vengono inviati come parte della raccolta di dati. |

Quando questi valori riservati sono preceduti da una barra rovesciata, sono stati inviati come parte della raccolta di dati.

| Carattere | Descrizione |
|--- |--- |
| `\\t` | Il valore '`\t`' è stato inviato durante la raccolta dei dati, con escape da parte di Adobe. |
| `\\n` | Il valore '`\n`' è stato inviato durante la raccolta dei dati, con escape da parte di Adobe. |
| `\\` | Il valore '`\`' è stato inviato durante la raccolta dei dati, con escape da parte di Adobe. |

Ad esempio, un visitatore del sito utilizza la ricerca interna e cerca "search\nstring". Compila eVar1 con "search\nstring" e invialo ad Adobe. Adobe riceve l’hit ed evita la newline inclusa nella stringa. Il valore effettivo inserito nei dati non elaborati è "search\\nstring".

## Caratteri speciali nelle variabili con più valori (events_list, products_list, mvvar)

I seguenti caratteri hanno un significato speciale nelle colonne che possono contenere più valori.

| Carattere | Descrizione |
|--- |--- |
| `,` | Virgola. Rappresenta la fine di un singolo valore. Separa le stringhe di prodotto, gli ID evento o altri valori. |
| `;` | Semi-due punti. Rappresenta la fine di un singolo valore in `product_list`. Separa i campi all'interno di una singola stringa di prodotto. |
| `=` | È uguale al segno. Assegna un valore a un evento in `product_list`. |
| `^` | Accento circonflesso. Rimuove i caratteri quando vengono inviati come parte della raccolta di dati. |

Quando questi valori riservati sono preceduti da un oggetto, sono stati inviati come parte della raccolta di dati.

| Carattere | Descrizione |
|--- |--- |
| `^,` | Il valore '`,`' è stato inviato durante la raccolta dei dati, con escape da parte di Adobe. |
| `^;` | Il valore '`;`' è stato inviato durante la raccolta dei dati, con escape da parte di Adobe. |
| `^=` | Il valore '`=`' è stato inviato durante la raccolta dei dati, con escape da parte di Adobe. |
| `^^` | Il valore '`^`' è stato inviato durante la raccolta dei dati, con escape da parte di Adobe. |
