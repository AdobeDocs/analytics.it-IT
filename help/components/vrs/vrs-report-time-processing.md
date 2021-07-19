---
description: L’elaborazione dei tempi di report è un’impostazione della suite di rapporti virtuali che consente l’elaborazione dei dati in modo retroattivo e non distruttivo.
title: Elaborazione dell'ora rapporto
uuid: 1a1d82ea-8c93-43cc-8689-cdcf59c309b1
exl-id: 3742b9d1-f1fb-4690-bd44-b4719ff9d9bc
source-git-commit: 3867573780a791ec4cf2b2ceda33707d972f3f5c
workflow-type: tm+mt
source-wordcount: '1419'
ht-degree: 3%

---

# Elaborazione dell&#39;ora rapporto

L’elaborazione dei tempi di report è un’impostazione della suite di rapporti virtuali che consente l’elaborazione dei dati in modo retroattivo e non distruttivo.

>[!NOTE]
>
>L’elaborazione dei tempi di report è disponibile solo per Analysis Workspace.

L’elaborazione al momento della generazione dei rapporti influisce solo sui dati nella suite di rapporti virtuali e non influisce su alcun dato o raccolta di dati nella suite di rapporti di base. La differenza tra l’elaborazione dei tempi di report e l’elaborazione tradizionale di Analytics è meglio compresa utilizzando il seguente diagramma:

![Google1](assets/google1.jpg)

Durante l’elaborazione dei dati di Analytics, i dati scorrono attraverso la pipeline di raccolta dati e in una fase di preelaborazione, che prepara i dati per la generazione di rapporti. Questa fase di preelaborazione applica la logica di scadenza della visita e la logica di persistenza eVar (tra le altre cose) ai dati durante la raccolta. Lo svantaggio principale di questo modello di preelaborazione è che richiede che qualsiasi configurazione venga eseguita in anticipo prima della raccolta dei dati. Ciò significa che eventuali modifiche alle impostazioni di preelaborazione si applicano solo ai nuovi dati da quel momento in poi. Ciò è problematico se i dati arrivano fuori ordine o se le impostazioni sono state configurate in modo errato.

L’elaborazione al momento della generazione dei rapporti è un modo fondamentalmente diverso di elaborare i dati di Analytics per la generazione dei rapporti. Anziché predeterminare la logica di elaborazione prima della raccolta dei dati, Analytics ignora il set di dati durante la fase di preelaborazione e applica questa logica ogni volta che viene eseguito un rapporto:

![Google2](assets/google2.jpg)

Questa architettura di elaborazione consente opzioni di reporting molto più flessibili. Ad esempio, puoi modificare il periodo di timeout della visita in qualsiasi momento in modo non distruttivo e tali modifiche si riflettono nella persistenza eVar e nei contenitori di segmenti retroattivamente come se aveste applicato quelle impostazioni prima che i dati venissero raccolti. Inoltre, puoi creare un numero qualsiasi di suite di rapporti virtuali, ciascuna con diverse opzioni di elaborazione dei tempi di report basate sulla stessa suite di rapporti di base, senza modificare nessuno dei dati nella suite di rapporti di base.

