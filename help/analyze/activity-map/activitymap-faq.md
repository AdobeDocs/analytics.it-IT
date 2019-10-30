---
description: Domande frequenti su come impostare, configurare e utilizzare le funzionalità in [!DNL Activity Map].
seo-description: Domande frequenti su come impostare, configurare e utilizzare le funzionalità in [!DNL Activity Map].
seo-title: Domande frequenti su [!DNL Activity Map]
solution: Analytics
title: Domande frequenti su [!DNL Activity Map]
topic: Activity Map
uuid: e4f6d4e2-55d1-4e32-bf70-a334178af370
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# [!DNL Activity Map]Domande frequenti

Domande frequenti su come impostare, configurare e utilizzare le funzioni in [!DNL Activity Map].

## Implementazione e AppMeasurement {#section_FB46DD652E854C07AD339D7DD5CBCEC6}

**D: Quali sono le fasi di implementazione per abilitare il nuovo[!DNL Activity Map]?**

A: Rivedere [Abilita [!DNL Activity Map]](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md)

**D: Tutti i clienti Analytics hanno accesso alla pagina Abilitazione ActivityMap di Strumenti di amministrazione?**

A: I clienti di Adobe SiteCatalyst non hanno accesso alla pagina di abilitazione di Admin Console. [!DNL Activity Map] Solo le società che hanno sottoscritto il contratto Adobe Analytics Standard e Adobe Analytics Premium hanno accesso a questa pagina di configurazione.

**D: Il nuovo codice AppMeasurement può essere configurato tramite Gestione tag dinamica (DTM)?**

