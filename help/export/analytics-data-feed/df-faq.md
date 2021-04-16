---
description: Domande frequenti sui feed di dati
keywords: Feed di dati;processo;pre colonna;post colonna;sensibilità maiuscole/minuscole
title: Domande frequenti sui feed di dati
exl-id: 1bbf62d5-1c6e-4087-9ed9-8f760cad5420
translation-type: tm+mt
source-git-commit: c6d4095fdf86be52c7921aed84b9229ac3b27f82
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 0%

---

# Domande frequenti sui feed di dati

Domande frequenti sui feed di dati.

## Qual è la differenza tra le colonne con un prefisso `post_` e le colonne senza un prefisso `post_`?

Le colonne senza il prefisso `post_` contengono i dati esattamente come sono stati inviati alla raccolta dati. Le colonne con un prefisso `post_` contengono il valore dopo l’elaborazione. Esempi che possono modificare un valore sono la persistenza delle variabili, le regole di elaborazione, le regole VISTA, la conversione di valuta o altri Adobi logici lato server. Se possibile, Adobe consiglia di utilizzare la versione `post_` di una colonna.

Se una colonna non contiene una versione `post_` (ad esempio, `visit_num`), può essere considerata una colonna post.

## Come vengono gestiti i feed di dati per la distinzione tra maiuscole e minuscole?

In Adobe Analytics, la maggior parte delle variabili viene considerata senza distinzione tra maiuscole e minuscole a scopo di reporting. Ad esempio, &quot;neve&quot;, &quot;neve&quot;, &quot;NEVE&quot; e &quot;sNow&quot; sono tutti considerati allo stesso valore. La distinzione tra maiuscole e minuscole viene mantenuta nei feed di dati.

Se vedi diverse varianti di maiuscole e minuscole dello stesso valore tra colonne non post e post (ad esempio, &quot;neve&quot; nella colonna precedente e &quot;neve&quot; nella colonna post), l’implementazione utilizza valori sia in maiuscolo che in minuscolo nel sito. La variazione di maiuscole e minuscole nella colonna post è stata precedentemente passata e memorizzata nel cookie virtuale o è stata elaborata più o meno nello stesso momento per quella suite di rapporti.

## I bot vengono filtrati dalle regole bot di Admin Console incluse nei feed di dati?

I feed di dati non includono bot filtrati da [regole bot della console di amministrazione](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/bot-removal/bot-removal.html).

## Perché visualizzo più valori `000` nella colonna dei feed di dati `event_list` o `post_event_list`?

Alcuni editor di fogli di calcolo, in particolare Microsoft Excel, arrotondano automaticamente numeri molto grandi. La colonna `event_list` contiene molti numeri delimitati da virgole e a volte Excel ne considera un numero elevato. Arrotonda le ultime diverse cifre a `000`.

Adobe consiglia di non aprire automaticamente i file `hit_data.tsv` in Microsoft Excel. Utilizzare invece la finestra di dialogo Importa dati di Excel e assicurarsi che tutti i campi siano trattati come testo.

## Perché non posso estrarre file &quot;Orari&quot; da dati che hanno più di 7 giorni?

Per i dati che hanno più di 7 giorni, i file &quot;Ogni ora&quot; di un giorno vengono combinati in un unico file &quot;Giornaliero&quot;.

Esempio: Il 9 marzo 2021 è stato creato un nuovo feed di dati e i dati dal 1° gennaio 2021 al 9 marzo vengono consegnati come &quot;Orario&quot;. Tuttavia, i file &quot;Ogni ora&quot; prima del 2 marzo 2021 sono combinati in un unico file &quot;Giornaliero&quot;. Puoi estrarre i file &quot;Ogni ora&quot; solo dai dati che hanno meno di 7 giorni dalla data di creazione. In questo caso, dal 2 marzo al 9 marzo.
