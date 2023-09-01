---
description: Scopri le domande frequenti sui Report Builder.
title: Domande frequenti sul Report Builder
feature: Report Builder
role: User, Admin
exl-id: 86604d39-2965-45a5-98ab-3ee4adcb7f97
source-git-commit: 66b7de0b008364e47253d319785c204ca479ab26
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 0%

---

# Domande frequenti su Report Builder

Domande frequenti in Report Builder.

## Posso utilizzare il `TODAY()` o `DATERANGE()` funzione nelle cartelle di lavoro?

Il [`TODAY()` funzione](https://support.microsoft.com/en-us/office/today-function-5eb3078d-a82c-4736-8930-2f51a028fdd9) in Excel restituisce il giorno corrente. Il [`DATEVALUE()` funzione](https://support.microsoft.com/en-us/office/datevalue-function-df8b07d4-7761-4a93-bc33-b7471bbff252) converte una stringa di data in un valore seriale. Sebbene sia utile per molte funzioni in Excel, Adobe consiglia vivamente di non utilizzare queste funzioni come parte delle richieste pianificate dal Report Builder. Adobe L’Assistenza clienti non supporta la risoluzione dei problemi relativi alle richieste che utilizzano una di queste funzioni.

I rapporti pianificati vengono elaborati su server che probabilmente non condividono i fusi orari come suite di rapporti. Il `TODAY()` un utente si aspetta e `TODAY()` gli utilizzi del server di elaborazione possono spesso essere diversi. Inoltre, la data utilizzata si basa sull’inizio dell’elaborazione. Se vengono eseguiti più rapporti contemporaneamente, la data può variare tra l’ora in cui viene richiesta e il momento in cui inizia l’elaborazione a causa di ritardi. Questo problema è presente se l’orario pianificato è vicino a mezzanotte.

I rapporti pianificati vengono elaborati anche su server che probabilmente non condividono la sintassi della data. Ad esempio: `7/1/YYYY` può fare riferimento a 1 luglio o 7 gennaio a seconda del paese o della regione. Utilizzo di `DATEVALUE()` funzione in questa data provocherebbe valori seriali diversi a seconda del computer che lo esegue.

In alternativa all’utilizzo di queste funzioni di Excel, Adobe consiglia vivamente di utilizzare intervalli di date all’interno di richieste di Report Builder. Nella prima pagina della Creazione guidata richieste, seleziona **[!UICONTROL Preset Dates]** nell’elenco a discesa, quindi in Date di uso comune, seleziona **[!UICONTROL Today]** o un altro intervallo di date desiderato. Questa impostazione richiede il tempo della suite di rapporti al momento dell’esecuzione e non il tempo di elaborazione della richiesta da parte del server.

## Quanto è grande e complessa la creazione delle cartelle di lavoro?

Il Report Builder supporta le cartelle di lavoro fino ai seguenti limiti:

* **1000 richieste**: una singola cartella di lavoro può contenere fino a 1000 richieste di dati. In presenza di rapporti o progetti che richiedono più di 1000 richieste, l’Adobe consiglia di separarli in più cartelle di lavoro.
* **20.000 richieste all&#39;ora per azienda**: il Report Builder utilizza l’API di reporting di Analytics per recuperare i dati. Ogni singola richiesta utilizza una chiamata API ogni volta che viene creata o aggiornata. Se l’organizzazione accumula più di 20.000 chiamate API in una determinata ora, devi aspettare l’ora successiva per recuperare nuovamente i dati.
* **Tempo di elaborazione di 4 ore**: i rapporti pianificati scadono dopo l’elaborazione per più di 4 ore. Se la cartella di lavoro contiene molte richieste complesse che utilizzano set di dati di grandi dimensioni, il rapporto pianificato potrebbe non riuscire.
