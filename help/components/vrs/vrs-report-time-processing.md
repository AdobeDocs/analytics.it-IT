---
description: L'elaborazione dei tempi di report è un'impostazione suite di rapporti virtuale che consente l'elaborazione di dati in modalità retroattiva e non distruttiva.
seo-description: L'elaborazione dei tempi di report è un'impostazione suite di rapporti virtuale che consente l'elaborazione di dati in modalità retroattiva e non distruttiva.
seo-title: Elaborazione dell'ora rapporto
title: Elaborazione dell'ora rapporto
uuid: 1 a 1 d 82 ea -8 c 93-43 cc -8689-cdcf 59 c 309 b 1
translation-type: tm+mt
source-git-commit: 658aba8a456f5760d4871fdc941150d64e9e2e94

---


# Elaborazione dell'ora rapporto

L'elaborazione dei tempi di report è un'impostazione suite di rapporti virtuale che consente l'elaborazione di dati in modalità retroattiva e non distruttiva.

> [!NOTE] Elaborazione tempo rapporto è disponibile solo per Analysis Workspace.

L'elaborazione dei tempi di rapporto incide solo sui dati nella suite di rapporti virtuali e non interessa alcun dato o raccolta dati nella suite di rapporti di base. La differenza tra Elaborazione dei tempi di report e Elaborazione tradizionale Analytics è più semplice, utilizzando il diagramma seguente:

![Google1](assets/google1.jpg)

Durante l'elaborazione dei dati di Analytics, i dati scorrono attraverso il pipeline della raccolta dati e in un passaggio di pre-elaborazione, che prepara i dati per il reporting. Questo passaggio di pre-elaborazione applica logica di scadenza visita e logica di persistenza evar (tra le altre cose) ai dati durante la raccolta. Il principale svantaggio di questo modello di pre-elaborazione è che richiede che qualsiasi configurazione venga eseguita in anticipo prima della raccolta dei dati. Ciò significa che tutte le modifiche apportate alle impostazioni di pre-elaborazione si applicano solo a nuovi dati da quel momento in avanti. Questo è problematico se i dati non vengono visualizzati o se le impostazioni sono state configurate in modo errato.

L'elaborazione dei tempi di report è un metodo sostanzialmente diverso per elaborare i dati di Analytics a scopo di reportistica. Invece di determinare la logica di elaborazione prima della raccolta dei dati, Analytics ignora il set di dati durante il passaggio di pre-elaborazione e applica questa logica ogni volta che viene eseguito un report:

![Google2](assets/google2.jpg)

Questa architettura di elaborazione consente opzioni di reporting molto più flessibili. Ad esempio, puoi cambiare il periodo di timeout visite in un qualsiasi periodo di tempo desiderato, e tali modifiche vengono riportate nella persistenza evar e i contenitori segmentano in modo retroattivo, come se fossero stati applicati prima della raccolta dei dati. Inoltre, puoi creare un numero qualsiasi di suite di rapporti virtuali, ciascuna con opzioni diverse di Elaborazione temporale basate sulla stessa suite di rapporti base, senza alterare nessuno dei dati nella suite di rapporti di base.

Elaborazione tempo rapporto consente anche ad Analytics di evitare che gli hit in background inizino nuove visite e consentano all' [SDK](https://marketing.adobe.com/developer/get-started/mobile/c-measuring-mobile-applications) di Mobile di comunicare al reporting di avviare una nuova visita ogni volta che viene attivato un evento App Launch.

Le seguenti opzioni di configurazione sono disponibili per le suite di rapporti virtuali con l'elaborazione dei tempi di rapporto abilitata:

