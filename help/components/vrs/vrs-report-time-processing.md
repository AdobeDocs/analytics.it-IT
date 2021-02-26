---
description: L'elaborazione dei tempi di rapporto è un'impostazione della suite di rapporti virtuali che consente l'elaborazione dei dati in modo retroattivo e non distruttivo.
title: Elaborazione dell'ora rapporto
uuid: 1a1d82ea-8c93-43cc-8689-cdcf59c309b1
translation-type: tm+mt
source-git-commit: d0fe97b9368cbc4c9e79f9e56adf9786b58dce1a
workflow-type: tm+mt
source-wordcount: '1421'
ht-degree: 3%

---


# Elaborazione dell&#39;ora rapporto

L&#39;elaborazione dei tempi di rapporto è un&#39;impostazione della suite di rapporti virtuali che consente l&#39;elaborazione dei dati in modo retroattivo e non distruttivo.

>[!NOTE]
>
>L&#39;elaborazione dei tempi di rapporto è disponibile solo per  Analysis Workspace.

L&#39;elaborazione dei tempi di report interessa solo i dati nella suite di rapporti virtuali e non ha alcun impatto sulla raccolta di dati o dati nella suite di rapporti di base. La differenza tra l&#39;elaborazione dei tempi di report e l&#39;elaborazione tradizionale di Analytics è meglio compresa utilizzando il seguente diagramma:

![Google1](assets/google1.jpg)

Durante l&#39;elaborazione dei dati di Analytics, i dati scorrono attraverso la pipeline di raccolta dati e in una fase di preelaborazione, che prepara i dati per la generazione di report. Questo passaggio di pre-elaborazione applica la logica di scadenza visita e  logica di persistenza eVar (tra le altre cose) ai dati durante la raccolta. Lo svantaggio principale di questo modello di preelaborazione è che richiede che qualsiasi configurazione venga eseguita in anticipo prima della raccolta dei dati. Ciò significa che qualsiasi modifica alle impostazioni di preelaborazione si applica solo ai nuovi dati da quel momento in poi. Ciò risulta problematico se i dati non vengono ordinati o se le impostazioni non sono state configurate correttamente.

L&#39;elaborazione dei tempi di report è un modo radicalmente diverso di elaborare i dati di Analytics per i report. Anziché predeterminare la logica di elaborazione prima della raccolta dei dati, Analytics ignora il set di dati durante la fase di preelaborazione e applica questa logica ogni volta che viene eseguito un report:

![Google2](assets/google2.jpg)

Questa architettura di elaborazione offre opzioni di reporting molto più flessibili. Ad esempio, puoi modificare il periodo di timeout della visita in qualsiasi periodo di tempo desideri in modo non distruttivo e tali modifiche si riflettono nella persistenza  eVar e nei contenitori dei segmenti retroattivamente, come se aveste applicato tali impostazioni prima della raccolta dei dati. Inoltre, puoi creare un numero qualsiasi di suite di rapporti virtuali, ognuna con diverse opzioni di elaborazione del tempo rapporto basate sulla stessa suite di rapporti di base, senza modificare nessuno dei dati nella suite di rapporti di base.

L&#39;elaborazione dei tempi di rapporto consente inoltre ad Analytics di impedire l&#39;avvio di nuove visite da parte degli hit in background e consente all&#39; [SDK per dispositivi mobili](https://marketing.adobe.com/developer/get-started/mobile/c-measuring-mobile-applications) di comunicare al reporting l&#39;avvio di una nuova visita ogni volta che viene attivato un evento di avvio dell&#39;app.

Le seguenti opzioni di configurazione sono attualmente disponibili per le suite di rapporti virtuali con l&#39;opzione Elaborazione ora rapporto abilitata:

