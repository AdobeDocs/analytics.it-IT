---
description: Come creare una scorecard delle dashboard di Analytics
title: Creare una scorecard
feature: Analytics Dashboards
role: User, Admin
source-git-commit: 012bbfa54d97ffcaf4cd0de380c196df06a03bfe
workflow-type: tm+mt
source-wordcount: '979'
ht-degree: 81%

---


# Impostare gli utenti esecutivi con l’app

In alcuni casi, gli utenti esecutivi potrebbero aver bisogno di ulteriore assistenza per accedere all’app e utilizzarla. Questa sezione offre informazioni per aiutarti a fornire tale assistenza.

## Prerequisiti per il sistema degli utenti esecutivi

Per garantire che gli utenti esecutivi abbiano accesso alle tue scorecard sull’app, assicurati che:

* Il sistema operativo per dispositivi mobili sui loro dispositivi sia iOS versione 10 o superiore o Android versione 4.4 (KitKat) o superiore
* Abbiano un accesso valido ad Adobe Analytics
* Tu abbia creato correttamente le scorecard per dispositivi mobili a essi destinate e condiviso con essi tali scorecard
* Abbiano accesso all’Analysis Workspace e alla suite di rapporti su cui si basa la scorecard
* Abbiano accesso ai Componenti che la scorecard include. Nota che puoi selezionare un’opzione quando condividi le scorecard per **[!UICONTROL Share embedded components]**.

## Download e installazione dell’app da parte dei dirigenti di Aiuto

**Per gli utenti esecutivi su iOS:**

Fai clic sul seguente collegamento (disponibile anche in Analytics in **[!UICONTROL Tools]** > **[!UICONTROL Analytics dashboards (Mobile App)]**) e segui le istruzioni per scaricare, installare e aprire l’app:

`[iOS link](https://apple.co/2zXq0aN)`

**Per gli utenti esecutivi su Android:**

Fai clic sul seguente collegamento (disponibile anche in Analytics in **[!UICONTROL Tools]** > **[!UICONTROL Analytics dashboards (Mobile App)]**) e segui le istruzioni per scaricare, installare e aprire l’app:

`[Android link](https://bit.ly/2LM38Oo)`

Una volta scaricata e installata, gli utenti esecutivi possono accedere all’app utilizzando le loro credenziali esistenti di Adobe Analytics; supportiamo sia gli ID Adobe che Enterprise ID e Federated ID.

![Schermata di benvenuto dell’app](assets/welcome.png)

## Aiuta i dirigenti ad accedere alla tua scorecard

1. Chiedi agli utenti esecutivi di accedere all’app.

   Viene visualizzata la schermata **[!UICONTROL Choose a company]**. Questa schermata elenca le aziende di accesso a cui appartiene l’utente esecutivo.

1. Chiedi loro di toccare il nome della società di accesso o dell’organizzazione Experience Cloud che si applica alla scorecard che hai condiviso.

   L’elenco delle scorecard mostra quindi tutte le scorecard che sono state condivise con l’amministratore in quella società di accesso.

1. Chiedi loro di ordinare questo elenco per **[!UICONTROL Most recently modified]**, se applicabile.

1. Chiedi loro di toccare il nome della scorecard per visualizzarla.

   ![Scegliere un’azienda](assets/accesscard.png)


### Spiegare l’interfaccia utente della scorecard

Spiega all’utente esecutivo come vengono visualizzate le tessere nelle scorecard condivise.

![Spiegare le tessere](assets/newexplain.png)

![Esempio di scorecard](assets/intro_scorecard.png)

Ulteriori informazioni sulle tessere:

* La granularità dei grafici sparkline dipende dalla lunghezza dell’intervallo date:
* Un giorno mostra una tendenza oraria
   * Più di un giorno e meno di un anno mostra una tendenza giornaliera
   * Un anno o più mostra una tendenza settimanale
   * La formula della variazione percentuale del valore è metrica totale (intervallo date attuale) – metrica totale (intervallo date di confronto)/metrica totale (intervallo date di confronto).
   * È possibile trascinare lo schermo verso il basso per aggiornare la scorecard.


