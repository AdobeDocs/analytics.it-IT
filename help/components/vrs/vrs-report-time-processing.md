---
description: L’elaborazione dei tempi di report è un’impostazione della suite di rapporti virtuali che consente l’elaborazione dei dati in modo retroattivo e non distruttivo.
title: Elaborazione dell'ora rapporto
role: Admin
solution: Analytics
feature: VRS
exl-id: 3742b9d1-f1fb-4690-bd44-b4719ff9d9bc
source-git-commit: 3be3de8c24e48f5ecddd37ff6d3cbcf64bca3209
workflow-type: tm+mt
source-wordcount: '1278'
ht-degree: 7%

---

# Elaborazione dell&#39;ora rapporto

[!UICONTROL Report time processing] è un’impostazione di suite di rapporti virtuale che consente l’elaborazione dei dati in Analysis Workspace in modo retroattivo e non distruttivo.

[!UICONTROL Report Time Processing] influisce solo sui dati della suite di rapporti virtuali e non su alcun dato o raccolta di dati nella suite di rapporti di base. La differenza tra [!UICONTROL Report Time Processing] e l’elaborazione tradizionale di Analytics è meglio intesa utilizzando il seguente diagramma:

![Pipe di elaborazione tradizionale](assets/google1.jpg)

Durante l’elaborazione dei dati di Analytics, i dati scorrono attraverso la pipeline di raccolta dati e in una fase di preelaborazione, che prepara i dati per la generazione di rapporti. Questa fase di preelaborazione applica la logica di scadenza della visita e la logica di persistenza eVar (tra le altre cose) ai dati durante la raccolta. Lo svantaggio principale di questo modello di preelaborazione è che richiede che qualsiasi configurazione venga eseguita in anticipo prima della raccolta dei dati. Ciò significa che eventuali modifiche alle impostazioni di preelaborazione si applicano solo ai nuovi dati da quel momento in poi. Ciò è problematico se i dati arrivano fuori ordine o se le impostazioni sono state configurate in modo errato.

[!UICONTROL Report Time Processing] è un modo fondamentalmente diverso di elaborare i dati di Analytics per la generazione di rapporti. Anziché predeterminare la logica di elaborazione prima della raccolta dei dati, Analytics ignora il set di dati durante la fase di preelaborazione e applica questa logica ogni volta che viene eseguito un rapporto:

![pipeline di elaborazione dei tempi di report](assets/google2.jpg)

Questa architettura di elaborazione consente opzioni di reporting molto più flessibili. Ad esempio, puoi modificare il periodo di timeout della visita in qualsiasi periodo di tempo desideri in modo non distruttivo e tali modifiche si riflettono nella persistenza eVar e nei contenitori dei segmenti per l’intero periodo di reporting. Inoltre, puoi creare un numero qualsiasi di suite di rapporti virtuali, ciascuna con diverse opzioni di elaborazione dei tempi di report basate sulla stessa suite di rapporti di base, senza modificare nessuno dei dati nella suite di rapporti di base.

[!UICONTROL Report Time Processing] consente inoltre ad Analytics di impedire l’avvio di nuove visite in background e consente [Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/docs/mobile.html?lang=it) per avviare una nuova visita ogni volta che viene attivato un evento di App Launch.

## Opzioni di configurazione

Le seguenti opzioni di configurazione sono attualmente disponibili per le suite di rapporti virtuali con l’elaborazione al momento della generazione del rapporto abilitata:

