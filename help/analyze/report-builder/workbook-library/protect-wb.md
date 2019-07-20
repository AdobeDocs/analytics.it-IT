---
description: Potete proteggere tutte le richieste in una cartella di lavoro mediante l'aggiunta e la modifica di richieste bloccando la cartella di lavoro. Questo consente la modifica offline dei documenti di lavoro, in modo da mettere in pausa tutte le richieste di rapporti per una modifica più efficiente.
seo-description: Potete proteggere tutte le richieste in una cartella di lavoro mediante l'aggiunta e la modifica di richieste bloccando la cartella di lavoro. Questo consente la modifica offline dei documenti di lavoro, in modo da mettere in pausa tutte le richieste di rapporti per una modifica più efficiente.
seo-title: Bloccare/sbloccare le cartelle di lavoro
solution: Analytics
title: Bloccare/sbloccare le cartelle di lavoro
topic: Generatore di report
uuid: ef 5 c 276 c -5 f 74-4741-b 6 fa -4 c 79 eda 29 f 62
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Bloccare/sbloccare le cartelle di lavoro

Potete proteggere tutte le richieste in una cartella di lavoro mediante l'aggiunta e la modifica di richieste bloccando la cartella di lavoro. Questo consente la modifica offline dei documenti di lavoro, in modo da mettere in pausa tutte le richieste di rapporti per una modifica più efficiente.

In qualità di analista, il blocco di una cartella di lavoro consente di proteggere le richieste di cartelle di lavoro contro manomissioni da parte di altri utenti all'interno dell'organizzazione. Allo stesso tempo, tali utenti possono ancora aggiornare le richieste nella cartella di lavoro.

To protect a workbook against editing, click **[!UICONTROL Locked]** on the Report Builder toolbar ( ![](assets/locked_icon.png)

).

To unprotect a workbook, click **[!UICONTROL Unlocked]** ( ![](assets/unlocked_icon.png)

).

Potete sbloccare una cartella di lavoro bloccata se disponete di una delle seguenti autorizzazioni:

* Siete un amministratore oppure
* Siete la persona che ha inizialmente bloccato la cartella di lavoro. In questo caso, non dovete essere un amministratore.

>[!NOTE]
>
>Non potete aggiungere una richiesta a una cartella di lavoro protetta, a meno che non disponiate delle autorizzazioni necessarie per sbloccare la cartella di lavoro.

Quando una cartella di lavoro è bloccata rispetto alla modifica richiesta,

* Gli utenti non possono creare o aggiungere richieste.
* Gli utenti non possono modificare le richieste tramite la procedura guidata Richiesta.
* Gli utenti non possono modificare le richieste tramite le funzioni Modifica richiesta multiple.
* Gli utenti non possono tagliare, copiare o incollare richieste. Tuttavia, gli utenti possono comunque utilizzare il menu di scelta rapida Taglia/Copia/Incolla nativo per tagliare, copiare o incollare il contenuto delle richieste.
* Gli utenti possono aggiornare le richieste singolarmente o come parte di un gruppo.
* Se la richiesta utilizza valori di input dalle celle (intervallo date, segmento, filtri), gli utenti possono modificare tali valori nelle celle e quindi modificare indirettamente le richieste aggiornandole.

If you try to edit a protected workbook (through the context menu, or **[!UICONTROL Request Manager]**, or **[!UICONTROL Edit Multiple Requests]**), you may or may not be allowed to do so:

* Se non disponete delle autorizzazioni necessarie per sbloccare le richieste, viene visualizzato questo prompt:

   ![](assets/locked_workbook_error.png)

* Se disponete delle autorizzazioni necessarie, non viene visualizzato alcun prompt e potete modificare la richiesta.

## Flusso di lavoro {#section_260D05FF632B41DB97DB43E2ADBE2E75}

Supponiamo che la cartella di lavoro A abbia una richiesta che sia bloccata, creata dall'utente A.

**Esempio 1: Utente amministratore (o Utente A)**

1. L'utente accede al Generatore di report e apre la cartella di lavoro A.
1. La cartella di lavoro A è attualmente bloccata, quindi il pulsante «Crea richiesta» viene disattivato nella barra degli strumenti e tutti gli altri pulsanti la cui funzionalità è disabilitata bloccando.
1. Se l'utente tenta di utilizzare uno dei pulsanti disattivati, viene visualizzato un messaggio che informa che la cartella di lavoro è bloccata.
1. L'utente può sbloccare la cartella di lavoro, per abilitare la funzionalità di modifica completa.
1. Dopo l'sblocco, la cartella di lavoro rimane sbloccata finché non viene nuovamente bloccata.

**Esempio 2: Utente non amministratore (utente B)**

1. L'utente accede al Generatore di report e apre la cartella di lavoro A.
1. L'utente non può aggiungere o modificare la richiesta.
1. L'utente non può sbloccare la cartella di lavoro.

