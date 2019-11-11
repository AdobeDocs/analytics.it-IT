---
description: AppMeasurement 3.x per iOS
seo-description: Documentazione precedente per AppMeasurement 3.x per iOS
seo-title: AppMeasurement 3.x per iOS
solution: Analytics
subtopic: Segnalibri
title: AppMeasurement 3.x per iOS
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 4907b2930d894525b93b02f743c095f824a61a3b

---


# AppMeasurement 3.x per iOS

*Nota: Questo documento contiene informazioni legacy per le versioni precedenti di AppMeasurement, in particolare per le versioni 3.x per iOS.
Per informazioni sull’implementazione AppMeasurement corrente, consultate[Informazioni su AppMeasurement per Javascript](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).*

*Ultimo aggiornamento 15/3/2018 AppMeasurement 3.x per iOS*

Adobe AppMeasurement per iOS consente di misurare le applicazioni native per iPhone e iPad in Adobe Experience Cloud.

Questa guida è divisa in due sezioni: una sezione per l'analista con esperienza Adobe Analytics e una sezione per lo sviluppatore iOS con esperienza di sviluppo di app mobili.

**Versioni** supportate: iOS 4.3 o successivo.

**Scarica la libreria** Le istruzioni e i collegamenti per il download per tutte le piattaforme mobili AppMeasurement sono disponibili nella pagina Measuring and OptimizingMobile Applications in Developer Connection. Per scaricare le librerie è necessario disporre di un account Developer Connection gratuito o di un login di reporting e analisi. I collegamenti per il download non vengono visualizzati finché non avete effettuato l'accesso.

## Avvio rapido di Analytics

Questa sezione illustra come implementare la libreria iOS e aggiungere il codice necessario per un’implementazione standard. I passaggi sono inclusi per mostrare come inviare eventi personalizzati e altri dati.

Come analista, devi abilitare i rapporti per l’applicazione mobile per la suite di rapporti. Se hai altre metriche da acquisire, devi fornire allo sviluppatore una descrizione delle variabili di dati di contesto che devono essere inviate dall'applicazione. Ad esempio, per raccogliere un nome utente dopo l’accesso, potete fare in modo che lo sviluppatore imposti il nome utente in una variabile di dati contestuali denominata `myco.username`.

### Abilitare i rapporti delle applicazioni mobili in Analytics

Analytics fornisce un'interfaccia per abilitare il tracciamento del ciclo di vita delle app mobili. Questa mappatura consente ad Analytics di generare automaticamente i rapporti sulle applicazioni mobili.

1. Apri Admin Console &gt; Suite di rapporti &gt; Modifica impostazioni &gt; Gestione mobile &gt; Generazione rapporti applicazioni mobili.
1. Fate clic su Abilita tracciamento del ciclo di vita delle app mobili.

Le metriche del ciclo di vita vengono ora acquisite e i rapporti sulle applicazioni mobili vengono visualizzati nel menu Rapporti di SiteCatalyst.

### Acquisire ulteriori metriche utilizzando le regole di elaborazione

Se l'implementazione invia eventi e dimensioni aggiuntivi utilizzando i dati contestuali, devi configurare le regole di elaborazione per acquisire tali dati.

Prima di creare le regole di elaborazione, è necessario che un utente all'interno dell'organizzazione diventi certificato. Per ulteriori informazioni, vedere la Guida sulle regole di elaborazione.

Dopo l'abilitazione delle regole di elaborazione, l'esempio Copia una variabile dati di contesto illustra il processo necessario per mappare i dati di contesto.

### (Facoltativo) Attiva tracciamento offline

Se intendi memorizzare gli hit quando il dispositivo è offline, le marche temporali devono essere abilitate nella suite di rapporti.

Dopo aver attivato il tracciamento offline, tutti gli hit devono essere contrassegnati con marca temporale o non vengono raccolti. Se i dati AppMeasurement vengono inviati a una suite di rapporti che raccoglie anche dati da JavaScript, potrebbe essere necessario impostare una suite di rapporti distinta per i dati mobili per evitare la perdita di dati, o includere una marca temporale personalizzata negli hit JavaScript utilizzando la variabile s.timestamp.

Se non sei sicuro se le marche temporali sono abilitate nella suite di rapporti, contatta l’Assistenza clienti.

## Guida introduttiva per sviluppatori

Questa sezione descrive i passaggi necessari per implementare la libreria iOS e iniziare a inviare i dati di misurazione, tra cui:

* Ottenere la libreria
* Aggiungere la libreria al progetto
* Parola rapida su TrackingHelper
* Implementazione


### Ottenere la libreria

Per scaricare la libreria Android, visita Misurazione e ottimizzazione di applicazioni mobili su Developer Connection. Dopo aver decompresso il file di download, si avranno i seguenti componenti software:

* admsAppLibrary.jar: Libreria progettata per l’uso con dispositivi e simulatori Android. Richiede Android 2.0 o versione successiva.
* Esempi\TrackingHelper.java: Classe opzionale progettata per tenere il codice di tracciamento separato dalla logica dell'applicazione.

### Aggiungere la libreria al progetto

1. Nell’IDE Eclipse, fai clic con il pulsante destro del mouse sul nome del progetto.
1. Seleziona Percorso creazione &gt; Aggiungi archivi esterni.
1. Seleziona `admsAppLibrary.jar`.
1. Fai clic su Apri.
1. Fai di nuovo clic con il pulsante destro del mouse sul progetto, quindi seleziona Percorso creazione &gt; Configura percorso build.
1. Fare clic sulla scheda Ordine ed esportazione.
1. Assicurarsi che `admsAppLibrary.jar` sia selezionato.

L’applicazione può importare le classi/interfacce dalla libreria admsAppLibrary.jar mediante import com.adobe.ADMS.*;

### Aggiungere le autorizzazioni dell'app

La libreria AppMeasurement richiede le seguenti autorizzazioni per inviare dati e registrare le chiamate di tracciamento offline:

* INTERNET
* ACCESS_NETWORK_STATE

To add these permissions, add the following lines to your AndroidManifest.xml file (in the application project directory):
`<uses-permission android:name="android.permission.INTERNET" />`
`<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />`

### Parola rapida su TrackingHelper

L’SDK include un’ulteriore classe opzionale, denominata TrackingHelper. TrackingHelper consente di separare il codice di misura dalla logica dell’applicazione.

Considerate l'esempio seguente: Nell'applicazione, si desidera inviare un evento che tenga traccia di ogni login. Potreste aggiungere il seguente codice direttamente dopo il codice di accesso per inviare l’evento (non preoccupatevi dei dettagli del codice, arriveremo a questi più tardi):

```
Hashtable<String, Object> contextData = new Hashtable<String, Object>();
contextData.put("username", "username_value");
measure.trackEvents("event1", contextData);
```

Questo approccio diretto va bene, ma non preferireste inserire questo codice da qualche altra parte, quindi è fuori strada mentre state sviluppando la vostra applicazione? TrackingHelper è che "altrove". All’interno di TrackingHelper, puoi inserire questo codice in un metodo denominato trackLogonEvent:

```
public static void trackLogonEvent (String username_value) {
Hashtable<String, Object> contextData = new Hashtable<String, Object>();
contextData.put("username", username_value);
measure.trackEvents("event1", contextData);
}
```

Ora, nel codice dell’applicazione, puoi tracciare un evento di accesso con una semplice chiamata a trackLogonEvent:

TrackingHelper.trackLogonEvent("username");

La chiamata di misura nel codice dell'applicazione è ridotta a una sola riga. Inoltre, se è necessario modificare la logica di misurazione sottostante, è necessario aggiornare solo TrackingHelper. Se un altro sviluppatore aggiunge al codice, può usare i metodi semplificati definiti senza seguire un corso di arresto anomalo nella libreria AppMeasurement.

È consigliabile utilizzare TrackingHelper per per le nuove implementazioni, anche se la configurazione richiede un minuto o due in più. I passaggi rimanenti di questa guida illustrano i passaggi necessari per impostare TrackingHelper e iniziare a inviare i dati di misurazione.

Assicuratevi di copiare TrackingHelper.java in una directory che contiene i file di classe per l'app, quindi sostituite il nome del pacchetto nella parte superiore del file in modo che corrisponda alla struttura del pacchetto (com.company.application). Se preferisci implementare senza TrackingHelper, puoi trovare diversi esempi all’interno di TrackingHelper che puoi copiare nell’applicazione.

### Implementazione

1. Apri TrackingHelper.java e aggiorna TRACKING_RSID e TRACKING_SERVER con il tuo ID suite di rapporti e il server di tracciamento. Ad esempio:

   ```
   private static final String TRACKING_RSID = "rsid";
   private static final String TRACKING_SERVER = "server";
   ```

   Questi valori sono obbligatori e devono essere corretti oppure la misurazione non funzionerà. Se non siete sicuri di questi valori, chiedete al vostro esperto SiteCatalyst.

2. Individua il metodo configureAppMeasurement. In questa area è possibile abilitare SSL, abilitare il tracciamento offline e apportare altre modifiche globali alla configurazione. Per il momento, rimuovete il commento dalla riga per abilitare debugLogging fino a quando le operazioni funzionano come previsto.

3. Aggiungi una chiamata per configurareAppMeasurement dall'attività principale nell'applicazione.

```
@Override
public void onCreate(Bundle savedInstanceState) {
super.onCreate(savedInstanceState);
setContentView(R.layout.main);
TrackingHelper.configureAppMeasurement(this);
}
```

È tutto il codice necessario per iniziare a tracciare le metriche personalizzate. Tuttavia, con alcune righe di codice aggiuntive, puoi abilitare il tracciamento del ciclo di vita per inviare automaticamente le metriche del ciclo di vita, compresi avvii, aggiornamenti, arresti e utenti giornalieri e mensili.

La libreria AppMeasurement effettua il sollevamento di tutti i costi, è sufficiente aggiungere due chiamate di metodo a ciascuna classe Activity dell'applicazione.

### (Consigliato) Tenere traccia degli eventi del ciclo di vita

Quando il tracciamento del ciclo di vita è abilitato, ogni volta che l’app viene avviata, viene inviato un singolo hit per tenere traccia di installazioni, aggiornamenti, giorni coinvolti e altre metriche del ciclo di vita.

Per avviare il tracciamento degli eventi del ciclo di vita, nell'app aggiungi chiamate ai metodi onResume() e onPause() in ogni attività all'interno dell'applicazione, come illustrato nell'esempio seguente. Consigliamo inoltre di passare l’attività o il servizio come oggetto contestuale anziché come contesto Applicazione globale.

```
@Override
protected void onResume() {
super.onResume();
TrackingHelper.startActivity(this);
}
@Override
protected void onPause() {
super.onPause();
TrackingHelper.stopActivity();
}
```

Tutto qui. Ora hai implementato il tracciamento del ciclo di vita di base nella tua app Android. Dopo che SiteCatalyst è stato configurato da Web Analyst per elaborare le metriche AppMeasurement per il reporting, la suite di rapporti SiteCatalyst conterrà le metriche del ciclo di vita predefinite.

Come proseguire:

* (Facoltativo) Tracciare Eventi Personalizzati. Aggiungi metodi personalizzati a TrackingHelper per per tenere traccia di tutti gli eventi da misurare nell’applicazione. Potete aggiungere metodi per tenere traccia di accessi, acquisti in-app e così via.
* (Facoltativo) Tracciare gli stati delle app. Lo stato di un'applicazione è simile alla visualizzazione di una pagina. In questa sezione viene illustrato come aggiungere un metodo personalizzato a TrackingHelper per tenere traccia dello stato di un’app.
* Avvio rapido misurazione video. Aggiungete del codice per tenere traccia delle metriche video, comprese le visualizzazioni video, il tempo totale riprodotto e i video più popolari.

### (Facoltativo) Tracciare eventi personalizzati

