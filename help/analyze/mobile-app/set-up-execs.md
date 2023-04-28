---
description: In alcuni casi, gli utenti esecutivi potrebbero aver bisogno di ulteriore assistenza per accedere all’app e utilizzarla. Questa sezione offre informazioni per aiutarti a fornire tale assistenza.
title: Impostare gli utenti esecutivi con l’app
feature: Analytics Dashboards
role: User, Admin
exl-id: 0e858407-2852-4a5f-a0df-3ba290fcca8f
source-git-commit: 34ba0e09cd909951a777b0ad3da080958633f97e
workflow-type: ht
source-wordcount: '731'
ht-degree: 100%

---

# Impostare gli utenti esecutivi con l’app

In alcuni casi, gli utenti esecutivi potrebbero aver bisogno di ulteriore assistenza per accedere all’app e utilizzarla. Questa sezione offre informazioni per aiutarti a fornire tale assistenza.

## Assicurarsi che gli utenti dell’app abbiano accesso ad Adobe Analytics

1. Imposta i nuovi utenti in [Admin Console di Experience Cloud](/help/admin/admin-console/permissions/product-profile.md).

1. Per poter condividere le scorecard, devi concedere agli utenti dell’app le autorizzazioni di accesso ai componenti delle scorecard come Analysis Workspace, alle suite di rapporti su cui sono basate le scorecard, nonché ai segmenti, alle metriche e alle dimensioni.

## Prerequisiti di sistema per gli utenti dell’app

Per garantire che gli utenti direzionali possano accedere alle scorecard nell’app, assicurati che:

* Il sistema operativo per dispositivi mobili sui loro dispositivi sia iOS versione 10 o superiore o Android versione 4.4 (KitKat) o superiore.
* Abbiano un accesso valido ad Adobe Analytics.
* Le scorecard per dispositivi mobili a essi destinate siano state correttamente create e condivise.
* Abbiano accesso ai Componenti che la scorecard include. Tieni presente che quando condividi le scorecard puoi selezionare l’opzione **[!UICONTROL Share embedded components]**.

## Aiutare i dirigenti a scaricare e installare l’app

**Per gli utenti direzionali su iOS:**

Fai clic sul seguente collegamento (disponibile anche in Analytics in **[!UICONTROL Tools]** > **[!UICONTROL Analytics dashboards (Mobile App)]**) e segui le istruzioni per scaricare, installare e aprire l’app:

`[iOS link](https://apple.co/2zXq0aN)`

**Per gli utenti direzionali su Android:**

Fai clic sul seguente collegamento (disponibile anche in Analytics in **[!UICONTROL Tools]** > **[!UICONTROL Analytics dashboards (Mobile App)]**) e segui le istruzioni per scaricare, installare e aprire l’app:

`[Android link](https://bit.ly/2LM38Oo)`

Una volta scaricata e installata, gli utenti direzionali possono accedere all’app utilizzando le loro credenziali esistenti di Adobe Analytics; supportiamo sia gli Adobe ID che Enterprise ID e Federated ID.

![Schermata di benvenuto dell’app](assets/welcome.png)

## Aiutare i dirigenti ad accedere alla scorecard

1. Chiedi agli utenti direzionali di accedere all’app.

   Viene visualizzata la schermata **[!UICONTROL Choose a company]**. Questa schermata elenca le aziende di accesso a cui appartiene l’utente direzionale.

1. Chiedi loro di toccare il nome dell’azienda o dell’organizzazione Experience Cloud applicabile alla scorecard condivisa.

   Vengono quindi elencate tutte le scorecard che sono state condivise con l’utente direzionale per l’azienda con cui è stato eseguito l’accesso.

1. Aiutali a ordinare l’elenco in base a **[!UICONTROL Most recently modified]**, se applicabile.

1. Chiedi loro di toccare il nome della scorecard per visualizzarla.

   ![Scegliere un’azienda](assets/accesscard.png)


### Spiegare l’interfaccia utente della scorecard

Spiega all’utente direzionale come appaiono le sezioni nelle scorecard condivise.

![Spiegare le sezioni](assets/newexplain.png)

![Esempio di scorecard](assets/intro_scorecard.png)

Ulteriori informazioni sulle sezioni:

* La granularità dei grafici sparkline dipende dalla lunghezza dell’intervallo date:
* Un giorno mostra una tendenza oraria
   * Più di un giorno e meno di un anno mostra una tendenza giornaliera.
   * Un anno o più mostra una tendenza settimanale.
   * La formula della variazione percentuale del valore è metrica totale (intervallo date attuale) – metrica totale (intervallo date di confronto)/metrica totale (intervallo date di confronto).
   * È possibile trascinare lo schermo verso il basso per aggiornare la scorecard.


1. Tocca una sezione per mostrare come funziona un raggruppamento dettagliato della sezione.

   ![Vista Raggruppamento](assets/sparkline.png)

   * Tocca un punto qualsiasi di una sparkline per visualizzare i dati associati a tale punto sulla linea.

   * È inclusa una tabella per visualizzare i dati delle dimensioni aggiunte alla sezione. Tocca la freccia giù per selezionare le dimensioni. Se non è stata aggiunta alcuna dimensione alla sezione, nella tabella vengono visualizzati i dati relativi al grafico.

1. Per modificare gli intervalli di date per la scorecard, tocca l’intestazione Data e seleziona la combinazione di intervalli di date principali e di confronto che desideri visualizzare.

   ![Modificare le date](assets/changedate.png)

## Modificare le preferenze dell’app

Per modificare le preferenze, tocca l’opzione **[!UICONTROL Preferences]** mostrata sopra. Nelle preferenze, puoi attivare l’accesso biometrico oppure la modalità scura dell’app come illustrato di seguito:

![Modalità scura](assets/darkmode.png)

## Risoluzione dei problemi

Se l’utente direzionale effettua l’accesso e vede un messaggio che dice che non è stato condiviso nulla:

![Niente di condiviso](assets/nothing.png)

* L’utente direzionale potrebbe aver selezionato l’istanza di Analytics sbagliata oppure
* la scorecard potrebbe non essere stata condivisa con l’utente direzionale.

Verifica che l’utente direzionale possa accedere all’istanza appropriata di Adobe Analytics e che la scorecard sia stata condivisa.

>[!IMPORTANT]
>
>A partire da ottobre 2020, Adobe sta gradualmente implementando una serie di miglioramenti per ottimizzare le prestazioni dell’app “Adobe Analytics dashboards”. Questi miglioramenti sono incentrati sulla memorizzazione nella cache dei dati Analytics storici utilizzati per popolare le scorecard con le date (escluso il giorno corrente). I dati verranno memorizzati nella cache fino a 24 ore in un account di archiviazione cloud pubblico Microsoft Azure protetto. Se preferisci rinunciare a queste funzioni di miglioramento delle prestazioni, contatta il team del tuo account Adobe.
