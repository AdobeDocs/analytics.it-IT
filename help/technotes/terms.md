---
title: Termini utilizzati in Adobe Analytics
description: Glossario di Adobe Analytics che definisce i termini comuni utilizzati.
exl-id: 07507ba1-a512-48d9-8022-6084de4ae262
feature: Implementation Basics
source-git-commit: 2eff7656741bdba3d5d7d1f33e9261b59f8e6083
workflow-type: tm+mt
source-wordcount: '2577'
ht-degree: 2%

---

# Termini utilizzati in Adobe Analytics

Usa questo glossario per comprendere il contesto di molti termini utilizzati da Adobe Analytics.

* **Activity Map:** Plug-in per browser che mostra le aree del sito su cui hai fatto più clic. Consulta [Activity Map](/help/analyze/activity-map/activity-map.md) nella guida utente Analizza.
* **Admin Console:** Può fare riferimento a:
   * Strumenti di amministrazione legacy, in cui vengono gestite le impostazioni della suite di rapporti in Adobe Analytics. Nelle versioni precedenti di Adobe Analytics, anche le autorizzazioni utente venivano gestite qui. Consulta [Strumenti di amministrazione](/help/admin/admin/c-admin-tools.md) nella guida utente Admin.
   * L’Admin Console di Adobe, in cui viene eseguito il provisioning dell’accesso ai prodotti e vengono gestite le autorizzazioni degli utenti. Consulta [Admin Console](/help/admin/admin-console/home.md) nella guida utente Admin.
