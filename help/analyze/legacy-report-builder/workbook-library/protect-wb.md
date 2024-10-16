---
description: Scopri come proteggere tutte le richieste in una cartella di lavoro dall’aggiunta e dalla modifica di richieste bloccando la cartella di lavoro.
title: Come bloccare e sbloccare le cartelle di lavoro
uuid: ef5c276c-5f74-4741-b6fa-4c79eda29f62
feature: Report Builder
role: User, Admin
exl-id: b5a83532-9fa7-4f1f-b744-e5d74781fffb
source-git-commit: bb908f8dd21f7f11d93eb2e3cc843f107b99950d
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 0%

---

# Bloccare e sbloccare le cartelle di lavoro

È possibile proteggere tutte le richieste di una cartella di lavoro dall&#39;aggiunta e dalla modifica di richieste bloccando la cartella di lavoro. In questo modo è possibile modificare le cartelle di lavoro in modalità offline sospendendo tutte le richieste di report per una modifica più efficiente.

In qualità di analista, il blocco di una cartella di lavoro consente di proteggere le richieste della cartella di lavoro da manomissioni da parte di altri utenti dell&#39;organizzazione. Allo stesso tempo, tali utenti possono comunque aggiornare le richieste nella cartella di lavoro.

Per impedire la modifica di una cartella di lavoro, fare clic su **[!UICONTROL Locked]** sulla barra degli strumenti del Report Builder ( ![](assets/locked_icon.png)).

Per rimuovere la protezione di una cartella di lavoro, fare clic su **[!UICONTROL Unlocked]** ( ![](assets/unlocked_icon.png)).

È possibile sbloccare una cartella di lavoro bloccata se si dispone di una delle seguenti autorizzazioni:

* Sei un amministratore, oppure
* L&#39;utente corrente ha inizialmente bloccato la cartella di lavoro. In questo caso, non è necessario essere un amministratore.

>[!NOTE]
>
>Non è possibile aggiungere una richiesta a una cartella di lavoro protetta se non si dispone delle autorizzazioni necessarie per sbloccare la cartella di lavoro.

Quando una cartella di lavoro è bloccata per impedire la modifica delle richieste,

* Gli utenti non possono creare e aggiungere richieste.
* Gli utenti non possono modificare le richieste tramite la Creazione guidata richieste.
* Gli utenti non possono modificare le richieste tramite le funzioni Modifica più richieste.
* Gli utenti non possono tagliare, copiare o incollare richieste. Tuttavia, gli utenti possono ancora utilizzare il menu di scelta rapida nativo di Excel Taglia/Copia/Incolla per tagliare/copiare/incollare il contenuto delle richieste.
* Gli utenti possono aggiornare le richieste, singolarmente o come parte di un gruppo.
* Se la richiesta utilizza valori di input dalle celle (intervallo di date, segmento, filtri), gli utenti possono modificare tali valori nelle celle e quindi modificare indirettamente le richieste aggiornandole.

Se si tenta di modificare una cartella di lavoro protetta tramite il menu di scelta rapida, oppure **[!UICONTROL Request Manager]** o **[!UICONTROL Edit Multiple Requests]**, è possibile che non sia consentito:

* Se non si dispone delle autorizzazioni per sbloccare una richiesta, verrà visualizzato un messaggio che indica che non si dispone dei diritti per sbloccare e modificare la cartella di lavoro.

  ![Schermata che mostra il messaggio di errore quando non disponi delle autorizzazioni necessarie per sbloccare una richiesta.](assets/locked_workbook_error.png)

## Flusso di lavoro {#section_260D05FF632B41DB97DB43E2ADBE2E75}

Supponiamo che la cartella di lavoro A abbia una richiesta che si trova in uno stato bloccato ed è stata creata dall&#39;utente A.

**Esempio 1: utente amministratore (o utente A)**

1. L’utente accede al Report Builder e apre la cartella di lavoro A.
1. La cartella di lavoro A è attualmente bloccata, pertanto il pulsante &quot;Crea richiesta&quot; viene disattivato nella barra degli strumenti, insieme a tutti gli altri pulsanti la cui funzionalità è disabilitata dal blocco.
1. Se l&#39;utente tenta di utilizzare uno dei pulsanti disattivati, viene visualizzato un messaggio che indica che la cartella di lavoro è attualmente bloccata.
1. L&#39;utente può sbloccare la cartella di lavoro, che consente la funzionalità di modifica completa.
1. Dopo lo sblocco, la cartella di lavoro rimane sbloccata fino a quando non viene esplicitamente nuovamente bloccata.

**Esempio 2: utente non amministratore (utente B)**

1. L’utente accede al Report Builder e apre la cartella di lavoro A.
1. L’utente non può aggiungere/modificare la richiesta.
1. Impossibile sbloccare la cartella di lavoro.