Gli eventi personalizzati sono metriche di successo univoche per l'applicazione in uso. Potete inviare un evento personalizzato quando un utente accede, avvia un acquisto in-app o fa clic su un collegamento alla pagina Facebook. La classe helper di tracciamento contiene un esempio che mostra come tracciare un evento personalizzato. Potete utilizzare questo metodo come modello per aggiungere altri metodi di tracciamento degli eventi.

In TrackingHelper.java, definisci un metodo di tracciamento evento personalizzato:

```
public static void trackCustomEvents () {
Hashtable<String, Object> contextData = new Hashtable<String, Object>();
contextData.put("contextKey", "value");
measure.trackEvents("event1, event2", contextData);
}
```

In tutto il codice, potete chiamare questo metodo per monitorare un evento personalizzato:

`TrackingHelper.trackCustomEvents();`

Utilizzate questo processo per aggiungere tutti i metodi di tracciamento degli eventi necessari. Una Parola rapida in TrackingHelper contiene un metodo di esempio per tracciare un evento di login.

### (Facoltativo) Tracciare gli stati delle app

La classe helper di tracciamento contiene anche un esempio che mostra come monitorare lo stato di un'applicazione. Il tracciamento di uno stato personalizzato è molto simile al tracciamento di un evento. L’unica differenza è l’utilizzo del metodo trackAppState invece di trackEvents.

```
measure.trackAppState("name", contextData);
```

Da un punto di vista di reporting, trackAppState incrementa le visualizzazioni di pagina, mentre trackEvents no.

## Avvio rapido misurazione video

La misurazione dei video è descritta nella guida Measuring Video in SiteCatalyst (Misurazione dei video in SiteCatalyst). Il processo generale da seguire per la misurazione del video è molto simile per tutte le piattaforme AppMeasurement. Questa sezione di avvio rapido fornisce una panoramica di base delle attività di sviluppo, con esempi di codice.

La stessa libreria, admsAppLibrary.jar, viene utilizzata per il tracciamento di applicazioni e video. La documentazione fa riferimento a questi metodi come modulo multimediale per la coerenza tra le diverse piattaforme.

Prima di utilizzare il modulo multimediale è necessario configurare un'istanza di misurazione.

Per implementare il tracciamento video su Android, effettuate le seguenti operazioni:

* Mappare gli eventi del lettore sulle variabili SiteCatalyst
* Configurare pietre miliari, segmenti e frequenza di chiamata
* Tracciare gli eventi del lettore

### Mappare gli eventi del lettore sulle variabili SiteCatalyst

Per configurare la misurazione video, dovete mappare gli eventi SiteCatalyst e le eVar selezionati per il tracciamento video sulle variabili dei dati contestuali. Per ulteriori informazioni, consultate Configurazione video SiteCatalyst.

Il Web Analyst deve fornire un foglio di lavoro di implementazione video contenente un elenco delle variabili SiteCatalyst configurate per la ricezione dei dati video:

* Nome video (eVar): eVar2
* Nome video (Prop): prop2
* Segmenti (eVar): eVar3
* Tipo di contenuto (eVar): eVar1
* Ora video (evento): event3
* Visualizzazioni video (evento): event1
* Completamento video (evento): event7
* Viste segmento video (evento): event2

1. Aggiungete il codice seguente dopo il codice aggiunto in Implementazione, sostituendo la variabile SiteCatalyst selezionata con l’esempio nel codice:

   ```
   ADMS_MediaMeasurement mediaMeasure = ADMS_MediaMeasurement.sharedInstance();
   Hashtable<String, Object> contextDataMapping = new Hashtable<String, Object>();
   contextDataMapping.put("a.media.name", "eVar2,prop2");
   contextDataMapping.put("a.media.segment", "eVar3");
   contextDataMapping.put("a.contentType", "eVar1"); //note that this is not in the .media
   namespace
   contextDataMapping.put("a.media.timePlayed", "event3");
   contextDataMapping.put("a.media.view", "event1");
   contextDataMapping.put("a.media.segmentView", "event2");
   contextDataMapping.put("a.media.complete", "event7");
   mediaMeasure.ContextDataMapping = contextDataMapping;
   ```

2. Configurare le pietre miliari, i segmenti e la frequenza delle chiamate.

3. Tracciare gli eventi del lettore.


### Configurare pietre miliari, segmenti e frequenza di chiamata

Le pietre miliari consentono di inviare un evento quando viene raggiunto uno specifico punto del video. I segmenti consentono di dividere il video in sezioni per un tracciamento più dettagliato. La frequenza delle chiamate consente di inviare chiamate di misurazione con il tempo visualizzato a intervalli specifici. Per ulteriori informazioni, consultate Metriche video.

### Mappe

È possibile definire le fasi cardine in base a una percentuale di lunghezza totale o in base ai secondi trascorsi. In questo esempio vengono definiti i punti cardine come percentuale della lunghezza totale. Per un video di 2 minuti, il codice seguente invia eventi milestone a 30 secondi, 60 secondi e 90 secondi.

```
Hashtable<String, Object> milestoneMapping = new Hashtable<String, Object>();
milestoneMapping.put("25", "event4");
milestoneMapping.put("50", "event5");
milestoneMapping.put("75", "event6");
contextDataMapping.put("a.media.milestones", milestoneMapping);
```


### Mappa scostamento

In questo esempio vengono definiti i punti cardine in secondi trascorsi dall’inizio del video. Per un video di 2 minuti, il seguente codice invia eventi milestone a 20 secondi, 40 secondi e 60 secondi, indipendentemente dalla lunghezza totale del video.

```
Hashtable<String, Object> offsetMilestoneMapping = new Hashtable<String, Object>();
offsetMilestoneMapping.put("20", "event8");
offsetMilestoneMapping.put("40", "event9");
offsetMilestoneMapping.put("60", "event10");

contextDataMapping.put("a.media.offsetMilestones", offsetMilestoneMapping);
```

### Esempi

```
//get sharedInstance
ADMS_MediaMeasurement mediaMeasure = ADMS_MediaMeasurement.sharedInstance();

//Track By Milestones:
mediaMeasure.trackMilestones = "25,50,75";

// track Milestones & segmentByMilestones:
mediaMeasure.trackMilestones = "25,50,75";
mediaMeasure.segmentByMilestones = true;

// track by seconds:
mediaMeasure.trackSeconds = 15;

// track Milestones & segmentByMilestones & seconds:
mediaMeasure.trackMilestones = "25,50,75";
mediaMeasure.segmentByMilestones = true;
mediaMeasure.trackSeconds = 15;

// track offsetMilestones & segmentByOffsetMilestones:
mediaMeasure.trackOffsetMilestones = "15,30,45,60,75,90";
mediaMeasure.segmentByOffsetMilestones = true;

// track offsetMilestones:
mediaMeasure.trackOffsetMilestones = "5,15,45";
```

### Tracciare gli eventi del lettore

Per misurare i video, è necessario aggiungere codice che indichi al modulo multimediale quando si verificano eventi nel lettore (utilizzando i metodi open, play, stop e close). Quando un utente avvia la riproduzione di un video, è necessario chiamare il metodo di riproduzione in modo che il modulo multimediale inizi a contare i secondi visualizzati.

Se l’utente mette in pausa il video, è necessario chiamare stop per mettere in pausa il conteggio. Questa operazione viene in genere eseguita utilizzando i gestori di eventi esposti dal lettore.

Ad esempio:

Carica: Chiamata aperta e riproduzione

Pausa: Chiama stop. Ad esempio, se un utente mette in pausa un video dopo 15 secondi, chiama stop("Video1",15)

Buffer: Interrompi chiamata durante il buffer video. Chiama la riproduzione quando la riproduzione riprende.

Riprendi: Chiama il gioco. Ad esempio, quando un utente riprende un video dopo aver inizialmente riprodotto 15 secondi del video, chiama.play("Video1",15).

Cursore (cursore): Quando l’utente trascina il cursore del video, chiama stop. Quando l’utente rilascia il cursore del video, chiama play.

Fine: Chiama stop, poi chiudi. Ad esempio, alla fine di un video di 100 secondi, chiamate stop("Video1",100), quindi close("Video1").

A tal fine, è possibile definire quattro funzioni personalizzate che è possibile chiamare dai gestori eventi del lettore multimediale. I vari parametri passati in open, play, stop e close provengono dal lettore. Lo pseudocodice seguente illustra come eseguire questa operazione:

```
function startMovie(){
mediaMeasure.open(mediaName,mediaLength,mediaPlayerName);
playMovie();
}
/*Call on video resume from pause and slider release*/
function playMovie(){
mediaMeasure.play(mediaName,mediaOffset);
}
/*Call on video pause and slider grab*/
function stopMovie(){
mediaMeasure.stop(mediaName,mediaOffset);
}
/*Call on video end*/
function endMovie(){
stopMovie();
mediaMeasure.close(mediaName);
Video Measurement Quick Start 12
```

## Metriche del ciclo di vita

In questo foglio di lavoro sono elencate le metriche e le dimensioni misurate quando è abilitato il tracciamento automatico del ciclo di vita.

### Metriche e dimensioni del ciclo di vita

Una volta configurate, le metriche del ciclo di vita vengono inviate nei parametri dei dati contestuali ad Analytics, ai parametri a Target con ciascuna chiamata Mbox e come segnale a Gestione dell'audience. Analytics e Target usano lo stesso formato; Gestione dell'audience usa invece un prefisso diverso per ogni metrica.

Per Analytics, i dati contestuali inviati con ciascuna chiamata di tracciamento del ciclo di vita vengono catturati automaticamente e segnalati utilizzando la metrica o la dimensione indicata nella prima colonna, con le eccezioni indicate nella colonna della descrizione.

| Metrica | Contesto di Analytics | Descrizione del segnale di Audience Manager contestuale di Analytics | Parametro Data/Target |
|--- |--- |--- |--- |
| Primi avvii | a.InstallEvent | c_a_InstallEvent | Attivazione alla prima esecuzione dopo l'installazione (o reinstallazione). |
| Aggiornamenti | a.UpgradeEvent | c_a_UpgradeEvent | Attivazione alla prima esecuzione dopo gli aggiornamenti (ogni volta che cambia il numero di versione). |
| Utenti giornalieri coinvolti | a.DailyEngUserEvent | c_a_DailyEngUserEvent | Attivazione quando l'applicazione viene utilizzata in un giorno particolare. |
| Utenti mensili coinvolti | Utenti mensili coinvolti | a.MonthlyEngUserEvent | Attivazione quando l'applicazione viene utilizzata in un mese particolare. |
| Avvii | a.LaunchEvent | c_a_LaunchEvent | Attivazione a ogni esecuzione, compresi arresti anomali e installazioni. | Lanci attivati anche in caso di ripresa dopo il superamento del timeout della sessione del ciclo di vita. |
| Arresti anomali | a.CrashEvent | c_a_CrashEvent | Attivazione quando l'applicazione non termina correttamente. L'evento viene inviato all'avvio dell'applicazione dopo l'arresto (l'applicazione viene considerata in arresto se non si esegue il comando di uscita). |
| Lunghezza sessione precedente | a.PreviousSessionLength | Cc_a_PreviousSessionLength | Totale aggregato Durata sessione precedente in secondi. |

*Nota: Utenti **giornalieri coinvolti e utenti**mensili coinvolti ****non vengono memorizzati automaticamente in una metrica Analytics. Devi creare una regola di elaborazione che imposti un evento personalizzato per l’acquisizione di queste metriche.*

### Dimensioni