* **Allocazione:** Se una variabile di conversione rileva più di un valore durante una visita, l’impostazione di allocazione della variabile determina quale valore viene mantenuto. Consulta [Variabili di conversione](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md) nella guida utente Admin.
* **Analysis Workspace:** Soluzione browser per la creazione di solidi progetti di analisi personalizzati e la democratizzazione delle informazioni. Offre maggiore flessibilità rispetto a Reports and Analytics.
* **Anomalia:** Rilevato utilizzando la modellazione statistica per trovare automaticamente tendenze impreviste nei dati. Il modello analizza le metriche e determina un limite inferiore, un limite superiore e un intervallo di valori previsto. Consulta [Rilevamento delle anomalie](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md) nella guida utente Analizza.
* **AppMeasurement:** Libreria dei codici utilizzata per raccogliere i dati e inviarli a Adobe. Consulta la [Homepage](/help/implement/home.md) della guida utente Implementa.
* **Slot ASI:** Non esiste più. Nelle versioni precedenti di Adobe Analytics, gli slot ASI fornivano un contenitore temporaneo per suite di rapporti per visualizzare i dati segmentati. Nella versione corrente di Adobe Analytics, i segmenti possono essere applicati istantaneamente a qualsiasi rapporto.
* **Raggruppamento:** Consente di visualizzare una dimensione all&#39;interno del contesto di un&#39;altra dimensione. Consulta [Suddividere dimensioni](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md) nella guida utente Analizza.
* **Rimbalzo:** Una visita costituita da un singolo hit. Consulta [Mancati recapiti](/help/components/metrics/bounces.md) nella guida utente Componenti. Consulta anche Accesso singolo.
* **Metrica calcolata:** Consente la combinazione di metriche, funzioni statistiche e formule esistenti da utilizzare nel reporting. Consulta [Metriche calcolate](/help/components/c-calcmetrics/cm-overview.md) nella guida utente Componenti.
* **Campagna:** Può fare riferimento a:
   * La variabile Campaign, che popola la dimensione Codice di tracciamento. Consulta [campagna](../implement/vars/page-vars/campaign.md) nella guida utente Implementa.
   * Una classificazione predefinita della dimensione Codice di tracciamento; creata automaticamente per tutte le suite di rapporti.
   * Adobe Campaign, parte di Adobe Experience Cloud. Ulteriori informazioni su [Adobe.com](https://www.adobe.com/it/marketing/campaign.html).
* **Canale:** Può fare riferimento a:
   * La variabile Canale, che popola la dimensione Sezioni del sito. Consulta [Variabili di pagina](/help/implement/vars/page-vars/page-variables.md) nella guida utente Implementa.
   * Marketing Channels, un componente che consente di comprendere il modo in cui gli utenti arrivano al sito. Consulta [Canali di marketing](/help/components/c-marketing-channels/c-getting-started-mchannel.md) nella guida utente Componenti.
* **Classificazione:** Funzione di Adobe Analytics che consente il raggruppamento di elementi dimensionali. Consulta [Classificazioni](/help/components/classifications/c-classifications.md) nella guida utente Componenti.
* **ClickMap:** Non più utilizzato. Plug-in browser legacy che mostra le aree del sito su cui hai fatto più clic. Questo strumento è stato ritirato a favore di Activity Map.
* **Feed dati clickstream:** Consulta Feed dati.
* **Coorte:** Un gruppo di persone che condividono le stesse caratteristiche per un determinato periodo di tempo. Vedi [Cos’è un’analisi per coorte?](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) nella guida utente Analizza.
* **Server di raccolta:** Consulta Server di raccolta dati.
* **Componente:** I componenti in Analysis Workspace sono dimensioni, metriche, segmenti e intervalli di date da trascinare su un progetto. Consulta [Panoramica dei componenti](/help/analyze/analysis-workspace/components/analysis-workspace-components.md) nella guida utente Analizza.
* **Variabili di dati di contesto:** Variabili temporanee utilizzate esclusivamente nelle regole di elaborazione. I valori delle variabili di dati contestuali vengono persi definitivamente se una regola di elaborazione non li copia in una variabile di conversione o di traffico. Consulta [Variabili di dati di contesto](../implement/vars/page-vars/contextdata.md) nella guida utente Implementa.
* **Variabile di conversione:** Noto anche come eVar. Memorizza un valore personalizzato e mantiene il valore della variabile fino alla scadenza. Consulta la [eVar](/help/components/dimensions/evar.md) nella guida utente dei Componenti.
* **Correlazione:** Non più utilizzato come termine; sostituito con raggruppamenti di dimensioni. Nelle versioni precedenti di Adobe Analytics, le correlazioni consentivano di suddividere le variabili di traffico. Consulta [Suddividere dimensioni](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md) nella guida utente Analizza.
* **Dati correnti:** Opzione in alcuni rapporti che consente di includere i dati raccolti di recente che non sono ancora stati completamente elaborati. Consulta [Dati correnti](/help/analyze/reports-analytics/current-data.md) nella guida utente Analizza.
* **Collegamento personalizzato:** Tipo di hit che contiene dati non di visualizzazione pagina. Consulta la [s.tl(), funzione](../implement/vars/functions/tl-method.md) nella guida utente Implementa. Vedi anche Hit.
* **Attributi del cliente:** Funzione di Experience Cloud che consente di caricare i dati degli attributi. Consulta [Attributi del cliente](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html?lang=it) nella guida utente dei servizi core.
* **Delegato all’Assistenza clienti:** Un utente designato autorizzato ad interagire direttamente con l’Assistenza clienti Adobe. Consulta [Delegati all’Assistenza clienti](https://helpx.adobe.com/experience-cloud/supported-users.html) nella Knowledge Base Experience Cloud.
* **Server di raccolta dati:** Server di proprietà di un Adobe che ricevono ed elaborano dati. Le richieste di immagini vengono inviate ai server di raccolta dati di Adobe per l’utilizzo nei rapporti.
* **Connettori dati:** Una soluzione di sviluppo completa che consente a terzi di automatizzare il caricamento di dati in Adobe Analytics. I clienti di tale terza parte possono utilizzare un connettore dati per arricchire i propri dati in Adobe Analytics. La maggior parte dei connettori dati utilizza un flusso di lavoro simile utilizzato in Origini dati. Consulta [Data Connectors](/help/import/data-connectors/data-connectors-eol.md) nella guida utente Importazione.
* **Feed dati:** Un’esportazione di dati non elaborati che elenca ogni hit come riga e le variabili come colonne separate. Utilizzato più comunemente per esportare dati di Adobe Analytics in un database di terze parti. Consulta [Feed dati](/help/export/analytics-data-feed/data-feed-overview.md) nella guida utente Esporta.
* **Origini dati:** Consente a un utente di caricare dati da un file in Adobe Analytics. Il file viene in genere estratto da un sito FTP. Consulta [Origini dati](/help/import/data-sources/overview.md) nella guida utente Importazione.
* **Data Warehouse:** Funzione di Adobe Analytics che consente di richiedere rapporti di dimensioni maggiori. Consulta [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) nella guida utente Esporta.
* **Data Workbench:** Precedentemente noto come Insight. Progettato per raccogliere, elaborare, analizzare e visualizzare dati dalle interazioni dei clienti online e offline su più canali.
* **Dimension:** Un tipo di componente che contiene valori variabili, come il testo. Alcuni esempi includono Nome pagina, Codice di tracciamento o Dominio di riferimento. Una metrica è in genere la sua controparte.
* **Serializzazione degli eventi:** Processo di implementazione delle misure per impedire la raccolta di eventi duplicati. Vedi [Serializzazione degli evento](../implement/vars/page-vars/events/event-serialization.md) nella Guida utente di implementazione.
* **eVar:** Consulta Variabile di conversione.
* **Evento:** Vedi Evento di successo.
* **ExcelClient:** Non più utilizzato come termine. Il nome del predecessore del Report Builder.
* **Scadenza:** Nel contesto di una variabile di conversione, per quanto tempo il valore persiste sul backend. Questa persistenza consente di associare gli eventi ai valori delle variabili prima dell’hit dell’evento. Consulta [Variabili di conversione](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md) nella guida utente Admin.
* **Flusso:** Tipo di visualizzazione in Analysis Workspace che mostra i percorsi seguiti dagli utenti sul sito. Consulta [Visualizzazione del flusso](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) nella guida utente Analizza.
* **Genesis:** Non più utilizzato come termine. Il nome precedente di Data Connectors.
* **Suite di rapporti globale:** Termine informale designato per una suite di rapporti che raccoglie hit da più siti.
* **Codice H:** Un predecessore dell&#39;AppMeasurement. Nelle versioni precedenti di Adobe Analytics, le versioni dei codici venivano misurate con &quot;versione H&quot;, come H.27.5, H.26, ecc.
* **Hit:** Una singola richiesta di immagine inviata ai server di raccolta dati Adobe. Le visualizzazioni di pagina e i collegamenti personalizzati possono essere entrambi denominati hit.
* **Richiesta immagine:** Immagine trasparente 1x1 pixel utilizzata per comunicare con i server di raccolta dati Adobe. Un sito web richiede questa immagine invisibile con una lunga stringa di query contenente dati; Adobe restituisce l’immagine invisibile e analizza la stringa di query ricevuta.
* **Approfondimento:** Può fare riferimento a:
   * Il nome precedente della Data Workbench.
   * Custom Insight, un nome storico per la variabile di traffico personalizzata.
* **KPI:** Abbreviazione per l’indicatore di prestazioni chiave. Metriche che aiutano un’azienda a comprendere le prestazioni del sito. Ogni organizzazione dispone di KPI diversi che misurano diversi aspetti della propria attività. Consulta [Creare un documento di progettazione della soluzione](/help/implement/prepare/solution-design.md) nella guida utente Implementa.
* **Latenza:** Ritardo tra la raccolta dei dati e il momento in cui sono disponibili nei rapporti. La latenza tipica in una suite di rapporti è di 30-90 minuti. Consulta [Latenza](/help/technotes/latency.md) nella guida utente delle note tecniche.
* **Lancio:** Non più utilizzato come termine. Il nome precedente abbreviato dei tag in Adobe Experience Platform, la soluzione di implementazione corrente di Adobe. Consulta [Panoramica sui tag](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=it) nella guida utente di Adobe Experience Platform.
* **Prop elenco:** Impostazione che converte una variabile di traffico tipica in modo da supportare più valori nello stesso hit. Qualsiasi variabile di traffico personalizzata può diventare un prop elenco se l’impostazione è abilitata. Consulta [prop](../implement/vars/page-vars/prop.md) nella guida utente Implementa.
* **Var elenco:** Una variabile distinta, separata dalle variabili di conversione. Le variabili elenco supportano più valori nello stesso hit e i valori delle variabili vengono mantenuti in una visita, in modo simile alle variabili di conversione. Per un’organizzazione sono disponibili solo tre variabili elenco. Consulta [list](/help/implement/vars/page-vars/list.md) nella guida utente Implementa.
* **Società di accesso:** Una raccolta di suite di rapporti utilizzata dall’organizzazione. Alcune organizzazioni dispongono di più società di accesso che si applicano a parti diverse della loro organizzazione.
* **Canale di marketing:** Funzione di Adobe Analytics che categorizza gli hit in base al modo in cui sono arrivati al sito. La logica utilizzata per categorizzare gli hit può essere personalizzata utilizzando le regole di elaborazione del canale di marketing. Consulta [Introduzione ai canali di marketing](/help/components/c-marketing-channels/c-getting-started-mchannel.md) nella guida utente Componenti.
* **Metrica:** Tipo di componente che contiene dati quantitativi. I valori delle metriche in genere contengono numeri, come Visualizzazioni pagina, Visite e Entrate. Una dimensione è in genere la sua controparte.
* **Mobile Services:** Un prodotto di Adobe ritirato che ha riunito le funzionalità di mobile marketing per applicazioni per dispositivi mobili da Adobe Experience Cloud, consentendoti di comprendere e migliorare il coinvolgimento degli utenti con le applicazioni.
* **Assegnazione di tag multisuite:** La pratica di inviare lo stesso hit a più suite di rapporti. Con l’introduzione delle suite di rapporti virtuali, questa pratica non è più in gran parte necessaria. La maggior parte delle attività di assegnazione tag per più suite facilita l’inserimento di una suite di rapporti globale.
* **Normalizzazione:** Un modo per organizzare una visualizzazione che prende tutte le metriche e le forza a proporzioni uguali, consentendo un confronto più semplice delle tendenze.
* **Eventi:** Tipo di metrica che mostra quanti hit è stato impostato o persistito un elemento dimensione. Consulta la [Occorrenze](/help/components/metrics/occurrences.md) nella guida utente dei Componenti.
* **Omniture:** Non più utilizzato come termine. L’organizzazione proprietaria di Adobe Analytics prima di essere acquisita da Adobe nel 2009.
* **Percorsi:** Consulta Flusso.
* **Visualizzazione pagina:** Tipo di hit che incrementa le visualizzazioni di pagina. Consulta la [Visualizzazioni pagina](/help/components/metrics/page-views.md) nella guida utente dei Componenti. Vedi anche Hit.
* **Persistenza:** Concetto astratto per le variabili di conversione che consente il collegamento tra un valore di variabile e un evento che si verifica su hit separati. Vedi anche Scadenza.
* **Chiamata al server primaria:** Nome alternativo per la richiesta di immagine o l’hit, utilizzato principalmente nel contesto dell’assegnazione di tag multisuite e della fatturazione. Quando lo stesso hit viene inviato a più suite di rapporti, la prima suite di rapporti è una chiamata al server principale, mentre le altre sono chiamate al server secondarie. Questa regola si applica a tutti i tipi di hit, inclusi la visualizzazione pagina e il tracciamento dei collegamenti. Vedi anche Chiamate al server secondarie.
* **Regole di elaborazione:** Può fare riferimento a:
   * Regole di elaborazione, un modo per modificare la raccolta dei dati utilizzando determinate regole nell’Admin Console. Consulta [Regole di elaborazione](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md) nella guida utente Admin.
   * Regole di elaborazione per il canale di marketing, un set di regole che determina il canale di marketing a cui appartiene un hit. Consulta [Regole di elaborazione per il canale di marketing](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md) nella guida utente Admin.
* **Proprietà:** Vedi Variabile di traffico.
* **Rapporto classifica:** Un formato di rapporto che segue in genere una dimensione con una metrica. Questo tipo di report consente di visualizzare gli elementi principali, ad esempio le pagine più visualizzate sul sito. Consulta anche Report con tendenze.
* **In tempo reale:** Visualizza le variabili configurate non appena vengono raccolte con una latenza minima o nulla. Consulta [Rapporti in tempo reale](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md) nella guida utente Admin.
* **Report Builder:** Componente aggiuntivo per Microsoft Excel che consente di creare richieste personalizzate a partire da dati di Adobe Analytics.
* **Suite di rapporti:** Contenitore generale a cui si inviano i dati. Tutti i rapporti in Adobe Analytics fanno riferimento a una suite di rapporti.
* **Reports &amp; Analytics:** Precedentemente noto come SiteCatalyst. Soluzione browser per la generazione di rapporti e analisi. Strumento di avvio nel pacchetto Analytics.
* **Intervallo date continuo:** Tipo di intervallo di date relativo che cambia con il passare del tempo. Ad esempio, un rapporto che mostra gli ultimi 7 giorni può essere considerato un intervallo di date continuo. Vedi anche intervallo di date statico.
* **RSID:** Abbreviazione per ID suite di rapporti. Una suite di rapporti ha sia un nome descrittivo che un ID suite di rapporti.
* **s.t():** Il nome della funzione in una libreria di AppMeasurement che invia una richiesta di immagine per la visualizzazione della pagina. Alcune librerie di AppMeasurement utilizzano `s.track()` invece. Consulta [t](../implement/vars/functions/t-method.md) nella guida utente Implementa.
* **s<span>.</span>tl():** Il nome della funzione in una libreria di AppMeasurement che invia una richiesta di immagine di tracciamento dei collegamenti. Alcune librerie di AppMeasurement utilizzano `s.trackLink()` invece. Consulta [tl](../implement/vars/functions/tl-method.md) nella guida utente Implementa.
* **s_code.js:** Nome del file JavaScript utilizzato nelle versioni storiche di Adobe Analytics. Il nome corrente del file JavaScript utilizzato è AppMeasurement.js.
* **Satellite:** Non più utilizzato come termine. Il nome del prodotto precedente per Dynamic Tag Management.
* **Chiamata al server secondaria:** Nome alternativo per la richiesta di immagine o l’hit, utilizzato principalmente nel contesto dell’assegnazione di tag multisuite e della fatturazione. Quando lo stesso hit viene inviato a più suite di rapporti, tutte le suite di rapporti dopo la prima elencate sono chiamate al server secondarie. Vedi anche Chiamate al server primarie.
* **Segmento:** Consente di concentrarsi su un sottoinsieme specifico di dati. Consulta [Segmentazione](/help/components/segmentation/seg-overview.md) nella guida utente Componenti.
* **Contenitore segmento:** La parte di un segmento che determina la quantità di dati da inserire. I contenitori possono essere basati su visualizzazione pagina, visita o visitatore. Consulta [Segmentazione](/help/components/segmentation/seg-overview.md) nella guida utente Componenti.
* **Serializzazione:** Consulta Serializzazione degli eventi.
* **Chiamata server:** Nome alternativo per una richiesta di immagine o un hit, utilizzato principalmente nel contesto della fatturazione.
* **Accesso singolo:** Visita in cui una dimensione aveva un solo valore univoco. La visita può avere più hit, purché non siano presenti più valori univoci. Consulta la [Accesso singolo](/help/components/metrics/single-access.md) nella guida utente dei Componenti. Consulta anche Notifica di mancato recapito.
* **SiteCatalyst:** Non più utilizzato come termine. Un nome di prodotto precedente per Adobe Analytics.
* **Documento di progettazione della soluzione:** Noto anche come Solution Design Reference (SDR, riferimento per la progettazione della soluzione). Documento interno gestito da un’organizzazione che illustra il modo in cui vengono utilizzate le variabili personalizzate e la logica utilizzata per compilarle. Consulta [Creare un documento di progettazione della soluzione](/help/implement/prepare/solution-design.md) nella guida utente Implementa.
* **Relazione secondaria:** Non più utilizzato come termine; sostituito con raggruppamenti di dimensioni. Nelle versioni precedenti di Adobe Analytics, le relazioni secondarie consentivano di suddividere le variabili di conversione. Consulta [Suddividere dimensioni](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md) nella guida utente Analizza.
* **Evento di successo:** Azione tracciata eseguita da un utente. La tua organizzazione determina quali eventi monitorare e quali variabili evento di successo utilizzi per tracciarlo. Consulta [Eventi personalizzati](/help/components/metrics/custom-events.md) nella guida utente Componenti.
* **Utente supportato:** Consulta Delegato all’Assistenza clienti.
* **Variabile traffico:** Noto anche come prop. Memorizza un valore personalizzato per un singolo hit. Le versioni precedenti di Adobe Analytics davano alle proprietà un valore univoco, ma i miglioramenti alla piattaforma rendono in gran parte superflue le variabili di traffico personalizzate. L’Adobe consiglia di utilizzare variabili di conversione personalizzate (eVar) nella maggior parte dei casi. Consulta la [Prop](/help/components/dimensions/prop.md) nella guida utente dei Componenti.
* **Rapporto con tendenze:** Un formato di rapporto che in genere mostra più intervalli di date con una metrica. Questo tipo di rapporto ti consente di visualizzare il comportamento di una metrica nel tempo. Vedi anche Rapporto con classifica.
* **Visitatore univoco**: rappresenta il numero di singoli utenti univoci che hanno visitato il sito. Un singolo visitatore univoco può avere più visite. Consulta la [Visitatori univoci](/help/components/metrics/unique-visitors.md) nella guida utente dei Componenti.
* **Suite di rapporti virtuale:** Contenitore virtuale di dati che fa riferimento a una suite di rapporti regolare e consente di perfezionare i dati. I dati non vengono inviati a una suite di rapporti virtuale, ma vengono inviati a una suite di rapporti normale, sulla cui base viene creata una suite di rapporti virtuale. Consulta [Suite di rapporti virtuali](/help/components/vrs/vrs-about.md) nella guida utente Componenti.
* **Visita:** Rappresenta il numero di sessioni univoche che si sono svolte sul sito. Consulta la [Visite](/help/components/metrics/visits.md) nella guida utente dei Componenti.
* **Regola VISTA:** Logica personalizzata creata da Adobe su richiesta di un cliente per copiare, analizzare o filtrare i dati lato server. Le regole VISTA in genere comportano costi aggiuntivi. Consulta anche Regole di elaborazione.
* **Web beacon:** Consulta Richiesta immagine.
