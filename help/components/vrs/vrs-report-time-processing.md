---
description: L’elaborazione dei tempi di report è un’impostazione della suite di rapporti virtuali che consente l’elaborazione dei dati in modo retroattivo e non distruttivo.
title: Elaborazione dell'ora rapporto
feature: VRS
exl-id: 3742b9d1-f1fb-4690-bd44-b4719ff9d9bc
source-git-commit: df16d37de742d96f66fd74d7a7b47729f0454fd5
workflow-type: tm+mt
source-wordcount: '1396'
ht-degree: 4%

---

# Elaborazione dell&#39;ora rapporto

[!UICONTROL Report time processing] è un’impostazione di suite di rapporti virtuale che consente l’elaborazione dei dati in modo retroattivo e non distruttivo.

>[!NOTE]
>
>[!UICONTROL Report Time Processing] è disponibile solo per Analysis Workspace.

[!UICONTROL Report Time Processing] influisce solo sui dati della suite di rapporti virtuali e non su alcun dato o raccolta di dati nella suite di rapporti di base. La differenza tra [!UICONTROL Report Time Processing] e l’elaborazione tradizionale di Analytics è meglio intesa utilizzando il seguente diagramma:

![Google1](assets/google1.jpg)

Durante l’elaborazione dei dati di Analytics, i dati scorrono attraverso la pipeline di raccolta dati e in una fase di preelaborazione, che prepara i dati per la generazione di rapporti. Questa fase di preelaborazione applica la logica di scadenza della visita e la logica di persistenza eVar (tra le altre cose) ai dati durante la raccolta. Lo svantaggio principale di questo modello di preelaborazione è che richiede che qualsiasi configurazione venga eseguita in anticipo prima della raccolta dei dati. Ciò significa che eventuali modifiche alle impostazioni di preelaborazione si applicano solo ai nuovi dati da quel momento in poi. Ciò è problematico se i dati arrivano fuori ordine o se le impostazioni sono state configurate in modo errato.

[!UICONTROL Report Time Processing] è un modo fondamentalmente diverso di elaborare i dati di Analytics per la generazione di rapporti. Anziché predeterminare la logica di elaborazione prima della raccolta dei dati, Analytics ignora il set di dati durante la fase di preelaborazione e applica questa logica ogni volta che viene eseguito un rapporto:

![Google2](assets/google2.jpg)

Questa architettura di elaborazione consente opzioni di reporting molto più flessibili. Ad esempio, puoi modificare il periodo di timeout della visita in qualsiasi momento in modo non distruttivo e tali modifiche si riflettono nella persistenza eVar e nei contenitori di segmenti retroattivamente come se aveste applicato quelle impostazioni prima che i dati venissero raccolti. Inoltre, puoi creare un numero qualsiasi di suite di rapporti virtuali, ciascuna con diverse opzioni di elaborazione dei tempi di report basate sulla stessa suite di rapporti di base, senza modificare nessuno dei dati nella suite di rapporti di base.

[!UICONTROL Report Time Processing] consente inoltre ad Analytics di impedire l’avvio di nuove visite in background e consente [Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/docs/mobile.html) per comunicare al reporting di avviare una nuova visita ogni volta che viene attivato un evento App Launch.

## Opzioni di configurazione

Le seguenti opzioni di configurazione sono attualmente disponibili per le suite di rapporti virtuali con l’elaborazione al momento della generazione del rapporto abilitata:

