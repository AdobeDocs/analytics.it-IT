---
description: Domande frequenti per configurare, configurare e utilizzare funzioni nella mappa dell'attività.
seo-description: Domande frequenti per configurare, configurare e utilizzare funzioni nella mappa dell'attività.
seo-title: Domande frequenti sulla Activity Map
solution: Analytics
title: Domande frequenti sulla Activity Map
topic: Activity map
uuid: e 4 f 6 d 4 e 2-55 d 1-4 e 32-bf 70-a 334178 af 370
translation-type: tm+mt
source-git-commit: 8f72f8cf086be0eade5616b074123a9f22e33347

---


# Domande frequenti sulla Activity Map

Domande frequenti per configurare, configurare e utilizzare funzioni nella mappa dell'attività.

## Implementation and AppMeasurement {#section_FB46DD652E854C07AD339D7DD5CBCEC6}

**Q: Quali sono i passaggi di implementazione per abilitare la nuova Activity Map?**

A: Please review [Enable Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md)

**Q: Tutti i clienti Analytics hanno accesso alla pagina Admin Tools activitymap Enablement?**

A: I clienti di Adobe sitecatalyst non hanno accesso alla pagina Abilitazione mappa dell'attività di Admin Console. Solo le società in Adobe Analytics Standard e Adobe Analytics Premium hanno accesso a questa pagina di configurazione.

**Q: Il nuovo codice appmeasurement può essere configurato tramite Gestione dinamica dei tag?**