| Metrica | Dati contestuali di Analytics/Parametro di Target | Segnale Audience Manager Contesto Analisi | Descrizione |
|--- |--- |--- |--- |
| Data di installazione | a.InstallDate | c_a_InstallDate | Data del primo avvio dopo l'installazione. DD/MM/YYYY |
| Aggiornamenti | a.UpgradeEvent | c_a_UpgradeEvent | Attivazione alla prima esecuzione dopo gli aggiornamenti (ogni volta che cambia il numero di versione). |
| ID app | a.AppID | c_a_AppID | Memorizza il nome e la versione dell'applicazione nel seguente formato:`[AppName] [BundleVersion]`. Ad esempio, myapp 1.1. |
| Giorni dal primo utilizzo | a.DaysSinceFirstUse | c_a_DaysSinceFirstUse | Numero di giorni dalla prima esecuzione. |
| Utenti mensili coinvolti | Utenti mensili coinvolti | a.MonthlyEngUserEvent | Attivazione quando l'applicazione viene utilizzata in un mese particolare. |
| Avvii | a.LaunchEvent | c_a_LaunchEvent | Attivazione a ogni esecuzione, compresi arresti anomali e installazioni. | Lanci attivati anche in caso di ripresa dopo il superamento del timeout della sessione del ciclo di vita. |
| Arresti anomali | a.CrashEvent | c_a_CrashEvent | Attivazione quando l'applicazione non termina correttamente. L'evento viene inviato all'avvio dell'applicazione dopo l'arresto (l'applicazione viene considerata in arresto se non si esegue il comando di uscita). |
| Lunghezza sessione precedente | a.PreviousSessionLength | Cc_a_PreviousSessionLength | Totale aggregato Durata sessione precedente in secondi. |
| Giorni dall'ultimo utilizzo | a.DaysSinceLastUse | c_a_DaysSinceLastUse | Numero di giorni dall'ultimo utilizzo. |
| Giorno della settimana | a.DayOfWeek | c_a_DayOfWeek | Numero del giorno della settimana in cui è stata avviata l'app. |
| Ora del giorno | a.HourOfDay | c_a_HourOfDay | Misura l’ora in cui è stata avviata l’app. Formato numerico in 24 ore. Utilizzato per la suddivisione del tempo per determinare le ore di utilizzo di picco. |
| Versione sistema operativo | a.OSVersion | c_a_OSVersion | Versione sistema operativo. |
| Giorni dall'ultimo aggiornamento | a.DaysSinceLastUpgrade | c_a_DaysSinceLastUpgrade | Numero di giorni dalla modifica del numero di versione dell'applicazione. |
| Avvii dall'ultimo aggiornamento | a.LaunchesSinceUpgrade | c_a_LaunchesSinceUpgrade | Numero di avvii dalla modifica del numero di versione dell'applicazione. |
| Nome del dispositivo | a.DeviceName | c_a_DeviceName | Memorizza il nome del dispositivo. | iOS: stringa di due cifre separate da virgola che identifica il dispositivo iOS. Di norma il primo numero rappresenta la generazione del dispositivo e il secondo numero indica membri diversi della famiglia di dispositivi. Per un elenco dei nomi di dispositivi più comuni, consulta Versioni dei dispositivi iOS. |
| Nome gestore | a.CarrierName | c_a_CarrierName | Memorizza il nome del gestore del servizio mobile, così come viene fornito dal dispositivo. |
| Risoluzione | a.Resolution | c_a_Resolution | Larghezza x altezza in pixel reali |

*Nota:**Giorni dall'ultimo aggiornamento**,**Avvii dall'ultimo aggiornamento**e nome ****gestore non vengono memorizzati automaticamente in una variabile Analytics. You must create a processing rule to copy these values to an Analytics variable for reporting.*

## Dati contestuali

I dati contestuali sono il metodo preferito per inviare i dati dell'applicazione ai server di raccolta.

Invece di assegnare in modo esplicito i valori a prop ed eVar, potete utilizzare le variabili di dati di contesto per inviare coppie di valori di nome mappate in SiteCatalyst. In base a queste coppie di valori chiave, è possibile impostare eventi, copiare valori in eVar e prop ed eseguire istruzioni condizionali aggiuntive. In questo modo si evita di effettuare aggiornamenti del codice per supportare diverse configurazioni delle suite di rapporti.

Esistono due modi per inviare i dati contestuali con i metodi di tracciamento. Tutti i dati contestuali impostati direttamente sull'oggetto PersistentContextData vengono inviati con ciascuna chiamata. Puoi anche trasmettere i dati contestuali come parametro a una singola chiamata di tracciamento inviata solo con tale chiamata.

### Dati contestuali persistenti

I valori inseriti in Dati contestuali persistenti vengono inviati con ogni chiamata al server. Nell’esempio seguente, "key" e "value" vengono inviati con tutte le chiamate trackAppState:

```
Hashtable<String, Object> contextData = new HashTable<String,Object>();
contextData.put("key", "value");
measure.setPersistentContextData(contextData);
measure.trackAppState("state1");
measure.trackAppState("state2");
measure.trackAppState("state3");
```

### Dati contestuali per una singola chiamata

Per inviare dati contestuali per una singola chiamata, invia dati contestuali come parametro alla chiamata di tracciamento (trackAppState, trackEvents e così via).

Nell’esempio seguente, "key" e "value" vengono inviati con tutte e tre le chiamate trackAppState. Tuttavia, "key2" e "value2" vengono inviati solo con la seconda chiamata trackAppState:

```
Hashtable<String, Object> contextData = new HashTable<String,Object>();
contextData.put("key", "value");
measure.setPersistentContextData = contextData;
Hashtable<String, Object> contextDataState = new HashTable<String,Object>();
contextDataState.put("key2", "value2");
measure.trackAppState("state1");
measure.trackAppState("state2", contextDataState);
measure.trackAppState("state3");
```

## Variabili di configurazione

Le seguenti variabili sono impostate quando l’applicazione viene avviata:

*Nota: Tutte le variabili di configurazione sono facoltative tranne ReportSuiteID e trackingServer.*

**Istanza condivisa**

Prima di effettuare chiamate di misurazione, è necessario recuperare un'istanza della libreria per ogni metodo che si chiama nella libreria delle misurazioni:

```
ADMS_Measurement measure = ADMS_Measurement.sharedInstance(((Activity)
context).getApplication());
```

*Nota: Le variabili di configurazione sono private. Utilizzare i metodi get e set per modificare questi valori.*

### Variabili di configurazione

**reportSuiteIDs**: (Obbligatorio) La suite di rapporti o le suite di rapporti (tag per più suite) che desideri monitorare. Per eseguire il tracciamento su più suite di rapporti, passa un elenco delimitato da virgole dei nomi di ciascuna suite di rapporti.

Non puoi ignorare questa variabile per una singola chiamata, devi modificare il valore persistente.

Sintassi:

```
String getReportSuiteIDs()
void setReportSuiteIDs(String reportSuiteIDs)
```

Esempi:

`measure.setReportSuiteIDs("rsid");`

Assegnazione di tag a più suite:
`measure.setReportSuiteIDs("rsid1, rsid2");`

**trackingServer**: (Obbligatorio) Identifica il server di raccolta.

Questa variabile deve essere compilata con il dominio del server di tracciamento, senza il prefisso del protocollo "http://" o "https://". Il prefisso del protocollo viene gestito automaticamente dalla libreria, in base alla variabile ssl.

Se ssl è true, viene eseguita una connessione sicura al server. Se ssl è false, viene eseguita una connessione non sicura.

Non puoi ignorare questa variabile per una singola chiamata, devi modificare il valore persistente.

Sintassi:

```
String getTrackingServer()
void setTrackingServer(String trackingServer)
```

Esempi:

`measure.setTrackingServer("metrics.corp1.com");`

**visitorID**: Predefinito: uuidIdentificatore univoco per ogni visitatore. Se non imposti un visitorID personalizzato, viene generato un visitorID univoco.

Consigliamo di utilizzare l’ID predefinito a meno che non disponiate di un caso d’uso specifico per impostare l’ID visitatore. L’impostazione di un visitorID personalizzato può causare visite duplicate quando si utilizza il tracciamento del ciclo di vita. Per evitare questo problema, imposta l’ID visitatore prima di configurare la misurazione dell’app.

**set** di caratteri: Il valore predefinito è UTF-8

Sintassi:

```
String getCharSet()
void setCharSet(String charSet)
```

Esempi:
`[measure.setCharacterSet("UTF-8");`

**currencyCode**:Default è none (viene utilizzato il valore definito per la suite per report)

Il Codice valuta utilizzato per gli acquisti o gli eventi di valuta tracciati nell'applicazione Android.

Sintassi:

```
String getCurrencyCode()
void setCurrencyCode(String currencyCode)
```

Esempi:
`measure.setCurrencyCode("USD");`

**lifecycleSessionTimeout**: Il valore predefinito è 5 minuti

Specifica l’intervallo di tempo, in secondi, che deve trascorrere tra un avvio dell’app e quello successivo affinché questo sia considerato come una nuova sessione. Il timeout viene applicato anche quando l’applicazione viene lasciata in background e poi riattivata. Il tempo durante il quale l’app rimane in background non viene incluso nella durata della sessione.

Sintassi:

```
int getLifecycleSessionTimeout()
void setLifecycleSessionTimeout(int sessionLength)
```

Esempi:

`measure.setLifecycleSessionTimeout(600); //10 minute session`

**ssl**: Il valore predefinito è false

Abilita (true) o disabilita (false) l’invio dei dati di misurazione tramite SSL (HTTPS). Non puoi ignorare questa variabile per una singola chiamata, devi modificare il valore persistente.

Sintassi:

`void setSSL(boolean ssl)`

Esempi:

`measure.setSSL(true);`

**debugLogging** Valore predefinito false

Abilita (true) o disabilita (false) la visualizzazione delle informazioni di debug e la versione della libreria nella console di output. Per impostazione predefinita, questa variabile è impostata su false. Non puoi ignorare questa variabile per una singola chiamata, devi modificare il valore persistente.

Sintassi:

`void setDebugLogging(boolean debugLogging)`

Esempi:

`measure.setDebugLogging(true);`

## Variabili di tracciamento

**Istanza condivisa**

Prima di effettuare chiamate di misurazione, è necessario recuperare un'istanza della libreria per ogni metodo che si chiama nella libreria delle misurazioni:

```
ADMS_Measurement measure = ADMS_Measurement.sharedInstance(((Activity)
context).getApplication());
```

*Nota: Le variabili di configurazione sono private. Utilizzare i metodi get e set per modificare questi valori.*

### Variabili di tracciamento persistenti

**Evar**: Imposta l'eVar specificata sul valore fornito. L'eVar viene inviato con tutte le chiamate di tracciamento finché non viene cancellato impostandolo su una stringa vuota o chiamando le variabili di cancellazione.

Sintassi:

`void setEvar(int evarNum, String evarValue)`

Esempio:
`measure.setEvar(1, "value");`

**Prop**: Imposta la proprietà specificata sul valore fornito. Il prop viene inviato con tutte le chiamate di tracciamento finché non viene cancellato impostandolo su una stringa vuota o chiamando clearVars.

Sintassi:

`void setProp(int propNum, String propValue)`

Esempio:

`measure.setProp(1, "value");`

**Asciugatore**: Imposta la variabile corrispondente specificata sul valore fornito. La variabile dell'erede viene inviata con tutte le chiamate di tracciamento finché non viene cancellata impostandola su una stringa vuota o chiamando clearVars.

Sintassi:

`void setHier(int hierNum, String hierValue)`

Esempio:

`measure.setHier(1, "value");`


**ListVar**: Imposta la listVar specificata sul valore fornito. ListVar viene inviato con tutte le chiamate di tracciamento finché non viene cancellato impostandolo su una stringa vuota o chiamando clearVars.

Sintassi:

`void setListVar(int listNum, String listValue)`

Esempio:

`measure.setListVar(1, "value");`

**purchaseID**: L’ID acquisto viene utilizzato per impedire che un ordine venga conteggiato più volte da SiteCatalyst.

