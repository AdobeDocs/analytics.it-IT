---
description: La colonna pre contiene i dati così come è stato inviato alla raccolta dati. La colonna post contiene il valore dopo l'elaborazione.
keywords: Feed dati; processo; pre column; post, colonna; distinzione tra maiuscole e minuscole
seo-description: La colonna pre contiene i dati così come è stato inviato alla raccolta dati. La colonna post contiene il valore dopo l'elaborazione.
seo-title: Colonne pre e post
solution: Analytics
title: Colonne pre e post
topic: Reports & Analytics
uuid: a 415327 b -6151-4 d 08-b 8 b 9-5 aaa 2348 eb 0 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Colonne pre e post

La colonna pre contiene i dati così come è stato inviato alla raccolta dati. La colonna post contiene il valore dopo l'elaborazione.

Ad esempio, persistence persistence, processing rules, VISTA rules, and currency conversion may change the final value recorded for a variable that appears in the post column. Per la maggior parte dei calcoli si desidera utilizzare la colonna del post, a meno che non si stia applicando logica di business personalizzata (ad esempio, applicazione di una formula personalizzata per determinare l'attribuzione).

If a column does not contain a pre or a post version (for example, `visit_num`), then the column can be considered a post column. Columns prefixed with " `pre_`" typically contain data that was populated by Adobe and not sent by your implementation. For example, `pre_browser` is populated by Adobe, but `evar1` is populated by your implementation. Both of these columns have a " `post_`" column ( `post_browser`, `post_evar1`), which contains the value used by reporting.

## Case Sensitivity in Values {#section_F979E099BFAB4AFEBEA2D7E228963CE8}

La maggior parte delle variabili di Analytics sono considerate insensibili a maiuscole/minuscole a scopo di reporting, ovvero varianti di maiuscole/minuscole diverse sono considerate uguali ("neve", "Neve", "NEVE" e "NEVE" vengono considerati tutti lo stesso valore). Tuttavia, a scopo di visualizzazione, la sensibilità alle maiuscole e minuscole viene conservata perché la maggior parte dei clienti preferisce essere in grado di inviare caratteri misti da visualizzare nei rapporti.

Quando si elabora il feed di dati, è possibile utilizzare valori minuscoli a scopo di confronto, anche se è probabile che si desideri conservare casi a scopo di visualizzazione.

Se notate varianti maiuscole/minuscole dello stesso valore tra le colonne pre e post (ad esempio "neve" nella colonna precedente e "Neve" nella colonna post), significa che state passando sia versioni maiuscole che minuscole dello stesso valore all'interno del sito. La variazione della maiuscola nella colonna del post è stata passata in precedenza e salvata nel cookie virtuale oppure elaborata contemporaneamente per quella suite di rapporti. Ad esempio:

Hit 1: s. list 1 = "Tabby, Persiano, Siamese";

Hit 2: s. list 1 = «tabby, persiano, siamese»;

Quando l'hit 2 è indicato nel feed di dati, la colonna anteriore conterrà la struttura esatta passata in (tabby, persiano, siamese), ma il valore dell'hit 1 è probabilmente persistente per quel visitatore e verrà riportato nella colonna post (che sarà Tabby, Persiano, Siamese) perché hit 1 e 2 contengono lo stesso valore quando è eseguito un confronto senza distinzione tra maiuscole e minuscole.
