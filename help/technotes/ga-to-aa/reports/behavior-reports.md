---
title: Rapporti sul comportamento in Adobe  Analytics
description: Scopri come creare rapporti sul comportamento in Adobe  Analytics
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 0%

---


# Rapporti sul comportamento

I rapporti sul comportamento mostrano informazioni sul modo in cui gli utenti interagiscono con il sito.

Questa pagina presuppone che l&#39;utente disponga di conoscenze di base sull&#39;utilizzo  Analysis Workspace. Consultate [Creare un rapporto di base in  Analysis Workspace per gli utenti](create-report.md) di Google  Analytics se non avete ancora familiarità con lo strumento in Adobe  Analytics.

## Flusso comportamentale

Il rapporto sul flusso di comportamento può essere ricreato utilizzando la visualizzazione Flusso.

1. Fai clic sull’icona delle visualizzazioni a sinistra, quindi trascina una visualizzazione Flusso nell’area di lavoro sopra la tabella a forma libera
2. Individuare la dimensione **Pagina** , quindi fare clic sull&#39;icona Freccia per visualizzare i valori della pagina. Gli elementi dimensione sono colorati in giallo.
3. Individuate il valore della pagina con cui iniziare e trascinatelo nello spazio contrassegnato come &quot;Dimensione o elemento&quot; al centro
4. Questo rapporto di flusso è interattivo. Fate clic su uno dei valori per espandere i flussi alle pagine successive o precedenti. Per espandere o comprimere le colonne, usate il menu di scelta rapida. All’interno dello stesso rapporto di flusso possono essere utilizzate dimensioni diverse.

![Report flusso](/help/technotes/ga-to-aa/assets/flow.png)

## Contenuto del sito - Tutte le pagine

Il rapporto sulle pagine mostra le prestazioni delle singole pagine sul sito.

1. Nel menu Componenti, individua la dimensione **Pagine** e trascinala nell’area grande della tabella a forma libera con l’etichetta &quot;Rilascia qui una dimensione&quot;.
2. Trascina le metriche desiderate nell&#39;area di lavoro accanto alla metrica **Occorrenze** creata automaticamente. Consulta la guida [alla traduzione](common-metrics.md) Metrica per informazioni dettagliate su come ottenere ciascuna metrica.

In alternativa, Adobe offre diversi ambienti di lavoro già creati, denominati modelli. Il modello Consumo di contenuto (Web) fornisce un valore simile al rapporto Tutte le pagine.

1. Fate clic su *[!UICONTROL Project]>[!UICONTROL New]*, per aprire una finestra modale con le opzioni del progetto.
2. Fate clic sul modello Consumo di contenuto (Web), quindi fate clic su Crea.

## Contenuto del sito - Drill-down dei contenuti

Il rapporto di espansione del contenuto consente di analizzare il traffico delle pagine in base alla struttura URL. È necessaria un&#39;implementazione aggiuntiva per  Analysis Workspace. Adobe consiglia di collaborare con un consulente per l&#39;implementazione per garantire che i dati vengano raccolti con precisione.

## Contenuto del sito - Pagine di destinazione

Il rapporto sulle pagine di destinazione mostra le pagine di destinazione principali del sito. Le pagine di destinazione sono disponibili in  Analysis Workspace come dimensione **Pagina** di immissione.

1. Nel menu Componenti, individua la dimensione Pagina **** di immissione e trascinala nell’area grande della tabella a forma libera con l’etichetta &quot;Rilascia qui una dimensione&quot;.
2. Trascina le metriche desiderate nell&#39;area di lavoro accanto alla metrica **Occorrenze** creata automaticamente. Consulta la guida [alla traduzione](common-metrics.md) Metrica per informazioni dettagliate su come ottenere ciascuna metrica.

Adobe consiglia di utilizzare la metrica **Visite** per questa dimensione.

## Contenuto del sito - Esci da pagine

Il rapporto Pagine di uscita mostra le pagine principali che sono diventate l&#39;ultima pagina di una visita di un individuo. È disponibile in  Analysis Workspace con lo stesso nome.

1. Nel menu Componenti, individua la dimensione Pagina **di** uscita e trascinala nell’area grande della tabella a forma libera con l’etichetta &quot;Rilascia qui una dimensione&quot;.
2. Trascina le metriche desiderate nell&#39;area di lavoro accanto alla metrica **Occorrenze** creata automaticamente. Consulta la guida [alla traduzione](common-metrics.md) Metrica per informazioni dettagliate su come ottenere ciascuna metrica.

Adobe consiglia di utilizzare la metrica **Visite** per questa dimensione.

## Rapporti sulla velocità del sito

I rapporti sulla velocità del sito mostrano la velocità di caricamento delle pagine, rivelando le opportunità per aumentare i tempi di caricamento delle pagine.

Questa funzione richiede un&#39;implementazione aggiuntiva su entrambe le piattaforme; Adobe consiglia di collaborare con un consulente per l&#39;implementazione per verificare che questi dati siano configurati correttamente per  Analysis Workspace. Il plug-in [](/help/implement/vars/plugins/getpageloadtime.md) getPageLoadTime viene in genere assegnato a un eVar per ottenere i dati sulle prestazioni in Adobe  Analytics.

## Rapporti sulla ricerca nel sito

I rapporti sulla ricerca nel sito forniscono informazioni approfondite sul modo in cui i visitatori utilizzano le funzionalità di ricerca interna del sito.

Questa funzione richiede un&#39;implementazione aggiuntiva su entrambe le piattaforme; Adobe consiglia di collaborare con un consulente per l&#39;implementazione per verificare che questi dati siano configurati correttamente per  Analysis Workspace. In genere, un termine di ricerca interno viene estratto da un parametro di stringa di query e inserito in una eVar per il reporting.

## Rapporti sugli eventi

Gli eventi presentano notevoli differenze strutturali tra Google e Adobe  Analytics. Entrambe richiedono ulteriori modifiche di implementazione per funzionare correttamente sulla rispettiva piattaforma.

* In Google  Analytics, gli eventi sono definiti nella vostra implementazione come testo. Gli eventi hanno categorie, azioni ed etichette.
* In Adobe  Analytics, gli eventi vengono impostati per la prima volta nell&#39;Admin Console  a cui è assegnato un identificatore. Tale identificatore viene utilizzato nel codice di implementazione. Ad esempio:
   1. È possibile impostare event1 nell&#39;Admin Console  come &quot;Registrazioni&quot;.
   2. Nella tua implementazione, includeresti event1 nella variabile degli eventi nella pagina di conferma della registrazione. Ogni volta che viene visualizzata la pagina di conferma della registrazione, event1 aumenta.
   3. In  Analysis Workspace, &#39;Registrazioni&#39; viene visualizzata come metrica da utilizzare in qualsiasi rapporto.

Poiché questa funzione richiede modifiche all&#39;implementazione, Adobe consiglia di collaborare con un consulente per l&#39;implementazione per verificare che i dati siano configurati correttamente per  Analysis Workspace.

## Report di Publisher

Analogamente a quanto Google richiede una connessione con Google Ad Manager, Adobe offre un prodotto dedicato per fornire approfondimenti denominato Adobe  Advertising Cloud. Se l&#39;azienda è interessata a utilizzare questo prodotto, contatta l&#39;Account Manager dell&#39;organizzazione.