* **[!UICONTROL Visit Timeout]:** L’impostazione di timeout visita definisce la quantità di inattività che un visitatore univoco deve avere prima dell’avvio automatico di una nuova visita. Il valore predefinito è 30 minuti. Ad esempio, se imposti il timeout di visita a 15 minuti, viene creato un nuovo raggruppamento di visite per ogni sequenza di hit raccolta, separate da 15 minuti di inattività. Questa impostazione ha un impatto non solo sui conteggi delle visite, ma anche sulla valutazione dei contenitori dei segmenti di visite e sulla logica di scadenza delle visite per tutte le eVar in scadenza alla visita. Una diminuzione del timeout della visita determinerà probabilmente un aumento del numero totale di visite nei rapporti, mentre un aumento del timeout della visita ridurrà probabilmente il numero totale di visite nei rapporti.
* **[!UICONTROL Mobile App Visit Settings]:** Per le suite di rapporti contenenti dati generati da app mobili tramite [SDK di Adobe Mobile](https://experienceleague.adobe.com/docs/mobile.html), sono disponibili altre impostazioni di visita. Queste impostazioni non sono distruttive e influiscono solo sugli hit raccolti tramite gli SDK di Mobile. Queste impostazioni non hanno alcun impatto sui dati raccolti al di fuori dell&#39;SDK di Mobile.
* **[!UICONTROL Prevent Background Hits from starting a new Visit]:** Gli hit in background vengono raccolti dagli SDK di Mobile quando l&#39;app è in background.
* **[!UICONTROL Start a New Visit upon each App Launch]:** Oltre al timeout previsto per la visita, puoi forzare l’inizio di una visita ogni volta che un evento App Launch è stato registrato dagli SDK Mobile, indipendentemente dalla finestra di inattività. Questa impostazione influisce sulla metrica di visita e sul contenitore del segmento di visita, nonché sulla logica di scadenza della visita sulle eVar.
* **[!UICONTROL Start New Visit with Event]:** Viene avviata una nuova sessione quando un evento viene attivato, a prescindere dal timeout di una sessione. La nuova sessione creata include l’evento che l’ha avviata. Inoltre, puoi utilizzare più eventi per avviare una sessione e una nuova sessione viene avviata se nei dati viene rilevato uno qualsiasi degli eventi. Questa impostazione influisce sul conteggio delle visite, sul contenitore di segmentazione delle visite e sulla logica di scadenza delle visite sugli eVar.

Ecco un video sull’avvio di una nuova visita con un evento:

>[!VIDEO](https://video.tv.adobe.com/v/23129/?quality=12)

## Limiti di elaborazione dei tempi di report

L’elaborazione dei tempi di report non supporta tutte le metriche e dimensioni disponibili nel reporting tradizionale di Analytics. Le suite di rapporti virtuali che utilizzano l’elaborazione al momento della generazione dei rapporti sono accessibili solo in Analysis Workspace e non in [!UICONTROL Reports & Analytics], Data Warehouse, Report Builder, feed di dati o API di reporting.

Inoltre, l’elaborazione dell’ora rapporto elabora solo i dati provenienti dall’intervallo di date del rapporto (in seguito denominato &quot;finestra della data&quot;). Ciò significa che i valori di eVar impostati su &quot;non scade mai&quot; per un visitatore prima dell’intervallo di date del rapporto non persistono nelle finestre di reporting e non compaiono nei rapporti. Ciò significa anche che le misurazioni della fidelizzazione dei clienti si basano esclusivamente sui dati presenti nell’intervallo di date del rapporto e non sull’intera cronologia prima dell’intervallo di date del rapporto.

Di seguito è riportato un elenco di metriche e dimensioni attualmente non supportate quando si utilizza l’ elaborazione al momento del rapporto :

* **Analytics for Target:** Attualmente non supportato. È previsto un supporto futuro.
* **Analytics per metriche/dimensioni riservate Advertising Cloud:** Attualmente non supportato. È previsto un supporto futuro.
* **Metrica ad accesso singolo:** Non supportato in modo permanente.
* **Variabili elenco:** Attualmente non supportato. È previsto un supporto futuro.
* **eVar contatore:** Non supportato in modo permanente.
* **Variabili dei canali di marketing:** Attualmente non supportato. È previsto un supporto futuro.
* **Giorni dall&#39;ultimo Dimension di acquisto:** A causa della natura della finestra a discesa Data elaborazione ora rapporto , questa dimensione non è supportata.
* **Giorni precedenti al primo Dimension di acquisto:** A causa della natura della finestra a discesa Data elaborazione ora rapporto , questa dimensione non è supportata.
* **Dimension di frequenza di ritorno:** A causa della natura della finestra a discesa Data elaborazione ora rapporto , questa dimensione non è supportata. È possibile un approccio alternativo utilizzando una metrica di conteggio delle visite in un segmento o utilizzando la metrica di visita in un rapporto istogramma.
* **Giorni dall’ultimo Dimension della visita:** A causa della natura della finestra a discesa Data elaborazione ora rapporto , questa dimensione non è supportata.
* **Dimension originale pagina di ingresso:** A causa della natura della finestra a discesa Data elaborazione ora rapporto , questa dimensione non è supportata.
* **eVar di allocazione lineare:** Attualmente non supportato. È previsto un supporto futuro.
* **Dimension di dominio di riferimento originale:** Attualmente non supportato. È previsto un supporto futuro.
* **Numero visita:** A causa della natura della finestra a comparsa Data elaborazione ora rapporto, questa metrica non è supportata. In alternativa, nelle app per dispositivi mobili, puoi utilizzare una metrica calcolata che include visitatori/visite con la metrica Installazione app per identificare nuovi visitatori o visite.
* **Origini dati ID transazione:** Attualmente non supportato. È previsto un supporto futuro.

## Dimensioni e metriche interessate

Di seguito è riportato un elenco di dimensioni e metriche che sono interessate a seconda delle impostazioni di elaborazione al momento del rapporto selezionate:

* Se l’opzione &quot;Impedisci agli hit di sfondo di avviare una nuova visita&quot; è abilitata, si verificano le seguenti modifiche. Vedi [Sessionizzazione in base al contesto](vrs-mobile-visit-processing.md) per ulteriori informazioni.
   * **Frequenza rimbalzi/rimbalzi:** Gli hit di sfondo non seguiti da un hit in primo piano non sono considerati come non recapitati e non contribuiscono alla frequenza di rimbalzo.
   * **Tempo trascorso in secondi per visita:** Solo le visite che includono hit in primo piano contribuiscono a questa metrica.
   * **Tempo trascorso per visita:** Solo le visite che includono hit in primo piano contribuiscono a questa metrica.
   * **Dimension e metriche di ingresso/uscita:** In questa dimensione vengono visualizzate solo le entrate e le uscite dalle visite con hit in primo piano.
   * **Metrica Visitatori univoci:** Visitatori univoci non include i visitatori che avevano solo hit di background nell’intervallo di date del rapporto.
* **Visite:** Le visite riflettono tutte le impostazioni configurate dalla suite di rapporti virtuali, che possono essere diverse dalla suite di rapporti di base.
* **Eventi serializzati con ID evento:** Gli eventi che utilizzano la serializzazione degli eventi con un ID evento sono deduplicati solo per gli eventi che si verificano all’interno dell’intervallo di date del rapporto per un visitatore. Questi eventi non vengono deduplicati in tutte le date o in tutto il mondo a causa della finestra a comparsa Data elaborazione ora rapporto .
* **Acquisti/Entrate/Ordini/Unità:** Quando si utilizza l’ID acquisto, queste metriche vengono deduplicate solo per gli ID acquisto duplicati che si verificano all’interno dell’intervallo di date del rapporto per un visitatore, anziché in tutte le date o i visitatori a livello globale a causa della finestra Data elaborazione ora rapporto .
* **eVar non merchandising/eVar riservate:** I valori impostati in un eVar persistono solo se il valore è stato impostato all&#39;interno dell&#39;intervallo di date del rapporto a causa della finestra Data elaborazione ora rapporto. Inoltre, le scadenze basate sul tempo possono scadere con un’ora di anticipo o con un’ora di ritardo se la persistenza si estende per un cambiamento dell’ora legale.
* **eVar per merchandising/eVar riservate:** Vedi sopra. Inoltre, per la sintassi di conversione, in cui il binding è impostato su &quot;qualsiasi evento&quot;, viene utilizzato invece &quot;qualsiasi hit&quot;.
* **Tipo di hit:** Questa dimensione specifica se un hit è in primo piano o in background.