1. Toccare una tessera per mostrare come funziona un raggruppamento dettagliato della tessera.

   ![Vista Raggruppamento](assets/sparkline.png)

   * Tocca un punto qualsiasi di una sparkline per visualizzare i dati associati a tale punto sulla linea.

   * È inclusa una tabella per visualizzare i dati delle dimensioni aggiunte alla tessera. Tocca la freccia giù per selezionare le dimensioni. Se non è stata aggiunta alcuna dimensione alla tessera, nella tabella vengono visualizzati i dati relativi al grafico.

1. Per modificare gli intervalli di date per la scorecard, tocca l’intestazione Data e seleziona la combinazione di intervalli di date principali e di confronto che desideri visualizzare.

   ![Modificare le date](assets/changedate.png)

## Modificare le preferenze dell’app

Per modificare le preferenze, tocca l’opzione **[!UICONTROL Preferences]** mostrata sopra. Nelle preferenze, puoi attivare l’accesso biometrico oppure la modalità scura dell’app come illustrato di seguito:

![Modalità scura](assets/darkmode.png)

## Risoluzione dei problemi

Se l’utente esecutivo effettua l’accesso e vede un messaggio che dice che non è stato condiviso nulla:

![Niente di condiviso](assets/nothing.png)

* L’utente esecutivo può aver selezionato l’istanza di Analytics sbagliata, oppure
* La scorecard potrebbe non essere stata condivisa con l’utente esecutivo.

Verifica che l’utente esecutivo possa accedere alla giusta istanza di Adobe Analytics e che la scorecard sia stata condivisa.

### Segnala un bug

Toccare l’opzione e scegliere una sottocategoria del bug. Nel modulo per la segnalazione di un bug, fornisci il tuo indirizzo e-mail nel campo superiore e la tua descrizione del bug nel campo sotto di esso. Al messaggio viene automaticamente allegata una schermata con le informazioni del tuo account, ma puoi cancellarla, se lo desideri, toccando la **X** nell’immagine allegata. Ci sono anche delle opzioni per effettuare una registrazione dello schermo, aggiungere altre schermate o allegare file. Per inviare la segnalazione, toccare l’icona dell’aeroplano di carta in alto a destra del modulo.

![Segnalare un bug](assets/newbug.png)

### Lasciare un feedback

1. Tocca l’icona dell’utente in alto a destra della schermata dell’app.
1. Nella schermata **[!UICONTROL Settings]**, tocca l’opzione **[!UICONTROL Feedback]**.
1. Tocca per visualizzare le opzioni per lasciare un feedback.

   ![Schermata Settings](assets/settings.png)

### Suggerisci un miglioramento

Toccare l’opzione e scegliere una sottocategoria del suggerimento. Nel modulo di suggerimento, fornisci il tuo indirizzo e-mail nel campo superiore e la tua descrizione del bug nel campo sotto di esso. Al messaggio viene automaticamente allegata una schermata con le informazioni del tuo account, ma puoi cancellarla, se lo desideri, toccando la **X** nell’immagine allegata. Ci sono anche delle opzioni per effettuare una registrazione dello schermo, aggiungere altre schermate o allegare file. Per inviare il suggerimento, toccare l’icona dell’aeroplano di carta in alto a destra del modulo.

### Fai una domanda

Tocca l’opzione e fornisci il tuo indirizzo e-mail nel campo superiore e la tua domanda nel campo sotto di esso. Al messaggio viene automaticamente allegata una schermata, ma puoi cancellarla, se lo desideri, toccando la **X** nell’immagine allegata. Ci sono anche delle opzioni per effettuare una registrazione dello schermo, aggiungere altre schermate o allegare file. Per inviare la domanda, toccare l’icona dell’aeroplano di carta in alto a destra del modulo.

>[!IMPORTANT]
>
>A partire da ottobre 2020, Adobe sta gradualmente implementando una serie di miglioramenti per ottimizzare le prestazioni dell’app “Adobe Analytics dashboards”. Questi miglioramenti sono incentrati sulla memorizzazione nella cache dei dati Analytics storici utilizzati per popolare le scorecard con le date (escluso il giorno corrente). I dati verranno memorizzati nella cache fino a 24 ore in un account di archiviazione cloud pubblico Microsoft Azure protetto. Se preferisci non utilizzare queste funzioni di miglioramento delle prestazioni, contatta il tuo Customer Success Manager.
