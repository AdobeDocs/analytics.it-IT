---
description: È possibile proteggere tutte le richieste di una cartella di lavoro dall'aggiunta e dalla modifica di richieste bloccando la cartella di lavoro. Questo consente la modifica offline delle cartelle di lavoro mettendo in pausa tutte le richieste di report per una modifica più efficiente.
title: Bloccare/sbloccare le cartelle di lavoro
uuid: ef5c276c-5f74-4741-b6fa-4c79eda29f62
feature: Report Builder
role: User, Admin
exl-id: b5a83532-9fa7-4f1f-b744-e5d74781fffb
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 1%

---

# Bloccare/sbloccare le cartelle di lavoro

È possibile proteggere tutte le richieste di una cartella di lavoro dall&#39;aggiunta e dalla modifica di richieste bloccando la cartella di lavoro. Questo consente la modifica offline delle cartelle di lavoro mettendo in pausa tutte le richieste di report per una modifica più efficiente.

In qualità di analista, il blocco di una cartella di lavoro consente di proteggere le richieste della cartella di lavoro da manomissioni da parte di altri utenti all’interno dell’organizzazione. Allo stesso tempo, questi utenti possono comunque aggiornare le richieste nella cartella di lavoro.

Per proteggere una cartella di lavoro dalla modifica, fare clic su **[!UICONTROL Locked]** sulla barra degli strumenti del Report Builder ( ![](assets/locked_icon.png)

).

Per rimuovere la protezione da una cartella di lavoro, fare clic su **[!UICONTROL Unlocked]** ( ![](assets/unlocked_icon.png)

).

È possibile sbloccare una cartella di lavoro bloccata se si dispone di una delle seguenti autorizzazioni:

* Sei un amministratore o
* Sei la persona che ha inizialmente bloccato la cartella di lavoro. In questo caso, non devi essere un amministratore.

>[!NOTE]
>
>Non è possibile aggiungere una richiesta a una cartella di lavoro protetta a meno che non si disponga delle autorizzazioni necessarie per sbloccare la cartella di lavoro.

Quando una cartella di lavoro viene bloccata contro la modifica della richiesta,

* Gli utenti non possono creare/aggiungere richieste.
* Gli utenti non possono modificare le richieste tramite la Creazione guidata richieste.
* Gli utenti non possono modificare le richieste tramite le funzioni Modifica più richieste .
* Gli utenti non possono tagliare, copiare o incollare le richieste. Tuttavia, gli utenti possono comunque utilizzare il menu di scelta rapida nativo di Excel Taglia, Copia, Incolla per tagliare, copiare e incollare il contenuto delle richieste.
* Gli utenti possono aggiornare le richieste singolarmente o come parte di un gruppo.
* Se la richiesta utilizza i valori di input delle celle (intervallo di date, segmento, filtri), gli utenti possono modificare questi valori nelle celle e quindi modificare indirettamente le richieste aggiornandole.

Se si tenta di modificare una cartella di lavoro protetta (tramite il menu di scelta rapida o **[!UICONTROL Request Manager]** o **[!UICONTROL Edit Multiple Requests]**), è possibile o non è consentito eseguire questa operazione:

* Se non disponi delle autorizzazioni per sbloccare le richieste, viene visualizzato questo prompt:

   ![](assets/locked_workbook_error.png)

* Se disponi delle autorizzazioni necessarie, non viene visualizzato alcun prompt e puoi modificare la richiesta.

## Flusso di lavoro {#section_260D05FF632B41DB97DB43E2ADBE2E75}

Supponiamo che la cartella di lavoro A abbia una richiesta che si trova in uno stato bloccato ed è stata creata dall&#39;utente A.

**Esempio 1: Utente amministratore (o utente A)**

1. L&#39;utente accede al Report Builder e apre la cartella di lavoro A.
1. La cartella di lavoro A è attualmente bloccata, pertanto il pulsante &quot;Crea richiesta&quot; è disattivato nella barra degli strumenti, insieme a tutti gli altri pulsanti la cui funzionalità è disabilitata bloccando.
1. Se l&#39;utente tenta di utilizzare uno dei pulsanti disattivati, viene visualizzato un messaggio che informa che la cartella di lavoro è attualmente bloccata.
1. L&#39;utente può sbloccare la cartella di lavoro, consentendo così la piena funzionalità di modifica.
1. Dopo lo sblocco, la cartella di lavoro rimane sbloccata fino a quando non viene esplicitamente risbloccato.

**Esempio 2: Utente non amministratore (utente B)**

1. L&#39;utente accede al Report Builder e apre la cartella di lavoro A.
1. L&#39;utente non può aggiungere/modificare la richiesta.
1. L&#39;utente non può sbloccare la cartella di lavoro.
