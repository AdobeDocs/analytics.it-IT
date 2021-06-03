---
title: Debugger Adobe Experience Cloud legacy
description: Installa il debugger Adobe Experience Cloud legacy. Questo debugger esamina i tag di Analytics, Target, Advertising Cloud, Identity Service e Launch.
exl-id: 8fd07285-f702-4770-81bd-5f856561f4a9
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '682'
ht-degree: 2%

---

# Debugger Adobe Experience Cloud legacy

>[!IMPORTANT]
>
>Questo strumento di debug non viene più mantenuto. Adobe consiglia invece di utilizzare l’ [Estensione Adobe Experience Cloud Debugger Chrome](https://docs.adobe.com/content/help/it-IT/experience-cloud/user-guides/home.translate.html).

La sezione [!UICONTROL Legacy Debugger] esamina i tag per la maggior parte dei servizi Adobe Experience Cloud. L’utilizzo del debugger consente di vedere quali dati vengono inviati ad Adobe in una determinata pagina del sito. Puoi utilizzare queste informazioni per risolvere i problemi o convalidare l’implementazione della tua organizzazione.

## Installazione del debugger legacy

Crea un bookmarklet JavaScript per installare il debugger.

### Passaggio 1: Copia codice bookmarklet

Copia il seguente codice negli Appunti:

```JavaScript
javascript:void(window.open("","stats_debugger","width=800,height=800,location=0,menubar=0,status=1,toolbar=0,resizable=1,scrollbars=1").document.write("<script language=\"JavaScript\" id=dbg src=\"https://www.adobetag.com/d1/digitalpulsedebugger/live/DPD.js\"></"+"script>"+"<script language=\"JavaScript\">window.focus();</script>"));
```

### Passaggio 2: Incolla il codice del bookmarklet in un segnalibro

Ogni browser ha diversi modi di gestire i segnalibri, ma il concetto è lo stesso. Viene creato un segnalibro con il nome desiderato e il codice del bookmarklet come URL.

#### Chrome

Se insistai per non utilizzare l&#39; [estensione chrome](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html), puoi utilizzare al suo posto il bookmarklet di debug legacy.

1. Fai clic sui tre punti in alto a destra, quindi vai a Segnalibri > Gestione segnalibri. È inoltre possibile premere `Ctrl` + `Shift` + `O` (Windows) o `Cmd` + `Shift` + `O` (Mac).
2. In alto a destra del gestore dei segnalibri, fare clic sui tre punti, quindi fare clic su &#39;Aggiungi nuovo segnalibro&#39;.
3. Nel campo Nome , etichettalo &quot;Adobe Experience Cloud Debugger&quot; e incolla lo snippet di codice nel campo URL.
4. Utilizzare il gestore dei segnalibri per inserire il nuovo bookmarklet nella posizione desiderata.

#### Firefox

1. Fai clic sulle tre righe in alto a destra, quindi vai a Libreria > Segnalibri > Mostra tutti i segnalibri. È inoltre possibile premere `Ctrl` + `Shift` + `B` (Windows) o `Cmd` + `Shift` + `B` (Mac).
2. Fare clic su Organizza > Nuovo segnalibro.
3. Nel campo Nome , etichettalo &quot;Adobe Experience Cloud Debugger&quot; e incolla lo snippet di codice nel campo Posizione. I campi Tag e Parola chiave non sono obbligatori.
4. Utilizzare la finestra della libreria per inserire il nuovo bookmarklet nella posizione desiderata.

#### Bordo

Edge non è in grado di creare manualmente un bookmarklet, ma l’URL di un segnalibro può essere modificato in un bookmarklet.

1. Fai clic sull’icona a forma di stella sul lato destro del campo URL per contrassegnare la pagina corrente come segnalibro.
2. Denomina il segnalibro &quot;Adobe Experience Cloud Debugger&quot; e salvalo nel percorso desiderato.
3. Fare clic sull&#39;icona a forma di stella con le linee per aprire la barra Preferiti.
4. Fai clic con il pulsante destro del mouse sul segnalibro appena creato, quindi seleziona &quot;Modifica URL&quot;.
5. Incolla lo snippet di codice nel campo di testo, quindi premi Invio.

#### Safari

Safari non è in grado di creare manualmente un bookmarklet, ma l’URL di un segnalibro può essere modificato in un bookmarklet.

1. Fai clic sull’icona Condividi in alto a destra, per aprire una finestra modale per i segnalibri.
2. Denomina il segnalibro &quot;Adobe Experience Cloud Debugger&quot; e salvalo nel percorso desiderato.
3. Fare clic su Segnalibri > Modifica segnalibri, quindi individuare il segnalibro appena creato.
4. Fai clic con il pulsante destro del mouse su > Modifica indirizzo, quindi incolla lo snippet di codice nel campo di testo.

## Utilizzo del debugger legacy

Passa alla pagina desiderata sul sito, quindi fai clic sul bookmarklet. Viene visualizzata una finestra a comparsa che mostra i dati inviati ad Adobe.

>[!NOTE]
>
>Alcuni plug-in e blocchi popup di blocco di annunci possono interferire con il caricamento della finestra del debugger. Controlla i pop-up bloccati nel browser e ammettili in modo che il debugger possa funzionare correttamente.

Il debugger dispone di diverse opzioni disponibili, che consentono di personalizzare la visualizzazione dei dati. Nessuna di queste opzioni influisce sulla raccolta dei dati.

* **Prodotti di Experience Cloud visualizzati:** mostra o nasconde le richieste di immagini per ciascun prodotto di Experience Cloud corrispondente.
* **Decode URL:** l’URL decodifica la richiesta di immagine per farla corrispondere a quanto viene visualizzato nel reporting. Adobe consiglia di lasciare selezionata questa casella.
* **Aggiornamento automatico:** aggiorna automaticamente la finestra a comparsa ogni pochi secondi per verificare la presenza di ulteriori richieste di immagini sulla pagina. Se devi copiare/incollare contenuto nel debugger, disattiva l’aggiornamento automatico in modo che la selezione rimanga attiva.
* **Formato descrittivo:** consente di attivare o disattivare il formato di visualizzazione tra etichette utili e stringhe di query non elaborate in una richiesta di immagine. Per ulteriori informazioni, consulta [Parametri query della raccolta dati](query-parameters.md) .

Per salvare le opzioni di visualizzazione predefinite per il debugger, fai clic con il pulsante destro del mouse sul collegamento &quot;Adobe Debugger&quot; nell’angolo in alto a destra, quindi copia l’indirizzo del collegamento. Modifica il bookmarklet di debug corrente e incolla lo snippet di codice aggiornato nel campo URL.
