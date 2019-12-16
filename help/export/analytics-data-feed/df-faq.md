---
description: Domande frequenti sui feed di dati
keywords: Data Feed;job;pre column;post column;case sensitivity
title: Domande frequenti sui feed di dati
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Domande frequenti sui feed di dati

Domande frequenti sui feed di dati.

## Qual è la differenza tra le colonne con un `post_` prefisso e le colonne senza un `post_` prefisso?

Le colonne senza il `post_` prefisso contengono i dati esattamente come sono stati inviati alla raccolta dati. Le colonne con un `post_` prefisso contengono il valore dopo l’elaborazione. Esempi che possono modificare un valore sono la persistenza variabile, le regole di elaborazione, le regole VISTA, la conversione di valuta o altre logiche lato server applicate da Adobe. Per quanto possibile, Adobe consiglia di utilizzare la `post_` versione di una colonna.

Se una colonna non contiene una `post_` versione (ad esempio, `visit_num`), la colonna può essere considerata una colonna di post.

## In che modo i feed di dati gestiscono la sensibilità alle maiuscole/minuscole?

In Adobe Analytics, la maggior parte delle variabili viene considerata senza distinzione tra maiuscole e minuscole ai fini del reporting. Ad esempio, 'neve', 'neve', 'Snow' e 'sNow' sono tutti considerati allo stesso valore. La sensibilità delle maiuscole e delle minuscole viene mantenuta nei feed di dati.

Se si visualizzano diverse varianti di maiuscole e minuscole dello stesso valore tra colonne non post e post (ad esempio, 'neve' nella precolonna e 'neve' nella colonna post), l'implementazione utilizza sia valori maiuscoli che minuscoli nel sito. La variante case nella colonna post è stata precedentemente passata e memorizzata nel cookie virtuale, oppure è stata elaborata più o meno allo stesso tempo per quella suite di rapporti.