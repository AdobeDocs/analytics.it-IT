---
description: Domande frequenti su come impostare, configurare e utilizzare le funzioni nella Activity Map.
title: Domande frequenti su Activity Map
topic: Activity map
uuid: e4f6d4e2-55d1-4e32-bf70-a334178af370
translation-type: tm+mt
source-git-commit: fa9efcba40ae00c22e99f68f5be8f4d5bf32e44c

---


# Domande frequenti su Activity Map

Domande frequenti su come impostare, configurare e utilizzare le funzioni nella Activity Map.

## Implementazione e AppMeasurement

**D: Quali sono i passaggi di implementazione per abilitare la nuova Activity Map?**

A: Rivedete [Attiva Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md)

**D: Tutti i clienti Analytics hanno accesso alla pagina Abilitazione ActivityMap di Strumenti di amministrazione?**

A: I clienti di Adobe SiteCatalyst non hanno accesso alla pagina Abilitazione Activity Map di Admin Console. Solo le società che hanno sottoscritto il contratto Adobe Analytics Standard e Adobe Analytics Premium hanno accesso a questa pagina di configurazione.

**D: Il nuovo codice AppMeasurement può essere configurato tramite Gestione tag dinamica (DTM)?**

A: Sì, puoi implementare [](https://marketing.adobe.com/resources/help/en_US/dtm/analytics_dtm.html) manualmente il nuovo codice AppMeasurement.

**D: Quali sono le grandi modifiche nella libreria AppMeasurement v1.6?**

A: L’unica modifica in AppMeasurement v1.6 è nella metodologia del processo di tracciamento dei collegamenti Mappa dell’attività che richiede la raccolta di nome pagina, ID collegamento e ID regione.

**D: AppMeasurement verrà implementato a livello di dominio anziché su pagine specifiche?**

A: AppMeasurement viene implementato a livello di suite di rapporti. Il livello suite di rapporti è generalmente associato a un livello di dominio, ma questo è diverso per ogni implementazione.

**D: Gestione dinamica dei tag carica automaticamente una versione precedente (1.3.4) dell’API del visitatore rispetto a quella desiderata dalla Activity Map (1.5.1). Questo è un problema?**

R: No. La funzionalità Activity Map non dipende da VisitorAPI.

## Applicazione Activity Map

**D: In che modo Activity Map supporta le applicazioni SPA (Single Page Applications)?**

A:

* Ogni pochi secondi, Activity Map analizza la pagina Web, alla ricerca di modifiche alla pagina. ActivityMap trova nuovo contenuto nella pagina senza dover caricare una nuova pagina, ma questo nuovo contenuto viene sempre attribuito al primo pageName trovato al caricamento della pagina.

* Activity Map controlla se la visibilità dei collegamenti di cui è a conoscenza è cambiata. Se viene rilevata una modifica nella visibilità, la colonna [Collegamenti sulla pagina](/help/analyze/activity-map/activitymap-links-report.md) presente della tabella del collegamento si aggiorna con **[!UICONTROL Displayed]** o **[!UICONTROL Hidden]**.

* Quando l&#39;interazione dell&#39;utente crea nuovo contenuto, tutti i nuovi elementi che AppMeasurement identifica come collegamento verranno aggiunti alla **[!UICONTROL Links On Page]** tabella. Activity Map invia una nuova richiesta di dati che include questi nuovi collegamenti. I nuovi collegamenti dovrebbero essere visualizzati nella **[!UICONTROL Links On Page]** tabella quando la richiesta di dati viene gestita dall&#39;interfaccia utente.

**D: Activity Map fornisce dati sulle &quot;viste&quot;?**

A: No, il tracciamento di tutti i collegamenti visualizzati su ogni caricamento di pagina richiede la raccolta di molti più dati. Come componente aggiuntivo gratuito, Activity Map non fornisce questa funzionalità.

**D: Posso usare Activity Map se in precedenza non ho utilizzato Visitor ClickMap sul mio sito Web?**

A: L&#39;installazione della versione precedente, ora denominata ClickMap, non è un prerequisito per l&#39;implementazione della nuova versione. Adobe continuerà a supportare la versione precedente per un periodo di tempo limitato.

**D: Quali browser e versioni sono supportati da Activity Map?**

A: Supportiamo la versione più recente dei quattro browser principali (Chrome, Firefox, Safari e IE).

**D: Quali sono le impostazioni di sovrapposizione predefinite?**

A: Per impostazione predefinita, Activity Map mostra tutti i collegamenti che hanno raccolto i dati.

Quando i pannelli a comparsa sono visualizzati sopra alle pagine Web del cliente, le sovrapposizioni appartenenti ai collegamenti situati sotto il pannello a comparsa possono essere visualizzate nella parte superiore del pannello a comparsa.

**D: Perché mancano alcune sovrapposizioni di elementi classificati?**

A: Alcuni collegamenti con classifica potrebbero essere nascosti dalla pagina (ad esempio, collegamenti di sottomenu). Di conseguenza, le sovrapposizioni di collegamento corrispondenti non verranno visualizzate. Potete quindi aspettarvi di vedere le classificazioni delle sovrapposizioni che mancano alcuni valori di classificazione specifici, perché il livello viene calcolato per tutti i collegamenti nella pagina (il presente + quelli nascosti).

**D: In che modo viene determinata la classificazione dei collegamenti nel rapporto Tutti i collegamenti?**

* In modalità **Sfumatura** e **Bolla** : La classificazione è determinata dalla colonna metrica. Per i collegamenti con lo stesso valore di metrica, il livello è ulteriormente basato sull&#39;ordine alfabetico ID collegamento.
* In modalità **Gainer &amp; Loser** , la classificazione è determinata principalmente dalla colonna % Guadagno. Per i collegamenti con lo stesso Guadagno, il rango è ulteriormente basato sull&#39;ordine alfabetico ID collegamento.

**D: Perché i dati del clic del collegamento non vengono raccolti quando è in esecuzione Activity Map?**

A: Mentre la Activity Map è in uso, i dati del clic sul collegamento non vengono raccolti dal tag Analytics. Questo comportamento segue il comportamento del plug-in ClickMap.

**D: In che modo il rapporto Activity Map All Links (Mappa dell&#39;attività tutti i collegamenti) viene confrontato con il reporting Activity Map di Reporting e analisi?**

A: Per inserire il rapporto Tutti i collegamenti nella Activity Map, viene creata una richiesta di suddivisione come segue: Activity Map Page = &quot;visitedpage&quot;, suddivisa per Activity Map Link&amp;Region in `<list of link&regions present in the page at rendering time>`.

Per ottenere un rapporto equivalente in Reporting e analisi, dovrete prima passare al report Activity Map Page (Mappa dell&#39;attività). Qui, filtrate il nome pagina visitato nella Activity Map. Il nome Pagename visitato viene visualizzato nella colonna a sinistra nel pannello Dettagli pagina Activity Map Bottom (Dettagli pagina Activity Map in basso). Una volta trovata la pagina, puoi suddividerla e scegliere Activity Map Links &amp; Region come dimensione secondaria.

Tuttavia, è importante notare che il rapporto ottenuto in R&amp;A elenca tutti i collegamenti e le regioni raccolti per quella pagina. Ma Activity Map riporta solo i rapporti su Links&amp;Region attualmente presenti nella pagina Web. Quindi se avete un sito di notizie, questo mostrerà solo i dati per le notizie presenti in questo momento, e non le notizie che erano presenti prima della giornata.

**D: Come funziona Activity Map con pagine contenenti più tag che elencano più suite di rapporti?**

A: Per impostazione predefinita, Activity Map utilizza la suite di rapporti associata al primo tag inviato dalla pagina. Potete selezionare una suite di rapporti con tag diversa tramite la scheda Activity Map Settings (Impostazioni Activity Map) > Others (Altri).

**D: Per quanto tempo è possibile eseguire la scansione Activity Map per il tag Analytics?**

A: Il tag Analytics viene analizzato fino a 20 secondi dopo un evento di completamento della pagina.

**D: In che modo Activity Map gestisce il contenuto dinamico?**

A: Activity Map verifica ogni 2 secondi per verificare se sono state rilevate modifiche allo stato della pagina Web, ad esempio:

* Contenuto HTML che è diventato visibile
* Contenuto HTML nascosto
* Nuovo contenuto HTML inserito

Se il contenuto è nascosto o visualizzato, l&#39;applicazione modifica automaticamente lo stato dei collegamenti interessati (e quindi le sovrapposizioni) da nascosto a mostrato o da mostrato a nascosto.

Se viene inserito nuovo contenuto, l&#39;applicazione recupererà i collegamenti associati, estrarrà i dati di analisi per tali collegamenti e aggiungerà sovrapposizioni per tali collegamenti.

**D: Su quale metrica si basa il rapporto Flusso di pagina?**

A: Tutti i dati visualizzati si basano sulle visualizzazioni della pagina.

**D: È possibile spiegare il comportamento della Activity Map con vari tipi di pagine?**

*Pagina Web senza tag Analytics*

Nella barra degli strumenti, sotto alla barra degli strumenti è visualizzato un messaggio di avviso che indica che non è presente alcun tag.

*Pagina Web con tag Analytics incompatibile (AppMeasurement v1.5 o versioni precedenti)*

Viene visualizzato un messaggio di avviso che indica che è necessario aggiornare il codice della pagina alla versione 1.6 o successiva.

*Pagina Web con tag Analytics compatibile (AppMeasurement v1.6 o versione successiva), ma la generazione di rapporti Activity Map non era abilitata in Strumenti di amministrazione*

Viene visualizzato un messaggio di avviso che indica che è necessario richiedere all&#39;amministratore di \[Abilitare il rapporto Activity Map\](/home/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md&quot;).

**D: Posso esportare i dati Activity Map (contextData) tramite Feed[dati](https://docs.adobe.com/content/help/en/analytics/export/analytics-data-feed/data-feed-overview.html)Analytics?**

R: No.

## Segmentazione in Activity Map

**D: I segmenti sono legati ai singoli segmenti di utenti? I segmenti condivisi sono disponibili nella Activity Map?**

A: Activity Map eredita i segmenti di reporting da Analytics.

**D: I segmenti funzionano in modalità Live?**

A: No, i segmenti non funzionano in modalità Live. La funzionalità è equivalente a quella dei report in tempo reale in Reporting e analisi.

## Suite di rapporti virtuali

**D: Activity Map è compatibile con le suite di rapporti virtuali?**

R: Sì. Tuttavia, a causa delle limitazioni della suite di rapporti virtuali, la modalità Live della Activity Map non è compatibile con le suite di rapporti virtuali.
