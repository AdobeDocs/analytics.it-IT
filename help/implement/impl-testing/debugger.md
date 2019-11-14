---
description: Installa il debugger legacy di Adobe Experience Cloud. Questo debugger esamina i tag per Analytics, Target, Advertising Cloud, Identity Service, DTM e Launch.
title: Adobe Experience Cloud Debugger precedente
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Adobe Experience Cloud Debugger precedente

> [!IMPORTANT] Questo strumento di debug non viene più mantenuto. Adobe consiglia di utilizzare invece l’estensione [Chrome di](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html)Adobe Experience Cloud Debugger.

Vengono [!UICONTROL Legacy Debugger] analizzati i tag per la maggior parte dei servizi Adobe Experience Cloud. L’utilizzo del debugger consente di visualizzare i dati inviati ad Adobe su qualsiasi pagina del sito. Potete utilizzare queste informazioni per risolvere eventuali problemi o convalidare l'implementazione dell'organizzazione.

## Installazione del debugger legacy

Creare un bookmarklet JavaScript per installare il debugger.

### Passaggio 1: Copia codice bookmarklet

Copia il codice seguente negli Appunti:

```JavaScript
javascript:void(window.open("","stats_debugger","width=800,height=800,location=0,menubar=0,status=1,toolbar=0,resizable=1,scrollbars=1").document.write("<script language=\"JavaScript\" id=dbg src=\"https://www.adobetag.com/d1/digitalpulsedebugger/live/DPD.js\"></"+"script>"+"<script language=\"JavaScript\">window.focus();</script>"));
```

### Passaggio 2: Incolla il codice del bookmarklet in un segnalibro

Ogni browser dispone di diversi metodi per gestire i segnalibri, ma il concetto è lo stesso. Viene creato un segnalibro con il nome desiderato e il codice del bookmarklet come URL.

#### Chrome

Se si insiste a non utilizzare l'estensione [](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html)chrome, è possibile utilizzare il bookmarklet precedente del debugger.

1. Fare clic sui tre punti in alto a destra, quindi passare a Segnalibri &gt; Gestione segnalibri. Potete anche premere `Ctrl` + `Shift` + `O` (Windows) o `Cmd` + `Shift` + `O` (Mac).
2. In alto a destra del gestore dei segnalibri, fare clic sui tre punti, quindi fare clic su 'Aggiungi nuovo segnalibro'.
3. Nel campo Nome, etichettatelo "Adobe Experience Cloud Debugger" e incollate lo snippet di codice nel campo URL.
4. Utilizzare il gestore dei segnalibri per posizionare il nuovo bookmarklet nella posizione desiderata.

#### Firefox

1. Fare clic sulle tre righe in alto a destra, quindi passare a Libreria &gt; Segnalibri &gt; Mostra tutti i segnalibri. Potete anche premere `Ctrl` + `Shift` + `B` (Windows) o `Cmd` + `Shift` + `B` (Mac).
2. Fare clic su Organizza &gt; Nuovo segnalibro.
3. Nel campo Nome, etichettalo "Adobe Experience Cloud Debugger" e incolla lo snippet di codice nel campo Posizione. I campi Tag e Parola chiave non sono obbligatori.
4. Utilizzare la finestra della libreria per posizionare il nuovo bookmarklet nella posizione desiderata.

#### Edge

Edge non è in grado di creare manualmente un bookmarklet, ma è possibile modificare l'URL di un segnalibro.

1. Fate clic sull’icona a forma di stella sul lato destro del campo URL per contrassegnare la pagina corrente come segnalibro.
2. Denominate il segnalibro "Adobe Experience Cloud Debugger" e salvatelo nella posizione desiderata.
3. Fate clic sull'icona a stella con le linee per aprire la barra Preferiti.
4. Fare clic con il pulsante destro del mouse sul segnalibro appena creato, quindi selezionare Modifica URL.
5. Incollate lo snippet di codice nel campo di testo, quindi premete Invio.

#### Safari

Safari non è in grado di creare manualmente un bookmarklet, ma è possibile modificare l'URL di un segnalibro.

1. Fate clic sull'icona Condividi in alto a destra, per aprire una finestra modale con segnalibro.
2. Denominate il segnalibro "Adobe Experience Cloud Debugger" e salvatelo nella posizione desiderata.
3. Fare clic su Segnalibri &gt; Modifica segnalibri, quindi individuare il segnalibro appena creato.
4. Fare clic con il pulsante destro del mouse &gt; Modifica indirizzo, quindi incollare lo snippet di codice nel campo di testo.

## Utilizzo del debugger legacy

Per utilizzare il debugger, passare alla pagina desiderata sul sito, quindi fare clic sul bookmarklet. Viene visualizzata una finestra a comparsa che mostra i dati inviati ad Adobe.

> [!NOTE] Alcuni plug-in e blocchi pop-up di blocco di annunci possono interferire con il caricamento della finestra del debugger. Controllate le finestre a comparsa bloccate nel browser e consentitele il corretto funzionamento del debugger.

Il debugger dispone di diverse opzioni, tutte per personalizzare la modalità di visualizzazione dei dati. Nessuna di queste opzioni influisce sulla raccolta dei dati.

* **** Prodotti Experience Cloud visualizzati: Mostra o nasconde le richieste di immagini per ciascun prodotto Experience Cloud.
* **** Decode URL: L’URL decodifica la richiesta di immagine in modo che corrisponda a quanto viene visualizzato nel reporting. Adobe consiglia di lasciare questa casella selezionata.
* **** Aggiornamento automatico: Aggiorna automaticamente la finestra a comparsa ogni pochi secondi per verificare la presenza di ulteriori richieste di immagini sulla pagina. Se è necessario copiare/incollare contenuto nel debugger, disattivare l'aggiornamento automatico in modo che la selezione rimanga invariata.
* **** Formato intuitivo: Attiva/disattiva il formato di visualizzazione tra etichette utili e stringhe di query non elaborate in una richiesta di immagine. Per ulteriori informazioni, vedi Parametri [query di raccolta](../js-implementation/data-collection/query-parameters.md) dati.

Per salvare le opzioni di visualizzazione predefinite per il debugger, fai clic con il pulsante destro del mouse sul collegamento Adobe Debugger nell'angolo in alto a destra, quindi copia l'indirizzo del collegamento. Modificare il bookmarklet del debugger corrente e incollare lo snippet di codice aggiornato nel campo URL.
