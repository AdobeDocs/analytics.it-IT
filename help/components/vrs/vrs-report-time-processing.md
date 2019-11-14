---
description: L'elaborazione dei tempi di rapporto è un'impostazione della suite di rapporti virtuali che consente l'elaborazione dei dati in modo retroattivo e non distruttivo.
title: Elaborazione dell'ora rapporto
uuid: 1a1d82ea-8c93-43cc-8689-cdcf59c309b1
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Elaborazione dell'ora rapporto

L'elaborazione dei tempi di rapporto è un'impostazione della suite di rapporti virtuali che consente l'elaborazione dei dati in modo retroattivo e non distruttivo.

> [!NOTE] L’elaborazione dei tempi di rapporto è disponibile solo per Analysis Workspace.

L'elaborazione dei tempi di report interessa solo i dati nella suite di rapporti virtuali e non ha alcun impatto sulla raccolta di dati o dati nella suite di rapporti di base. La differenza tra l'elaborazione dei tempi di report e l'elaborazione tradizionale di Analytics è meglio compresa utilizzando il seguente diagramma:

![Google1](assets/google1.jpg)

Durante l'elaborazione dei dati di Analytics, i dati scorrono attraverso la pipeline di raccolta dati e in una fase di preelaborazione, che prepara i dati per la generazione di report. Questo passaggio di pre-elaborazione applica la logica di scadenza visita e la logica di persistenza eVar (tra le altre cose) ai dati durante la raccolta. Lo svantaggio principale di questo modello di preelaborazione è che richiede che qualsiasi configurazione venga eseguita in anticipo prima della raccolta dei dati. Ciò significa che qualsiasi modifica alle impostazioni di preelaborazione si applica solo ai nuovi dati da quel momento in poi. Ciò risulta problematico se i dati non vengono ordinati o se le impostazioni non sono state configurate correttamente.

L'elaborazione dei tempi di report è un modo radicalmente diverso di elaborare i dati di Analytics per i report. Anziché predeterminare la logica di elaborazione prima della raccolta dei dati, Analytics ignora il set di dati durante la fase di preelaborazione e applica questa logica ogni volta che viene eseguito un report:

![Google2](assets/google2.jpg)

Questa architettura di elaborazione offre opzioni di reporting molto più flessibili. Ad esempio, puoi modificare il periodo di timeout della visita in qualsiasi periodo di tempo desideri in modo non distruttivo e tali modifiche si riflettono nella persistenza e nei contenitori di segmenti dell'eVar in modo retroattivo, come se aveste applicato tali impostazioni prima della raccolta dei dati. Inoltre, puoi creare un numero qualsiasi di suite di rapporti virtuali, ognuna con diverse opzioni di elaborazione del tempo rapporto basate sulla stessa suite di rapporti di base, senza modificare nessuno dei dati nella suite di rapporti di base.

L'elaborazione dei tempi di rapporto consente inoltre ad Analytics di impedire l'avvio di nuove visite da parte degli hit di background e consente all'SDK [](https://marketing.adobe.com/developer/get-started/mobile/c-measuring-mobile-applications) mobile di segnalare l'avvio di una nuova visita ogni volta che viene attivato un evento di avvio dell'app.

Le seguenti opzioni di configurazione sono attualmente disponibili per le suite di rapporti virtuali con l'opzione Elaborazione ora rapporto abilitata:

