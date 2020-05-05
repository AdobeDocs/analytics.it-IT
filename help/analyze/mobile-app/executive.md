---
description: Istruzioni per l'uso delle scorecard delle dashboard.
title: Guida esecutiva delle dashboard di Adobe Analytics
translation-type: tm+mt
source-git-commit: abb781413559c2da872ecfe3dbc9eb6df1cdbb74

---


# Dashboard di Adobe Analytics: guida introduttiva per l&#39;utente esecutivo

>[!IMPORTANT]
>
>I dashboard di Adobe Analytics non vengono rilasciati ed è disponibile solo per il test beta tra i clienti invitati. Questa documentazione è destinata solo agli utenti della versione beta e non rappresenta la funzionalità completa della funzione. Se siete interessati a diventare un utente beta per questa caratteristica, si prega di contattare Ashok Gorrepati (gorrepati@adobe.com).

## Introduzione

Le dashboard di Adobe Analytics forniscono informazioni ovunque e in qualsiasi momento da Adobe Analytics.  L’app consente agli utenti di accedere a scorecard intuitive da dispositivi mobili. Le scorecard sono una raccolta di metriche chiave e di altri componenti presentati in un layout a tessere che puoi toccare per visualizzare raggruppamenti più dettagliati e rapporti sulle tendenze. I dashboard sono supportati sia sui sistemi operativi iOS che su quelli Android.

## Informazioni su questa guida

Questa guida è destinata ad aiutare gli utenti esecutivi a leggere e interpretare le scorecard nelle dashboard di Analytics. L’app consente agli utenti esecutivi di visualizzare una rappresentazione generale di importanti dati riassuntivi in modo semplice e veloce sui propri dispositivi mobili.

## Glossario dei termini

| Termine | Definizione |
|--- |--- |
| Consumatore | Utente esecutivo che visualizza metriche e conoscenze chiave provenienti da Analytics su un dispositivo mobile |
| Curatore | Persona esperta in materia di dati che trova e distribuisce le conoscenze provenienti da Analytics e configura le scorecard da mostrare al consumatore |
| Cura | L’atto di creare o modificare una scorecard mobile contenente metriche, dimensioni e altri componenti pertinenti per il consumatore |
| Scorecard | Una vista per dashboard contenente una o più sezioni |
| Tessera | Una rappresentazione di una metrica all’interno di una vista Scorecard |
| Raggruppamento | Una vista secondaria accessibile toccando una tessera nella scorecard. Questa vista mostra maggiori informazioni sulla metrica visualizzata sulla tessera e, opzionalmente, riporta informazioni su dimensioni di raggruppamento aggiuntive. |
| Intervallo date | Intervallo di date principale per il reporting dei dashboard |
| Intervallo date di confronto | L’intervallo date che viene confrontato con l’intervallo date primario |

## Ottenere la configurazione delle dashboard sul dispositivo

Per utilizzare le dashboard in modo efficace, è necessario che il curatore Scorecard vi aiuti a configurarlo. Questa sezione fornisce informazioni per aiutarti a effettuare la configurazione con l’assistenza del tuo curatore.

### Ottenere l’accesso

Per accedere alle scorecard nelle dashboard, assicurarsi che:

* Di avere un accesso valido ad Adobe Analytics
* Che il tuo curatore abbia creato correttamente le scorecard per dispositivi mobili e le abbia condivise con te

### Download e installazione di dashboard

Per scaricare e installare l’app, segui i passaggi relativi al sistema operativo del tuo dispositivo.

**Per dispositivi iOS:**

