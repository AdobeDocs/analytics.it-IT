---
title: Domande frequenti sugli Report Builder
description: Domande frequenti per Report Builder.
translation-type: tm+mt
source-git-commit: 47b14bde1bb1217bcb172c6d4f01d68f917d44db
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 0%

---


# Domande frequenti sugli Report Builder

Domande frequenti in tutto il Report Builder.

## È possibile utilizzare la `TODAY()` funzione o `DATERANGE()` nei libri di lavoro?

La [`TODAY()` funzione](https://support.microsoft.com/en-us/office/today-function-5eb3078d-a82c-4736-8930-2f51a028fdd9) in Excel restituisce il giorno corrente. La [`DATEVALUE()` funzione](https://support.microsoft.com/en-us/office/datevalue-function-df8b07d4-7761-4a93-bc33-b7471bbff252) converte una stringa data in un valore seriale. Anche se utile per molte funzioni all&#39;interno di Excel,  Adobe consiglia vivamente di non utilizzare queste funzioni come parte delle richieste pianificate del Report Builder. &#39;Assistenza clienti di Adobe non supporta le richieste di risoluzione dei problemi che utilizzano una di queste funzioni.

I report pianificati vengono elaborati su server che probabilmente non condividono fusi orari come suite di rapporti. L&#39;utente `TODAY()` si aspetta e `TODAY()` il server di elaborazione spesso può essere diverso. Inoltre, la data utilizzata si basa sull&#39;inizio dell&#39;elaborazione. Se molti rapporti vengono eseguiti contemporaneamente, la data può variare tra l’ora in cui viene richiesto e la data in cui inizia l’elaborazione a causa di ritardi. Questo problema è presente se l&#39;ora pianificata è vicina a mezzanotte.

I report pianificati vengono elaborati anche su server che probabilmente non condividono la sintassi della data. Ad esempio, `7/1/YYYY` può fare riferimento al 1° luglio o al 7 gennaio, a seconda del paese o della regione in cui si trova. L&#39;utilizzo della `DATEVALUE()` funzione in questa data comporterebbe valori seriali diversi a seconda del computer che la esegue.

Come alternativa all&#39;utilizzo di queste funzioni Excel,  Adobe consiglia vivamente di utilizzare intervalli di date all&#39;interno delle richieste del Report Builder. Nella prima pagina della procedura guidata di richiesta, selezionate **[!UICONTROL Preset Dates]** nel menu a discesa, quindi in Date utilizzate comunemente, selezionate **[!UICONTROL Today]** o un altro intervallo di date desiderato. Questa impostazione richiede il tempo della suite di rapporti al momento dell&#39;esecuzione e non il momento in cui il server elabora la richiesta.

## Quanto sono grandi e complesse le mie cartelle di lavoro?

Il Report Builder supporta le cartelle di lavoro fino ai seguenti limiti:

* **1000 richieste**: Una cartella di lavoro può contenere fino a 1000 richieste di dati in una singola cartella di lavoro. Se disponete di rapporti o progetti che richiedono più di 1000 richieste,  Adobe consiglia di separarle in più cartelle di lavoro.
* **20.000 richieste all&#39;ora per azienda**: Il Report Builder utilizza l&#39;API di reporting di Analytics per recuperare i dati. Ogni singola richiesta utilizza una chiamata API ogni volta che viene creata o aggiornata. Se l&#39;organizzazione accumula più di 20.000 chiamate API in un&#39;ora specificata, devi aspettare fino all&#39;ora successiva per recuperare nuovamente i dati.
* **Tempo** di elaborazione di 4 ore: Timeout dei report pianificati dopo l&#39;elaborazione delle ultime 4 ore. Se la cartella di lavoro contiene molte richieste complesse che utilizzano set di dati di grandi dimensioni, il rapporto pianificato potrebbe non riuscire.