Ogni volta che l’evento di acquisto viene utilizzato sul sito, devi assegnare a questo acquisto un ID univoco utilizzando la variabile purchaseID.

`measure.setPurchaseID("unique_id");`

**transactionID**: Origini dati integrazione utilizzano un ID transazione per collegare i dati offline a una transazione online (come un lead o un acquisto generato online).

Ogni ID transazione univoco inviato ad Adobe viene registrato in preparazione del caricamento di informazioni offline su tale transazione da Origini dati.

`measure.setTransactionID("unique_id");`

**appState**: (nome pagina)Il valore fornito per lo stato dell'app viene memorizzato nella variabile nome pagina.

`measure.setAppState("state");`

**canale**: measurement.setChannel("mobile");

**appSection**: Il valore fornito per la sezione app è memorizzato nella variabile server.

Sintassi:

`void setAppSection(String Section)`

Esempio:
`measure.setAppSection("news");`

**campagna**

Sintassi:

`void setCampaign(String Campaign)`

Esempio:

`measure.setCampaign("112233");`

**products**

Sintassi:

```
void setProducts(String Products)
// example Products string: Category;Product[,Category;Product]
```

Esempio:

`measure.setProducts("Running;Shoe");`

**events**

Sintassi:

`void setEvents(String Event) //comma-delimited list`

Esempio:

`measure.setEvents("event1, event2");`

**geoState**

Sintassi:

`void setGeoState(String GeoState)`

Esempio:

`measure.setGeoState("UT");`

**geoZip**

Sintassi:

`void setGeoZip(String GeoZip)`

Esempio:

`measure.setGeoZip("12345");`

**Dati** contestuali persistenti:I valori inseriti in Dati contestuali persistenti vengono inviati con ogni chiamata al server. Per inviare dati di contesto per una singola chiamata, invia una tabella di hash contextData come parametro alla chiamata di tracciamento (trackAppState, trackEvents e così via).

Esempio:

```
Hashtable contextData = new Hashtable<String, Object>();
contextData.put("key", "value");
measure.setPersistentContextData(contextData);
```

Consulta Dati contestuali.

**linkTrackVars**: Elenco delimitato da virgole di nomi di variabili che limitano il set corrente di variabili per il tracciamento dei collegamenti. Se linkTrackVars non è definito, AppMeasurement per Android invia tutte le variabili definite con una chiamata trackLink.

Sintassi:

`void setLinkTrackVars(String Vars) //comma-delimited list`

Esempio:

`measure.setLinkTrackVars("eVar1, prop1");`

**linkTrackEvents**: Elenco delimitato da virgole di eventi che limitano il set corrente di eventi per il tracciamento dei collegamenti. Se linkTrackEvents non è definito, AppMeasurement per Android invia tutti gli eventi con una chiamata trackLink.

Sintassi:

`void setLinkTrackEvents(String Events) //comma-delimited list`

Esempio:

`measure.setLinkTrackEvents("event1, event2");`

## Metodi

Questa sezione contiene un elenco dei metodi forniti dalla libreria Android.

**Istanza condivisa**

Prima di effettuare chiamate di misurazione, è necessario recuperare un'istanza della libreria per ogni metodo che si chiama nella libreria delle misurazioni:

```
ADMS_Measurement measure = ADMS_Measurement.sharedInstance(((Activity)
context).getApplication());
```

### Configurazione iniziale

Questo metodo configura le variabili richieste e deve essere chiamato prima di altri metodi.

**configureMeasurement**: Questo metodo viene utilizzato per configurare i due parametri necessari per avviare la misurazione dell’applicazione. È necessario impostare i valori reportSuiteIDs e trackingServer sull'oggetto di misurazione utilizzando questo metodo prima di inviare chiamate server.

Sintassi:

`void configureMeasurement(String reportSuiteIDs, String trackingServer)`

Esempi:

`measure.configureMeasurement("my_rsid", "my_tracking_server");`

### Tracciamento evento e stato

Si tratta dei metodi principali utilizzati per tenere traccia degli eventi personalizzati e degli stati dell'app.

**trackAppState**: Questo è il modo consigliato per monitorare gli stati dell'applicazione nell'applicazione. Il valore fornito in appState viene visualizzato come variabile del nome della pagina della chiamata al server. È necessario fornire la stringa appState per ogni chiamata, perché non viene trasferita alla chiamata successiva.

I dati contestuali inviati con questa chiamata vengono aggiunti a qualsiasi valore in persistentContextData e inviati con la chiamata. Solo i valori impostati in persistentContextData rimangono per la chiamata successiva.

Sintassi:

`void trackAppState(string AppStateName)`

Esempi:

`measure.trackAppState("state");`

```
Hashtable contextData = new Hashtable<String, Object>();
contextData.put("key", "value");
measure.trackAppState("state", contextData);
```

**trackEvents**: Questo è il metodo consigliato per tenere traccia degli eventi nell’applicazione. trackEvents è simile a trackAppState, ma invia eventi invece dei nomi di pagina. Gli eventi vengono forniti come stringa delimitata da virgole. La stringa eventi deve essere specificata per ogni chiamata, poiché non viene trasferita alla chiamata successiva.

Questo metodo esegue una chiamata sottostante a trackLinkURL in cui linkURL è impostato su nil, linkType è impostato su "o" e linkName viene popolato con l’ID applicazione.

Ciò significa che i collegamentiTrackVars e linkTrackEvents si applicano alle chiamate a trackEvents.

I dati contestuali inviati con questa chiamata vengono aggiunti a qualsiasi valore in persistentContextData e inviati con la chiamata. Solo i valori impostati in persistentContextData rimangono per la chiamata successiva.

Sintassi:

`void trackEvents(string Events)`

Esempi:

`measure.trackEvents("event1");`

```
Hashtable<String, Object> contextData = new HashTable<String,Object>();
contextData.put("key", "value");
measure.trackEvents("event1", contextData);
```

**Importa nota se utilizzi il metodo trackLink**

trackEvents effettua una chiamata sottostante a trackLink, dove linkURL è impostato su null, linkType è impostato su "o" e linkName viene popolato con l’ID applicazione. Ciò consente di evitare che il conteggio della visualizzazione pagina (visualizzazione stato) venga incrementato ogni volta che si invia un evento.

Se si chiama trackLink direttamente e si impostano i valori per linkTrackVars e linkTrackEvents, queste limitazioni di variabile ed evento si applicano a TrackEvents. Ciò significa che solo le variabili e gli eventi definiti in questi elenchi vengono inviati con TrackEvents. Impostate linkTrackVars e linkTrackEvents su null, a meno che non desideriate applicare tali limitazioni a trackEvents.

### Tracciamento avanzato (track e trackLink)

Questi metodi forniscono opzioni di tracciamento aggiuntive che consentono di compilare direttamente proprietà, eVar e altre variabili SiteCatalyst. Devono essere utilizzati da clienti con un’implementazione esistente o che hanno familiarità con altre implementazioni di SiteCatalyst.

`track` e `trackLink` sono i metodi di misurazione di base implementati in tutte le versioni delle librerie di misurazione Adobe su più piattaforme. Nella maggior parte dei casi, quando monitori applicazioni mobili, è più semplice utilizzare i metodi trackAppState e trackEvents anziché chiamare direttamente track e trackLink.

Il tracciamento (tracciamento) della visualizzazione pagina e il tracciamento dei collegamenti (trackLink) invia tutte le variabili persistenti con valori (non-null, non-empty, non-zero). Prima di chiamare track o trackLink, devi reimpostare o svuotare tutte le variabili in base alle esigenze.

*Nota: A causa della natura multithread delle applicazioni moderne, non è consigliabile impostare valori variabili persistenti da inviare con una chiamata di tracciamento futura (tramite setEvar, setProp, setHier, SetListVar e setPersistentContextData). Ad esempio, se il valore di una variabile è impostato in più thread, il valore potrebbe trovarsi in uno stato incoerente al momento della chiamata di tracciamento. Per evitare questo problema, è consigliabile trasmettere i dati contestuali a ogni chiamata di tracciamento e impostare il valore della variabile in Regole di elaborazione.

**Descrizioni dei metodi**

**track**: Invia al server di raccolta una visualizzazione pagina standard, insieme a eventuali variabili aggiuntive impostate sull'oggetto di misurazione.

Ogni chiamata al tracciamento invia tutti i dati persistenti definiti sull'oggetto di misurazione (elencati nella descrizione per clearVars), più tutti i dati contextData o le variabili fornite solo per quella chiamata. Se si invia una variabile definita, qualsiasi valore nella variabile persistente corrispondente viene sovrascritto.

Sintassi:

```
void track()
void track(Hashtable<String, Object> contextData)
void track(Hashtable<String, Object> contextData, Hashtable<String, Object>
variables)
```

Esempi:

`measure.track();`

```
measure.setEvar(1, "evar1value");
Hashtable contextData = new Hashtable<String, Object>();
contextData.put("key", "value");
measure.track(contextData);
```

```
//set an eVar
measure.setEvar(1, "evar1value");
//contextData
Hashtable contextData = new Hashtable<String, Object>();
contextData.put("key", "value");
//variable overrides
Hashtable variableOverrides = new Hashtable<String, Object>();
variableOverrides.put("evar2", "evar2value");
//sends eVar1, eVar2 (set in overrides), and context data
measure.track(contextData, variableOverrides);
```

**trackLink**: Invia dati di collegamento personalizzati, scaricati o usciti ai server di raccolta dati Adobe, insieme a eventuali variabili trackconfig con valori.

Utilizza trackLink per tenere traccia di tutte le attività che non devono acquisire una visualizzazione pagina.

Sintassi:

```
void trackLink(String linkURL, String linkType, String linkName,
Hashtable<String, Object> contextData, Hashtable<String, Object> variables)
```

**linkURL**: Identifica l’URL su cui è stato fatto clic. Se non viene specificato alcun URL, viene utilizzato il nome. Utilizzate questa opzione solo per il collegamento a una pagina Web dall'applicazione Android. In caso contrario, passate null per questo parametro.

**linkType**: Identifica il rapporto sul collegamento che visualizzerà l’URL o il nome. I valori supportati includono:
* "o" (collegamenti personalizzati)
* "d" (Download di file)
* "e" (collegamenti di uscita)

**linkName**: Nome visualizzato nel rapporto sul collegamento. Se non viene specificato alcun nome, il rapporto utilizza l'URL.

Per raccogliere i dati, devi specificare il parametro linkURL o linkName. Se non si utilizza uno di questi parametri, i dati contestuali o altre variabili, passare null come valore.

Esempi:

`measure.trackLink("url", "o", "name", contextData, null);`

**setEvar**: Imposta l'eVar specificata sul valore fornito. L'eVar viene inviato con tutte le chiamate di tracciamento finché non viene cancellato impostandolo su una stringa vuota o chiamando le variabili di cancellazione.

Sintassi:

`void setEvar(int evarNum, String evarValue)`

**setProp**: Imposta la proprietà specificata sul valore fornito. Il prop viene inviato con tutte le chiamate di tracciamento finché non viene cancellato impostandolo su una stringa vuota o chiamando le variabili di cancellazione.

Sintassi:

`void setProp(int propNum, String propValue)`

**setHier**: Imposta la variabile corrispondente specificata sul valore fornito. La variabile dell'erede viene inviata con tutte le chiamate di tracciamento finché non viene cancellata impostandola su una stringa vuota o chiamando le variabili di cancellazione.

Sintassi:

`void setHier(int hierNum, String hierValue)`

**setListVar**: Imposta la listVar specificata sul valore fornito. ListVar viene inviato con tutte le chiamate di tracciamento finché non viene cancellato impostandolo su una stringa vuota o chiamando le variabili di cancellazione.

Sintassi:

`void setListVar(int listNum, String listValue)`

