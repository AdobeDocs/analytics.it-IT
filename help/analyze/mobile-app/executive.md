---
description: Istruzioni per l'impostazione delle scorecard dell'app mobile.
title: Guida alla cura delle app Adobe Analytics Mobile
translation-type: tm+mt
source-git-commit: 9149e9ad5a74ef1de0ece5fb0056ee6fee5d50e9

---


# App mobile Analytics: Guida rapida utente

## Introduzione

L'app mobile Adobe Analytics fornisce informazioni ovunque e in qualsiasi momento da Adobe Analytics.  L'app consente agli utenti di accedere mobile a scorecard intuitive. Le scorecard sono una raccolta di metriche chiave e altri componenti presentati in un layout a piastrelle che potete toccare per suddivisioni più dettagliate e report con tendenze. L'app mobile è supportata sia sui sistemi operativi iOS che su quelli Android.

## Informazioni su questa guida

 Questa guida è destinata ad aiutare gli utenti esecutivi a leggere e interpretare le scorecard nell'app mobile Analytics. L'app consente agli utenti amministratori di visualizzare un ampio rendering di importanti dati di riepilogo in modo rapido e semplice sui propri dispositivi mobili.

## Glossario dei termini

| Termine | Definizione |
|--- |--- |
| Consumer | Personalità esecutiva che visualizza metriche chiave e informazioni da Analytics su un dispositivo mobile |
| Curatore | Persona con informazioni sui dati che trova e distribuisce approfondimenti da Analytics e configura gli scorecard da visualizzare per il consumatore |
| Cura | Creazione o modifica di una scorecard mobile contenente metriche, dimensioni e altri componenti rilevanti per il consumatore |
| Scorecard | Visualizzazione app mobile contenente uno o più riquadri |
| Affianca | Rendering di una metrica in una visualizzazione scorecard |
| Suddividi | Vista secondaria accessibile toccando una sezione nella scorecard. Questa visualizzazione si espande sulla metrica visualizzata nella sezione e, facoltativamente, riporta ulteriori dimensioni di suddivisione. |
| Intervallo date | L'intervallo di date principale per il reporting delle app mobili |
| Intervallo date confronto | Intervallo di date confrontato con l'intervallo di date principale |

## Ottenere la configurazione dell'app sul dispositivo

Per utilizzare l'app in modo efficace, è necessario che il curatore Scorecard ti aiuti a configurarla. Questa sezione fornisce informazioni utili per la configurazione con l’assistenza del curatore.

### Ottieni accesso

Per accedere alle scorecard nell'app, accertati che:

* Hai un accesso valido ad Adobe Analytics
* Il vostro curatore ha creato correttamente le scorecard mobili e le ha condivise con voi

### Scaricate e installate l'app

Per scaricare e installare l'app, segui i passaggi descritti in base al sistema operativo sul tuo dispositivo.

**Per i dispositivi iOS:**

