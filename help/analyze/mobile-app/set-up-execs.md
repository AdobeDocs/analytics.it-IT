---
description: Come creare una scorecard delle dashboard di Analytics
title: Creare una scorecard
feature: Analytics Dashboards
role: User, Admin
source-git-commit: 63f4f69cd22531ced7c65d1b38fdc982da97887b
workflow-type: tm+mt
source-wordcount: '709'
ht-degree: 63%

---


# Impostare gli utenti esecutivi con l’app

In alcuni casi, gli utenti esecutivi potrebbero aver bisogno di ulteriore assistenza per accedere all’app e utilizzarla. Questa sezione offre informazioni per aiutarti a fornire tale assistenza.

## Assicurati che gli utenti dell&#39;app abbiano accesso ad Adobe Analytics

1. Imposta i nuovi utenti nell&#39; [Admin Console Experience Cloud](/help/admin/admin-console/permissions/product-profile.md).

1. Per poter condividere le scorecard, devi concedere agli utenti dell’app le autorizzazioni per accedere ai componenti delle scorecard come Analysis Workspace, alle suite di rapporti su cui sono basate le scorecard, nonché ai segmenti, alle metriche e alle dimensioni.

## Prerequisiti di sistema per gli utenti dell’app

Per garantire che gli utenti esecutivi abbiano accesso alle tue scorecard sull’app, assicurati che:

* Il sistema operativo per dispositivi mobili sui loro dispositivi sia iOS versione 10 o superiore o Android versione 4.4 (KitKat) o superiore
* Abbiano un accesso valido ad Adobe Analytics.
* Le scorecard per dispositivi mobili sono state create correttamente e condivise con loro.
* Hanno accesso ai Componenti inclusi nella scorecard. Tieni presente che puoi selezionare un’opzione quando condividi le scorecard in **[!UICONTROL Share embedded components]**.

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

>[!IMPORTANT]
>
>A partire da ottobre 2020, Adobe sta gradualmente implementando una serie di miglioramenti per ottimizzare le prestazioni dell’app “Adobe Analytics dashboards”. Questi miglioramenti sono incentrati sulla memorizzazione nella cache dei dati Analytics storici utilizzati per popolare le scorecard con le date (escluso il giorno corrente). I dati verranno memorizzati nella cache fino a 24 ore in un account di archiviazione cloud pubblico Microsoft Azure protetto. Se preferisci non utilizzare queste funzioni di miglioramento delle prestazioni, contatta il tuo Customer Success Manager.