* **Timeout visita:** l’impostazione di timeout visita definisce la quantità di inattività che un visitatore univoco deve avere prima dell’avvio automatico di una nuova visita. Il valore predefinito è 30 minuti. Ad esempio, se imposti il timeout della visita a 15 minuti, viene creato un nuovo raggruppamento visite per ogni sequenza di hit raccolti, separati da 15 minuti di inattività. Questa impostazione ha effetto non solo sui conteggi delle visite, ma anche sulla valutazione dei contenitori dei segmenti delle visite e sulla logica di scadenza delle visite per qualsiasi eVar in scadenza al momento della visita. Una riduzione del timeout per la visita potrebbe aumentare il numero totale di visite nei rapporti, mentre un aumento del timeout per la visita probabilmente ridurrà il numero totale di visite nei rapporti.
* **Impostazioni delle visite delle app mobili:** per le suite di rapporti contenenti dati generati dalle app mobili tramite gli SDK [ di Mobile ](https://www.adobe.io/apis/cloudplatform/mobile.html) Adobe, sono disponibili impostazioni aggiuntive per le visite. Queste impostazioni non sono distruttive e interessano solo gli hit raccolti tramite gli SDK di Mobile. Queste impostazioni non hanno alcun impatto sui dati raccolti al di fuori dell&#39;SDK di Mobile.
* **Impedisci agli hit in background di avviare una nuova visita: gli hit in** background vengono raccolti dagli SDK di Mobile quando l&#39;app è in stato di background.
* **Avvia una nuova visita a ogni avvio dell’app:** oltre al timeout previsto per la visita, puoi forzare l’inizio di una visita ogni volta che un evento App Launch è stato registrato dagli SDK di Mobile, indipendentemente dalla finestra di inattività. Questa impostazione influisce sulla metrica visita e sul contenitore del segmento visita, nonché sulla logica di scadenza della visita nelle eVar.
* **Avvia nuova visita con evento:** una nuova sessione inizia quando un evento viene attivato, a prescindere dal timeout di una sessione. La nuova sessione creata include l’evento che l’ha avviata. Inoltre, puoi utilizzare più eventi per avviare una sessione e una nuova sessione viene avviata se nei dati viene rilevato uno qualsiasi degli eventi. Questa impostazione influirà sul conteggio delle visite, sul contenitore di segmentazione delle visite e sulla logica di scadenza delle visite sulle eVar.

L&#39;elaborazione dei tempi di report non supporta tutte le metriche e dimensioni disponibili nei report Analytics tradizionali. Le suite di rapporti virtuali che utilizzano l&#39;elaborazione del tempo di rapporto sono accessibili solo in  Analysis Workspace e non saranno accessibili in [!UICONTROL Reports & Analytics], Data Warehouse, Report Builder, feed di dati o nell&#39;API di reporting.

Inoltre, l&#39;elaborazione del tempo di report elabora solo i dati che provengono dall&#39;intervallo di date del rapporto (denominato &quot;finestra delle date&quot; di seguito). Ciò significa che  valori di eVar impostati su &quot;never expires&quot; per un visitatore prima dell&#39;intervallo di date del rapporto non persistono nelle finestre di rapporto e non vengono visualizzati nei rapporti. Ciò significa anche che le misurazioni della fidelizzazione dei clienti si basano esclusivamente sui dati presenti nell&#39;intervallo di date del rapporto e non sull&#39;intera cronologia prima dell&#39;intervallo di date del rapporto.

Di seguito è riportato un elenco di metriche e dimensioni che non sono attualmente supportate quando si utilizza l&#39;elaborazione dei tempi di report:

* **Analytics per Target:** attualmente non supportato. È previsto un sostegno futuro.
* **Analisi per  metriche/dimensioni riservate Advertising Cloud:** attualmente non supportate. È previsto un sostegno futuro.
* **Metrica di accesso singolo:** permanentemente non supportata.
* **Var elenco:** Attualmente non supportate. È previsto un sostegno futuro.
* **Contrassegno eVar:** permanentemente non supportato.
* **Variabili canale di marketing:** attualmente non supportate. È previsto un sostegno futuro.
* **Giorni dall&#39;ultimo Dimension di acquisto:** a causa della natura della finestra Data elaborazione ora rapporto, questa dimensione non è supportata.
* **Giorni prima del primo Dimension di acquisto:** a causa della natura della finestra Data elaborazione ora rapporto, questa dimensione non è supportata.
* **Dimension di frequenza di restituzione:** a causa della natura della finestra Data elaborazione ora rapporto, questa dimensione non è supportata. È possibile utilizzare un approccio alternativo utilizzando una metrica di conteggio visite in un segmento, oppure utilizzando la metrica visite in un report di istogramma.
* **Dimension Giorni dall’ultima visita:** a causa della natura della finestra Data elaborazione ora rapporto, questa dimensione non è supportata.
* **Pagina di entrata Dimension originale:** a causa della natura della finestra Data elaborazione ora rapporto, questa dimensione non è supportata.
* **eVar di allocazione lineare:** attualmente non supportate. È previsto un sostegno futuro.
* **Dimension di dominio di riferimento originale:** attualmente non supportato. È previsto un sostegno futuro.
* **Numero visita:** a causa della natura della finestra Data elaborazione ora rapporto, questa metrica non è supportata. In alternativa, nelle app mobili puoi utilizzare una metrica calcolata che include visitatori/visite con la metrica Installazione app per identificare nuovi visitatori o visite.
* **Origini dati ID transazione:** attualmente non supportate. È previsto un sostegno futuro.

Di seguito è riportato un elenco di dimensioni e metriche che vengono influenzate a seconda delle impostazioni di elaborazione del tempo rapporto selezionate:

* Se l&#39;opzione &quot;Impedisci agli hit di sfondo di avviare una nuova visita&quot; è abilitata, si verificano le seguenti modifiche. Per ulteriori informazioni, vedere [Sessionizzazione in base al contesto](vrs-mobile-visit-processing.md).
   * **Frequenza rimbalzi/rimbalzi: gli hit** di sfondo non seguiti dall’hit in primo piano non vengono considerati come rimbalzi e non contribuiscono alla frequenza di rimbalzo.
   * **Tempo trascorso secondi per visita:** solo le visite che includono hit in primo piano contribuiscono a questa metrica.
   * **Tempo trascorso per visita:** solo le visite che includono hit in primo piano contribuiscono a questa metrica.
   * **Metriche e Dimension di entrata/uscita: in questa dimensione vengono visualizzate solo le voci e le uscite** delle visite con hit in primo piano.
   * **Metrica Visitatori univoci:Visitatori** unici non include i visitatori che avevano solo hit in background nell’intervallo di date del rapporto.
* **Visite:** le visite riflettono le impostazioni configurate dalla suite di rapporti virtuali, che possono essere diverse dalla suite di rapporti di base.
* **Eventi serializzati con ID evento:** Eventi che utilizzano la serializzazione evento con un ID evento sono deduplicati solo per gli eventi che si verificano entro l’intervallo di date del rapporto per un visitatore. Questi eventi non vengono deduplicati in tutte le date o in tutto il mondo a causa della finestra Data elaborazione ora rapporto.
* **Acquisti/Ricavi/Ordini/Unità:** quando si utilizza l&#39;ID acquisto, queste metriche vengono deduplicate solo per gli ID acquisto duplicati che si verificano all&#39;interno dell&#39;intervallo di date del rapporto per un visitatore anziché in tutte le date o in tutti i visitatori a livello globale a causa della finestra Data elaborazione ora rapporto.
* **eVar non merchandising/eVar riservate:** I valori impostati in un eVar  persistono solo se il valore è stato impostato all&#39;interno dell&#39;intervallo di date del rapporto a causa della finestra Data elaborazione ora rapporto. Inoltre, le scadenze basate sull&#39;ora possono scadere con un&#39;ora di anticipo o con un&#39;ora di ritardo se la persistenza si estende per un cambiamento dell&#39;ora legale.
* **eVar di merchandising/eVar riservate:** vedi sopra. Inoltre, per la sintassi di conversione, in cui il binding è impostato su &quot;qualsiasi evento&quot;, viene utilizzato &quot;qualsiasi hit&quot;.
* **Tipo di hit:** questa dimensione specifica se un hit è in primo piano o sullo sfondo.