A: Sì, puoi implementare [](https://marketing.adobe.com/resources/help/en_US/dtm/analytics_dtm.html) manualmente il nuovo codice AppMeasurement.

**D: Quali sono le grandi modifiche nella libreria AppMeasurement v1.6?**

A: L’unica modifica in AppMeasurement v1.6 è nella metodologia del processo di tracciamento dei [!DNL Activity Map] collegamenti che richiede la raccolta di nome pagina, ID collegamento e ID regione.

**D: AppMeasurement verrà implementato a livello di dominio anziché su pagine specifiche?**

A: AppMeasurement viene implementato a livello di suite di rapporti. Il livello suite di rapporti è generalmente associato a un livello di dominio, ma questo è diverso per ogni implementazione.

**D: Gestione dinamica dei tag carica automaticamente una versione precedente (1.3.4) dell’API del visitatore rispetto a[!DNL Activity Map]quanto richiesto (1.5.1). Questo è un problema?**

R: No. [!DNL Activity Map] non dipende da VisitorAPI.

## [!DNL Activity Map] application {#section_E4F2DAC09EBA4E3BA7BACB49A0A89F8D}

**D: Posso utilizzare[!DNL Activity Map]se non ho utilizzato in precedenza Visitor ClickMap sul mio sito Web?**

A: L'installazione della versione precedente, ora denominata ClickMap, non è un prerequisito per implementare la nuova versione. Adobe continuerà a supportare la versione precedente per un periodo di tempo limitato.

**D: Quali browser e versioni sono supportati da[!DNL Activity Map]?**

A: Supportiamo solo la versione più recente dei quattro browser principali (Chrome, Firefox, Safari e IE).

**D: Quali sono le impostazioni di sovrapposizione predefinite?**

A: Per impostazione predefinita, [!DNL Activity Map] mostra TUTTI i collegamenti che hanno raccolto dati.

Quando i pannelli popup sono visualizzati sopra alle pagine Web del cliente, le sovrapposizioni appartenenti ai collegamenti situati sotto il pannello a comparsa possono essere visualizzate nella parte superiore del pannello a comparsa.

**D: Perché mancano alcune sovrapposizioni di elementi classificati?**

A: Alcuni collegamenti classifica potrebbero essere nascosti dalla pagina (ad esempio, collegamenti di sottomenu). Di conseguenza, le sovrapposizioni di collegamento corrispondenti non verranno visualizzate. Potete quindi aspettarvi di vedere le classificazioni delle sovrapposizioni che mancano alcuni valori di classificazione specifici, perché il livello viene calcolato per tutti i collegamenti nella pagina (il presente + quelli nascosti).

**D: In che modo viene determinata la classificazione dei collegamenti nel rapporto Tutti i collegamenti?**

* In modalità **Sfumatura** e **Bolla** : La classificazione è determinata dalla colonna metrica. Per i collegamenti con lo stesso valore di metrica, il livello è ulteriormente basato sull'ordine alfabetico ID collegamento.
* In modalità **Gainer &amp; Loser** , la classificazione è determinata principalmente dalla colonna % Guadagno. Per i collegamenti con lo stesso Guadagno, il rango è ulteriormente basato sull'ordine alfabetico ID collegamento.

**D: Perché i dati del clic del collegamento non vengono raccolti durante l'[!DNL Activity Map]esecuzione?**

A: Quando [!DNL Activity Map] è in uso, i dati del clic sul collegamento non vengono raccolti dal tag Analytics. Questo comportamento segue il comportamento del plug-in ClickMap.

**D: Perché il menu a discesa della metrica elenca la stessa metrica più volte?**

A: elenca [!DNL Activity Map] le metriche per tutte le suite di rapporti. Di conseguenza, potete aspettarvi di vedere la duplicazione se l'azienda non ha eseguito un processo [di consolidamento](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/cm_transition.html)delle metriche.

L'elenco a discesa Metrica consente di limitare l'elenco delle metriche calcolate a quelle assegnate alla suite di rapporti della pagina visitata.

**D: Qual è il rapporto[!DNL Activity Map]Tutti i collegamenti rispetto ai[!DNL Activity Map]rapporti di Reporting e analisi?**

A: Per inserire il rapporto Tutti i collegamenti, [!DNL Activity Map]viene creata una richiesta di suddivisione come segue: [!DNL Activity Map] Pagina = "visitedpage", suddivisa per [!DNL Activity Map] Link&amp;Region in `<list of link&regions present in the page at rendering time>`.

Per ottenere un report equivalente in Reporting e analisi, dovrete prima passare al report [!DNL Activity Map] Pagina. Qui si applica il filtro per il nome pagina visitato in [!DNL Activity Map]. Il nome Pagename visitato viene visualizzato nella colonna a sinistra nel pannello inferiore Dettagli [!DNL Activity Map] pagina. Una volta trovata la pagina, puoi suddividerla e scegliere [!DNL Activity Map] Collegamenti e regioni come dimensione secondaria.

Tuttavia, è importante notare che il rapporto ottenuto in R&amp;A elenca tutti i collegamenti e le regioni raccolti per quella pagina. Tuttavia, [!DNL Activity Map] solo i rapporti su Links&amp;Region attualmente presenti nella pagina Web. Quindi se avete un sito di notizie, questo mostrerà solo i dati per le notizie presenti in questo momento, e non le notizie che erano presenti prima della giornata.

**D: Come funziona[!DNL Activity Map]con pagine contenenti più tag che elencano più suite di rapporti?**

A: Per impostazione predefinita, [!DNL Activity Map] utilizza la suite di rapporti associata al primo tag inviato dalla pagina.

Puoi selezionare una suite di rapporti con tag diversa tramite la scheda [!DNL Activity Map] Impostazioni &gt; Altri.

**D: Per quanto tempo[!DNL Activity Map]effettua la scansione del tag Analytics?**

A: Il tag Analytics viene analizzato fino a 20 secondi dopo un evento di completamento della pagina.

**D: Come si[!DNL Activity Map]gestisce il contenuto dinamico?**

A: verifica [!DNL Activity Map] ogni 2 secondi se sono state apportate modifiche allo stato della pagina Web, ad esempio:

* Contenuto HTML che è diventato visibile
* Contenuto HTML nascosto
* Nuovo contenuto HTML inserito

Se il contenuto è nascosto o visualizzato, l'applicazione modifica automaticamente lo stato dei collegamenti interessati (e quindi le sovrapposizioni) da nascosto a mostrato o da mostrato a nascosto.

Se viene inserito nuovo contenuto, l'applicazione recupererà i collegamenti associati, estrarrà i dati di analisi per tali collegamenti e aggiungerà sovrapposizioni per tali collegamenti.

**D: Su quale metrica si basa il rapporto Flusso di pagina?**

A: Tutti i dati visualizzati si basano sulle visualizzazioni della pagina.

**D: È possibile spiegare[!DNL Activity Map]il comportamento con vari tipi di pagine?**

*Pagina Web senza tag Analytics*

Nella barra degli strumenti, sotto alla barra degli strumenti è visualizzato un messaggio di avviso che indica che non è presente alcun tag.

*Pagina Web con tag Analytics incompatibile (AppMeasurement v1.5 o versioni precedenti)*

Viene visualizzato un messaggio di avviso che indica che è necessario (/home/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md) aggiornare il codice della pagina alla versione 1.6.

*Pagina Web con tag Analytics compatibile (AppMeasurement v1.6 o versione successiva), ma[!DNL Activity Map]il reporting non era abilitato in Strumenti di amministrazione*

Viene visualizzato un messaggio di avviso che indica che è necessario richiedere all'amministratore di \[Abilitare il [!DNL Activity Map] rapporto\](/home/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md").

**D: Posso esportare[!DNL Activity Map]i dati (contextData) tramite Feed[dati](https://marketing.adobe.com/resources/help/en_US/reference/analytics-data-feed.html)Analytics?**

R: No.

## Segmentazione in [!DNL Activity Map]{#section_44D6C5F59B8542DC8A3AF38BD8078DCA}

**D: I segmenti sono legati ai singoli segmenti di utenti? Oppure i segmenti condivisi di livello Amministratore sono disponibili in[!DNL Activity Map]?**

A: eredita [!DNL Activity Map] i segmenti di livello Amministratore (segmenti di reporting) da Analytics.

**D: I segmenti funzionano in modalità Live?**

A: No, i segmenti non funzionano in modalità Live. La funzionalità è equivalente a quella dei report in tempo reale in Reporting e analisi.

## Suite di rapporti virtuali {#section_BDB0CA9E732F478EAC349A79753A78DB}

**D: È[!DNL Activity Map]compatibile con le suite di rapporti virtuali?**

A: Sì. Tuttavia, a causa delle limitazioni della suite di rapporti virtuali, [!DNL Activity Map]la modalità Live non è compatibile con le suite di rapporti virtuali.
