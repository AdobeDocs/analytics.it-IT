---
description: Domande frequenti sui feed di dati
keywords: Data Feed;job;pre column;post column;case sensitivity
title: Domande frequenti sui feed di dati
translation-type: tm+mt
source-git-commit: a94b8e090b9a3c75a57fd396cac8486bba2e5d79
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 0%

---


# Domande frequenti sui feed di dati

Domande frequenti sui feed di dati.

## Qual è la differenza tra le colonne con un `post_` prefisso e le colonne senza un `post_` prefisso?

Le colonne senza il `post_` prefisso contengono i dati esattamente come sono stati inviati alla raccolta dati. Le colonne con un `post_` prefisso contengono il valore dopo l’elaborazione. Esempi che possono modificare un valore sono la persistenza variabile, le regole di elaborazione, le regole VISTA, la conversione di valuta o altri Adobi di logica  lato server.  Adobe consiglia di utilizzare, ove possibile, la `post_` versione di una colonna.

Se una colonna non contiene una `post_` versione (ad esempio, `visit_num`), la colonna può essere considerata una colonna di post.

## In che modo i feed di dati gestiscono la sensibilità alle maiuscole/minuscole?

In  Adobe Analytics, la maggior parte delle variabili non fa distinzione tra maiuscole e minuscole ai fini del reporting. Ad esempio, &#39;neve&#39;, &#39;neve&#39;, &#39;Snow&#39; e &#39;sNow&#39; sono tutti considerati allo stesso valore. La sensibilità delle maiuscole e delle minuscole viene mantenuta nei feed di dati.

Se si visualizzano diverse varianti di maiuscole e minuscole dello stesso valore tra colonne non post e post (ad esempio, &#39;neve&#39; nella precolonna e &#39;neve&#39; nella colonna post), l&#39;implementazione utilizza sia valori maiuscoli che minuscoli nel sito. La variante case nella colonna post è stata precedentemente passata e memorizzata nel cookie virtuale, oppure è stata elaborata più o meno allo stesso tempo per quella suite di rapporti.

## I bot sono filtrati dalle regole bot della console di amministrazione incluse nei feed di dati?

I feed di dati non includono i bot filtrati dalle regole bot della console [di amministrazione](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/bot-removal/bot-removal.html).

## Perché visualizzo più `000` valori nella colonna `event_list` `post_event_list` o feed di dati?

Alcuni editor di fogli di calcolo, in particolare Microsoft Excel, arrotondano automaticamente numeri molto grandi. La `event_list` colonna contiene molti numeri delimitati da virgole, che talvolta vengono considerati grandi da Excel. arrotonda le ultime cifre a `000`.

 Adobe consiglia di non aprire automaticamente `hit_data.tsv` i file in Microsoft Excel. Utilizzare la finestra di dialogo Importa dati di Excel e assicurarsi che tutti i campi siano trattati come testo.