* **[!UICONTROL Visit Timeout]:** L’impostazione di timeout visita definisce la quantità di inattività che un visitatore univoco deve avere prima dell’avvio automatico di una nuova visita. Il valore predefinito è 30 minuti. Ad esempio, se imposti il timeout di visita a 15 minuti, viene creato un nuovo raggruppamento di visite per ogni sequenza di hit raccolta, separate da 15 minuti di inattività. Questa impostazione ha un impatto non solo sui conteggi delle visite, ma anche sulla valutazione dei contenitori dei segmenti di visite e sulla logica di scadenza delle visite per tutte le eVar in scadenza alla visita. Una diminuzione del timeout della visita determinerà probabilmente un aumento del numero totale di visite nei rapporti, mentre un aumento del timeout della visita ridurrà probabilmente il numero totale di visite nei rapporti.
* **[!UICONTROL Mobile App Visit Settings]:** Per le suite di rapporti contenenti dati generati da app mobili tramite [SDK di Adobe Mobile](https://experienceleague.adobe.com/docs/mobile.html?lang=it), sono disponibili altre impostazioni di visita. Queste impostazioni non sono distruttive e influiscono solo sugli hit raccolti tramite gli SDK di Mobile. Queste impostazioni non hanno alcun impatto sui dati raccolti al di fuori dell&#39;SDK di Mobile.
* **[!UICONTROL Prevent Background Hits from starting a new Visit]:** Gli hit in background vengono raccolti dagli SDK di Mobile quando l&#39;app è in background.
* **[!UICONTROL Start a New Visit upon each App Launch]:** Oltre al timeout previsto per la visita, puoi forzare l’inizio di una visita ogni volta che un evento App Launch è stato registrato dagli SDK Mobile, indipendentemente dalla finestra di inattività. Questa impostazione influisce sulla metrica di visita e sul contenitore del segmento di visita, nonché sulla logica di scadenza della visita sulle eVar.
* **[!UICONTROL Start New Visit with Event]:** Viene avviata una nuova sessione quando un evento viene attivato, a prescindere dal timeout di una sessione. La nuova sessione creata include l’evento che l’ha avviata. Inoltre, puoi utilizzare più eventi per avviare una sessione e una nuova sessione viene avviata se nei dati viene rilevato uno qualsiasi degli eventi. Questa impostazione influisce sul conteggio delle visite, sul contenitore di segmentazione delle visite e sulla logica di scadenza delle visite sugli eVar.

Ecco un video sull’avvio di una nuova visita con un evento:

>[!VIDEO](https://video.tv.adobe.com/v/23129/?quality=12)

## Limiti di elaborazione dei tempi di report

L’elaborazione dei tempi di report non supporta tutte le metriche e dimensioni disponibili nel reporting tradizionale di Analytics. Le suite di rapporti virtuali che utilizzano l’elaborazione al momento della generazione dei rapporti sono accessibili solo in Analysis Workspace e non in [!UICONTROL Reports & Analytics], Data Warehouse, Report Builder, feed di dati o API di reporting.

Inoltre, l’elaborazione dell’ora rapporto elabora solo i dati provenienti dall’intervallo di date del rapporto (in seguito denominato &quot;finestra della data&quot;). Ciò significa che i valori di eVar impostati su &quot;non scade mai&quot; per un visitatore prima dell’intervallo di date del rapporto non persistono nelle finestre di reporting e non compaiono nei rapporti. Ciò significa anche che le misurazioni della fidelizzazione dei clienti si basano esclusivamente sui dati presenti nell’intervallo di date del rapporto e non sull’intera cronologia prima dell’intervallo di date del rapporto.

Le dimensioni e le metriche seguenti non sono supportate con l’elaborazione al momento della generazione del rapporto:

* **Analytics for Target**
* **Dimensioni/metriche di Analytics per Advertising Cloud**
* **Utilizzare le eVar come contatore**
* [**Giorni precedenti al primo acquisto**](/help/components/dimensions/days-before-first-purchase.md)
* [**Giorni dall&#39;ultimo acquisto**](/help/components/dimensions/days-since-last-purchase.md)
* [**Giorni dall&#39;ultima visita**](/help/components/dimensions/days-since-last-visit.md)
* **Pagina di ingresso originale**
* **eVar di allocazione lineare**
* **Variabili elenco**
* [**Dimensioni dei canali di marketing**](/help/components/dimensions/marketing-channel.md)
* [**Dominio di riferimento originale**](/help/components/dimensions/original-referring-domain.md)
* [**Frequenza di ritorno**](/help/components/dimensions/return-frequency.md)
* [**Accesso singolo**](/help/components/metrics/single-access.md)
* **Origini dati ID transazione**
* [**Numero di visite**](/help/components/dimensions/visit-number.md)

## Dimensioni e metriche interessate

Di seguito è riportato un elenco di dimensioni e metriche che sono interessate a seconda delle impostazioni di elaborazione al momento del rapporto selezionate:

* Se l’opzione &quot;Impedisci agli hit di sfondo di avviare una nuova visita&quot; è abilitata, si verificano le seguenti modifiche. Vedi [Sessionizzazione in base al contesto](vrs-mobile-visit-processing.md) per ulteriori informazioni.
   * [**Rimbalzi**](/help/components/metrics/bounces.md) / [**Frequenza di rimbalzo:**](/help/components/metrics/bounce-rate.md) Gli hit di sfondo non seguiti da un hit in primo piano non sono considerati come non recapitati e non contribuiscono alla frequenza di rimbalzo.
   * [**Tempo trascorso in secondi per visita:**](/help/components/metrics/time-spent-per-visit.md) Solo le visite che includono hit in primo piano contribuiscono a questa metrica.
   * **Tempo trascorso per visita:** Solo le visite che includono hit in primo piano contribuiscono a questa metrica.
   * [**Metrica di ingresso**](/help/components/metrics/entries.md) / [**Metrica di uscita:**](/help/components/metrics/exits.md) In questa dimensione vengono visualizzate solo le entrate e le uscite dalle visite con hit in primo piano.
   * [**Dimensione di ingresso**](/help/components/dimensions/entry-dimensions.md) / [**Dimensioni di uscita:**](/help/components/dimensions/exit-dimensions.md) In questa dimensione vengono visualizzate solo le entrate e le uscite dalle visite con hit in primo piano.
   * [**Metrica Visitatori univoci:**](/help/components/metrics/unique-visitors.md) Visitatori univoci non include i visitatori che avevano solo hit di background nell’intervallo di date del rapporto.
* [**Visite:**](/help/components/metrics/visits.md) Le visite riflettono tutte le impostazioni configurate dalla suite di rapporti virtuali, che possono essere diverse dalla suite di rapporti di base.
* **Eventi serializzati con ID evento:** Gli eventi che utilizzano la serializzazione degli eventi con un ID evento sono deduplicati solo per gli eventi che si verificano all’interno dell’intervallo di date del rapporto per un visitatore. Questi eventi non vengono deduplicati in tutte le date o in tutto il mondo a causa della finestra a comparsa Data elaborazione ora rapporto .
* **Acquisti** / [**Entrate**](/help/components/metrics/revenue.md) / [**Ordini**](/help/components/metrics/orders.md) / [**Unità:**](/help/components/metrics/units.md) Quando si utilizza l’ID acquisto, queste metriche vengono deduplicate solo per gli ID acquisto duplicati che si verificano all’interno dell’intervallo di date del rapporto per un visitatore, anziché in tutte le date o i visitatori a livello globale a causa della finestra Data elaborazione ora rapporto .
* [**eVar non merchandising**](/help/components/dimensions/evar.md) / **eVar riservate:** I valori impostati in un eVar persistono solo se il valore è stato impostato all&#39;interno dell&#39;intervallo di date del rapporto a causa della finestra Data elaborazione ora rapporto. Inoltre, le scadenze basate sul tempo possono scadere con un’ora di anticipo o con un’ora di ritardo se la persistenza si estende per un cambiamento dell’ora legale.
* [**eVar per merchandising**](/help/components/dimensions/evar-merchandising.md) / **eVar riservate:** Vedi sopra. Inoltre, per la sintassi di conversione, in cui il binding è impostato su &quot;qualsiasi evento&quot;, viene utilizzato invece &quot;qualsiasi hit&quot;.
* [**Tipo di hit:**](/help/components/dimensions/hit-type.md) Questa dimensione specifica se un hit è in primo piano o in background.
* **Dimension con (traffico ridotto) o &quot;Uniques Superato&quot;:** L’elemento di riga (traffico ridotto) viene determinato in modo leggermente diverso quando si utilizza l’elaborazione al momento del rapporto e non è garantito che corrisponda a quello osservato durante il reporting sulla suite di rapporti di base. Gli elementi riga di Dimension che non fanno parte di traffico ridotto non rappresentano il 100% dei dati per tale riga. Queste differenze possono diventare più pronunciate più alto è il numero di valori univoci esistenti in una dimensione.
