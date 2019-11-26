---
title: Canale interno (aggiornamento sessione)
description: Informazioni sul canale interno (aggiornamento sessione).
translation-type: tm+mt
source-git-commit: 4cd12beff4d9007d4c2037a9998417ff85c4ade9

---


# Canale interno (aggiornamento sessione)

Il canale interno (spesso rinominato come Aggiornamento sessione) consiste in visite al sito in cui l’URL di provenienza corrisponde alla configurazione dei filtri URL interni nell’Admin Console, il che significa che il visitatore è venuto dall’interno del sito per avviare la visita.

![](assets/int-channel1.png)

## Escludere le best practice

È consigliabile deselezionare l’opzione Ignora ultimo tocco per i canali Direct e Internal, in modo che non possano ricevere credito da altri canali touch persistenti (o da altri canali reciproci).

>[!NOTE]Questo documento presuppone che l'opzione Aggiornamento diretto e Aggiornamento sessione non siano selezionate.

![](assets/int-channel2.png)

## Periodo di coinvolgimento

Sia il primo che l’ultimo canale touch per un visitatore vengono reimpostati dopo 30 giorni di inattività in quel browser.

>[!NOTE] Il valore predefinito è 30 giorni e può essere modificato in base alle esigenze tramite le impostazioni Amministratore.

Se il visitatore utilizza il sito frequentemente, la finestra di coinvolgimento si espanderà con loro. Devono essere inattivi per 30 giorni affinché il periodo scada e i canali vengano reimpostati.
Esempio:

* Giorno 1: L'utente accede al sito sul display. I canali Primo e Ultimo tocco verranno impostati su Display.

* Giorno 2: L'utente viene al sito su Natural Search. Il primo tocco rimane Display e l'ultimo tocco è impostato su Natural Search.

* Giorno 35: L'utente non è stato sul sito in 33 giorni e torna utilizzando la scheda che aveva aperto nel browser. Presupponendo una finestra di coinvolgimento di 30 giorni, la finestra si sarebbe chiusa e i cookie di Marketing Channel sarebbero scaduti. Il primo canale touch e l’ultimo touch vengono reimpostati e impostati su Aggiornamento sessione, dal momento che l’utente proviene da un URL interno.

## Relazione tra il primo e l'ultimo tocco

Per comprendere l’interazione tra il primo e l’ultimo tocco e per confermare che le impostazioni locali funzionano come previsto, potete eseguire il pulling di un rapporto sui canali di primo tocco, relativo in parte a un rapporto sull’ultimo canale, con l’aggiunta della metrica di successo chiave (vedere l’esempio di seguito). L’esempio illustra l’interazione tra canali primo e ultimo contatto.

![](assets/int-channel3.png)

L’intersezione in cui prima corrisponde all’ultimo tocco è evidenziata in arancione. Sia l'aggiornamento diretto che l'aggiornamento della sessione ottengono solo l'ultimo tocco di credito se erano anche il primo canale touch, perché non possono ottenere credito da altri canali persistenti (righe evidenziate in grigio).

## Perché si verifica l'aggiornamento della sessione?

Poiché sappiamo che l’aggiornamento dell’ultima sessione può avvenire solo se è stato anche il primo tocco, gli scenari seguenti spiegano come l’aggiornamento della sessione potrebbe essere un canale di primo tocco.

### Scenario 1: Timeout sessione

Un visitatore accede al sito Web e quindi lascia la scheda aperta nel browser per utilizzarla in un secondo momento. Il periodo di coinvolgimento del visitatore scade (o elimina volontariamente i cookie) e utilizza la scheda aperta per visitare nuovamente il sito Web. Poiché l’URL di provenienza è un dominio interno, la visita verrà classificata come Aggiornamento sessione.

### Scenario 2: Non tutte le pagine del sito dispongono di tag

Un visitatore arriva sulla pagina A senza tag, quindi passa alla pagina B con tag. La pagina A viene visualizzata come referente interno e la visita viene classificata come Aggiornamento sessione.

### Scenario 3: Reindirizza

Se un reindirizzamento non è impostato per trasmettere i dati del referente alla nuova pagina di destinazione, i dati del referente di entrata vera andranno persi e ora la pagina di reindirizzamento (probabilmente una pagina interna) verrà visualizzata come dominio di riferimento. La visita verrà classificata come Aggiornamento sessione.

### Scenario 4: Traffico tra domini

Un visitatore passa da un dominio che viene attivato alla Suite A a un altro che viene attivato nella Suite B. Se nella Suite B i filtri URL interni includono il primo dominio, la visita nella Suite B verrà registrata come Interno, poiché Marketing Channels la vede come una nuova visita nella seconda suite. La visita verrà classificata come Aggiornamento sessione.

### Scenario 5: Lunghi tempi di caricamento delle pagine

Un visitatore arriva sulla pagina A che si trova in condizioni di aumento e il codice Adobe Analytics si trova nella parte superiore della pagina. Prima che tutti i contenuti con aumento (inclusa la richiesta di immagini di Adobe Analytics) possano essere caricati, l'aumento dei clic del pulsante a pagina B. La pagina B avvia la richiesta di immagine di Adobe Analytics. Poiché la richiesta di immagine della pagina A non è mai stata caricata, la seconda pagina viene visualizzata come il primo hit della visita in Adobe Analytics, con la pagina A come referente. La visita viene classificata come Aggiornamento sessione.

### Scenario 6: Cancellazione dei cookie nel sito centrale

Un visitatore accede al sito e a metà sessione cancella i cookie. Entrambi i canali First e Last-touch venivano reimpostati e la visita veniva classificata come Aggiornamento sessione (perché il referente era interno).