**setPersistentContextData**:I valori inseriti in Dati contestuali persistenti vengono inviati con ogni chiamata al server. Per inviare dati di contesto per una singola chiamata, invia una tabella di hash contextData come parametro alla chiamata di tracciamento (trackAppState, trackEvents e così via).

```
Hashtable<String, Object> contextData = new HashTable<String,Object>();
contextData.put("key", "value");
measure.setPersistentContextData(contextData);
```

Consulta Dati contestuali.

**clearVars**: Rimuove i valori dalle seguenti variabili dall'oggetto:

```
props
eVars
heirs
listVars
events
PersistentContextData
purchaseID
transactionID
appState
channel
appSection
campaign
products
geoZip
geoState
linkTrackVars
linkTrackEvents
```

Sintassi:

`void clearVars()`

Esempi:
`measure.clearVars();`

**Tracciamento offline**

*Nota: Per abilitare AppMeasurement offline, le marche temporali devono essere abilitate nella suite di rapporti.*

Le seguenti variabili consentono di memorizzare le chiamate di misurazione quando l’applicazione è offline.  Per abilitare AppMeasurement offline, le marche temporali devono essere abilitate nella suite di rapporti. Dopo aver apportato questa modifica, tutti gli hit devono avere marca temporale o devono essere eliminati. Se i dati AppMeasurement vengono inviati a una suite di rapporti che raccoglie anche dati da JavaScript, potrebbe essere necessario impostare una suite di rapporti distinta per Offline AppMeasurement per evitare la perdita di dati.

Quando abilitata, AppMeasurement offline si comporta come segue:
* L'applicazione invia una chiamata al server, ma la trasmissione dei dati non riesce.
* AppMeasurement genera un timestamp per l’hit corrente.
* AppMeasurement esegue il buffer dei dati hit ed effettua il backup dei dati hit nel buffer allo storage permanente per evitare la perdita di dati.

Ad ogni hit successivo, o all’intervallo definito da offlineThrottleDelay, AppMeasurement tenta di inviare i dati dell’hit nel buffer, mantenendo l’ordine di hit originale. Se la trasmissione dei dati ha esito negativo, continua a bufferizzare i dati di hit (questa operazione continua mentre il dispositivo è offline).

### Metodi di Configurazione

**setOfflineTrackingEnabled**: Il valore predefinito è false. Abilita o disabilita il tracciamento offline per la libreria delle misurazioni.

Sintassi:

`void setOfflineTrackingEnabled(boolean Enabled);`

Esempi:
"misura.setOfflineTrackingEnabled(true);

**setOfflineHitLimit**: Il valore predefinito è 1000. Numero massimo di hit offline memorizzati nella coda. Se il limite di hit è impostato su 5000, le prestazioni potrebbero risultare compromesse.

Sintassi:

`void setOfflineHitLimit(int offlineHitLimit)`

Esempi:

`measure.setOfflineHitLimit(2000);`

**getTrackingQueueSize**: Restituisce il numero di chiamate di tracciamento memorizzate nella coda offline.

Sintassi:

`int getTrackingQueueSize()`

Esempi:

`int size = measure.getTrackingQueueSize();`

**clearTrackingQueue**: Rimuove tutte le chiamate di tracciamento memorizzate dalla coda offline.

Sintassi:

`void clearTrackingQueue()`

Esempi:

`measure.clearTrackingQueue();`

**Avvertenza: da usare con cautela quando si cancella la coda manualmente; questa operazione non può essere annullata.**


**setOnline e setOffline**: Impostare manualmente lo stato online o offline dell'oggetto di misura. La libreria rileva automaticamente quando il dispositivo è offline o online, pertanto questi metodi sono necessari solo se si desidera forzare la misurazione offline. SetOnline viene utilizzato solo per tornare allo stato online dopo essere stato disconnesso manualmente.

Quando la misurazione è offline:

* Se offlineTrackingEnabled è true: gli hit vengono memorizzati finché la misurazione non è online.
* Se offlineTrackingEnabled è false: gli hit vengono scartati.

Sintassi:

```
void setOnline()
void setOffline()
```

Esempi:

```
measure.setOffline();
measure.setOnline();
```

## Tracciamento offline

AppMeasurement consente di misurare l'utilizzo dell'applicazione anche quando il dispositivo Android è offline.

*Nota: Per abilitare AppMeasurement offline, le marche temporali devono essere abilitate nella suite di rapporti.*

Consultate Tracciamento offline.

## Target

Adobe offre la possibilità di distribuire contenuti mirati all'interno delle applicazioni Android.

Il contenuto restituito da Test&amp;Target può essere costituito da qualsiasi contenuto basato su testo, ad esempio HTML, XML o normale. Una volta caricato il contenuto, spetta allo sviluppatore dell'applicazione Android decidere come utilizzarlo all'interno dell'applicazione. Il contenuto può essere visualizzato come HTML o utilizzato per modificare il comportamento dell'applicazione. Questa guida fornisce un esempio di utilizzo semplice delle classi Test&amp;Target.

Requisiti

* JDK 5/6/7
* Android SDK per la piattaforma 1.5 o versione successiva.

L’esempio riportato in questa sezione è basato su Eclipse.

**Ottenere la libreria**

Per scaricare la libreria Android, visita Misurazione e ottimizzazione di applicazioni mobili su Developer Connection.

Dopo aver decompresso il file di download, si avranno i seguenti componenti software:

* admsAppLibrary.jar: Libreria progettata per l’uso con dispositivi e simulatori Android. Richiede Android 2.0 o versione successiva.
* Esempi\TrackingHelper.java: Classe opzionale progettata per tenere il codice di tracciamento separato dalla logica dell'applicazione.

**Aggiungere la libreria al progetto**

1. Nell’IDE Eclipse, fai clic con il pulsante destro del mouse sul nome del progetto.
1. Seleziona Percorso creazione &gt; Aggiungi archivi esterni.
1. Selezionate admsAppLibrary.jar.
1. Fai clic su Apri.
1. Fai di nuovo clic con il pulsante destro del mouse sul progetto, quindi seleziona Percorso creazione &gt; Configura percorso build.
1. Fare clic sulla scheda Ordine ed esportazione.
1. Verifica che admsAppLibrary.jar sia selezionato.

Your application can import the classes/interfaces from the admsAppLibrary.jar library by using `importcom.adobe.ADMS.*;`

**Aggiungere le autorizzazioni dell’app**

La libreria AppMeasurement richiede le seguenti autorizzazioni per inviare dati e registrare le chiamate di tracciamento offline:

* INTERNET
* ACCESS_NETWORK_STATE

Per aggiungere queste autorizzazioni, aggiungete le seguenti righe al file AndroidManifest.xml (nella directory di progetto dell’applicazione):

