---
description: L’elaborazione dei tempi di report è un’impostazione della suite di rapporti virtuale che consente di elaborare i dati in modo retroattivo e non distruttivo.
title: Elaborazione dell'ora rapporto
role: Admin
solution: Analytics
feature: VRS
exl-id: 3742b9d1-f1fb-4690-bd44-b4719ff9d9bc
source-git-commit: ec4edb257490d326ab8f8de51a4ab9412a2b4a28
workflow-type: tm+mt
source-wordcount: '1262'
ht-degree: 7%

---

# Elaborazione dell&#39;ora rapporto

[!UICONTROL Report time processing] è un’impostazione della suite di rapporti virtuale che consente di elaborare i dati in Analysis Workspace in modo retroattivo e non distruttivo.

[!UICONTROL Report Time Processing] influisce solo sui dati nella suite di rapporti virtuale e non influisce su alcuna raccolta di dati nella suite di rapporti di base. La differenza tra [!UICONTROL Report Time Processing] e l’elaborazione Analytics tradizionale è meglio conosciuta utilizzando il diagramma seguente:

![Pipeline di elaborazione tradizionale](assets/google1.jpg)

Durante l’elaborazione dei dati di Analytics, i dati scorrono attraverso la pipeline di raccolta dati e si trasformano in un passaggio di pre-elaborazione, che prepara i dati per il reporting. Questo passaggio di preelaborazione applica la logica di scadenza della visita e la logica di persistenza eVar (tra le altre cose) ai dati durante la raccolta. Lo svantaggio principale di questo modello di pre-elaborazione è che richiede che qualsiasi configurazione venga eseguita in anticipo prima della raccolta dei dati. Ciò significa che qualsiasi modifica alle impostazioni di pre-elaborazione si applica solo ai nuovi dati da quel momento in poi. Ciò è problematico se i dati arrivano fuori servizio o se le impostazioni non sono state configurate correttamente.

[!UICONTROL Report Time Processing] è un modo fondamentalmente diverso di elaborare i dati di Analytics a scopo di reporting. Invece di predeterminare la logica di elaborazione prima della raccolta dei dati, Analytics ignora il set di dati durante il passaggio di preelaborazione e applica questa logica ogni volta che viene eseguito un rapporto:

![Pipeline di elaborazione dei tempi di report](assets/google2.jpg)

Questa architettura di elaborazione offre opzioni di reporting molto più flessibili. Ad esempio, puoi impostare il periodo di timeout della visita in base al periodo di tempo desiderato in modo non distruttivo, e le modifiche si riflettono nei contenitori di persistenza e segmenti in eVar per l’intero periodo di reporting. Inoltre, puoi creare un numero qualsiasi di suite di rapporti virtuali, ciascuna con diverse opzioni di Elaborazione dell’ora rapporto basate sulla stessa suite di rapporti di base, senza modificare nessuno dei dati nella suite di rapporti di base.