* **** Timeout visita: L’impostazione di timeout della visita definisce la quantità di inattività che un visitatore univoco deve avere prima dell’avvio automatico di una nuova visita. Il valore predefinito è 30 minuti. Ad esempio, se imposti il timeout della visita a 15 minuti, viene creato un nuovo raggruppamento visite per ogni sequenza di hit raccolti, separati da 15 minuti di inattività. Questa impostazione ha effetto non solo sui conteggi delle visite, ma anche sulla valutazione dei contenitori dei segmenti delle visite e sulla logica di scadenza delle visite per qualsiasi eVar in scadenza al momento della visita. Una riduzione del timeout per la visita potrebbe aumentare il numero totale di visite nei rapporti, mentre un aumento del timeout per la visita probabilmente ridurrà il numero totale di visite nei rapporti.
* **** Impostazioni delle visite alle app mobili: Per le suite di rapporti contenenti dati generati dalle app mobili tramite gli SDK [di](https://www.adobe.io/apis/cloudplatform/mobile.html)Adobe Mobile, sono disponibili impostazioni di visita aggiuntive. Queste impostazioni non sono distruttive e interessano solo gli hit raccolti tramite gli SDK di Mobile. Queste impostazioni non hanno alcun impatto sui dati raccolti al di fuori dell'SDK di Mobile.
* **** Impedisci agli hit di sfondo di avviare una nuova visita: Gli hit in background vengono raccolti dagli SDK di Mobile quando l'app è in stato di background.
* **** Avvia una nuova visita a ogni lancio dell'app: Oltre al timeout della visita, puoi forzare l'inizio di una visita ogni volta che un evento App Launch è stato registrato dagli SDK di Mobile, indipendentemente dalla finestra di inattività. Questa impostazione influisce sulla metrica visita e sul contenitore del segmento visita, nonché sulla logica di scadenza della visita nelle eVar.
* **** Avvia nuova visita con evento: Una nuova sessione inizia quando un evento viene attivato, a prescindere dal timeout di una sessione. La nuova sessione creata include l’evento che l’ha avviata. Inoltre, potete utilizzare più eventi per avviare una sessione e una nuova sessione viene attivata se nei dati sono osservati degli eventi. Questa impostazione influirà sul conteggio delle visite, sul contenitore di segmentazione delle visite e sulla logica di scadenza delle visite sulle eVar.

L'elaborazione dei tempi di report non supporta tutte le metriche e dimensioni disponibili nei report Analytics tradizionali. Le suite di rapporti virtuali che utilizzano l'elaborazione del tempo di rapporto sono accessibili solo in Analysis Workspace e non saranno accessibili in [!UICONTROL Reports & Analytics], Analisi ad hoc, Data Warehouse, Generatore di report, Feed dati o nell'API di reporting.

Inoltre, l'elaborazione del tempo di report elabora solo i dati che provengono dall'intervallo di date del rapporto (denominato "finestra delle date" di seguito). Ciò significa che i valori eVar impostati su "never expires" per un visitatore prima dell'intervallo di date del rapporto non persistono nelle finestre di rapporto e non vengono visualizzati nei rapporti. Ciò significa anche che le misurazioni della fedeltà dei clienti si basano esclusivamente sui dati presenti nell'intervallo di date del rapporto e non sull'intera cronologia prima dell'intervallo di date del rapporto.

Di seguito è riportato un elenco di metriche e dimensioni che non sono attualmente supportate quando si utilizza l'elaborazione dei tempi di report:

* **** Analytics per Target: Attualmente non supportato. È previsto un sostegno futuro.
* **** Analisi per metriche/dimensioni riservate di Advertising Cloud: Attualmente non supportato. È previsto un sostegno futuro.
* **** Metrica di accesso singolo: Permanentemente non supportato.
* **** Varie elenco: Attualmente non supportato. È previsto un sostegno futuro.
* **** eVar contatore: Permanentemente non supportato.
* **** Variabili canale di marketing: Attualmente non supportato. È previsto un sostegno futuro.
* **** Giorni dall'ultima dimensione di acquisto: Data la natura della finestra Data elaborazione ora rapporto, questa dimensione non è supportata.
* **** Giorni prima della prima dimensione di acquisto: Data la natura della finestra Data elaborazione ora rapporto, questa dimensione non è supportata.
* **** Dimensione frequenza di ritorno: Data la natura della finestra Data elaborazione ora rapporto, questa dimensione non è supportata. È possibile utilizzare un approccio alternativo utilizzando una metrica di conteggio visite in un segmento, oppure utilizzando la metrica visite in un report di istogramma.
* **** Giorni dall’ultima dimensione visita: Data la natura della finestra Data elaborazione ora rapporto, questa dimensione non è supportata.
* **** Dimensione originale pagina di entrata: Data la natura della finestra Data elaborazione ora rapporto, questa dimensione non è supportata.
* **** eVar di allocazione lineare: Attualmente non supportato. È previsto un sostegno futuro.
* **** Dimensione dominio di riferimento originale: Attualmente non supportato. È previsto un sostegno futuro.
* **** Numero visita: Data la natura della finestra Data elaborazione ora rapporto, questa metrica non è supportata. In alternativa, nelle app mobili puoi utilizzare una metrica calcolata che include visitatori/visite con la metrica Installazione app per identificare nuovi visitatori o visite.
* **** Origini dati ID transazione: Attualmente non supportato. È previsto un sostegno futuro.

Di seguito è riportato un elenco di dimensioni e metriche che vengono influenzate a seconda delle impostazioni di elaborazione del tempo rapporto selezionate:

* Se l'opzione "Impedisci agli hit di sfondo di avviare una nuova visita" è abilitata, si verificano le seguenti modifiche. Per ulteriori informazioni, consulta Sessionizzazione basata sul [contesto](vrs-mobile-visit-processing.md) .
   * **** Frequenza rimbalzi/rimbalzi: Gli hit di sfondo non seguiti da un hit in primo piano non vengono considerati come rimbalzo e non contribuiscono alla frequenza di rimbalzo.
   * **** Tempo trascorso Secondi Per Visita: Solo le visite che includono hit in primo piano contribuiscono a questa metrica.
   * **** Tempo trascorso per visita: Solo le visite che includono hit in primo piano contribuiscono a questa metrica.
   * **** Dimensioni e metriche di entrata/uscita: In questa dimensione vengono visualizzate solo le entrate e le uscite dalle visite con hit in primo piano.
   * **** Metrica Visitatori univoci: Visitatori univoci non include i visitatori che avevano solo hit in background nell’intervallo di date del rapporto.
* **** Visite: Le visite riflettono tutte le impostazioni configurate dalla suite di rapporti virtuali, che possono essere diverse dalla suite di rapporti di base.
* **** Eventi serializzati con ID evento: Gli eventi che utilizzano la serializzazione degli eventi con un ID evento sono deduplicati solo per gli eventi che si verificano entro l'intervallo di date del rapporto per un visitatore. Questi eventi non vengono deduplicati in tutte le date o in tutto il mondo a causa della finestra Data elaborazione ora rapporto.
* **** Acquisti/Ricavi/Ordini/Unità: Quando si utilizza l'ID acquisto, queste metriche vengono deduplicate solo per gli ID acquisto duplicati che si verificano all'interno dell'intervallo di date del rapporto per un visitatore anziché in tutte le date o in tutto il mondo a causa della finestra Data elaborazione ora rapporto.
* **** eVar non merchandising/eVar riservate: I valori impostati in una eVar persistono solo se il valore è stato impostato all'interno dell'intervallo di date del rapporto a causa della finestra Data elaborazione ora rapporto. Inoltre, le scadenze basate sull'ora possono scadere con un'ora di anticipo o con un'ora di ritardo se la persistenza si estende per un cambiamento dell'ora legale.
* **** eVar di merchandising/eVar riservate: Vedere sopra. Inoltre, per la sintassi di conversione, in cui il binding è impostato su "qualsiasi evento", viene utilizzato "qualsiasi hit".
* **** Tipo di hit: Questa dimensione specifica se un hit è in primo piano o sullo sfondo.
