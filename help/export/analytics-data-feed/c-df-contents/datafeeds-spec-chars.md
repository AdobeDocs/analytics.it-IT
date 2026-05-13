---
description: Informazioni sui caratteri speciali utilizzati nel feed di dati.
keywords: Feed dati;job;caratteri speciali;hit_data;variabili multivalore;elenco_eventi;elenco_prodotti;mvars
subtopic: data feeds
title: Caratteri speciali nei feed di dati
feature: Data Feeds
exl-id: b816ebc5-0b23-4420-aa8c-b88953d031e6
TQID: https://experienceleague.adobe.com/2ekzWPqnIapW2Vrqg6DL9qDf9EcPG2-iLY4NdbdhKNI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 333
ht-degree: 2%

---

# Caratteri speciali nei feed di dati

Adobe utilizza la logica di escape per assicurarsi che i valori inviati ai server di raccolta dati non danneggino o non danneggino i file di feed dati. I seguenti caratteri sono riservati da Adobe per le seguenti finalità in `hit_data.tsv`.

## Caratteri speciali in qualsiasi colonna

| Carattere | Descrizione |
|--- |--- |
| `\t` | Rappresenta una scheda. Contrassegna la fine di una colonna o di un campo dati. |
| `\n` | Rappresenta una nuova riga. Contrassegna la fine di una riga o di un hit. |
| `\` | Barra rovesciata. Evita i caratteri quando vengono inviati come parte della raccolta dati. |

Quando questi valori riservati sono preceduti da una barra rovesciata, sono stati inviati come parte della raccolta dati.

| Carattere | Descrizione |
|--- |--- |
| `\\t` | Il valore &#39;`\t`&#39; è stato inviato durante la raccolta dati, con escape da Adobe. |
| `\\n` | Il valore &#39;`\n`&#39; è stato inviato durante la raccolta dati, con escape da Adobe. |
| `\\` | Il valore &#39;`\`&#39; è stato inviato durante la raccolta dati, con escape da Adobe. |

Ad esempio, un visitatore del tuo sito utilizza la ricerca interna e cerca `"search\nstring"`. Compilate eVar1 con `"search\nstring"` e inviate tale valore ad Adobe. Adobe riceve questo hit ed esce dalla nuova riga inclusa nella stringa. Il valore effettivo inserito nei dati non elaborati è `"search\\nstring"`.

## Caratteri speciali nelle variabili con più valori (events_list, products_list, mvars)

I seguenti caratteri hanno un significato speciale nelle colonne che possono contenere più valori.

| Carattere | Descrizione |
|--- |--- |
| `,` | Virgola. Rappresenta la fine di un singolo valore. Separa le stringhe di prodotto, gli ID evento o altri valori. |
| `;` | Punto e virgola. Rappresenta la fine di un singolo valore in `product_list`. Separa i campi all’interno di una singola stringa di prodotto. |
| `=` | Segno di uguale. Assegna un valore a un evento in `product_list`. |
| `^` | Attenzione. Evita i caratteri quando vengono inviati come parte della raccolta dati. |

Quando questi valori riservati sono preceduti da un accento circonflesso, sono stati inviati come parte della raccolta di dati.

| Carattere | Descrizione |
|--- |--- |
| `^,` | Il valore &#39;`,`&#39; è stato inviato durante la raccolta dati, con escape da Adobe. |
| `^;` | Il valore &#39;`;`&#39; è stato inviato durante la raccolta dati, con escape da Adobe. |
| `^=` | Il valore &#39;`=`&#39; è stato inviato durante la raccolta dati, con escape da Adobe. |
| `^^` | Il valore &#39;`^`&#39; è stato inviato durante la raccolta dati, con escape da Adobe. |
