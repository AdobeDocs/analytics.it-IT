---
title: Rapporti sul comportamento in Adobe Analytics
description: Scopri come creare rapporti di comportamento in Adobe Analytics
feature: Third-party Integration
exl-id: ea441afa-e595-4ffa-b446-d67e87f8a7c9
source-git-commit: c53f886d5329e2a3b5023f9396c3aa2360a86901
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 5%

---

# Rapporti sul comportamento

I rapporti sul comportamento mostrano informazioni sul modo in cui gli utenti interagiscono con il sito.

Questa pagina presuppone che l’utente abbia una conoscenza di base dell’utilizzo di Analysis Workspace. Consulta [Creazione di un rapporto di base in Analysis Workspace per gli utenti Google Analytics](create-report.md) se non hai ancora familiarità con lo strumento in Adobe Analytics.

## Flusso di comportamento

Il rapporto sul flusso di comportamento può essere ricreato utilizzando la visualizzazione Flusso.

1. Fai clic sull’icona delle visualizzazioni a sinistra, quindi trascina una visualizzazione Flusso sul workspace sopra la tabella a forma libera
2. Individua il **Pagina** , quindi fai clic sull’icona a forma di freccia per visualizzare i valori della pagina. Gli elementi Dimension sono di colore giallo.
3. Individua il valore di pagina desiderato per iniziare, quindi trascinalo nello spazio al centro con l’etichetta &quot;Dimension o elemento&quot;
4. Questo rapporto di flusso è interattivo. Fai clic su uno dei valori per espandere i flussi alle pagine successive o precedenti. Utilizza il menu di scelta rapida per espandere o comprimere le colonne. Possono essere utilizzate anche dimensioni diverse all’interno dello stesso rapporto di flusso.

![Rapporto di flusso](/help/technotes/ga-to-aa/assets/flow.png)

## Contenuto del sito - Tutte le pagine

Il rapporto pagine mostra le prestazioni delle singole pagine del sito.

1. Nel menu Componenti, individua **Pagine** e trascinarlo nella grande area della tabella a forma libera denominata &quot;Rilascia qui un Dimension&quot;.
2. Trascina le metriche desiderate nell’area di lavoro insieme al file creato automaticamente **Occorrenze** metrica. Consulta la [Guida alla traduzione delle metriche](common-metrics.md) per informazioni dettagliate su come ottenere ciascuna metrica.

In alternativa, in Adobe sono disponibili diverse aree di lavoro predefinite denominate modelli. Il modello Consumo di contenuti (Web) fornisce un valore simile al rapporto tutte le pagine.

1. Clic *[!UICONTROL Project]>[!UICONTROL New]*, che apre una finestra modale con le opzioni di progetto.
2. Fai clic sul modello Consumo di contenuti (Web), quindi fai clic su Crea.

## Contenuto del sito - Espansione dei contenuti

Il rapporto di approfondimento del contenuto consente di esaminare il traffico di pagina per struttura URL. È necessaria un’implementazione aggiuntiva per l’utilizzo in Analysis Workspace. L’Adobe consiglia di collaborare con un consulente per l’implementazione per garantire la raccolta accurata di questi dati.

## Contenuto del sito - Pagine di destinazione

Il rapporto pagine di destinazione mostra le pagine di destinazione principali del sito. Le pagine di destinazione sono disponibili in Analysis Workspace come **Pagina di ingresso** dimensione.

1. Nel menu Componenti, individua **Pagina di ingresso** e trascinarlo nella grande area della tabella a forma libera denominata &quot;Rilascia qui un Dimension&quot;.
2. Trascina le metriche desiderate nell’area di lavoro insieme al file creato automaticamente **Occorrenze** metrica. Consulta la [Guida alla traduzione delle metriche](common-metrics.md) per informazioni dettagliate su come ottenere ciascuna metrica.

L’Adobe consiglia di utilizzare **Visite** per questa dimensione.

## Contenuto del sito - Pagine di uscita

Il rapporto pagine di uscita mostra le pagine principali che sono diventate l’ultima pagina della visita di un individuo. È disponibile in Analysis Workspace con lo stesso nome.

1. Nel menu Componenti, individua **Esci da pagina** e trascinarlo nella grande area della tabella a forma libera denominata &quot;Rilascia qui un Dimension&quot;.
2. Trascina le metriche desiderate nell’area di lavoro insieme al file creato automaticamente **Occorrenze** metrica. Consulta la [Guida alla traduzione delle metriche](common-metrics.md) per informazioni dettagliate su come ottenere ciascuna metrica.

L’Adobe consiglia di utilizzare **Visite** per questa dimensione.

## Rapporti velocità sito

I rapporti sulla velocità del sito mostrano la velocità di caricamento delle pagine, rivelando opportunità per aumentare i tempi di caricamento delle pagine.

Questa funzione richiede un’implementazione aggiuntiva su entrambe le piattaforme; l’Adobe consiglia di collaborare con un consulente per l’implementazione per garantire che questi dati siano configurati correttamente per Analysis Workspace. Il [plug-in getPageLoadTime](/help/implement/vars/plugins/getpageloadtime.md) viene in genere assegnato a un eVar per ottenere i dati sulle prestazioni in Adobe Analytics.

## Rapporti sulla ricerca nel sito

I rapporti sulla ricerca nel sito forniscono informazioni approfondite su come i visitatori utilizzano le funzionalità di ricerca interna del sito.

Questa funzione richiede un’implementazione aggiuntiva su entrambe le piattaforme; l’Adobe consiglia di collaborare con un consulente per l’implementazione per garantire che questi dati siano configurati correttamente per Analysis Workspace. In genere, un termine di ricerca interno viene estratto da un parametro di stringa di query e inserito in un eVar per il reporting.

## Rapporti sugli eventi

Gli eventi presentano alcune differenze strutturali importanti tra Google e Adobe Analytics. Entrambi richiedono ulteriori modifiche all’implementazione per funzionare correttamente sulla rispettiva piattaforma.

* Nelle Google Analytics, gli eventi sono definiti come testo nell’implementazione. Gli eventi hanno categorie, azioni ed etichette.
* In Adobe Analytics, gli eventi vengono inizialmente impostati nell’Admin Console in cui gli viene assegnato un identificatore. Tale identificatore viene utilizzato nel codice di implementazione. Ad esempio:
   1. È possibile impostare event1 nell&#39;Admin Console come &#39;Registrazioni&#39;.
   2. Nell’implementazione di, includeresti event1 nella variabile degli eventi nella pagina di conferma della registrazione. Ogni volta che viene visualizzata la pagina di conferma della registrazione, event1 aumenta.
   3. In Analysis Workspace, &quot;Registrazioni&quot; viene visualizzato come metrica da utilizzare in qualsiasi rapporto.

Poiché questa funzione richiede modifiche all’implementazione, Adobe consiglia di collaborare con un consulente per l’implementazione per garantire che i dati siano configurati correttamente per Analysis Workspace.

## Rapporti di Publisher

Simile a come Google richiede una connessione con Google Ad Manager, Adobe offre un prodotto dedicato per fornire approfondimenti denominato Adobe Advertising Cloud. Se la tua organizzazione è interessata a utilizzare questo prodotto, contatta il team del tuo account Adobe.
