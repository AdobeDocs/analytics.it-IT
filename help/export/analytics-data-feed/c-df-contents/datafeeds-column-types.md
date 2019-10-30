---
description: La pre colonna contiene i dati durante l'invio alla raccolta dati. La colonna post contiene il valore dopo l'elaborazione.
keywords: Feed dati;processo;pre-colonna;post-colonna;case Sensibilità
seo-description: La pre colonna contiene i dati durante l'invio alla raccolta dati. La colonna post contiene il valore dopo l'elaborazione.
seo-title: Colonne pre e post
solution: Analytics
title: Colonne pre e post
topic: Reports and Analytics
uuid: a415327b-6151-4d08-b8b9-5aaa2348eb0c
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Colonne pre e post

La pre colonna contiene i dati durante l'invio alla raccolta dati. La colonna post contiene il valore dopo l'elaborazione.

Ad esempio, persistenza variabile, regole di elaborazione, regole VISTA e conversione della valuta potrebbero modificare il valore finale registrato per una variabile che viene visualizzata nella colonna di post. Per la maggior parte dei calcoli si desidera utilizzare la colonna di post a meno che non si stia applicando una logica aziendale personalizzata (ad esempio, l'applicazione di una formula personalizzata per determinare l'attribuzione).

Se una colonna non contiene una versione pre o post (ad esempio `visit_num`), la colonna può essere considerata una colonna post. Le colonne con prefisso " `pre_`" contengono in genere dati compilati da Adobe e non inviati dall’implementazione. Ad esempio, `pre_browser` è popolato da Adobe, ma `evar1` viene compilato dall’implementazione. Entrambe queste colonne hanno una colonna " `post_`" ( `post_browser`, `post_evar1`), che contiene il valore utilizzato dai report.

## Sensibilità maiuscole/minuscole nei valori {#section_F979E099BFAB4AFEBEA2D7E228963CE8}

La maggior parte delle variabili di Analytics sono considerate senza distinzione tra maiuscole e minuscole a scopo di reporting, il che significa che le diverse variazioni di maiuscole e minuscole sono considerate allo stesso valore ("neve", "neve", "Snow", "SNOW" e "sNow" sono tutte considerate uguali). Tuttavia, a scopo di visualizzazione, la distinzione tra maiuscole e minuscole viene mantenuta, poiché la maggior parte dei clienti preferisce poter inviare caratteri maiuscoli e minuscoli da visualizzare nei rapporti.

Durante l'elaborazione del feed di dati, è possibile utilizzare valori minuscoli a scopo di confronto, anche se è probabile che si desideri mantenere il caso a scopo di visualizzazione.

Se si visualizzano diverse variazioni di maiuscole e minuscole dello stesso valore tra le colonne pre e post (ad esempio, "neve" nella precolonna e "Neve" nella colonna post), significa che si passano sia le versioni in maiuscolo che quelle in minuscolo dello stesso valore sul sito. La variante case nella colonna post è stata precedentemente passata e memorizzata nel cookie virtuale, oppure è stata elaborata più o meno allo stesso tempo per quella suite di rapporti. Ad esempio:

Hit 1: s.list1="Tabby,Persiano,Siamese";

Hit 2: s.list1="tabby,persian,siamese";

Quando l'hit 2 è segnalato nel feed di dati, la pre colonna conterrà l'esatto involucro passato (tabby,persian,siamese), ma il valore dell'hit 1 è probabilmente persistente per quella visita e sarà riportato nella colonna di post (che sarà Tabby,Persian,Siamese), dal momento che l'hit 1 e 2 contengono esattamente lo stesso valore quando viene eseguito un confronto senza distinzione tra maiuscole e minuscole.
