---
description: Informazioni sui caratteri speciali utilizzati nel feed di dati.
keywords: Feed di dati;processo;caratteri speciali;dati_hit;variabili con più valori;elenco_eventi;elenco_prodotti;mvar
subtopic: data feeds
title: Caratteri speciali nei feed di dati
feature: Nozioni di base su Reports & Analytics
uuid: 5efe019b-39e6-4226-a936-88202a02f5e6
exl-id: b816ebc5-0b23-4420-aa8c-b88953d031e6
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 2%

---

# Caratteri speciali nei feed di dati

Ad Adobe, utilizza la logica escape per assicurarti che i valori inviati ai server di raccolta dati non danneggino o danneggiino i file di feed di dati. I seguenti caratteri sono riservati per Adobe ai seguenti fini in `hit_data.tsv`.

## Caratteri speciali in qualsiasi colonna

| Carattere | Descrizione |
|--- |--- |
| `\t` | Rappresenta una scheda. Contrassegna la fine di una colonna o di un campo di dati. |
| `\n` | Rappresenta una nuova riga. Segna la fine di una riga o di un hit. |
| `\` | Barra rovesciata. Ignora i caratteri quando inviati come parte della raccolta dati. |

Quando questi valori riservati sono preceduti da una barra inversa, sono stati inviati come parte della raccolta di dati.

| Carattere | Descrizione |
|--- |--- |
| `\\t` | Il valore &#39;`\t`&#39; è stato inviato durante la raccolta dei dati, in sequenza per Adobe. |
| `\\n` | Il valore &#39;`\n`&#39; è stato inviato durante la raccolta dei dati, in sequenza per Adobe. |
| `\\` | Il valore &#39;`\`&#39; è stato inviato durante la raccolta dei dati, in sequenza per Adobe. |

Ad esempio, un visitatore del sito utilizza la ricerca interna e cerca &quot;search\nstring&quot;. È possibile compilare eVar1 con &quot;search\nstring&quot; e inviare tale valore ad Adobe. Adobe riceve questo hit ed evita la nuova riga inclusa nella stringa. Il valore effettivo inserito nei dati non elaborati è &quot;search\\nstring&quot;.

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
| `^,` | Il valore &#39;`,`&#39; è stato inviato durante la raccolta dei dati, in sequenza per Adobe. |
| `^;` | Il valore &#39;`;`&#39; è stato inviato durante la raccolta dei dati, in sequenza per Adobe. |
| `^=` | Il valore &#39;`=`&#39; è stato inviato durante la raccolta dei dati, in sequenza per Adobe. |
| `^^` | Il valore &#39;`^`&#39; è stato inviato durante la raccolta dei dati, in sequenza per Adobe. |