1. Fai clic sul seguente collegamento pubblico (è disponibile anche in Analytics in **Strumenti** &gt; App **** mobile):

   [Collegamento](https://testflight.apple.com/join/WtXMQxlI)iOS: `https://testflight.apple.com/join/WtXMQxlI`

   Dopo aver fatto clic sul collegamento, viene visualizzata la seguente schermata Verifica:

   ![Schermata di verifica](assets/testflight1.png)

2. Toccate il collegamento **Visualizza in App Store** sullo schermo per scaricare l'app TestFlight.

3. Dopo aver installato l'app Testflight, trova e installa l'app mobile Adobe Analytics dall'interno di TestFlight come mostrato di seguito:

   ![Schermata di verifica](assets/testflight2.png)

**Per i dispositivi Android:**

1. Toccate il seguente collegamento Play Store sul dispositivo dell'utente (è disponibile anche in Analytics in **Strumenti** &gt; App **** mobile):


   [Android](https://play.google.com/apps/testing/com.adobe.analyticsmobileapp): `https://play.google.com/apps/testing/com.adobe.analyticsmobileapp`

   Dopo aver toccato il collegamento, toccate il collegamento Diventa un tester nella schermata seguente:

   ![Riproduci store, schermata](assets/play.png)

2. Toccate il **download sul collegamento Google Play** nella schermata seguente:

   ![Collegamento di download](assets/playnext.png)

## Utilizzo dell'app

Per utilizzare l'app:

1. Effettuate l'accesso all'app. La schermata di accesso verrà visualizzata all'avvio dell'app. Seguite i prompt utilizzando le credenziali Adobe Analytics esistenti. Supportiamo sia Adobe che Enterprise ID/Federated ID.

   ![Sign in sequence](assets/signseq.png)

2. Scegliete una società. Dopo l'accesso all'app, viene visualizzata la schermata **Scegli una società** . In questa schermata sono elencate le società di accesso alle quali appartenete. Toccate il nome della società associata alla scorecard condivisa con voi.

3. Nell'elenco Scorecard vengono quindi visualizzate tutte le scorecard condivise con voi. Toccate la scorecard da visualizzare.

   ![Scegliere una società](assets/accesscard.png)

   *Nota: Se effettuate l’accesso e viene visualizzato un messaggio che informa che non è stato condiviso nulla, verificate quanto segue con il vostro curatore:*

   * *Puoi accedere all’istanza di Analytics giusta*
   * *La scorecard è stata condivisa con voi*

      ![Nessuna condivisione](assets/nothing.png)

4. Esaminare l'aspetto delle sezioni nella scorecard.

   ![Sezioni spiegate](assets/newexplain.png)

   Ulteriori informazioni sulle sezioni:

   * La granularità dei grafici sparkline dipende dalla lunghezza dell'intervallo di date:
   * Un giorno mostra una tendenza oraria
   * Più di un giorno e meno di un anno mostra una tendenza giornaliera
   * Un anno o più mostra una tendenza settimanale
   * La formula di variazione del valore percentuale è totale della metrica (intervallo di date corrente) - totale della metrica (intervallo di date di confronto) / totale della metrica (intervallo di date di confronto).
   * Per aggiornare la scorecard è possibile spostare lo schermo verso il basso.

5. Toccate una sezione per vedere come funziona una suddivisione dettagliata per la sezione.

   ![Visualizzazione per sottogruppi di lavoro](assets/sparkline.png)


6. Per modificare gli intervalli di date per la scorecard:

   ![Modifica date](assets/changedate.png)

   *Nota: Puoi anche modificare allo stesso modo gli intervalli di date all’interno della visualizzazione Suddivisione mostrata sopra.*

   A seconda dell’intervallo di tempo che toccate (**Giorno**, **Settimana**, **Mese** o **Anno**), verranno visualizzate due opzioni per gli intervalli di date, quella attuale o quella immediatamente precedente. Toccate una di queste due opzioni per selezionare il primo intervallo. Nell'elenco **COMPARE A** , toccare una delle opzioni presentate per confrontare i dati di questo periodo di tempo con il primo intervallo di date selezionato. Toccate **Fine** in alto a destra nella schermata. I campi **Intervalli** di date e Scorecard vengono aggiornati con i nuovi dati di confronto dei nuovi intervalli selezionati.

7. Ottieni aggiornamenti scorecard. Se una scorecard non include tutte le metriche o le suddivisioni che potrebbero interessarti, contatta il team Analytics per richiedere l'aggiornamento della scorecard. Una volta aggiornata, potete tirare giù la scheda sullo schermo per aggiornarla e caricare i dati aggiunti di recente.



8. Lasciate un feedback. Per lasciare un commento:

   1. Toccate l'icona utente in alto a destra della schermata dell'app.
   2. Nella schermata **Account** personale, toccate l'opzione **Feedback** .
   3. Toccate per visualizzare le opzioni per lasciare il feedback.
   ![Lascia feedback](assets/feedback.png)
   ![Opzioni di feedback](assets/feedback_option.png)


**Per segnalare un bug**:

Toccate l’opzione e scegliete una sottocategoria del bug. Nel modulo per segnalare un bug, fornite il vostro indirizzo e-mail nel campo superiore e la descrizione del bug nel campo sottostante. Al messaggio viene automaticamente collegata una schermata delle informazioni dell'account, ma è possibile eliminarla toccando la **X** nell'immagine dell'allegato. Sono inoltre disponibili opzioni per effettuare una registrazione dello schermo, aggiungere altre schermate o allegare file. Per inviare il rapporto, toccare l'icona del piano carta in alto a destra nel modulo.


![Segnala bug](assets/newbug.png)

**Per suggerire un miglioramento**:

Toccate l’opzione e scegliete una sottocategoria per il suggerimento. Nel modulo dei suggerimenti, fornite il vostro indirizzo e-mail nel campo superiore e la descrizione del bug nel campo sottostante. Al messaggio viene automaticamente collegata una schermata delle informazioni dell'account, ma è possibile eliminarla toccando la **X** nell'immagine dell'allegato. Sono inoltre disponibili opzioni per effettuare una registrazione dello schermo, aggiungere altre schermate o allegare file. Per inviare il suggerimento, toccate l'icona del piano carta in alto a destra nel modulo.

**Per porre una domanda**:

Toccate l’opzione e fornite il vostro indirizzo e-mail nel campo superiore e la domanda nel campo sottostante. Una schermata viene automaticamente collegata al messaggio, ma è possibile eliminarla toccando la **X** nell'immagine dell'allegato. Sono inoltre disponibili opzioni per effettuare una registrazione dello schermo, aggiungere altre schermate o allegare file. Per inviare la domanda, toccate l'icona del piano carta in alto a destra nel modulo.