1. Click the following public link (It is also available in Analytics under **Tools** > **dashboards**):

   [Link iOS](https://testflight.apple.com/join/WtXMQxlI): `https://testflight.apple.com/join/WtXMQxlI`

   Dopo aver fatto clic sul link, viene visualizzata la seguente schermata di Testflight:

   ![Schermata di Testflight](assets/testflight1.png)

2. Toccare il link **Visualizza nell’App Store** sullo schermo per scaricare l’app Testflight.

3. Dopo aver installato l’app Testflight, trova e installa le dashboard di Adobe Analytics dall’interno di Testflight come mostrato di seguito:

   ![Schermata di Testflight](assets/testflight2.png)

**Per dispositivi Android:**

1. Tap the following Play Store link on the user&#39;s device (It is also available in Analytics under **Tools** > **dashboards**):


   [Android](https://play.google.com/apps/testing/com.adobe.analyticsmobileapp): `https://play.google.com/apps/testing/com.adobe.analyticsmobileapp`

   Dopo aver toccato il link, toccare il link Diventa un tester nella seguente schermata:

   ![Schermata del Play Store](assets/play.png)

2. Toccare il link **scarica su Google Play** nella seguente schermata:

   ![Link di download](assets/playnext.png)

## Utilizzare le dashboard

Per utilizzare le dashboard:

1. Accedi all’app. La schermata di accesso verrà visualizzata all&#39;avvio delle dashboard. Segui le istruzioni utilizzando le tue credenziali esistenti di Adobe Analytics. Supportiamo sia gli ID Adobe che quelli Enterprise/Federated.

   ![Sequenza di accesso](assets/signseq.png)

2. Scegli un’azienda. After you sign into dashboards, the **Choose a company** screen appears. Questa schermata elenca le aziende di accesso a cui appartieni. Tocca il nome dell’azienda associata alla scorecard condivisa con te.

3. L’elenco delle scorecard mostra quindi tutte le scorecard che sono state condivise con te. Tocca la scorecard che desideri visualizzare.

   ![Scegliere un’azienda](assets/accesscard.png)

   *Nota: se effettui l’accesso e vedi un messaggio che dice che non è stato condiviso nulla, verifica quanto segue con il tuo curatore:*

   * *Riesci ad accedere alla giusta istanza di Analytics*
   * *La scorecard è stata condivisa con te*

      ![Niente di condiviso](assets/nothing.png)

4. Esamina come appaiono le tessere nella scorecard.

   ![Informazioni sulle tessere](assets/newexplain.png)

   Ulteriori informazioni sulle tessere:

   * La granularità dei grafici sparkline dipende dalla lunghezza dell’intervallo date:
   * Un giorno mostra una tendenza oraria
   * Più di un giorno e meno di un anno mostra una tendenza giornaliera
   * Un anno o più mostra una tendenza settimanale
   * La formula della variazione percentuale del valore è metrica totale (intervallo date attuale) – metrica totale (intervallo date di confronto)/metrica totale (intervallo date di confronto).
   * È possibile trascinare lo schermo verso il basso per aggiornare la scorecard.

5. Toccare una tessera per mostrare come funziona un raggruppamento dettagliato della tessera.

   ![Vista Raggruppamento](assets/sparkline.png)


6. Per modificare gli intervalli date per la tua scorecard:

   ![Modificare le date](assets/changedate.png)

   *Nota: è possibile modificare allo stesso modo anche gli intervalli date all’interno della vista Raggruppamento mostrata sopra.*

   A seconda dell’intervallo che si tocca (**Giorno**, **Settimana**, **Mese** o **Anno**), si vedranno due opzioni per gli intervalli date: l’intervallo di tempo attuale o quello immediatamente prima. Toccare una di queste due opzioni per selezionare il primo intervallo. Nell’elenco **CONFRONTA CON**, toccare una delle opzioni che vengono mostrate per confrontare i dati di questo periodo di tempo con il primo intervallo date selezionato. Toccare **Fine** in alto a destra dello schermo. Il campo **Intervalli date** e le tessere della scorecard vengono aggiornati con i nuovi dati di confronto dei nuovi intervalli selezionati.

7. Ricevere gli aggiornamenti delle scorecard. Se una scorecard non include tutte le metriche o i raggruppamenti che potrebbero interessarti, contatta il tuo team di Analytics per far aggiornare la scorecard. Una volta aggiornata, è possibile trascinare giù la scheda sullo schermo per aggiornarla e caricare i dati aggiunti di recente.



8. Lasciare un feedback. Per lasciare un feedback:

   1. Toccate l&#39;icona utente in alto a destra della schermata delle dashboard.
   2. Nella schermata **Il mio account**, toccare l’opzione **Feedback**.
   3. Toccare per visualizzare le opzioni per lasciare un feedback.
   ![Lasciare un feedback](assets/feedback.png)
   ![Opzioni del feedback](assets/feedback_option.png)


**Per segnalare un bug**:

Toccare l’opzione e scegliere una sottocategoria del bug. Nel modulo per la segnalazione di un bug, fornisci il tuo indirizzo e-mail nel campo superiore e la tua descrizione del bug nel campo sotto di esso. Al messaggio viene automaticamente allegata una schermata con le informazioni del tuo account, ma puoi cancellarla, se lo desideri, toccando la **X** nell’immagine allegata. Ci sono anche delle opzioni per effettuare una registrazione dello schermo, aggiungere altre schermate o allegare file. Per inviare la segnalazione, toccare l’icona dell’aeroplano di carta in alto a destra del modulo.


![Segnalare un bug](assets/newbug.png)

**Per suggerire un miglioramento**:

Toccare l’opzione e scegliere una sottocategoria del suggerimento. Nel modulo di suggerimento, fornisci il tuo indirizzo e-mail nel campo superiore e la tua descrizione del bug nel campo sotto di esso. Al messaggio viene automaticamente allegata una schermata con le informazioni del tuo account, ma puoi cancellarla, se lo desideri, toccando la **X** nell’immagine allegata. Ci sono anche delle opzioni per effettuare una registrazione dello schermo, aggiungere altre schermate o allegare file. Per inviare il suggerimento, toccare l’icona dell’aeroplano di carta in alto a destra del modulo.

**Per fare una domanda**:

Tocca l’opzione e fornisci il tuo indirizzo e-mail nel campo superiore e la tua domanda nel campo sotto di esso. Al messaggio viene automaticamente allegata una schermata, ma puoi cancellarla, se lo desideri, toccando la **X** nell’immagine allegata. Ci sono anche delle opzioni per effettuare una registrazione dello schermo, aggiungere altre schermate o allegare file. Per inviare la domanda, toccare l’icona dell’aeroplano di carta in alto a destra del modulo.