* **Timeout visita:** L'impostazione Timeout visita definisce la quantità di inattività che un visitatore univoco deve avere prima che venga avviata automaticamente una nuova visita. Impostazione predefinita: 30 minuti. Ad esempio, se imposti il timeout della visita su 15 minuti, viene creato un nuovo raggruppamento delle visite per ogni sequenza di hit raccolti, separati da 15 minuti di inattività. Questa impostazione interessa non solo i conteggi delle visite, ma anche il modo in cui vengono valutati i contenitori dei segmenti di visita e la logica di scadenza delle visite per qualsiasi evar che scade alla visita. Diminuendo il timeout visita, probabilmente aumenterà il numero totale di visite nei rapporti, aumentando probabilmente il numero totale di visite nei rapporti.
* **Impostazioni visita app mobile:** Per le suite di rapporti contenenti dati generati dalle app mobili tramite gli SDK [di Adobe Mobile](https://www.adobe.io/apis/cloudplatform/mobile.html), sono disponibili impostazioni aggiuntive per le visite. Queste impostazioni sono non distruttive e interessano solo gli hit raccolti tramite gli SDK di Mobile. Queste impostazioni non hanno alcun impatto sui dati raccolti all'esterno dell'SDK di Mobile.
* **Impedisci agli hit di background di iniziare una nuova visita:** Gli hit in background vengono raccolti dagli SDK di Mobile quando l'app è in stato di sfondo.
* **Avvia una nuova visita su ogni avvio app:** Oltre al timeout della visita, puoi forzare la visita di una visita ogni volta che un evento App Launch è stato registrato dagli SDK Mobile, a prescindere dalla finestra inattività. Questa impostazione influisce sulla metrica visita e sul contenitore del segmento visite, oltre che sulla logica di scadenza delle visite sulle evar.
* **Inizia nuova visita con evento:** Quando un evento viene avviato, viene avviata una nuova sessione, a prescindere dal timeout di una sessione. La nuova sessione appena creata include l'evento che la ha avviata. Inoltre, è possibile utilizzare più eventi per avviare una sessione e una nuova sessione viene attivata se uno di questi eventi viene osservato nei dati. Questa impostazione influirà sul conteggio delle visite, sul contenitore di segmentazione visite e sulla logica di scadenza delle visite sulle evar.

L'elaborazione dei tempi di report non supporta tutte le metriche e le dimensioni disponibili nei tradizionali rapporti di Analytics. Le suite di rapporti virtuali che utilizzano l'elaborazione dei tempi di report sono accessibili solo in Analysis Workspace e non sono accessibili in [!UICONTROL Reports & Analytics], Analisi ad hoc, Data Warehouse, Generatore di report, Feed dati o nell'API di reporting.

Inoltre, l'elaborazione dei tempi di rapporto elabora solo i dati derivanti dall'intervallo di date del rapporto (denominato "data della data" sotto). Ciò significa che i valori evar impostati per «non scade» per un visitatore prima dell'intervallo di date del rapporto non rimangono nelle finestre di reporting e non vengono visualizzati nei report. Ciò significa anche che le misurazioni della fedeltà dei clienti si basano unicamente sui dati presenti nell'intervallo di date del rapporto e non sull'intera cronologia prima dell'intervallo di date del rapporto.

Di seguito è riportato un elenco di metriche e dimensioni non supportate quando si utilizza l'elaborazione dei tempi di rapporto:

* **Analytics per Target:** Attualmente non supportato. Il supporto futuro è pianificato.
* **Analytics for Advertising Metrics/Dimensions metrics/dimensions:** Attualmente non supportato. Il supporto futuro è pianificato.
* **Metrica di accesso singolo:** Non supportato definitivamente.
* **Variabili elenco:** Attualmente non supportato. Il supporto futuro è pianificato.
* **Evar:** Non supportato definitivamente.
* **Variabili di Marketing Channels:** Attualmente non supportato. Il supporto futuro è pianificato.
* **Giorni dall'ultimo numero di acquisto:** A causa della natura della finestra Data elaborazione tempo rapporto, questa dimensione non è supportata.
* **Giorni prima della dimensione del primo acquisto:** A causa della natura della finestra Data elaborazione tempo rapporto, questa dimensione non è supportata.
* **Dimensione frequenza restituita:** A causa della natura della finestra Data elaborazione tempo rapporto, questa dimensione non è supportata. È possibile utilizzare un approccio alternativo utilizzando una metrica di conteggio delle visite in un segmento o la metrica visita in un report istogramma.
* **Giorni dall'ultima dimensione visita:** A causa della natura della finestra Data elaborazione tempo rapporto, questa dimensione non è supportata.
* **Dimensione originale pagina di partecipazione:** A causa della natura della finestra Data elaborazione tempo rapporto, questa dimensione non è supportata.
* **Evar di allocazione lineare:** Attualmente non supportato. Il supporto futuro è pianificato.
* **Dimensione dominio di riferimento originale:** Attualmente non supportato. Il supporto futuro è pianificato.
* **Numero visita:** A causa della natura della finestra Data di elaborazione tempo rapporto, questa metrica non è supportata. In alternativa alle app mobili, puoi utilizzare una metrica calcolata, tra cui visitatori/visite con la metrica Installazione app per identificare nuovi visitatori o visite.
* **Origini dati ID transazione:** Attualmente non supportato. Il supporto futuro è pianificato.

Di seguito è riportato un elenco di dimensioni e metriche interessate a seconda delle impostazioni di elaborazione del tempo di rapporto selezionate:

* Se è abilitato l'opzione Impedisci agli hit di background di avviare una nuova visita, si verificano le seguenti modifiche. Per [ulteriori informazioni, consulta Sessionizzazione](vrs-mobile-visit-processing.md) basata sul contesto.
   * **Bounce/Bounce Rate:** Gli hit in background non seguiti da un hit in primo piano non sono considerati rimbalzi e non contribuiscono alla velocità di rimbalzo.
   * **Tempo trascorso secondi per visita:** Solo le visite che includono hit in primo piano contribuiscono a questa metrica.
   * **Tempo trascorso per visita:** Solo le visite che includono hit in primo piano contribuiscono a questa metrica.
   * **Dimensioni di entrata/uscita e metriche:** In questa dimensione appaiono solo le entrate e uscite dalle visite con hit in primo piano.
   * **Metrica Visitatori unici:** Visitatori univoci non include visitatori che avevano solo hit di sfondo nell'intervallo di date del rapporto.
* **Visite:** Le visite riflettono qualsiasi impostazione configurata dalla suite di rapporti virtuali, che può essere diversa dalla suite di rapporti di base.
* **Eventi serializzati con ID evento:** Gli eventi che utilizzano la serializzazione evento con un ID evento vengono deduplicati solo per gli eventi che si verificano nell'intervallo di date del rapporto per un visitatore. Questi eventi non vengono deduplicati in tutte le date o in tutti i visitatori a causa della cronologia Data elaborazione tempo rapporto.
* **Acquisti/Entrate/Ordini/Unità:** Quando l'ID acquisto viene utilizzato, queste metriche vengono deduplicate solo per gli ID di acquisto duplicati che si verificano nell'intervallo di date del rapporto per un visitatore piuttosto che per tutta la data o i visitatori a causa della finestra temporale di Elaborazione tempo rapporto.
* **Evar non di merchandising/evar riservati:** I valori impostati in una evar rimangono invariati solo se il valore è stato impostato entro l'intervallo date del rapporto a causa della finestra della data di elaborazione del tempo report. Inoltre, le scadenza temporizzate possono scadere un'ora prima o un'ora in meno se la persistenza si estende su un cambiamento di orario legale.
* **Evar per merchandising/evar riservati:** Vedi sopra. Inoltre, per la sintassi di conversione, dove il binding è impostato su "qualsiasi evento", viene utilizzato "any hit".
* **Tipo di hit:** Questa dimensione specifica se un hit è in primo piano o in background.
