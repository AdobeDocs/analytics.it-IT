---
description: Scopri le domande frequenti su Report Builder.
title: Domande frequenti su Report Builder
feature: Report Builder
role: User, Admin
exl-id: 86604d39-2965-45a5-98ab-3ee4adcb7f97
source-git-commit: 83f199a3bb76147b98aba014b62ea3c02c766ddd
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 100%

---

# Domande frequenti su Report Builder

Domande frequenti su Report Builder.

## Posso utilizzare la funzione `TODAY()` o `DATERANGE()` nelle cartelle di lavoro? {#today}

La funzione [`TODAY()`](https://support.microsoft.com/it-it/office/today-function-5eb3078d-a82c-4736-8930-2f51a028fdd9) in Excel restituisce il giorno corrente. La funzione [`DATEVALUE()`](https://support.microsoft.com/it-it/office/datevalue-function-df8b07d4-7761-4a93-bc33-b7471bbff252) converte una stringa di data in un valore seriale. Sebbene siano utile per molte funzioni in Excel, Adobe consiglia vivamente di non utilizzare queste funzioni come parte delle richieste pianificate dal Report Builder. L’Assistenza clienti di Adobe non supporta la risoluzione dei problemi relativi alle richieste che utilizzano una di queste funzioni.

I rapporti pianificati vengono elaborati su server che probabilmente non condividono i fusi orari come la suite di rapporti. La data `TODAY()` che un utente si aspetta e quella `TODAY()` che il server di elaborazione utilizza possono spesso essere diversi. Inoltre, la data utilizzata si basa sull’inizio dell’elaborazione. Se vengono eseguiti più rapporti contemporaneamente, la data può variare tra l’ora in cui viene richiesta e il momento in cui inizia l’elaborazione a causa di ritardi. Questo problema è presente se l’orario pianificato è vicino a mezzanotte.

I rapporti pianificati vengono elaborati anche su server che probabilmente non condividono la sintassi della data. Ad esempio: `7/1/YYYY` può fare riferimento al 1° luglio o al 7 gennaio a seconda del paese o dell’area geografica. L’utilizzo della funzione `DATEVALUE()` in questa data comporterebbe valori seriali diversi a seconda del computer che la esegue.

In alternativa all’utilizzo di queste funzioni di Excel, Adobe consiglia vivamente di utilizzare intervalli di date all’interno delle richieste di Report Builder. Nella prima pagina della procedura guidata delle richieste, seleziona **[!UICONTROL Preset Dates]** nell’elenco a discesa, quindi in Date di uso comune, seleziona **[!UICONTROL Today]** o un altro intervallo di date desiderato. Questa impostazione tiene conto dell’orario della suite di rapporti al momento dell’esecuzione e non quello di elaborazione della richiesta da parte del server.

## Quanto grandi e complesse possono essere le cartelle di lavoro che creo? {#complexity}

Report Builder supporta le cartelle di lavoro entro i seguenti limiti:

* **1000 richieste**: una singola cartella di lavoro può contenere fino a 1000 richieste di dati. In presenza di rapporti o progetti che richiedono più di 1000 richieste, Adobe consiglia di separarli in più cartelle di lavoro.
* **20.000 richieste all’ora per azienda**: Report Builder utilizza l’API di reporting di Analytics per recuperare i dati. Ogni singola richiesta utilizza una chiamata API ogni volta che viene creata o aggiornata. Se l’organizzazione accumula più di 20.000 chiamate API in una determinata ora, devi aspettare l’ora successiva per recuperare nuovamente i dati.
* **Tempo di elaborazione di 4 ore**: i rapporti pianificati scadono dopo l’elaborazione per più di 4 ore. Se la cartella di lavoro contiene molte richieste complesse che utilizzano set di dati di grandi dimensioni, il rapporto pianificato potrebbe non riuscire.

## Come è possibile sapere se ho accesso a Report Builder? {#access}

L’accesso deve essere concesso dall’amministratore di Adobe Analytics. L’amministratore configura i profili di prodotto in [Adobe Admin Console](https://experienceleague.adobe.com/it/docs/analytics/admin/admin-console/home). Chiedi al tuo amministratore di concederti l’accesso.
