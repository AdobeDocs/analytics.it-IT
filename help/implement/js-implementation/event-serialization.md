---
description: La serializzazione degli eventi è il processo di implementazione delle misure per evitare che gli eventi duplicati immettano i report di Analytics. Questo può verificarsi frequentemente quando l'utente aggiorna la pagina più volte, passa più volte a una determinata pagina o salva la pagina Web sul proprio computer (ad esempio, se un cliente salva una pagina di conferma acquisti sul proprio computer, ogni volta che la visualizza e le entrate vengono conteggiate di nuovo, se la serializzazione degli eventi non è già attiva).
keywords: Implementazione di Analytics
seo-description: La serializzazione degli eventi è il processo di implementazione delle misure per evitare che gli eventi duplicati immettano i report di Analytics. Questo può verificarsi frequentemente quando l'utente aggiorna la pagina più volte, passa più volte a una determinata pagina o salva la pagina Web sul proprio computer (ad esempio, se un cliente salva una pagina di conferma acquisti sul proprio computer, ogni volta che la visualizza e le entrate vengono conteggiate di nuovo, se la serializzazione degli eventi non è già attiva).
seo-title: Panoramica sulla serializzazione degli eventi
solution: Analytics
title: Panoramica sulla serializzazione degli eventi
topic: Sviluppatore e implementazione
uuid: 8 c 7883 bb -5 ba 4-4440-af 80-c 0 d 15867570 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Panoramica sulla serializzazione degli eventi

La serializzazione degli eventi è il processo di implementazione delle misure per evitare che gli eventi duplicati immettano i report di Analytics. Questo può verificarsi frequentemente quando l'utente aggiorna la pagina più volte, passa più volte a una determinata pagina o salva la pagina Web sul proprio computer (ad esempio, se un cliente salva una pagina di conferma acquisti sul proprio computer, ogni volta che la visualizza e le entrate vengono conteggiate di nuovo, se la serializzazione degli eventi non è già attiva).

[!UICONTROL Event serialization] è utile nelle seguenti istanze:

* Una pagina può essere ricaricata o aggiornata e invia ripetutamente un evento. [!UICONTROL Event serialization] impedisce che gli eventi vengano ripetuti utilizzando un numero di serie per ogni evento.
* L'utente salva la pagina sul proprio computer per la successiva revisione. Questo scenario è molto comune nelle pagine di conferma degli acquisti per rivedere le ricevute degli acquisti. [!UICONTROL Event serialization] impedisce che la pagina successiva ricarichi gli eventi.

>[!NOTE]
>
>Origini dati non supporta la serializzazione degli eventi o la deduplicazione.

This document describes the process used to implement [!UICONTROL Event serialization] for [!UICONTROL conversion] and [!UICONTROL custom] events. To use [!UICONTROL Event serialization], you must first enable it in  **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suite]** &gt; **[!UICONTROL[select report suite]]** &gt; **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Success Events]** . Then select which events you want recorded in the [!UICONTROL Unique Event Recording] column.

## Default Behavior {#section_892BB2BEFC434B69869D4504A8B54308}

Il comportamento predefinito consiste nel conteggiare ogni istanza di un evento. An event is set for each [!UICONTROL pageview]that is counted, even on page reloads or page refreshes. The [!UICONTROL s.purchaseID] variable is used in order to uniquely identify each order (purchase). Questo consente a un utente di ricaricare la pagina dell'ordine senza conteggiare l'ordine, le entrate o i prodotti. Una funzione simile è disponibile per tutti gli eventi. This includes pre-defined events such as [!UICONTROL prodView] and [!UICONTROL scCheckout], as well as all custom events.

<!-- 

event_serialization_impl.xml

 -->

To use [!UICONTROL Event serialization], you must first enable it in  **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suite]** &gt; **[!UICONTROL[select report suite]]** &gt; **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Success Events]** . Then select which events you want recorded in the [!UICONTROL Unique Event Recording] column. È possibile impostare un evento con tre impostazioni diverse.

