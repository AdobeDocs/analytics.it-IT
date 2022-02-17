---
title: Rapporti sul comportamento in Adobe Analytics
description: Scopri come creare rapporti sul comportamento in Adobe Analytics
feature: Third-party Integration
exl-id: ea441afa-e595-4ffa-b446-d67e87f8a7c9
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 5%

---

# Rapporti sul comportamento

I rapporti sul comportamento mostrano informazioni su come gli utenti interagiscono con il tuo sito.

Questa pagina presuppone che l’utente abbia una conoscenza di base dell’utilizzo di Analysis Workspace. Vedi [Creare un rapporto di base in Analysis Workspace per gli utenti di Google Analytics](create-report.md) se non hai ancora familiarità con lo strumento in Adobe Analytics.

## Flusso comportamentale

Il rapporto sul flusso di comportamento può essere ricreato utilizzando la visualizzazione Flusso.

1. Fai clic sull’icona delle visualizzazioni a sinistra e trascina una visualizzazione Flusso nell’area di lavoro sopra la tabella a forma libera
2. Individua il **Pagina** , quindi fai clic sull’icona Freccia per visualizzare i valori della pagina. Gli articoli di Dimension sono di colore giallo.
3. Individua il valore di pagina desiderato da iniziare e trascinalo nello spazio contrassegnato come &quot;Dimension o elemento&quot; al centro
4. Questo rapporto di flusso è interattivo. Fai clic su uno dei valori per espandere i flussi alle pagine successive o precedenti. Utilizza il menu di scelta rapida per espandere o comprimere le colonne. Possono essere utilizzate anche dimensioni diverse all’interno dello stesso rapporto di flusso.

![Rapporto di flusso](/help/technotes/ga-to-aa/assets/flow.png)

## Contenuto del sito - Tutte le pagine

Il rapporto sulle pagine mostra le prestazioni delle singole pagine del sito.

1. Nel menu Componenti , individua la **Pagine** e trascinarlo nell’area grande della tabella a forma libera denominata &quot;Rilascia qui un Dimension&quot;.
2. Trascina le metriche desiderate nell’area di lavoro accanto alla creazione automatica **Occorrenze** metrica. Consulta la sezione [Guida alla traduzione delle metriche](common-metrics.md) per informazioni dettagliate su come ottenere ciascuna metrica rispettiva.

In alternativa, Adobe fornisce diverse aree di lavoro predefinite denominate modelli. Il modello Consumo di contenuto (Web) fornisce un valore simile al rapporto su tutte le pagine.

1. Fai clic su *[!UICONTROL Project]>[!UICONTROL New]*, che apre una finestra modale con le opzioni di progetto.
2. Fai clic sul modello Consumo di contenuti (Web), quindi fai clic su Crea.

## Contenuto del sito - Drill-down dei contenuti

Il rapporto di espansione del contenuto ti consente di esaminare il traffico della pagina in base alla struttura dell’URL. È necessaria un’implementazione aggiuntiva per l’utilizzo in Analysis Workspace. Adobe consiglia di lavorare con un consulente di implementazione per garantire che questi dati vengano raccolti con precisione.

## Contenuto del sito - Pagine di destinazione

Il rapporto sulle pagine di destinazione mostra le pagine di destinazione principali sul sito. Le pagine di destinazione sono disponibili in Analysis Workspace come **Pagina di ingresso** dimensione.

1. Nel menu Componenti , individua la **Pagina di ingresso** e trascinarlo nell’area grande della tabella a forma libera denominata &quot;Rilascia qui un Dimension&quot;.
2. Trascina le metriche desiderate nell’area di lavoro accanto alla creazione automatica **Occorrenze** metrica. Consulta la sezione [Guida alla traduzione delle metriche](common-metrics.md) per informazioni dettagliate su come ottenere ciascuna metrica rispettiva.

L&#39;Adobe consiglia di utilizzare **Visite** metrica per questa dimensione.

## Contenuto del sito - Esci dalle pagine

Il rapporto Pagine di uscita mostra le pagine principali che sono diventate l’ultima pagina di una visita individuale. È disponibile in Analysis Workspace con lo stesso nome.

1. Nel menu Componenti , individua la **Pagina di uscita** e trascinarlo nell’area grande della tabella a forma libera denominata &quot;Rilascia qui un Dimension&quot;.
2. Trascina le metriche desiderate nell’area di lavoro accanto alla creazione automatica **Occorrenze** metrica. Consulta la sezione [Guida alla traduzione delle metriche](common-metrics.md) per informazioni dettagliate su come ottenere ciascuna metrica rispettiva.

L&#39;Adobe consiglia di utilizzare **Visite** metrica per questa dimensione.

## Rapporti sulla velocità del sito

I rapporti sulla velocità del sito mostrano la velocità di caricamento delle pagine, mostrando le opportunità per aumentare i tempi di caricamento delle pagine.

Questa funzione richiede un’implementazione aggiuntiva su entrambe le piattaforme; Adobe consiglia di lavorare con un consulente di implementazione per garantire che questi dati siano configurati correttamente per Analysis Workspace. La [plug-in getPageLoadTime](/help/implement/vars/plugins/getpageloadtime.md) viene generalmente assegnato a un eVar per ottenere i dati sulle prestazioni in Adobe Analytics.

## Rapporti sulla ricerca nel sito

I rapporti di ricerca del sito forniscono informazioni approfondite su come i visitatori utilizzano le funzionalità di ricerca interna del sito.

Questa funzione richiede un’implementazione aggiuntiva su entrambe le piattaforme; Adobe consiglia di lavorare con un consulente di implementazione per garantire che questi dati siano configurati correttamente per Analysis Workspace. In genere un termine di ricerca interno viene prelevato da un parametro di stringa query e inserito in un eVar per il reporting.

## Rapporti sugli eventi

Gli eventi presentano alcune importanti differenze strutturali tra Google e Adobe Analytics. Entrambi richiedono ulteriori modifiche all’implementazione per funzionare correttamente sulla rispettiva piattaforma.

* In Google Analytics, gli eventi sono definiti nell’implementazione come testo. Gli eventi hanno categorie, azioni ed etichette.
* In Adobe Analytics, gli eventi vengono inizialmente impostati nell’Admin Console in cui gli viene assegnato un identificatore. Tale identificatore viene utilizzato nel codice di implementazione. Ad esempio:
   1. È possibile impostare event1 nell’Admin Console come &quot;Registrazioni&quot;.
   2. Nella tua implementazione, includeresti event1 nella variabile degli eventi nella pagina di conferma della registrazione. Ogni volta che viene visualizzata la pagina di conferma della registrazione, l&#39;evento1 aumenta.
   3. In Analysis Workspace, &quot;Registrazioni&quot; viene visualizzato come una metrica da utilizzare in qualsiasi rapporto.

Poiché questa funzione richiede modifiche all’implementazione, Adobe consiglia di lavorare con un consulente di implementazione per garantire che i dati siano configurati correttamente per Analysis Workspace.

## Report degli editori

Simile a come Google richiede una connessione con Google Ad Manager, Adobe offre un prodotto dedicato per fornire informazioni chiamate Adobe Advertising Cloud. Se la tua organizzazione è interessata all&#39;utilizzo di questo prodotto, contatta l&#39;Account Manager della tua organizzazione.