L’elaborazione dei tempi di report consente inoltre ad Analytics di impedire l’avvio di nuove visite in background e consente all’ [SDK mobile](https://www.adobe.io/apis/cloudplatform/mobile.html) di comunicare al reporting di avviare una nuova visita ogni volta che viene attivato un evento di App Launch.

Le seguenti opzioni di configurazione sono attualmente disponibili per le suite di rapporti virtuali con l’elaborazione al momento della generazione del rapporto abilitata:

* **Timeout visita:** l’impostazione di timeout visita definisce la quantità di inattività che un visitatore univoco deve avere prima dell’avvio automatico di una nuova visita. Il valore predefinito è 30 minuti. Ad esempio, se imposti il timeout di visita a 15 minuti, viene creato un nuovo raggruppamento di visite per ogni sequenza di hit raccolta, separate da 15 minuti di inattività. Questa impostazione ha un impatto non solo sui conteggi delle visite, ma anche sulla valutazione dei contenitori dei segmenti di visite e sulla logica di scadenza delle visite per tutte le eVar in scadenza alla visita. Una diminuzione del timeout della visita determinerà probabilmente un aumento del numero totale di visite nei rapporti, mentre un aumento del timeout della visita ridurrà probabilmente il numero totale di visite nei rapporti.
* **Impostazioni delle visite all’app mobile:** per le suite di rapporti contenenti dati generati dalle app mobili tramite gli SDK per dispositivi mobili di  [Adobe](https://www.adobe.io/apis/cloudplatform/mobile.html), sono disponibili altre impostazioni di visita. Queste impostazioni non sono distruttive e influiscono solo sugli hit raccolti tramite gli SDK di Mobile. Queste impostazioni non hanno alcun impatto sui dati raccolti al di fuori dell&#39;SDK di Mobile.
* **Impedisci agli hit in background di avviare una nuova visita:** gli hit in background vengono raccolti dagli SDK di Mobile quando l’app è in background.
* **Avvia una nuova visita su ogni avvio dell’app:** oltre al timeout previsto per la visita, puoi forzare l’inizio di una visita ogni volta che un evento App Launch è stato registrato dagli SDK di Mobile, indipendentemente dalla finestra di inattività. Questa impostazione influisce sulla metrica di visita e sul contenitore del segmento di visita, nonché sulla logica di scadenza della visita sulle eVar.
* **Avvia nuova visita con evento:** viene avviata una nuova sessione quando viene attivato un evento, a prescindere dal timeout di una sessione. La nuova sessione creata include l’evento che l’ha avviata. Inoltre, puoi utilizzare più eventi per avviare una sessione e una nuova sessione viene avviata se nei dati viene rilevato uno qualsiasi degli eventi. Questa impostazione influisce sul conteggio delle visite, sul contenitore di segmentazione delle visite e sulla logica di scadenza delle visite sugli eVar.

L’elaborazione dei tempi di report non supporta tutte le metriche e dimensioni disponibili nel reporting tradizionale di Analytics. Le suite di rapporti virtuali che utilizzano l’elaborazione al momento della generazione dei rapporti sono accessibili solo in Analysis Workspace e non in [!UICONTROL Reports & Analytics], Data Warehouse, Report Builder, feed di dati o nelle API di reporting.

Inoltre, l’elaborazione dell’ora rapporto elabora solo i dati provenienti dall’intervallo di date del rapporto (in seguito denominato &quot;finestra della data&quot;). Ciò significa che i valori di eVar impostati su &quot;non scade mai&quot; per un visitatore prima dell’intervallo di date del rapporto non persistono nelle finestre di reporting e non compaiono nei rapporti. Ciò significa anche che le misurazioni della fidelizzazione dei clienti si basano esclusivamente sui dati presenti nell’intervallo di date del rapporto e non sull’intera cronologia prima dell’intervallo di date del rapporto.

Di seguito è riportato un elenco di metriche e dimensioni attualmente non supportate quando si utilizza l’ elaborazione al momento del rapporto :

* **Analytics for Target:** attualmente non supportato. È previsto un supporto futuro.
* **Analytics per metriche/dimensioni riservate Advertising Cloud:** al momento non supportato. È previsto un supporto futuro.
* **Metrica ad accesso singolo:** permanentemente non supportata.
* **Var elenco:** attualmente non supportate. È previsto un supporto futuro.
* **eVar del contatore:** permanentemente non supportato.
* **Variabili dei canali di marketing:** al momento non supportate. È previsto un supporto futuro.
* **Giorni dall’ultimo Dimension di acquisto:** a causa della natura della finestra a comparsa Data di elaborazione ora rapporto, questa dimensione non è supportata.
* **Giorni precedenti al primo Dimension di acquisto:** a causa della natura della finestra a comparsa Data di elaborazione ora rapporto, questa dimensione non è supportata.
* **Dimension di frequenza di ritorno:** a causa della natura della finestra a discesa Data di elaborazione ora rapporto, questa dimensione non è supportata. È possibile un approccio alternativo utilizzando una metrica di conteggio delle visite in un segmento o utilizzando la metrica di visita in un rapporto istogramma.
* **Dimension Giorni dall’ultima visita:** a causa della natura della finestra a comparsa Data di elaborazione ora rapporto, questa dimensione non è supportata.
* **Dimension originale pagina di ingresso:** a causa della natura della finestra a discesa Data di elaborazione ora rapporto, questa dimensione non è supportata.
* **eVar di allocazione lineare:** attualmente non supportate. È previsto un supporto futuro.
* **Dimension di dominio di riferimento originale:** attualmente non supportato. È previsto un supporto futuro.
* **Numero visita:** a causa della natura della finestra a discesa Data di elaborazione dell’ora rapporto, questa metrica non è supportata. In alternativa, nelle app per dispositivi mobili, puoi utilizzare una metrica calcolata che include visitatori/visite con la metrica Installazione app per identificare nuovi visitatori o visite.
* **Origini dati ID transazione:** attualmente non supportate. È previsto un supporto futuro.

Di seguito è riportato un elenco di dimensioni e metriche che sono interessate a seconda delle impostazioni di elaborazione al momento del rapporto selezionate:

* Se l’opzione &quot;Impedisci agli hit di sfondo di avviare una nuova visita&quot; è abilitata, si verificano le seguenti modifiche. Per ulteriori informazioni, consulta [Sessionizzazione in base al contesto](vrs-mobile-visit-processing.md) .
   * **Frequenza rimbalzi/rimbalzi:** gli hit di sfondo non seguiti da un hit in primo piano non sono considerati come non recapitati e non contribuiscono alla frequenza di rimbalzo.
   * **Tempo trascorso in secondi per visita:** solo le visite che includono hit in primo piano contribuiscono a questa metrica.
   * **Tempo trascorso per visita:** solo le visite che includono hit in primo piano contribuiscono a questa metrica.
   * **Dimension e metriche di ingresso/uscita:** in questa dimensione vengono visualizzate solo le entrate e le uscite dalle visite con hit in primo piano.
   * **Metrica Visitatori univoci:** i Visitatori unici non includono i visitatori che avevano solo hit di background nell’intervallo di date del rapporto.
* **Visite:** le visite riflettono le impostazioni configurate dalla suite di rapporti virtuali, che possono essere diverse dalla suite di rapporti di base.
* **Eventi serializzati con ID evento:** gli eventi che utilizzano la serializzazione degli eventi con un ID evento vengono deduplicati solo per gli eventi che si verificano all’interno dell’intervallo di date del rapporto per un visitatore. Questi eventi non vengono deduplicati in tutte le date o in tutto il mondo a causa della finestra a comparsa Data elaborazione ora rapporto .
* **Acquisti/Entrate/Ordini/Unità:** quando si utilizza l’ID acquisto, queste metriche vengono deduplicate solo per gli ID acquisto duplicati che si verificano entro l’intervallo di date del rapporto per un visitatore e non in tutte le date o i visitatori a livello globale a causa della finestra a discesa Data elaborazione ora rapporto .
* **eVar non merchandising/eVar riservate:** i valori impostati in un eVar persistono solo se il valore è stato impostato all&#39;interno dell&#39;intervallo di date del rapporto a causa della finestra della data di elaborazione dell&#39;ora rapporto. Inoltre, le scadenze basate sul tempo possono scadere con un’ora di anticipo o con un’ora di ritardo se la persistenza si estende per un cambiamento dell’ora legale.
* **eVar per merchandising/eVar riservate:** vedi sopra. Inoltre, per la sintassi di conversione, in cui il binding è impostato su &quot;qualsiasi evento&quot;, viene utilizzato invece &quot;qualsiasi hit&quot;.
* **Tipo di hit:** questa dimensione specifica se un hit è in primo piano o in background.