**Always record event**: Questo è il comportamento predefinito di tutti gli eventi quando inizialmente è attivato. Tutti gli eventi inclusi nelle richieste di immagini verranno inviati direttamente ad Analytics, inclusa la pagina di ricarica.

**Registra una volta per visita**: Un evento con questa impostazione consente di tenere traccia della prima istanza dell'evento in una determinata visita. Una volta avviata la nuova visita, è possibile tracciare di nuovo ogni evento con questa impostazione attivata. Questo è un modo efficace per attenuare gli eventi duplicati mediante aggiornamento del browser.

**Usa ID evento**: Questa impostazione consente di associare ogni evento a un ID univoco. Se Analytics rileva un eventid già visualizzato prima con quella variabile, non verrà conteggiato nei report.

L'unico evento che non può avere la serializzazione eventi abilitata è l'evento di acquisto, in quanto utilizza la variabile s. purchaseid. Tutti gli altri eventi ecommerce e eventi personalizzati possono avere queste impostazioni abilitate.

* Usate un identificatore univoco per consentire l'attivazione di un evento per ID univoco.
* Inviare più eventi, quindi utilizzare Analytics per attivare l'attivazione di un evento per visita.

To implement [!UICONTROL Event serialization], provide a unique ID for the event, for example event1:1234ABCD.

## Event Serialization - Once per Unique ID {#section_8806E48B497546F5A335383FB8627694}

Once [!UICONTROL Event serialization] is implemented, and [!DNL Analytics] receives a duplicate number, it ignores the event. Un evento viene conteggiato solo una volta per ogni valore univoco. Se il numero è univoco, viene conteggiato un'altra istanza evento, come nell'esempio seguente:

| Nome utente | Descrizione | Sintassi evento | Analytics Total Event 1 Count |
|---|---|---|---|
| John | L'utente visualizza la pagina per la prima volta. | event 1:1000 | 1 |
| John | L'utente ricarica la pagina (un modulo potrebbe non riuscire e la pagina da ricaricare). | event 1:1000 | 1 |
| Stacy | L'utente visualizza la pagina per la prima volta. | event 1:1001 | 2 |
| Stacy | L'utente ricarica la pagina (un modulo potrebbe non riuscire e la pagina da ricaricare). | event 1:1001 | 2 |
| Jill | L'utente visualizza la pagina per la prima volta, le inserisce correttamente e passa alla pagina successiva. | event 1:1002 | 3 |
| Jamie | La pagina visualizzazioni utente per la prima volta | event1 | 4 |
| Jamie | L'utente dimentica di compilare il campo cognome sul modulo. Il modulo viene visualizzato di nuovo con le informazioni mancanti evidenziate. | event1 | 5 |

Quando selezionate ID di serializzazione, tenete presente quanto segue:

* Gli ID di serializzazione devono essere di almeno 20 caratteri.
* Gli ID di serializzazione devono essere caratteri alfanumerici.
* Gli ID di serializzazione sono separati per ogni evento di successo. Pertanto, potete utilizzare lo stesso ID per più eventi di successo, se necessario, ma non per lo stesso evento di successo.
* Gli ID di serializzazione sono legati alla suite di rapporti, quindi se utilizzate i tag multisuite per inviare dati a più suite di rapporti, tenetela presente.
* Gli ID di serializzazione non scadono, quindi anche se lo stesso ID viene utilizzato anni dopo, l'evento success non sarà più conteggiato.
* L'eliminazione dei cookie non impedisce la serializzazione degli ID evento perché gli ID di serializzazione sono memorizzati sui server Adobe e non sono basati su cookie.
* L'evento di successo con cui non è possibile utilizzare la serializzazione ID evento è l'evento Purchase, che utilizza una variabile s. purchaseid speciale per la serializzazione.

## Event Serialization - Once per Visit {#section_C919D44F321A47FBBF043D0C57A2A050}

[!DNL Analytics] offre una funzione che consente l'attivazione di un evento solo una volta per visita.

This can be enabled from the UI:  **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suite]** &gt; **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Conversion]** &gt; **[!UICONTROL Success Events]** .