[!UICONTROL Report Time Processing] consente inoltre ad Analytics di impedire che gli hit in background diano inizio a nuove visite e consente [SDK di Adobe Experience Platform Mobile](https://experienceleague.adobe.com/docs/mobile.html?lang=it) per iniziare una nuova visita ogni volta che viene attivato un evento App Launch.

## Opzioni di configurazione

Le seguenti opzioni di configurazione sono attualmente disponibili per le suite di rapporti virtuali con l’opzione Elaborazione al momento del rapporto abilitata:

* **[!UICONTROL Visit Timeout]:** L’impostazione di timeout visita definisce la quantità di inattività che un visitatore univoco deve avere prima che una nuova visita venga avviata automaticamente. Il valore predefinito è 30 minuti. Ad esempio, se imposti il timeout visita su 15 minuti, viene creato un nuovo raggruppamento di visite per ogni sequenza di hit raccolta, separate da 15 minuti di inattività. Questa impostazione influisce non solo sui conteggi delle visite, ma anche sul modo in cui vengono valutati i contenitori dei segmenti di visita e sulla logica di scadenza delle visite per tutte le eVar in scadenza alla visita. La riduzione del timeout visita probabilmente aumenterà il numero totale di visite nel reporting, mentre l’aumento del timeout visita probabilmente diminuirà il numero totale di visite nel reporting.
* **[!UICONTROL Mobile App Visit Settings]:** Per suite di rapporti contenenti dati generati da app mobili tramite [SDK per dispositivi mobili Adobe](https://experienceleague.adobe.com/docs/mobile.html?lang=it), sono disponibili impostazioni di visita aggiuntive. Queste impostazioni non sono distruttive e influiscono solo sugli hit raccolti tramite gli SDK di Mobile. Queste impostazioni non hanno alcun impatto sui dati raccolti al di fuori dell’SDK di Mobile.
* **[!UICONTROL Prevent Background Hits from starting a new Visit]:** Gli hit in background vengono raccolti dagli SDK di Mobile quando l&#39;app si trova in uno stato di background.
* **[!UICONTROL Start a New Visit upon each App Launch]:** Oltre al timeout della visita, puoi forzare l’inizio di una visita ogni volta che un evento App Launch viene registrato dagli SDK di Mobile, indipendentemente dalla finestra di inattività. Questa impostazione influisce sulla metrica Visita e sul contenitore del segmento di visita, nonché sulla logica di scadenza della visita nelle eVar.
* **[!UICONTROL Start New Visit with Event]:** Viene avviata una nuova sessione quando un evento viene attivato, a prescindere dal timeout di una sessione. La nuova sessione creata include l’evento che l’ha avviata. Inoltre, puoi utilizzare più eventi per avviare una sessione e una nuova sessione viene avviata se nei dati viene rilevato uno qualsiasi degli eventi. Questa impostazione influirà sul conteggio delle visite, sul contenitore di segmentazione delle visite e sulla logica di scadenza delle visite nelle eVar.

Ecco un video su come iniziare una nuova visita con un evento:

>[!VIDEO](https://video.tv.adobe.com/v/23129/?quality=12)

## Limitazioni dell’elaborazione dei tempi di report

L’elaborazione dei tempi di report non supporta tutte le metriche e le dimensioni disponibili nel reporting tradizionale di Analytics. Le suite di rapporti virtuali che utilizzano l’elaborazione dei tempi di report sono accessibili solo in Analysis Workspace e non in [!UICONTROL Reports & Analytics], Data Warehouse, Report Builder, Data Feeds o l’API di reporting.

Inoltre, Elaborazione dell’ora rapporto elabora solo i dati che provengono dall’intervallo di date del rapporto (di seguito &quot;finestra di data&quot;). Ciò significa che i valori eVar impostati su &quot;mai scadere&quot; per un visitatore prima dell’intervallo di date del rapporto non persistono nelle finestre di rapporto e non vengono visualizzati nei rapporti. Ciò significa anche che le misurazioni della fedeltà dei clienti si basano esclusivamente sui dati presenti nell’intervallo di date del rapporto e non sull’intera cronologia precedente all’intervallo di date del rapporto.

Le dimensioni e le metriche seguenti non sono supportate con l’elaborazione dell’ora rapporto:

* **Analytics for Target**
* **Dimensioni/metriche di Analytics per Advertising Cloud**
* **Utilizzare le eVar come contatore**
* **Giorni precedenti al primo acquisto**
* **Giorni dall&#39;ultimo acquisto**
* **Giorni dall&#39;ultima visita**
* **Pagina di ingresso originale**
* **eVar di allocazione lineare**
* **Variabili elenco**
* **Dimensioni dei canali di marketing**
* **Dominio di riferimento originale**
* **Restituisci frequenza**
* **Accesso singolo**
* **Origini dati ID transazione**
* **Numero visita**

## Dimensioni e metriche interessate

Di seguito è riportato un elenco di dimensioni e metriche interessate a seconda delle impostazioni di Elaborazione dell’ora rapporto selezionate:

* Se è abilitato &quot;Impedisci agli hit in background di avviare una nuova visita&quot;, si verificano le seguenti modifiche. Consulta [Sessione in base al contesto](vrs-mobile-visit-processing.md) per ulteriori informazioni.
   * **Mancato recapito/Percentuale rimbalzo:** Gli hit di sfondo non seguiti da un hit in primo piano non sono considerati un mancato recapito e non contribuiscono al tasso di mancato recapito.
   * **Tempo trascorso in secondi per visita:** Solo le visite che includono hit in primo piano contribuiscono a questa metrica.
   * **Tempo trascorso per visita:** Solo le visite che includono hit in primo piano contribuiscono a questa metrica.
   * **Dimension e metriche di entrata/uscita:** In questa dimensione vengono visualizzate solo le entrate e le uscite dalle visite con hit in primo piano.
   * **Metrica visitatori univoci:** Visitatori unici non include i visitatori che hanno avuto solo hit di background nell&#39;intervallo di date del rapporto.
* **Visite:** Le visite riflettono le impostazioni configurate dalla suite di rapporti virtuali, che possono essere diverse da quelle della suite di rapporti di base.
* **Eventi serializzati con ID evento:** Gli eventi che utilizzano la serializzazione degli eventi con un ID evento vengono deduplicati solo per gli eventi che si verificano all’interno dell’intervallo di date del reporting per un visitatore. Questi eventi non vengono deduplicati in tutte le date o i visitatori a livello globale a causa della finestra di dialogo della data di elaborazione dell’ora rapporto.
* **Acquisti/Ricavi/Ordini/Unità:** Quando viene utilizzato l’ID acquisto, queste metriche vengono deduplicate solo per gli ID acquisto duplicati che si verificano all’interno dell’intervallo di date del rapporto per un visitatore anziché in tutte le date o i visitatori nel mondo a causa della finestra di visualizzazione della data Elaborazione dell’ora di rapporto.
* **eVar non di merchandising/eVar riservate:** I valori impostati in un eVar persistono solo se il valore è stato impostato nell&#39;intervallo di date del rapporto a causa della finestra di visualizzazione della data di elaborazione dell&#39;ora rapporto. Inoltre, le scadenze basate sull’ora possono scadere con un’ora di anticipo o con un’ora di ritardo se la persistenza si estende oltre la modifica dell’ora legale.
* **eVar per merchandising/eVar riservate:** Vedi sopra. Inoltre, per la sintassi di conversione, in cui l’associazione è impostata su &quot;any event&quot;, viene utilizzato &quot;any hit&quot;.
* **Tipo di hit:** Questa dimensione specifica se un hit è in primo piano o in background.
* **Dimension con (traffico ridotto) o &quot;valori univoci superati&quot;:** L’elemento di riga (a traffico ridotto) viene determinato in modo leggermente diverso quando si utilizza l’elaborazione dei tempi di report e non è garantito che corrisponda a quanto osservato durante la generazione di rapporti sulla suite di rapporti di base. Non è garantito che gli elementi riga di Dimension che non fanno parte di Low-traffic rappresentino il 100% dei dati per tale elemento riga. Queste differenze possono diventare più pronunciate quanto più elevato è il numero di valori univoci in una dimensione.