A: Yes, you can [manually implement](https://marketing.adobe.com/resources/help/en_US/dtm/analytics_dtm.html) the new AppMeasurement code.

**Q: Quali sono le modifiche principali nella libreria appmeasurement v 1.6?**

A: L'unico cambiamento in appmeasurement v 1.6 è la metodologia di processo di tracciamento della mappa dell'attività che richiede la raccolta di nome pagina, ID collegamento e dominid.

**Q: Appmeasurement verrà implementata a livello di dominio anziché su pagine specifiche?**

A: Appmeasurement viene implementata a livello di suite di rapporti. Il livello di report-suite viene generalmente associato a un livello di dominio, ma questo è diverso per ogni implementazione.

**Q: DTM carica automaticamente una versione precedente (1.3.4) dell'API Visitatore rispetto a want Map want (1.5.1). Is this a problem?**

R: No. La funzionalità Activity Map (Mappa dell'attività) non dipende dalla visitorapi.

## Activity Map application {#section_E4F2DAC09EBA4E3BA7BACB49A0A89F8D}

**Q: Posso usare Activity Map se in precedenza non ho utilizzato clickmap visitatore sul mio sito Web?**

A: La versione precedente, ora denominata semplicemente clickmap, installata non è un prerequisito per l'implementazione della nuova versione. Adobe continuerà a supportare la versione precedente per un periodo di tempo limitato.

**Q: Quali browser e versioni sono supportati da Activity Map?**

A: Supportiamo solo la versione più recente dei quattro browser principali (Chrome, Firefox, Safari e IE).

**Q: Quali sono le impostazioni predefinite per le sovrapposizioni?**

A: Per impostazione predefinita, Activity Map mostra tutti i collegamenti che hanno raccolto dati.

Quando si visualizzano pannelli a comparsa sopra le pagine Web del cliente, sovrapposizioni appartenenti ai collegamenti che si trovano sotto il pannello popup possono essere visualizzate sopra il pannello a comparsa.

**Q: Perché mancano alcune sovrapposizioni di elementi classifica?**

A: Alcuni collegamenti a classifica possono essere nascosti dalla pagina (ad esempio, collegamenti sottomenu). Di conseguenza, le sovrapposizioni di collegamento corrispondenti non verranno mostrate. Pertanto, si potrebbe prevedere di visualizzare classificazioni di sovrapposizione prive di alcuni valori di classificazione specifici, in quanto il livello viene calcolato per tutti i collegamenti nella pagina (quella corrente + quelle nascoste).

**Q: In che modo la classificazione dei collegamenti è determinata nel report Tutti i collegamenti?**

* In **Gradient** and **Bubble** mode: Ranking is determined by the metric column. Per i collegamenti con lo stesso valore di metrica, il livello è ulteriormente basato sull'ordine alfabetico ID.
* In **Gainer &amp; Loser** mode, rank is primarily determined by the % Gain column. Per i collegamenti con lo stesso Guadagno, il livello è ulteriormente basato sull'ordine alfabetico ID.

**Q: Perché i dati del clic di collegamento non vengono raccolti quando Activity Map è in esecuzione?**

A: Mentre la mappa dell'attività è utilizzata, i dati di clic sul collegamento non vengono raccolti dal tag Analytics. Questo comportamento segue il comportamento del plug-plugin clickmap.

**Q: Perché l'elenco a discesa della metrica elenca più volte la stessa metrica?**

A: Activity Map elenca le metriche per tutte le suite di rapporti. As a result, you can expect to see duplication if the company has not gone through a [metric consolidation process](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/cm_transition.html).

Il menu a discesa Metrica consente di limitare l'elenco delle metriche calcolate a quelle assegnate alla suite di rapporti della pagina visitata.

**Q: In che modo il Rapporto Activity Map All Links (Mappa attività) confronta con Reporting e mappa dell'attività di Analytics?**

A: To pull the All Links Report in Activity Map, we create a breakdown request as follows: Activity Map Page = “visitedpage”, broken down by Activity Map Link&amp;Region in `<list of link&regions present in the page at rendering time>`.

Per ottenere un rapporto equivalente in Reporting e analisi, devi prima andare al rapporto Pagina mappa dell'attività. In tal caso, potete filtrare il nome pagina visitato nella mappa dell'attività. Il nome pagename visitato viene visualizzato nella colonna a sinistra nel pannello Dettagli pagina Mappa dell'attività. Una volta trovata la pagina, puoi suddividere la pagina e scegliere Collegamenti e aree dell'attività come dimensione secondaria.

Tuttavia, è importante notare che il report ottenuto in R e A includerà tutti i collegamenti e le regioni raccolti per quella pagina. Tuttavia, l'attività mappa solo i collegamenti e le regioni attualmente presenti nella pagina Web. Quindi, se hai un sito di notizie, in questa fase verranno mostrati solo i dati delle notizie che sono state presentate, e non le ultime notizie presentate in precedenza.

**Q: In che modo Activity Map funziona con pagine contenenti più tag che elenca più suite di rapporti?**

A: Per impostazione predefinita, Activity Map utilizza la suite di rapporti associata al primo tag inviato dalla pagina.

Puoi selezionare una suite di rapporti con tag diversa tramite la scheda Activity Map Settings &gt; Others (Impostazioni mappa attività).

**Q: Per quanto tempo la scansione Activity Map viene eseguita per il tag Analytics?**

A: La scansione del tag Analytics viene eseguita fino a 20 secondi dopo un evento completo di una pagina.

**Q: In che modo la Mappa dell'attività gestisce il contenuto dinamico?**

A: La mappa dell'attività controlla ogni 2 secondi per verificare se sono state rilevate modifiche nello stato della pagina Web, ad esempio:

* Contenuto HTML che è diventato visibile
* Contenuto HTML nascosto
* Nuovo contenuto HTML inserito

Se il contenuto è nascosto o mostrato, l'applicazione modifica automaticamente i collegamenti interessati (e quindi sovrapposizioni) da nascosto a mostra o da mostrare a nascosto.

Se viene inserito un nuovo contenuto, l'applicazione recupererà i collegamenti associati, estrae i dati di analisi e aggiunge le sovrapposizioni per tali collegamenti.

**Q: Quale metrica è il rapporto Flusso pagina basato su?**

A: Tutti i dati visualizzati sono basati sulle visualizzazioni di pagina.

**Q: È possibile spiegare il comportamento Activity Map con vari tipi di pagine?**

*Pagina Web senza tag Analytics*

Di seguito viene visualizzato un messaggio di avviso per indicare che non è presente alcun tag.

*Pagina Web con tag Analytics non compatibile (appmeasurement v 1.5 o versioni precedenti)*

Viene visualizzato un messaggio di avviso che indica che è necessario (/home/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable. md) aggiornare il codice della pagina alla release v 1.6.

*Pagina Web con tag Analytics compatibile (appmeasurement v 1.6 o versione successiva), ma il reporting Activity Map non era abilitato in Strumenti di amministrazione*

Viene visualizzato un messaggio di avviso per indicare che è necessario chiedere all'amministratore di\ [abilitare il report Activity Map\] (/home/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable. md ").

**Q: Posso esportare dati Activity Map (contextdata) tramite[feed dati di Analytics](https://marketing.adobe.com/resources/help/en_US/reference/analytics-data-feed.html)?**

R: No.

## Segmentation in Activity Map {#section_44D6C5F59B8542DC8A3AF38BD8078DCA}

**Q: I segmenti sono associati ai singoli segmenti di utenti? Or are shared Admin-level segments available in Activity Map?**

A: Activity Map eredita i segmenti di amministratori (segmenti di reporting) da Analytics.

**Q: I segmenti funzionano in modalità Live?**

A: No, i segmenti non funzionano in modalità Live. La funzionalità è equivalente a quella dei report in tempo reale in Reporting e analisi.

## Virtual report suites {#section_BDB0CA9E732F478EAC349A79753A78DB}

**Q: Activity Map è compatibile con suite di rapporti virtuali?**

A: Sì. Tuttavia, a causa delle limitazioni della suite di rapporti virtuali, la Modalità Live della Activity Map non è compatibile con le suite di rapporti virtuali.
