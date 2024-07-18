---
title: Debugger legacy di Adobe Experience Cloud
description: Installa il debugger legacy di Adobe Experience Cloud. Questo debugger analizza i tag di Analytics, Target, Advertising Cloud, Identity Service e Data Collection.
feature: Validation
exl-id: 8fd07285-f702-4770-81bd-5f856561f4a9
role: Admin, Developer, Leader, User
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 0%

---

# Debugger legacy di Adobe Experience Cloud

>[!IMPORTANT]
>
>Questo strumento di debug non viene più mantenuto. L&#39;Adobe consiglia invece di utilizzare l&#39;estensione [Adobe Experience Cloud Debugger Chrome](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=it).

[!UICONTROL Legacy Debugger] esamina i tag per la maggior parte dei servizi Adobe Experience Cloud. L’utilizzo del debugger consente di visualizzare quali dati vengono inviati agli Adobi in una determinata pagina del sito. Puoi utilizzare queste informazioni per risolvere eventuali problemi o convalidare l’implementazione dell’organizzazione.

## Installazione del debugger legacy

Crea un bookmarklet JavaScript per installare il debugger.

### Passaggio 1: copia codice bookmarklet

Copia il seguente codice negli Appunti:

```JavaScript
javascript:void(window.open("","stats_debugger","width=800,height=800,location=0,menubar=0,status=1,toolbar=0,resizable=1,scrollbars=1").document.write("<script language=\"JavaScript\" id=dbg src=\"https://www.adobetag.com/d1/digitalpulsedebugger/live/DPD.js\"></"+"script>"+"<script language=\"JavaScript\">window.focus();</script>"));
```

### Passaggio 2: incolla il codice del bookmarklet in un segnalibro

Ogni browser ha diversi modi per gestire i segnalibri, ma il concetto è lo stesso. Viene creato un segnalibro con il nome desiderato e il codice del segnalibro come URL.

#### Chrome

Se si insiste a non utilizzare l&#39;estensione [chrome](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=it), è possibile utilizzare il bookmarklet del debugger legacy.

1. Fai clic sui tre punti in alto a destra, quindi vai a Segnalibri > Gestione segnalibri. È inoltre possibile premere `Ctrl` + `Shift` + `O` (Windows) o `Cmd` + `Shift` + `O` (Mac).
2. In alto a destra in Gestione segnalibri, fai clic sui tre punti, quindi su Aggiungi nuovo segnalibro.
3. Nel campo Nome, etichettalo come &quot;Adobe Experience Cloud Debugger&quot; e incolla lo snippet di codice nel campo URL.
4. Usate Gestione segnalibri per posizionare il nuovo bookmarklet nella posizione desiderata.

#### Firefox

1. Fai clic sulle tre righe in alto a destra, quindi vai a Libreria > Segnalibri > Mostra tutti i segnalibri. È inoltre possibile premere `Ctrl` + `Shift` + `B` (Windows) o `Cmd` + `Shift` + `B` (Mac).
2. Fai clic su Organizza > Nuovo segnalibro.
3. Nel campo Nome, etichettalo come &quot;Adobe Experience Cloud Debugger&quot; e incolla lo snippet di codice nel campo Posizione. I campi Tag e Parola chiave non sono obbligatori.
4. Utilizzare la finestra della libreria per posizionare il nuovo bookmarklet nella posizione desiderata.

#### Edge

Edge non può creare manualmente un bookmarklet, ma un URL di segnalibro può essere modificato in un bookmarklet.

1. Fai clic sull’icona a forma di stella sul lato destro del campo URL per aggiungere un segnalibro alla pagina corrente.
2. Denomina il segnalibro &quot;Adobe Experience Cloud Debugger&quot; e salvalo nella posizione desiderata.
3. Fare clic sull&#39;icona stella con le righe per aprire la barra Preferiti.
4. Fare clic con il pulsante destro del mouse sul segnalibro appena creato e selezionare &#39;Modifica URL&#39;.
5. Incolla lo snippet di codice nel campo di testo, quindi premi Invio.

#### Safari

Safari non può creare manualmente un bookmarklet, ma un URL di segnalibro può essere modificato in un bookmarklet.

1. Fai clic sull’icona Condividi in alto a destra, per aprire una finestra modale per segnalibri.
2. Denomina il segnalibro &quot;Adobe Experience Cloud Debugger&quot; e salvalo nella posizione desiderata.
3. Selezionate Segnalibri (Bookmarks) > Modifica segnalibri (Edit Bookmarks) e individuate il segnalibro appena creato.
4. Fai clic con il pulsante destro del mouse su > Modifica indirizzo, quindi incolla lo snippet di codice nel campo di testo.

## Utilizzo del debugger legacy

Passa alla pagina desiderata del sito, quindi fai clic sul bookmarklet. Viene visualizzata una finestra pop-up con i dati inviati all&#39;Adobe.

>[!NOTE]
>
>Alcuni plug-in e blocchi popup di ad-blocking possono interferire con il caricamento della finestra di debugger. Verifica la presenza di popup bloccati nel browser e consenti che funzionino correttamente.

Il debugger dispone di diverse opzioni disponibili, tutte che personalizzano la modalità di visualizzazione dei dati. Nessuna di queste opzioni influisce sulla raccolta dei dati.

* **Prodotti di Experience Cloud visualizzati:** mostra o nasconde le richieste di immagini per ciascun prodotto di Experience Cloud.
* **Decodifica URL:** L&#39;URL decodifica la richiesta di immagine in modo che corrisponda a quanto visualizzato nel reporting. L’Adobe consiglia di lasciare selezionata questa casella.
* **Aggiornamento automatico:** aggiorna automaticamente il popup ogni pochi secondi per verificare la presenza di altre richieste di immagini nella pagina. Se devi copiare/incollare il contenuto nel debugger, disattiva l’aggiornamento automatico in modo che la selezione rimanga invariata.
* **Formato descrittivo:** Attiva o disattiva il formato di visualizzazione tra le etichette utili e le stringhe di query non elaborate in una richiesta di immagine. Per ulteriori informazioni, vedere [Parametri query raccolta dati](query-parameters.md).

Per salvare le opzioni di visualizzazione predefinite per il debugger, fai clic con il pulsante destro del mouse sul collegamento &#39;Adobe Debugger&#39; nell&#39;angolo in alto a destra, quindi copia l&#39;indirizzo del collegamento. Modifica il bookmarklet di debugger corrente e incolla lo snippet di codice aggiornato nel campo URL.