```
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

Esempio 

Dopo aver aggiunto la libreria al progetto e le autorizzazioni per l'app, potete utilizzare le due classi Test&amp;Target, MboxFactory e Mbox.

L’esempio seguente mostra come caricare contenuto HTML da Test&amp;Target in una WebView all’interno di una semplice applicazione Android. Questo esempio presuppone che le offerte HTML e la campagna associate siano già state create nello strumento di amministrazione di Test&amp;Target e che la campagna sia stata approvata.

1. Completate i passaggi in Implementazione, quindi importate il pacchetto testandtarget nella parte superiore della sottoclasse Application o Activitysubclass:

   `com.adobe.adms.testandtarget.*;`

2. Seguite il codice numerato riportato di seguito per creare una mbox (consultate i commenti per la spiegazione di ogni riga di codice). Per completare questo passaggio, dovrete conoscere il codice cliente e il nome della mbox utilizzata nella configurazione della campagna in Test&amp;Target Admin Tool.

   ```
   public class AndroidDemoApplication extends Activity {
   private WebView _webView;
   public void onCreate(Bundle savedInstanceState) {
   super.onCreate(savedInstanceState);
   _webView = new WebView(this);
   setContentView(_webView);
   // 1. Create an instance of the MboxFactory class with your client code.
   MboxFactory factory = new MboxFactory("androiddemo16");
   // 2. Use the MboxFactory instance to create an Mbox.
   Mbox mbox = factory.create("DemoApp");
   // 3. Set the default content for the Mbox.
   mbox.setDefaultContent("<h1>DEFAULT CONTENT</h1>");
   /**
   * 4. Create a custom MboxContentConsumer to consume the content returned. The
   * CustomMboxContentConsumer class defined below simply displays the content
   * returned in a BrowserField as HTML.
   */
   CustomConsumer consumer = new CustomConsumer(_webView);
   mbox.addOnLoadConsumer(consumer);
   // 5. Load the Mbox.
   mbox.load();
   ...
   ```

3. Definire la classe personalizzata che implementa l'interfaccia MboxContentConsumer. Questa interfaccia astratta richiede solo che venga definito un metodo denominato "consume" in cui trasmettere il contenuto. La classe CustomConsumer definita di seguito mostra semplicemente il contenuto in una WebView.

   ```
   class CustomConsumer implements MboxContentConsumer {
   private WebView _view;
   public CustomConsumer(WebView webview) {
   _view = webview;
   }
   public void consume(String content) {
   _view.loadData(content, "text/html", "utf-8");
   }
   }
   ```

4. Fate clic con il pulsante destro del mouse sul progetto e selezionate Esegui come &gt; Applicazione Android per creare e testare l'applicazione. Se avete configurato correttamente e approvato la campagna Test&amp;Target, l’offerta viene visualizzata nell’emulatore del dispositivo Android.

**Metriche del ciclo di vita**

Se le metriche del ciclo di vita sono abilitate, le metriche del ciclo di vita vengono inviate come parametri a ciascun caricamento mbox.

* (Consigliato) Tenere traccia degli eventi del ciclo di vita
* Metriche del ciclo di vita

## Gestione dell'audience

Adobe offre la possibilità di inviare segnali e recuperare segmenti di visitatori dalla gestione dell'audience.

### Requisiti

* JDK 5/6/7
* Android SDK per la piattaforma 1.5 o versione successiva.

L’esempio riportato in questa sezione è basato su Eclipse.

### Ottenere la libreria

Per scaricare la libreria Android, visita Misurazione e ottimizzazione di applicazioni mobili su Developer Connection.

Dopo aver decompresso il file di download, si avranno i seguenti componenti software:

* admsAppLibrary.jar: Libreria progettata per l’uso con dispositivi e simulatori Android. Richiede Android 2.0 o versione successiva.
* Esempi\TrackingHelper.java: Classe opzionale progettata per tenere il codice di tracciamento separato dalla logica dell'applicazione.

### Aggiungere la libreria al progetto

1. Nell’IDE Eclipse, fai clic con il pulsante destro del mouse sul nome del progetto.
1. Seleziona Percorso creazione &gt; Aggiungi archivi esterni.
1. Selezionate admsAppLibrary.jar.
1. Fai clic su Apri.
1. Fai di nuovo clic con il pulsante destro del mouse sul progetto, quindi seleziona Percorso creazione &gt; Configura percorso build.
1. Fare clic sulla scheda Ordine ed esportazione.
1. Verifica che admsAppLibrary.jar sia selezionato.

Your application can import the classes/interfaces from the admsAppLibrary.jar library by using `importcom.adobe.ADMS.*;`

### Aggiungere le autorizzazioni dell'app

La libreria AppMeasurement richiede le seguenti autorizzazioni per inviare dati e registrare le chiamate di tracciamento offline:
* INTERNET
* ACCESS_NETWORK_STATE

Per aggiungere queste autorizzazioni, aggiungete le seguenti righe al file AndroidManifest.xml (nella directory di progetto dell’applicazione):

```
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

### Esempio di codice

Dopo aver aggiunto la libreria al progetto, potete utilizzare la classe ADMS_AudienceManager. Per importare il pacchetto di Gestione dell'audience aggiungi: `import com.adobe.adms.audiencemanager;`

1. Configurare la gestione dell'audience:

   `ADMS_AudienceManager.ConfigureAudienceManager("mycompany.demdex.net", this);`

   Sostituisci mycompany.demdex.net con il tuo endpoint. Gestione dell'audience può essere configurata in qualsiasi punto dell'applicazione.


2. Se necessario, impostate dpid e dpuuid.

   `ADMS_AudienceManager.SetDpidAndDpuuid("284", "abc123");`

3. Crea un dizionario delle caratteristiche e invia il dizionario in un segnale.

```
HashMap<String, Object> data = new HashMap<String, Object>();
data.put("trait", "b");
ADMS_AudienceManager.SubmitSignal(data, new
ADMS_AudienceManager.AudienceManagerCallback<HashMap>() {
@Override
public void call(HashMap visitorProfile) {
// do things with visitorProfile
}
});
```

Il dizionario del profilo visitatore viene restituito nella callback come parametro di contenuto.

### Metriche del ciclo di vita

Se le metriche del ciclo di vita sono abilitate e la gestione dell'audience è configurata in application:didFinishLaunchingWithOptions:, al termine della configurazione viene inviato un segnale contenente le metriche del ciclo di vita.

* (Consigliato) Tenere traccia degli eventi del ciclo di vita
* Metriche del ciclo di vita

### Guida di riferimento di ADMS_AudienceManager

**Metodi**

**ConfigureAudienceManager**: Imposta l'endpoint di gestione dell'audience.

Sintassi:

`public static void ConfigureAudienceManager(String server, Context context);`

Esempio:

`ADMS_AudienceManager.ConfigureAudienceManager("mycompany.demdex.net", this);`

**GetDebugLogging**: Restituisce un valore booleano che indica se i metodi di Audience Manager forniscono o meno la registrazione di debug nella console.

Sintassi:

`public static boolean GetDebugLogging();`

**GetDpid**: Restituisce il dpid.

Sintassi:

`public static String GetDpid();`

**GetDpuuid**: Restituisce il dpuuid.

Sintassi:

`public static String GetDpuuid();`

**GetVisitorProfile**: Questo metodo può essere invocato in qualsiasi momento dopo aver inviato un segnale per recuperare il profilo visitatore più recente.

Il profilo visitatore contiene tutte le coppie di valori chiave restituite nell'oggetto roba.

Sintassi:

`public static HashMap GetVisitorProfile();`

**SetDebugLogging**: Abilita o disabilita la registrazione di debug nella console.

Sintassi:

`public static void SetDebugLogging(boolean logging);`

**SetDpidAndDpuuid**: Se sono impostati newDpid e newDpuuid, saranno inviati con ogni segnale.

Sintassi:

`public static void SetDpidAndDpuuid(String newDpid, String newDpuuid);`

**SubmitSignal**: Invia in un dizionario delle caratteristiche e riceve il profilo visitatore aggiornato in callback.

L'uuid della risposta JSON viene memorizzato internamente e utilizzato con tutti i segnali successivi. Viene inoltre inviata una richiesta di pixel a ogni URL presente nell'oggetto dests.

Sintassi:

```
public static void SubmitSignal(HashMap<String, Object> data,
AudienceManagerCallback<HashMap> callback);
```

### Interfaces

**Metodi**


**AudienceManagerCallback**

Sintassi:

```
public interface AudienceManagerCallback<T> {
AudienceManagerCallback
public void call(T item);
}
```

Interfaccia per l’oggetto utilizzato nel callback dalla chiamata SubmitSignal.


## Plug-in PhoneGap

Questo plug-in consente di inviare chiamate Android AppMeasurement dal progetto PhoneGap.

Per assistenza nella creazione di un progetto PhoneGap, consultate PhoneGap Getting Started with Android (Guida introduttiva di PhoneGap con Android).

Per scaricare il plug-in, consultate Plug-in iOS e Android per SiteCatalyst.

### Includere il plug-in

1. Copiate ADMS_plugin.java nel pacchetto nella cartella src.
2. copiate ADMS_Helper.js nella cartella assets/www/js del progetto PhoneGap.
3. Nella cartella res/xml, apri il file config.xml e registra un nuovo plug-in creando un nuovo nodo figlio in plugin: `<plugin name="ADMS_Plugin" value="[YOUR_PACKAGE_NAME].ADMS_plugin" />`

Ad esempio, se il pacchetto è denominato com.example.phonegaptest, il nodo del plug-in sarà il seguente: `<plugin name="ADMS_Plugin" value="com.example.phonegaptest.ADMS_plugin" />`

### Includere la libreria AppMeasurement

Per scaricare la libreria AppMeasurement, vedi Ottenere la libreria.

1. Copiate admsAppLibrary.jar nella cartella libs del progetto PhoneGap.
2. Verifica che admsAppLibrary.jar si trovi nel percorso di compilazione facendo clic con il pulsante destro del mouse su libs &gt; Percorso di creazione &gt; Configura percorso di creazione.
3. Nella scheda Librerie, se non è già presente nell'elenco, fai clic su Aggiungi JAR e seleziona admsAppLibrary.jar dalla cartella libs.


### Tracciamento automatico delle metriche del ciclo di vita

Il tracciamento delle metriche del ciclo di vita richiede una configurazione al di fuori di PhoneGap. Per abilitare il tracciamento automatico del ciclo di vita, completa i passaggi di implementazione nella Guida rapida per sviluppatori.

### Utilizzare il plug-in

Nei file html in cui desiderate usare il tracciamento, includete:

`<script type="text/javascript" src="js/ADMS_Helper.js"></script>`

È tutto, ora sei pronto per effettuare chiamate di misura. Consultate Metodi del plug-in PhoneGap.

### Risoluzione dei problemi

**La mia sintassi è corretta, perché il codice nel plugin non viene raggiunto?**

Controllare la console di output per verificare se si è verificato il seguente errore: `java.lang.ClassNotFoundException: ADMS_plugin`

Se si verifica questo errore, accertatevi di aver eseguito il passaggio 3 nella sezione Includi il plug-in.

## Metodi del plug-in PhoneGap

Nei file html in cui desiderate utilizzare questi metodi, includete:

`<script type="text/javascript" src="js/ADMS_Helper.js"></script>`

**Metodi di Configurazione**


**configureMeasurementWithReportSuiteIDsTrackingServer**: Questo metodo viene utilizzato per configurare i due parametri necessari per avviare la misurazione dell’applicazione. È necessario impostare i valori reportSuiteIDs e trackingServer sull'oggetto di misurazione utilizzando questo metodo prima di inviare chiamate server.

Sintassi:

`void configureMeasurementWithReportSuiteIDsTrackingServer(stringreportSuiteIDs, string trackingServer);`

Esempio:

`ADMS.configureMeasurementWithReportSuiteIDsTrackingServer("testRSID","10.20.40.199:5050");`

**setOnline e setOffline**: Impostare manualmente lo stato online o offline dell'oggetto di misura. La libreria rileva automaticamente quando il dispositivo è offline o online, pertanto questi metodi sono necessari solo se si desidera forzare la misurazione offline. SetOnline viene utilizzato solo per tornare allo stato online dopo essere stato disconnesso manualmente.

Quando la misurazione è offline:

* Se offlineTrackingEnabled è true: gli hit vengono memorizzati finché la misurazione non è online.
* Se offlineTrackingEnabled è false: gli hit vengono scartati.

Sintassi:

```
void setOnline();
void setOffline();
```

Esempio:

```
ADMS.setOnline();
ADMS.setOffline();
```

**setDebugLogging**: Abilita (true) o disabilita (false) la visualizzazione delle informazioni di debug. Per impostazione predefinita, questa variabile è impostata su false.

Non è possibile ignorare questa variabile utilizzando le sostituzioni delle variabili.

Sintassi:

`void setDebugLogging(bool debugLogging);`

Esempio:

`ADMS.setDebugLogging(true);`

### Metodi di tracciamento evento e stato


**trackAppState**: Questo è il metodo consigliato per tenere traccia degli stati dell’applicazione (ad esempio, pagine) nell’applicazione. Il valore fornito in appState viene visualizzato come variabile del nome della pagina della chiamata al server. È necessario fornire la stringa appState per ogni chiamata, perché non viene trasferita alla chiamata successiva.

Sintassi:

`void trackAppState(string stateName);`

Esempio:

`ADMS.trackAppState("login page");`

**trackAppStateWithContextData**: Questo è il metodo consigliato per tenere traccia degli stati dell’applicazione (ad esempio, pagine) nell’applicazione. Il valore fornito in appState viene visualizzato come variabile del nome della pagina della chiamata al server. È necessario fornire la stringa appState per ogni chiamata, perché non viene trasferita alla chiamata successiva.

I dati contestuali inviati con questa chiamata vengono aggiunti a qualsiasi valore in persistentContextData e inviati con la chiamata. Solo i valori impostati in persistentContextData rimangono per la chiamata successiva.

Sintassi:

`void trackAppStateWithContextData(string stateName, JSON cData);`

cData: oggetto JSON con coppie chiave-valore da inviare nei dati contestuali.

Esempio:

```
trackAppStateWithContextData("login page",
{"user":"john","remember":"true"});
```

**trackEvents**: Questo è il metodo consigliato per tenere traccia degli eventi nell’applicazione. trackEvents è simile a trackAppState, ma invia eventi invece dei nomi di pagina. Gli eventi vengono forniti come una stringa delimitata da virgole trackEvents. La stringa eventi deve essere specificata per ogni chiamata, poiché non viene trasferita alla chiamata successiva.

Questo metodo esegue una chiamata sottostante a trackLinkURL in cui linkURL è impostato su null, linkType è impostato su "o" e linkName viene popolato con l’ID applicazione.

Ciò significa che le chiamate a linkTrackVars e linkTrackEvents sono valide per `trackEvents`.

Sintassi:

`void trackEvents(string eventNames);`

Esempio:

`ADMS.trackEvents("login,event2");`

**Importa nota se utilizzi il metodo trackLink**

`trackEvents` effettua una chiamata sottostante a trackLinkURL, dove linkURL è impostato su null, linkType è impostato su "o" e linkName viene popolato con l’ID applicazione. Ciò viene fatto per evitare che il conteggio della visualizzazione pagina (visualizzazione stato) venga incrementato ogni volta che si tengono traccia degli eventi.

Se si chiama trackLinkURL direttamente e si impostano i valori per linkTrackVars e linkTrackEvents, queste limitazioni di variabile ed evento si applicano a TrackEvents. Ciò significa che solo le variabili e gli eventi definiti in questi elenchi vengono inviati con TrackEvents. Impostate linkTrackVars e linkTrackEvents su null, a meno che non desideriate applicare tali limitazioni a trackEvents.

**trackEventsWithContextData**: Questo è il metodo consigliato per tenere traccia degli eventi nell’applicazione. trackEvents è simile a trackAppState, ma invia eventi invece dei nomi di pagina. Gli eventi vengono forniti come stringa delimitata da virgole. La stringa eventi deve essere specificata per ogni chiamata, poiché non viene trasferita alla chiamata successiva.

Questo metodo effettua una chiamata sottostante a trackLinkURL in cui linkURL è impostato su null, linkType è impostato su "o" e linkName viene popolato con l’ID applicazione.

Ciò significa che i collegamentiTrackVars e linkTrackEvents si applicano alle chiamate a trackEvents.

I dati contestuali inviati con questa chiamata vengono aggiunti a qualsiasi valore in persistentContextData e inviati con la chiamata. Solo i valori impostati in persistentContextData rimangono per la chiamata successiva.

Sintassi:

`void trackEventsWithContextData(string eventNames, JSON cData);`

cData: oggetto JSON con coppie chiave-valore da inviare nei dati contestuali.

Esempio:

`ADMS.trackEventsWithContextData("login,event2",
{"user":"john","remember":"true"});`

**Importa nota se utilizzi il metodo trackLink**

trackEvents effettua una chiamata sottostante a trackLinkURL, dove linkURL è impostato su null, linkType è impostato su "o" e linkName viene popolato con l’ID applicazione. Ciò viene fatto per evitare che il conteggio della visualizzazione pagina (visualizzazione stato) venga incrementato ogni volta che si tengono traccia degli eventi.

Se si chiama trackLinkURL direttamente e si impostano i valori per linkTrackVars e linkTrackEvents, queste limitazioni di variabile ed evento si applicano a TrackEvents. Ciò significa che solo le variabili e gli eventi definiti in questi elenchi vengono inviati con TrackEvents. Impostate linkTrackVars e linkTrackEvents su null, a meno che non desideriate applicare tali limitazioni a trackEvents.

**Metodi di tracciamento avanzati (track e trackLink)**

Questi metodi forniscono opzioni di tracciamento aggiuntive che consentono di compilare direttamente proprietà, eVar e altre variabili SiteCatalyst. Devono essere utilizzati da clienti con un’implementazione esistente o che hanno familiarità con altre implementazioni di SiteCatalyst.

`track` e `trackLink` sono i metodi di misurazione di base implementati in tutte le versioni delle librerie di misurazione Adobe su più piattaforme. Nella maggior parte dei casi, quando monitori applicazioni mobili, è più semplice utilizzare i metodi trackAppState e trackEvents anziché chiamare direttamente track e trackLink.

Il tracciamento (tracciamento) della visualizzazione pagina e il tracciamento dei collegamenti (trackLink) invia tutte le variabili persistenti con valori (non-null, non-empty, non-zero). Prima di chiamare track o trackLink, devi reimpostare o svuotare tutte le variabili in base alle esigenze.

**Metodi**

**track**: Invia al server di raccolta una visualizzazione pagina standard, insieme a eventuali variabili aggiuntive impostate sull'oggetto di misurazione.

Sintassi:

`void track();`

Esempio:

`ADMS.track();`

**trackWithContextData**: Invia al server di raccolta una visualizzazione pagina standard, insieme a eventuali variabili aggiuntive impostate sull'oggetto di misurazione.

Ogni chiamata a trackWithContextData invia tutti i dati persistenti definiti sull'oggetto di misurazione (elencati nella descrizione per clearVars), più tutti i dati contestuali forniti per tale chiamata.

Sintassi:

`void trackWithContextData(JSON cData);`

cData: oggetto JSON con coppie chiave-valore da inviare nei dati contestuali.

Esempio:

`ADMS.trackWithContextData({"key1":"value1","key2":"value2"});`


**trackWith ContextDataAndVariables**: Invia al server di raccolta una visualizzazione pagina standard, insieme a eventuali variabili aggiuntive impostate sull'oggetto di misurazione.

Ogni chiamata a trackWithContextDataAndVariables invia tutti i dati persistenti definiti sull'oggetto di misura (elencati nella descrizione per clearVars), più eventuali contextData e variabili fornite solo per quella chiamata. Se si invia una variabile definita, qualsiasi valore nella variabile persistente corrispondente viene sovrascritto.

Sintassi:

`void trackWithContextDataAndVariables(JSON cData, JSON vars);`

cData: oggetto JSON con coppie chiave-valore da inviare nei dati contestuali.

Esempio:

```
ADMS.trackWithContextDataAndVariables({"key1":"value1","key2":"value2"},
{"eVar1":"newValue","prop3":"newValue"});
```

**trackLinkURLWithLinkTypeName**: Invia dati di collegamento personalizzati, scaricati o usciti ai server di raccolta dati Adobe, insieme a qualsiasi variabile di configurazione del tracciamento con valori.

Utilizza trackLink per tenere traccia di tutte le attività che non devono acquisire una visualizzazione pagina.

Ogni chiamata a trackLinkURLWithLinkTypeNameContextDataVariables invia tutti i dati persistenti definiti sull’oggetto di misurazione (elencati nella descrizione per clearVars), più eventuali contextData forniti solo per tale chiamata.

Sintassi:

```
void trackLinkURLWithLinkTypeNameContextDataVariables(string`
linkUrl, string linkType, string linkName, JSON cData, JSON vars);
```

cData: oggetto JSON con coppie chiave-valore da inviare nei dati contestuali.

Esempio:

```
ADMS.trackLinkURLWithLinkTypeNameContextDataVariables("theLink",
"o", "logout", {"key1":"value1"}, {"eVar1":"newValue"});
```

### Impostare e ottenere le variabili AppMeasurement

**Metodi**

**setEvarToValue**: Imposta l'eVar specificata sul valore fornito. L'eVar viene inviata con la successiva chiamata di tracciamento.

Sintassi:

`void setEvarToValue(int evar, string value);`

Esempio:

`ADMS.setEvarToValue(1, "newValue");`

**setPropToValue**: Imposta la proprietà specificata sul valore fornito. Il prop viene inviato con la successiva chiamata di tracciamento.

Sintassi:

void setPropToValue(int prop, valore stringa);

Esempio:

`ADMS.setPropToValue(1, "newValue");`

**setHierToValue**: Imposta la variabile hier specificata sul valore fornito. La variabile viene inviata con la successiva chiamata di tracciamento.

Sintassi:

`void setHierToValue(int hier, string value);`

Esempio:

`ADMS.setHierToValue(1, "newValue");`

**setListVarToValue**: Imposta il listener specificato sul valore fornito. Il listener viene inviato con la successiva chiamata di tracciamento.

Sintassi:

`void setListVarToValue(int list, string value);`

Esempio:

`ADMS.setListVarToValue(1, "newValue");`

**getEvar**: Ottiene la variabile specificata.

Sintassi:

`void getEvar(int evar, function success, function fail);`

Esempio:

```
ADMS.getEvar(1, function (value) { myTempEvar1 = value; }, function ()
{ myTempEvar1 = null; });
```

**getProp**: Ottiene la variabile specificata.

Sintassi:

`void getProp(int prop, function success, function fail);`

Esempio:

```
ADMS.getProp(1, function (value) { myTempProp1 = value; }, function ()
{ myTempProp1 = null; });
```

**getHier**: Ottiene la variabile specificata.

Sintassi:

`void getHier(int hier, function success, function fail);`

Esempio:

```
ADMS.getHier(1, function (value) { myTempHier1 = value; }, function ()
{ myTempHier1 = null; });
```

**getListVar**: Ottiene la variabile specificata.

Sintassi:

`void getListVar(int list, function success, function fail);`

Esempio:

```
ADMS.getListVar(1, function (value) { myTempListVar1 = value; }, function
() { myTempListVar1 = null; });
```

**clearVars**: Rimuove i valori dalle seguenti variabili dall'oggetto:

```
props
eVars
heirs
listVars
events
PersistentContextData
purchaseID
transactionID
appState
channel
appSection
campaign
products
geoZip
geoState
linkTrackVars
linkTrackEvents
```

Sintassi:

`void clearVars();`

Esempio:

`ADMS.clearVars();`

**trackingQueueSize**: Ottiene o imposta il numero di chiamate di tracciamento memorizzate nella coda offline.

Sintassi:

`void trackingQueueSize(function success, function fail);`

Esempio:

`ADMS.trackingQueueSize(function (value) { myQueueSize = value; }, function () { myQueueSize = 0; });`

**clearTrackingQueue**: Rimuove tutte le chiamate di tracciamento memorizzate dalla coda offline. Avvertenza: da usare con cautela quando si cancella la coda manualmente; questa operazione non può essere annullata.

Sintassi:

`void clearTrackingQueue();`

Esempio:

`ADMS.clearTrackingQueue();`

### Impostare e ottenere le variabili di configurazione

**Metodi**

**getVersion**: Ottiene la versione della libreria.

Sintassi:

`void getVersion(function success, function fail);`

Esempio:

```
ADMS.getVersion(function (value) { versionNum = value; }, function ()
{ versionNum = 1.0; });
```

**setReportSuiteIDs**: (Obbligatorio) La suite di rapporti o le suite di rapporti (tag per più suite) che desideri monitorare. Per eseguire il tracciamento su più suite di rapporti, passa un elenco delimitato da virgole dei nomi di ciascuna suite di rapporti.

Non puoi ignorare questa variabile per una singola chiamata, devi modificare il valore persistente.

Sintassi:
`void setReportSuiteIDs(string reportSuiteIDs);`

Esempio:

`ADMS.setReportSuiteIDs("rsid1, rsid2");`

**setTrackingServer**: (Obbligatorio) Identifica il server di raccolta.

Questa variabile deve essere compilata con il valore generato automaticamente in Code Manager.

Lo stesso valore viene utilizzato per il tracciamento protetto se ssl è abilitato.

Non puoi ignorare questa variabile per una singola chiamata, devi modificare il valore persistente.

Sintassi:

`void setTrackingServer(string trackingServer);`

Esempio:

`ADMS.setTrackingServer("10.23.52.191:5923");`

**setDataCenter**:

Sintassi:

`void setDataCenter(string dataCenter);`

Esempio:

`ADMS.setDataCenter("myDataCenter");`

**setVisitorID**: Il valore predefinito è CFUID.

Identificatore univoco per ogni visitatore. Se non imposti un visitorID personalizzato, all’avvio iniziale viene generato un visitorID univoco (che utilizza l’identificatore CFUUID di Apple) e quindi memorizzato in una chiave predefinita utente. Questa chiave viene utilizzata da AppMeasurement e PhoneGap da quel momento in poi. Questa chiave viene inoltre salvata e ripristinata durante il processo standard di backup dell'applicazione.

Sintassi:

`void setVisitorID(string visitorId);`

Esempio:

`ADMS.setVisitorID("myVisitorId");`

**setCharSet**: Il valore predefinito è UTF-8.

Sintassi:

`void setCharSet(string charSet);`

Esempio:

`ADMS.setCharSet("UTF-8");`

**setCurrencyCode**: Il valore predefinito è none (viene utilizzato il valore definito per la suite di rapporti).

Il codice valuta utilizzato per gli acquisti o gli eventi di valuta tracciati nell'applicazione iOS.

Sintassi:

`void setCurrencyCode(string currencyCode);`

Esempio:

`ADMS.setCurrencyCode("USD");`


**setSSLEnabled**: Il valore predefinito è false.

Abilita (true) o disabilita (false) l’invio dei dati di misurazione tramite SSL (HTTPS). Non puoi ignorare questa variabile per una singola chiamata, devi modificare il valore persistente.

Sintassi:

`void setSSLEnabled(bool sslEnabled);`

Esempio:

`ADMS.setSSLEnabled(false);`

### Impostare e ottenere variabili di tracciamento persistenti

**Metodi**

**setPurchaseID**:

Sintassi:

`void setPurchaseID(string purchaseId);`

Esempio:

`ADMS.setPurchaseID("purchase1");`

**setTransactionID**:

Sintassi:

`void setTransactionID(string transactionId);`

Esempio:

`ADMS.setTransactionID("transaction1");`

**setAppState**:

Sintassi:

`void setAppState(string stateName);`

Esempio:

`ADMS.setAppState("myAppState");`

**setChannel**:

Sintassi:

`void setChannel(string channel);`

Esempio:

`ADMS.setChannel("myChannel");`

**setAppSection**:

Sintassi:

`void setAppSection(string appSection);`

Esempio:

`DMS.setAppSection("myAppSection");`

**setCampaign**:

Sintassi:

`void setCampaign(string campaign);`

Esempio:

`ADMS.setCampaign("myCampaign");`

**setProducts**:

Sintassi:

`void setProducts(string products);`

Esempio:

`ADMS.setProducts("myProduct1,myProduct2");`

**setEvents**:

Sintassi:

`void setEvents(string events);`

Esempio:

`ADMS.setEvents("event1, event2");`

**setGeoState**

Sintassi:

`void setGeoState(string state);`

Esempio:

`ADMS.setGeoState("FL");`

**setGeoZip**:

Sintassi:

`void setGeoZip(string zip);`

Esempio:

`ADMS.setGeoZip("39984");`

**setPersistentContextData**: I dati contestuali rappresentano il metodo consigliato per la raccolta dei dati. Per inviare dati contestuali, create un oggetto JSON e assegnate coppie di valori chiave per i valori che desiderate inviare.

Sintassi:

`void setPersistentContextData(JSON cData);`

Esempio:

`ADMS.setPersistentContextData({"key1":"value1"});`

**persistContextData**:

Sintassi:

`void persistentContextData(function success, function fail);`

Esempio:

```
ADMS.persistentContextData(function(value) { alert(value); },
function(error) { alert(error); });
```

**setLinkTrackVars**: Elenco delimitato da virgole di nomi di variabili che limitano il set corrente di variabili per il tracciamento dei collegamenti.

Se linkTrackVars non è definito, il plug-in PhoneGap invia tutte le variabili definite con una chiamata trackLink.

Sintassi:

`void setLinkTrackVars(string linkTrackVars);`

Esempio:

`ADMS.setLinkTrackVars("eVar1,eVar2");`


**setLinkTrackEvents**: Elenco delimitato da virgole di eventi che limitano il set corrente di eventi per il tracciamento dei collegamenti. Se linkTrackEvents non è definito, il plug-in PhoneGap invia tutti gli eventi con una chiamata trackLink.

Sintassi:

`void setLinkTrackEvents(string linkTrackEvents);`

Esempio:

`ADMS.setLinkTrackEvents("event1,loginEvent");`


**setLightTrackVars**: Elenco delimitato da virgole di variabili che limitano il set corrente di variabili per le chiamate di tracciamento della luce. Le variabili inviate con una chiamata server leggero sono configurate da ClientCare.

Sintassi:

`void setLightTrackVars(string lightTrackVars);`

Esempio:

`ADMS.setLightTrackVars("prop1,hier3");`

### Tracciamento offline

**Metodi**

**setOfflineTrackingEnabled**:

Sintassi:

`void setOfflineTrackingEnabled(bool offlineTrackingEnabled);`

Esempio:

`ADMS.setOfflineTrackingEnabled(true);`

**setOfflineHitLimit**:

Sintassi:

`void setOfflineHitLimit(int offlineHitLimit);`

Esempio:

`ADMS.setOfflineHitLimit(3000);`

## Guida alla migrazione ad Android dalla versione 2.x alla versione 3.x

* AppMeasurement è ora ADMS_Measurement. Trova le posizioni in cui fai riferimento a questa classe e aggiorna il nome in ADMS_Measurement.
* getInstance è ora sharedInstance. Trovate le posizioni in cui chiamate getInstance e sostituitela con sharedInstance.
* Rimuovete tutte le chiamate alla misurazione churn (getChurnInstance). Queste chiamate vengono gestite mediante tracciamento automatico e le variabili vengono ora inserite utilizzando i dati contestuali.
* Timestamp rimosso. La libreria gestisce automaticamente le marche temporali.

La sintassi dei metodi seguenti è stata modificata. Gli esempi aggiornati per tutte le proprietà e tutti i metodi sono disponibili in Variabili e metodi di configurazione.


### Suite di rapporti

**Versione precedente (2.1.x)**

`account`

**Nuova versione (3.x)**

`reportSuiteIDs`

### Track

**Versione precedente (2.1.x)**


`String track()`

`String track(Hashtable variableOverrides)`

**Nuova versione (3.x)**

Passa null per i valori non utilizzati.

```
void track()
void track(Hashtable<String, Object>
contextData)
void track(Hashtable<String, Object>
contextData, Hashtable<String, Object>
variables)
```

### Collegamento traccia

**Versione precedente (2.1.x)**

```
String trackLink(String linkURL, String
linkType, String linkName)
```

```
String trackLink(String linkURL, String
linkType, String linkName,
Hashtable variableOverrides)
```

**Nuova versione (3.x)**

Queste due chiamate sono state sostituite da una singola chiamata. Passa null per i valori non utilizzati.

```
void trackLink(String linkURL, String linkType,
String linkName,
Hashtable<String, Object> contextData,
Hashtable<String, Object> variables)
```

### Metodi di tracciamento offline

**Versione precedente (2.1.x)**

`void forceOffline();`


`void forceOnline();`

**Nuova versione (3.x)**

`void setOnline();`

`void setOffline();`


### Variabili rinominate

L'elenco seguente mostra le variabili della versione 2.x con i valori corrispondenti nella versione 3.x. Diverse variabili sono state rimosse dalla versione 3.x per rendere la libreria più mobile e semplificare l'implementazione.


*Nota: La versione 3.x utilizza getter e setter invece delle variabili pubbliche. Sarà necessario aggiornare le posizioni nel codice in cui si impostano le variabili direttamente per utilizzare i metodi get e set.*

```
timestamp; //Removed
trackOffline; //void setOfflineTrackingEnabled(boolean Enabled)
offlineLimit; //void setOfflineHitLimit(int offlineHitLimit)
account; //reportSuiteIDs
linkURL; //Removed (sent with linkTrackURL)
linkName; //Removed (sent with linkTrackURL)
linkType; //Removed (sent with linkTrackURL)
linkTrackVars; //void setLinkTrackVars(String Vars) //comma-delimited list
linkTrackEvents; //void setLinkTrackEvents(String Events) //comma-delimited list
dc; //Removed
trackingServer; //void setTrackingServer(String trackingServer)
trackingServerSecure; //Removed, trackingServer value is used for secure server if ssl=YES
userAgent; //Removed
dynamicVariablePrefix; //Removed
visitorID; //void setVisitorID(String ID)
charSet; //void setCharSet(String charSet)
visitorNamespace; //Removed
pageName; //void setAppState(String State)
pageURL; //Removed
referrer; //Removed
currencyCode; //void setCurrencyCode(String currencyCode)
purchaseID; //void setPurchaseID(String ID)
channel; //void setChannel(String Channel)
server; //void setAppSection(String Section)
pageType; //Removed
transactionID; //void setTransactionID(String ID)
campaign; //void setCampaign(String Campaign)
state; //void setGeoState(String GeoState)
zip; //void setGeoZip(String GeoZip)
events; //void setEvents(String Event) //comma-delimited list
products; //void setProducts(String Products)
list1-list3; //setListVar(int listNum, String listValue);
hier1-heir5; //setHier(int hierNum, String hierValue);
prop1-prop75; //setProp(int propNum, String propValue);
eVar1-eVar75; //setEvar(int evarNum, String evarValue);
ssl; //void setSSL(boolean ssl)
linkLeaveQueryString; //Removed
debugTracking; //debugLogging
usePlugins; //Removed
useBestPractices; //Removed - handled by Lifecycle AutoTracking
contextData; //persistentContextData
```

## Utilizzo di Bloodhound per testare le applicazioni mobili

Il tool Bloodhound permette di inviare chiamate server a un computer locale per testare le applicazioni mobili.

*Importante: dal 30 aprile 2017, Adobe Bloodhound è stato ritirato. A partire dal 1° maggio 2017, non verranno più forniti ulteriori miglioramenti né supporto aggiuntivo Engineering o Adobe Expert Care.*

Durante lo sviluppo dell'applicazione, Bloodhound consente di visualizzare le chiamate server localmente e, facoltativamente, di inoltrare i dati ai server di raccolta di Adobe.

Bloodhound è disponibile per Mac e Windows.

### Requisiti

* Un computer Mac basato su Intel che esegue Snow Leopard (10.6) o versione successiva o un PC Windows.
* Connettività di rete ai dispositivi mobili o emulatori.

### Download

Consulta Bloodhound - App Measurement QA Tool in Developer Connection.

### Installazione

* Mac: apri il dmg che hai scaricato e trascina Bloodhound nella cartella Applicazioni.
* Windows: esegui il file di installazione che hai scaricato.

### Utilizzo di Bloodhound

Dopo aver avviato il tool, il server è disabilitato finché non fai clic sul pulsante Start. Fai clic su Start quando sei pronto per acquisire le chiamate server dall’applicazione.

Facoltativamente, puoi specificare un numero di porta personalizzato (deve essere superiore a 1024) prima di avviare il server. In caso contrario, il server seleziona automaticamente una porta aperta.

Quando il server è in esecuzione, devi configurare le applicazioni o i dispositivi affinché inviino i dati al tool, come spiegato nella sezione successiva.

### Configurare i dispositivi per l’invio degli hit a Bloodhound

Potete modificare le impostazioni proxy sul dispositivo per inviare richieste HTTP allo strumento. Se necessario, le richieste inviate al tool possono anche essere inoltrate ai server di raccolta dati Adobe.

Se il dispositivo non supporta un proxy, puoi inviare gli hit direttamente a Bloodhound per il test.

*Nota: Bloodhound non supporta il tracciamento SSL. Devi disattivare SSL nella libreria AppMeasurement quando usi Bloodhound per attività di test.*

#### Dispositivi iOS

Il dispositivo iOS deve essere connesso alla stessa rete del computer che esegue Bloodhound.

1. Vai a Impostazioni &gt; Wi-Fi.
1. Fai clic sulla freccia blu a destra della rete Wi-Fi corrente.
1. Scorri fino a Proxy HTTP.
1. Seleziona Automatico.
1. Inserisci l’URL e la porta del proxy (ricavati dall’interfaccia di Bloodhound) nel campo URL.

#### Altri dispositivi

Se il dispositivo supporta la configurazione automatica del proxy, puoi semplicemente utilizzare l’URL del proxy (dall’interfaccia di Bloodhound) come URL di configurazione automatica (Proxy Auto Config, PAC). Il supporto proxy varia a seconda della versione di Android; sono anche disponibili dei tool di configurazione proxy per Android che semplificano le operazioni di configurazione.

### Invio diretto degli hit

Per i dispositivi che non supportano i proxy (iOS Simulator, vecchie versioni di Android, ecc.), è possibile specificare Bloodhound come server di tracciamento al fine di acquisire gli hit che genera. A questo scopo, imposta il server di tracciamento su "<Bloodhound IP>:<BloodhoundPort>".

Ad esempio:

```
//iOS
[measure configureMeasurementWithReportSuiteIDs:@"my_rsid" trackingServer:@"10.10.2.2:5000"];
measure.ssl = NO;
```

```
//Android
measure.configureMeasurement("my_rsid", "10.10.2.2:5000");
measure.ssl = false;
```

```
//WinRT for Windows 8, Windows Phone 8
measure.ConfigureMeasurement("my_rsid", "10.10.2.2:5000");
measure.ssl = false;
```

### Problemi comuni e soluzioni

* La funzionalità di tracciamento di Bloodhound non supporta SSL. Eventuali hit di tracciamento inviati tramite SSL non vengono acquisiti, indipendentemente dal metodo utilizzato.

## Widget Android

I widget Android possono essere tracciati utilizzando gli stessi metodi dell'app. I widget condividono il contesto dell'applicazione con l'app, pertanto l'ordine degli hit e l'identificazione dei visitatori sono mantenuti.

Le seguenti linee guida aiutano nel tracciamento dei widget Android:

* Non implementare chiamate delle metriche del ciclo di vita (startActivity/stopActivity) nel widget stesso.
* Per tracciare il momento in cui un widget viene aggiunto alla schermata principale, aggiungi una chiamata trackState o trackEvent al metodo onEnabled del widget.
* Per tracciare il momento in cui l'app è avviata da un widget, aggiungi una chiamata trackState o trackEvent prima di creare l'intento di avviare l'applicazione.
* Se siete interessati a tracciare il contesto di un’azione, potete definire una variabile ContextData che fornisce l’opzione di segmentare separatamente ciascuna immagine (ad esempio, AppExperienceType="widget" vs. "app").
