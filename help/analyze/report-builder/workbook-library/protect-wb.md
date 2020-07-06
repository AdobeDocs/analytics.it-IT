---
description: È possibile proteggere tutte le richieste presenti in una cartella di lavoro dall'aggiunta e dalla modifica delle richieste bloccando la cartella di lavoro. Questo consente la modifica offline delle cartelle di lavoro mettendo in pausa tutte le richieste di rapporti per una modifica più efficiente.
title: Bloccare/sbloccare le cartelle di lavoro
topic: Report builder
uuid: ef5c276c-5f74-4741-b6fa-4c79eda29f62
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 1%

---


# Bloccare/sbloccare le cartelle di lavoro

È possibile proteggere tutte le richieste presenti in una cartella di lavoro dall&#39;aggiunta e dalla modifica delle richieste bloccando la cartella di lavoro. Questo consente la modifica offline delle cartelle di lavoro mettendo in pausa tutte le richieste di rapporti per una modifica più efficiente.

In qualità di analista, il blocco di una cartella di lavoro consente di proteggere le richieste della cartella di lavoro da manomissioni da parte di altri utenti all&#39;interno dell&#39;organizzazione. Allo stesso tempo, tali utenti possono comunque aggiornare le richieste nella cartella di lavoro.

Per proteggere una cartella di lavoro dalla modifica, fare clic **[!UICONTROL Locked]** sulla barra degli strumenti Generatore di report ( ![](assets/locked_icon.png)

).

Per rimuovere la protezione di una cartella di lavoro, fare clic su **[!UICONTROL Unlocked]** ( ![](assets/unlocked_icon.png)

).

È possibile sbloccare una cartella di lavoro bloccata se si dispone di una delle seguenti autorizzazioni:

* Siete un amministratore oppure
* È la persona che ha inizialmente bloccato la cartella di lavoro. In questo caso, non è necessario essere un amministratore.

>[!NOTE]
>
>Non è possibile aggiungere una richiesta a una cartella di lavoro protetta a meno che non si disponga delle autorizzazioni necessarie per sbloccare la cartella di lavoro.

Quando una cartella di lavoro viene bloccata contro la modifica della richiesta,

* Gli utenti non possono creare/aggiungere richieste.
* Gli utenti non possono modificare le richieste tramite la Richiesta guidata.
* Gli utenti non possono modificare le richieste mediante le funzioni Modifica richiesta multipla.
* Gli utenti non possono tagliare, copiare o incollare le richieste. Tuttavia, gli utenti possono comunque utilizzare il menu di scelta rapida nativo di Excel Taglia, Copia, Incolla per tagliare, copiare e incollare il contenuto delle richieste.
* Gli utenti possono aggiornare le richieste, singolarmente o come parte di un gruppo.
* Se la richiesta utilizza i valori di input delle celle (intervallo di date, segmento, filtri), gli utenti possono modificare questi valori nelle celle, quindi modificare indirettamente le richieste aggiornandole.

Se si tenta di modificare una cartella di lavoro protetta (tramite il menu di scelta rapida, **[!UICONTROL Request Manager]** o **[!UICONTROL Edit Multiple Requests]**), è possibile che non sia possibile eseguire questa operazione:

* Se non disponete delle autorizzazioni necessarie per sbloccare le richieste, viene visualizzato il seguente messaggio:

   ![](assets/locked_workbook_error.png)

* Se disponete delle autorizzazioni necessarie, non viene visualizzato alcun prompt e potete modificare la richiesta.

## Flusso di lavoro {#section_260D05FF632B41DB97DB43E2ADBE2E75}

Supponiamo che la cartella di lavoro A contenga una richiesta che si trova nello stato bloccato ed è stata creata dall&#39;utente A.

**Esempio 1: Utente amministratore (o utente A)**

1. L&#39;utente accede al Generatore di report e apre la cartella di lavoro A.
1. La cartella di lavoro A è attualmente bloccata, pertanto il pulsante &quot;Crea richiesta&quot; è disattivato nella barra degli strumenti, insieme a tutti gli altri pulsanti la cui funzionalità è disabilitata tramite blocco.
1. Se l&#39;utente tenta di utilizzare uno dei pulsanti disattivati, viene visualizzato un messaggio che informa che la cartella di lavoro è attualmente bloccata.
1. L&#39;utente può sbloccare la cartella di lavoro, per abilitare la funzionalità di modifica completa.
1. Dopo lo sblocco, la cartella di lavoro rimane sbloccata finché non viene nuovamente bloccata in modo esplicito.

**Esempio 2: Utente non amministratore (utente B)**

1. L&#39;utente accede al Generatore di report e apre la cartella di lavoro A.
1. L&#39;utente non può aggiungere o modificare la richiesta.
1. Impossibile sbloccare la cartella di lavoro.

