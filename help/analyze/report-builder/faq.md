---
title: Domande frequenti su Report Builder
description: Domande frequenti per Report Builder.
feature: Report Builder
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 1%

---


# Domande frequenti su Report Builder

Domande frequenti intorno al Report Builder.

## È possibile utilizzare la funzione `TODAY()` o `DATERANGE()` nelle cartelle di lavoro?

La funzione [`TODAY()`](https://support.microsoft.com/en-us/office/today-function-5eb3078d-a82c-4736-8930-2f51a028fdd9) in Excel restituisce il giorno corrente. La funzione [`DATEVALUE()`](https://support.microsoft.com/en-us/office/datevalue-function-df8b07d4-7761-4a93-bc33-b7471bbff252) converte una stringa di data in un valore seriale. Anche se utile per molte funzionalità in Excel, Adobe consiglia vivamente di non utilizzare queste funzioni come parte delle richieste pianificate del Report Builder. L’Assistenza clienti di Adobe non supporta le richieste di risoluzione dei problemi che utilizzano una di queste funzioni.

I report pianificati vengono elaborati su server che probabilmente non condividono fusi orari come suite di rapporti. Le `TODAY()` che un utente si aspetta e le `TODAY()` utilizzate dal server di elaborazione possono spesso essere diverse. Inoltre, la data utilizzata si basa sull&#39;inizio dell&#39;elaborazione. Se vengono eseguiti più rapporti contemporaneamente, la data può variare tra l’ora in cui è richiesta e il momento in cui inizia l’elaborazione a causa di ritardi. Questo problema è presente se l&#39;orario pianificato è vicino a mezzanotte.

I report pianificati vengono elaborati anche su server che probabilmente non condividono la sintassi della data. Ad esempio, `7/1/YYYY` può fare riferimento al 1° luglio o al 7 gennaio, a seconda del paese o dell’area geografica. L&#39;utilizzo della funzione `DATEVALUE()` in questa data comporterebbe valori seriali diversi a seconda del computer che lo esegue.

In alternativa all’utilizzo di queste funzioni Excel, Adobe consiglia vivamente di utilizzare intervalli di date all’interno delle richieste di Report Builder. Nella prima pagina della procedura guidata di richiesta, seleziona **[!UICONTROL Preset Dates]** nel menu a discesa, quindi in Date comunemente utilizzate, seleziona **[!UICONTROL Today]** o un altro intervallo di date desiderato. Questa impostazione richiede l’ora della suite di rapporti al momento dell’esecuzione e non l’ora del server che elabora la richiesta.

## Quanto posso creare le mie cartelle di lavoro grandi e complesse?

Report Builder supporta le cartelle di lavoro fino ai seguenti limiti:

* **1000 richieste**: Una cartella di lavoro può contenere fino a 1000 richieste di dati in una singola cartella di lavoro. Se si dispone di rapporti o progetti che richiedono più di 1000 richieste, Adobe consiglia di separarle in più cartelle di lavoro.
* **20.000 richieste all&#39;ora per azienda**: Il Report Builder utilizza l’API di reporting di Analytics per recuperare i dati. Ogni singola richiesta utilizza una chiamata API ogni volta che viene creata o aggiornata. Se nell’organizzazione vengono accumulate più di 20.000 chiamate API in un’ora specifica, è necessario attendere fino all’ora successiva per recuperare nuovamente i dati.
* **Tempo** di elaborazione 4 ore: Timeout dei report pianificati dopo l&#39;elaborazione delle ultime 4 ore. Se la cartella di lavoro contiene molte richieste complesse che utilizzano set di dati di grandi dimensioni, il rapporto pianificato potrebbe non riuscire.
