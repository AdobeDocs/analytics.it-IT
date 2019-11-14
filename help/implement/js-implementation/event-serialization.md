---
description: La serializzazione degli eventi è il processo di implementazione delle misure per impedire che gli eventi duplicati entrino nel reporting di Analytics. Ciò può verificarsi in genere quando un utente aggiorna la pagina più volte, accede a una determinata pagina più volte o salva la pagina Web nel proprio computer (ad esempio, se un cliente salva una pagina di conferma dell'acquisto nel proprio computer, ogni volta che visualizza gli ordini e le entrate vengono nuovamente conteggiate se la serializzazione dell'evento non è stata implementata).
keywords: Analytics Implementation
solution: Analytics
title: Panoramica sulla serializzazione degli eventi
topic: Developer and implementation
uuid: 8c7883bb-5ba4-4440-af80-c0d15867570c
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Panoramica sulla serializzazione degli eventi

La serializzazione degli eventi è il processo di implementazione delle misure per impedire che gli eventi duplicati entrino nel reporting di Analytics. Ciò può verificarsi in genere quando un utente aggiorna la pagina più volte, accede a una determinata pagina più volte o salva la pagina Web nel proprio computer (ad esempio, se un cliente salva una pagina di conferma dell'acquisto nel proprio computer, ogni volta che visualizza gli ordini e le entrate vengono nuovamente conteggiate se la serializzazione dell'evento non è stata implementata).

[!UICONTROL Event serialization] è utile nei seguenti casi:

* Una pagina può essere ricaricata o aggiornata e inviare ripetutamente un evento. [!UICONTROL Event serialization] impedisce il conteggio degli eventi utilizzando un numero di serie per ogni evento.
* L'utente salva la pagina nel computer per una revisione successiva. Questo scenario è abbastanza comune nelle pagine di conferma dell'acquisto per esaminare le ricevute di acquisto. [!UICONTROL Event serialization] impedisce che gli eventi vengano nuovamente conteggiati nella pagina successiva.

> [!NOTE] Origini dati non supporta la serializzazione o la deduplicazione degli eventi.

Questo documento descrive il processo utilizzato per implementare [!UICONTROL Event serialization] gli [!UICONTROL conversion] eventi e [!UICONTROL custom] gli eventi. Per utilizzare [!UICONTROL Event serialization], è innanzitutto necessario attivarlo in **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suite]** &gt; **[!UICONTROL[seleziona suite]di rapporti]** &gt; **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Success Events]** . Quindi selezionate gli eventi da registrare nella [!UICONTROL Unique Event Recording] colonna.

## Comportamento predefinito {#section_892BB2BEFC434B69869D4504A8B54308}

Il comportamento predefinito consiste nel contare ciascuna istanza di un evento. Un evento viene impostato per ogni [!UICONTROL pageview]oggetto conteggiato, anche sui ricarichi di pagina o sugli aggiornamenti di pagina. La [!UICONTROL s.purchaseID] variabile viene utilizzata per identificare in modo univoco ciascun ordine (acquisto). Questo consente a un utente di ricaricare la pagina dell'ordine senza contare nuovamente l'ordine, le entrate o i prodotti. Una funzione simile è disponibile per tutti gli eventi. Ciò include eventi predefiniti come [!UICONTROL prodView] e [!UICONTROL scCheckout], nonché tutti gli eventi personalizzati.

<!-- 

event_serialization_impl.xml

 -->

Per utilizzare [!UICONTROL Event serialization], è innanzitutto necessario attivarlo in **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suite]** &gt; **[!UICONTROL[seleziona suite]di rapporti]** &gt; **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Success Events]** . Quindi selezionate gli eventi da registrare nella [!UICONTROL Unique Event Recording] colonna. Un evento può essere impostato su tre diverse impostazioni.

**Registra sempre evento**: Questo è il comportamento predefinito di tutti gli eventi quando è attivato inizialmente. Tutti gli eventi inclusi nelle richieste di immagini verranno inviati direttamente ad Analytics, inclusi i ricarichi di pagina.

**Registra una volta per visita**: Un evento con questa impostazione abilitata terrà traccia solo della prima istanza dell’evento in una determinata visita. Una volta avviata una nuova visita, è possibile tracciare di nuovo ogni evento con questa impostazione abilitata. Questo è un modo efficace per attenuare i duplicati eventi tramite aggiornamenti del browser.

**Usa ID** evento: Questa impostazione consente di associare ogni evento a un ID univoco. Se Analytics visualizza un eventID già visto in precedenza con quella variabile, non verrà conteggiato nei report.

L’unico evento che non può avere la serializzazione dell’evento abilitata è l’evento acquisto, in quanto utilizza la variabile s.purchaseID. Tutti gli altri eventi eCommerce e gli eventi personalizzati possono avere queste impostazioni abilitate.

* Usate un identificatore univoco per consentire a un evento di essere attivato una volta per ciascun ID univoco.
* Inviate più eventi, quindi utilizzate Configura Analytics per attivare un evento una volta per visita.

Per implementare [!UICONTROL Event serialization], fornite un ID univoco per l’evento, ad esempio event1:1234ABCD.

## Serializzazione degli eventi - Una volta per ID univoco {#section_8806E48B497546F5A335383FB8627694}

Una volta [!UICONTROL Event serialization] implementato e [!DNL Analytics] ricevuto un numero duplicato, l'evento viene ignorato. Un evento viene conteggiato una sola volta per ogni valore univoco. Se il numero è univoco, viene conteggiata un'altra istanza di evento, come illustrato nell'esempio seguente:

| Nome utente | Descrizione | Sintassi evento | Conteggio eventi totali di Analytics1 |
|---|---|---|---|
| John | Visualizzazione della pagina per la prima volta. | event1:1000 | 1 |
| John | L'utente ricarica la pagina (l'invio di un modulo potrebbe non riuscire e la pagina potrebbe venire ricaricata). | event1:1000 | 1 |
| Stacy | Visualizzazione della pagina per la prima volta. | event1:1001 | 2 |
| Stacy | L'utente ricarica la pagina (l'invio di un modulo potrebbe non riuscire e la pagina potrebbe venire ricaricata). | event1:1001 | 2 |
| Jill | L'utente visualizza la pagina per la prima volta, immette correttamente le informazioni e passa alla pagina successiva. | event1:1002 | 3 |
| Jamie | Pagina Visualizzazioni utente per la prima volta | event1 | 4 |
| Jamie | L'utente dimentica di compilare il campo del cognome del modulo. Il modulo viene nuovamente visualizzato con le informazioni mancanti evidenziate. | event1 | 5 |

Quando si selezionano gli ID di serializzazione, tenere presente quanto segue:

* Gli ID di serializzazione devono contenere un massimo di 20 caratteri.
* Gli ID di serializzazione devono essere caratteri alfanumerici.
* Gli ID di serializzazione sono separati per ogni evento di successo. Pertanto, potete utilizzare lo stesso ID per più eventi di successo, se necessario, ma non per lo stesso evento di successo.
* Gli ID di serializzazione sono legati alla suite di rapporti; se utilizzi tag con più suite per inviare dati a più suite di rapporti, ricordati di questo tipo.
* Gli ID di serializzazione non scadono mai, quindi anche se lo stesso ID viene utilizzato anni dopo, l’evento di successo non verrà più conteggiato.
* L'eliminazione dei cookie non impedisce la serializzazione degli ID evento perché gli ID di serializzazione sono memorizzati sui server Adobe e non sono basati su cookie.
* L’unico evento di successo con cui non è possibile utilizzare la serializzazione ID evento è l’evento Purchase, che utilizza una variabile s.purchaseID speciale per la serializzazione.

## Serializzazione degli eventi - Una volta per visita {#section_C919D44F321A47FBBF043D0C57A2A050}

[!DNL Analytics] offre una funzione che consente a un evento di essere attivato una sola volta per visita.

Può essere attivato dall’interfaccia:  **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suite]** &gt; **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Conversion]** &gt; **[!UICONTROL Success Events]** .
