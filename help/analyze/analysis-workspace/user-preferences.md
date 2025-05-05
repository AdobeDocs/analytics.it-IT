---
title: Come impostare le preferenze utente e aziendali in Analysis Workspace
description: Puoi impostare le preferenze generali e di progetto per gli utenti, nonché una preferenza per un tema scuro.
feature: Workspace Basics
role: User, Admin
exl-id: f32e3061-f396-4730-96e1-d251b00e32f0
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '3108'
ht-degree: 99%

---

# Preferenze

Puoi gestire le impostazioni di Analysis Workspace e dei relativi componenti per tutti i nuovi progetti o pannelli creati. I progetti e i pannelli esistenti non sono interessati.


>[!BEGINSHADEBOX]

Consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Gestire le preferenze](https://video.tv.adobe.com/v/3429995/?quality=12&learn=on&captions=ita){target="_blank"} per un video dimostrativo.

>[!ENDSHADEBOX]


## Aggiornare le preferenze

1. In Adobe Analytics, vai alla pagina di destinazione [!UICONTROL **Progetto**], quindi seleziona [!UICONTROL **Preferences**].

   ![Preferenze utente](assets/user-preferences.png)

1. Per informazioni sulle preferenze disponibili in ogni scheda, continua con una delle sezioni seguenti di questo articolo:

   * [Preferenze generali](#general-preferences)

   * [Azienda](#company-preferences)

   * [Preferenze per i progetti](#project-preferences)

   * [Preferenze delle tabelle a forma libera](#freeform-table-preferences)

   * [Preferenze delle visualizzazioni](#visualizations-preferences)

## Preferenze generali

Puoi personalizzare le preferenze generali per tutti i nuovi progetti creati in Analysis Workspace. Per informazioni su come accedere a queste preferenze, consulta la sezione [Aggiornare le preferenze](#update-preferences).

| Preferenza | Opzioni |
| --- | --- |
| Pagina di destinazione | Scegli quale pagina visualizzare come pagina predefinita quando accedi ad Adobe Analytics: <ul><li>Elenco progetti (impostazione predefinita)</li><li>Progetto vuoto</li><li>Progetto specifico selezionato da un elenco</li></ul> |
| Mostra suggerimenti | Visualizza i suggerimenti in una casella blu nell’area in basso a destra di Analysis Workspace. <p>L’opzione è abilitata per impostazione predefinita.</p> |
| Componenti visualizzati nei gruppi della barra a sinistra | Scegli il numero di componenti da visualizzare nel menu Components (Componenti) nella barra a sinistra. <p>Scegliendo 0, il componente non sarà più accessibile dalla barra a sinistra di Workspaces.</p><p>Per impostazione predefinita, vengono visualizzati 5 componenti per ciascuno dei seguenti elementi:</p> <ul><li>Dimensioni</li><li>Metriche</li><li>Filtri</li><li>Intervalli di date</li></ul> <p>Per ulteriori informazioni sui componenti in Analysis Workspace, consulta la sezione [Panoramica dei componenti](/help/analyze/analysis-workspace/components/analysis-workspace-components.md).</p> |

## Preferenze aziendali

Puoi aggiornare le preferenze aziendali che si applicano a tutti gli utenti e ai progetti all’interno dell’organizzazione. Per informazioni su come accedere a queste preferenze, consulta la sezione [Aggiornare le preferenze](#update-preferences).

| Sezione | Preferenza | Opzioni |
| --- | --- | --- |
| **Scheda Rapporti** | | |
|  | Nascondi scheda Rapporti | Nasconde la scheda Rapporti per tutti gli utenti dell’organizzazione. |
| **Condivisione dei progetti** | | |
| | Consenti condivisione solo con gli utenti di Workspace | <p>Quando questa opzione è abilitata, gli utenti dell’organizzazione non possono visualizzare l’opzione “Condividi con chiunque” nel menu Condividi. Ciò significa che gli utenti non possono condividere i progetti con persone che non hanno un account Analysis Workspace nell’organizzazione come descritto in [Condividere un progetto con chiunque (accesso non richiesto)](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-public-link) in [Condividere progetti](/help/analyze/analysis-workspace/curate-share/share-projects.md).</p><p>Quando abiliti o disabiliti questa opzione, prendi in considerazione quanto segue:</p> <ul><li><p>Quando abiliti questa opzione, gli utenti che in precedenza avevano ricevuto l’accesso a un progetto tramite l’opzione di condivisione “Condividi con chiunque” non possono più accedere al progetto.</p></li><li><p>Se questa opzione è abilitata (per consentire la condivisione solo con gli utenti di Workspace) e viene successivamente disabilitata (per consentire la condivisione con chiunque), le persone che in precedenza hanno ricevuto l’accesso a un progetto tramite l’opzione di condivisione “Condividi con chiunque” non riottengono automaticamente l’accesso al progetto. In questo caso, l’utente che ha condiviso il progetto deve abilitare l’opzione [!UICONTROL **Il collegamento è attivo**] che è disponibile quando condividi un progetto con chiunque ([!UICONTROL **Condividi**] > [!UICONTROL **Condividi con chiunque**]), come descritto in [Condividere un progetto con chiunque (accesso non richiesto)](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-public-link) in [Condividere progetti](/help/analyze/analysis-workspace/curate-share/share-projects.md).</p></li> |
| | Richiedere autenticazione Experience Cloud | <p>Quando questa opzione è abilitata, gli utenti a cui viene dato accesso a un progetto dall’opzione “Condividi con chiunque” in Analysis Workspace devono eseguire l’autenticazione utilizzando le credenziali di Experience Cloud.</p> <p>Quando questa opzione è abilitata, ogni volta che un utente condivide un progetto utilizzando l’opzione di condivisione “Condividi con chiunque”, l’opzione “Richiedi autenticazione Experience Cloud” è abilitata nella finestra di dialogo di condivisione e non può essere disabilitata dall’utente che condivide il progetto. (Per informazioni su come gli utenti possono condividere i progetti con chiunque, consulta [Condividere un progetto con chiunque (accesso non richiesto)](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-public-link) in [Condividere progetti](/help/analyze/analysis-workspace/curate-share/share-projects.md).)</p> <p>Quando abiliti questa opzione, prendi in considerazione quanto segue:</p><ul><li><p>Quando abiliti questa opzione, tutti i progetti precedentemente condivisi con l’opzione di condivisione “Condividi con chiunque” e per i quali non è abilitata l’opzione “Richiedi autenticazione Experience Cloud”, vengono disattivati.</p></li> <li><p>Se questa opzione è abilitata (per richiedere l’autenticazione Experience Cloud) e viene successivamente disabilitata (per consentire a chiunque disponga del collegamento di accedere al progetto), le persone che in precedenza hanno ricevuto l’accesso a un progetto tramite l’opzione di condivisione “Condividi con chiunque” non riottengono automaticamente l’accesso al progetto. In questo caso, l’utente che ha condiviso il progetto deve abilitare l’opzione “Il collegamento è attivo” che è disponibile quando condividi un progetto con chiunque ([!UICONTROL **Condividi**] > [!UICONTROL **Condividi con chiunque**] > [!UICONTROL **Il collegamento è attivo**]), come descritto in [Condividere un progetto chiunque (accesso non richiesto)](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-public-link) in [Condividere progetti](/help/analyze/analysis-workspace/curate-share/share-projects.md).</p></li> <li><p>Questa opzione è disponibile solo se SSO è implementato nell’organizzazione. Per informazioni su come gli amministratori di sistema possono abilitare SSO per l’organizzazione, consulta [Configurare identità e Single Sign-On](https://helpx.adobe.com/it/enterprise/using/set-up-identity.html){target=_blank}.</p><p>Se SSO è configurato per l’organizzazione, verifica se nella console è implementato qualsiasi tipo di creazione automatica dell’account. In genere, questa configurazione viene configurata da un amministratore di sistema, come descritto in [Abilita creazione automatica dell’account](https://helpx.adobe.com/it/enterprise/using/automatic-account-creation.html){target=_blank}.</p></li><li><p>Se l’organizzazione opera in un settore che richiede la conformità HIPAA, questa opzione viene abilitata automaticamente e non può essere disabilitata.</p></li></ul> |

{style="table-layout:auto"}

## Preferenze Progetti e Analisi

Puoi personalizzare le preferenze per i progetti per tutti i nuovi progetti creati in Analysis Workspace. Per informazioni su come accedere a queste preferenze, consulta la sezione [Aggiornare le preferenze](#update-preferences).

Alcune di queste preferenze possono essere personalizzate anche per singoli progetti, come descritto in [Panoramica dei progetti](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md).

Fai clic sui titoli delle preferenze collegati per ulteriori informazioni e contesto su ciascuna preferenza.

| Sezione | Preferenza | Opzioni |
| --- | --- | --- |
| **Visualizzazione** | | |
|  | [Densità di visualizzazione](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html?lang=it) | Scegli il contenuto da visualizzare sullo schermo riducendo la spaziatura verticale della barra a sinistra, tabelle a forma libera e tabelle coorte. <ul><li>Compatta</li><li>Comoda</li><li>Espansa (impostazione predefinita)</li></ul> |
| | [Tavolozza dei colori](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/color-palettes.html?lang=it) | Scegli le palette di colori di visualizzazione utilizzate in Analysis Workspace.<ul><li>**Palette per categorie**: applicata a molte visualizzazioni in Analysis Workspace. Ogni colore rappresenta un valore di categoria distinto. Scegli tra le opzioni fornite da Adobe o immetti una palette personalizzata definita da valori esadecimali delimitati da virgole.</li><li>**Palette divergente**: applicata alla tabella coorte in Analysis Workspace. Questa palette contiene un significato numerico con due estremi e una linea di base al centro.</li><li>**Palette sequenziale**: applicata all’analisi guidata delle tendenze di frequenza (barre sovrapposte). Questa palette contiene un significato numerico che va dal chiaro allo scuro.</li></ul> |
| **Dati** | | |
|  | [Suite di rapporti](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=it#report-suite) | Scegli da dove le tabelle e le visualizzazioni derivano i propri dati. <ul><li>Più recente (impostazione predefinita)</li><li>Suite di rapporti specifica selezionata da un elenco</li></ul> |
|  | [Calendario](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=it#calendar) | Seleziona da un elenco di: <ul><li>Intervalli forniti da Adobe (l’impostazione predefinita è Questo mese)</li><li>Intervalli definiti personalizzati</li></ul> |
|  | [Tipo di pannello](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=it) | <ul><li>A forma libera (impostazione predefinita)</li><li>Vuoto</li><li>Quick Insights</li></ul> |
|  | Conta istanze ripetute | Consente di specificare se conteggiare o meno, per i rapporti, le istanze ripetute. Ad esempio, questa impostazione (se attivata) tratta più visualizzazioni consecutive della stessa pagina come molteplici visualizzazioni di pagina. Con questa opzione, vengono conteggiate come singole visualizzazioni di pagina. <p>**Nota:** questa impostazione ha effetto solo su determinate metriche (ad esempio Visite per pagina singola) e non sulle visualizzazioni Flusso o Fallout.</p> |
|  | Formato dei numeri | <ul><li>1.000,00 (impsotazione predefinita)</li><li>1.000,00</li><li>1 000,00</li></ul> |
|  | Carattere separatore CSV | <ul><li>Virgola (impostazione predefinita)</li><li>Punto e virgola</li><li>Due punti</li><li>Barra verticale</li><li>Punto</li><li>Spazio</li><li>Scheda</li></ul> |
|  | Mostra annotazioni | Scegli se rendere visibili le annotazioni nei progetti. Per ulteriori informazioni sulle annotazioni, consulta la sezione [Panoramica delle annotazioni](/help/analyze/analysis-workspace/components/annotations/overview.md). |

## Preferenze delle tabelle a forma libera

Puoi personalizzare le preferenze delle tabelle a forma libera per tutti i nuovi progetti creati in Analysis Workspace. Per informazioni su come accedere a queste preferenze, consulta la sezione [Aggiornare le preferenze](#update-preferences).

Alcune di queste preferenze possono essere personalizzate anche per singole tabelle.

Fai clic sui titoli della sezione collegata per ulteriori informazioni e contesto sulle preferenze disponibili.

| Sezione | Preferenza | Opzioni |
| --- | --- | --- |
| **Tabella** | | |
| | Tipo di tabella | <ul><li>A forma libera</li><li>Generatore di tabelle</li></ul> |
| | Metrica tabella predefinita | <ul><li>Occorrenze</li><li>Visitatori univoci</li><li>Visite</li></ul> |
| | Dimensioni della tabella predefinita | Scegli tra Minuto, Ora, Giorno, Settimana, Mese, Trimestre o Anno. |
| | Allinea date | Seleziona questa opzione per allineare le date di ogni colonna affinché inizino tutte sulla stessa riga. |
| **[Colonna](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)** | | |
| | Testo a capo nelle intestazioni | Consente di mandare automaticamente a capo il testo delle intestazioni nelle tabelle a forma libera, per agevolare la lettura delle intestazioni e la condivisione delle tabelle. Questa opzione è utile per la creazione di file PDF e per le metriche con nomi lunghi. È attivata per impostazione predefinita. |
| | Mostra totali | Questo totale è in genere uguale o un sottoinsieme del [!UICONTROL Grand Total] (Totale complessivo). Riflette eventuali filtri applicati alla tabella a forma libera, inclusa l’opzione [!UICONTROL Include None] (Includi nessuna). |
| | Mostra totali complessivi | Questo totale rappresenta tutti gli hit che sono stati raccolti, talvolta denominati “totale suite di rapporti”. Quando un segmento viene applicato a livello di pannello o all’interno della tabella a forma libera, questo totale si regola per riflettere tutti gli hit che corrispondono ai criteri del segmento. Il totale complessivo non è supportato per tabelle o raggruppamenti con [righe statiche](/help/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.md). |
| | Mostra sparkline | Mostra o nascondi i grafici a linee nella parte inferiore del grafico. Quando è nascosta, la legenda non fa più riferimento visivamente alle linee. |
| | Numero | Determina se mostrare/nascondere il valore numerico di una metrica nella cella. Ad esempio, se la metrica è Visualizzazioni di pagina, il valore numerico corrisponde al numero di visualizzazioni di pagina per l’elemento riga. |
| | Percentuale | Determina se mostrare o nascondere il valore percentuale di una metrica nella cella. Ad esempio, se la metrica è Visualizzazioni di pagina, il valore percentuale corrisponde al numero di visualizzazioni di pagina per l’elemento riga, diviso per il totale di visualizzazioni di pagina per la colonna.  Nota: per garantire una maggiore precisione, è possibile visualizzare percentuali superiori al 100%. Inoltre, abbiamo spostato il limite superiore al 1000% per assicurare che le colonne possano crescere anche in larghezza. |
| | Mostra anomalie <!-- This setting was moved from the "Project" tab. this is already in the tool/docs under "Freeform table, But the doc doesn't give a definition. --> | Determina se eseguire il rilevamento delle anomalie sui valori di questa colonna. |
| | Interpret zero as no value (Interpreta zero come nessun valore) | Per le celle con valore 0, determina se visualizzare 0 oppure la cella vuota. Questa funzione è particolarmente utile se si esaminano i dati quotidianamente e il mese in corso non è ancora terminato.  Invece di visualizzare valori 0 per le date future, è possibile sostituirli con delle celle vuote. Anche i grafici si adeguano a questa impostazione (ossia, se è stata selezionata, non visualizzano linee o barre con valori 0). |
| | Informazioni di base | Determina se mostrare o nascondere tutta la formattazione della cella, inclusi il grafico a barre e la formattazione condizionale <ul><li>Grafico a barre</li> Visualizza un grafico a barre orizzontale che rappresenta il valore della cella rispetto al totale della colonna. <li>Formattazione condizionale</li>Per ulteriori informazioni sulla formattazione condizionale, consulta la sezione “Formattazione condizionale” in [Impostazioni colonna](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)</ul> |
| | Anteprima cella | Mostra un’anteprima di ciascuna cella con le opzioni di formattazione attualmente selezionate attive. |
| **[Riga](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)** | | |
| | Raggruppamento per posizione | Seleziona questa opzione per far sì che il raggruppamento rimanga nella posizione dell’elemento anziché nell’elemento stesso. Per ulteriori informazioni sulle suddivisioni, consulta la sezione [Suddividere le dimensioni](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md). |
| | Calcolo percentuale | <ul><li>Colonna</li><li>Riga</li></ul> |
| | Totali colonne (solo righe statiche) | <ul><li>Visualizza somma di righe: mostra la somma dei singoli elementi di riga </li><li>Visualizza totale complessivo: mostra la somma deduplicata di righe.</li></ul> |

## Preferenze delle visualizzazioni

Puoi aggiornare le preferenze di visualizzazione per tutti i nuovi progetti creati in Analysis Workspace. Per informazioni su come accedere a queste preferenze, consulta la sezione [Aggiornare le preferenze](#update-preferences).

Alcune di queste preferenze possono essere personalizzate anche per le singole visualizzazioni.

Fai clic sui titoli della sezione collegata per ulteriori informazioni e contesto sulle preferenze disponibili.

| Sezione | Preferenza | Opzioni |
| --- | --- | --- |
| **Impostazioni predefinite generali** | | |
| | Percentuali | Visualizza i valori in percentuale per tutte le visualizzazioni. |
| | Visualizzazione legenda | Consente di nascondere il testo della legenda dettagliato per tutte le visualizzazioni. |
| | Limite massimo elementi | Riduce il numero di elementi sull’asse X per tutte le visualizzazioni. Può essere utile se disponi di un set di dati di grandi dimensioni. |
| | Visualizza asse doppio (se applicabile) | Applicabile solo in presenza di due metriche. È possibile avere un asse y a sinistra (per una metrica) e un altro a destra (per l’altra metrica). Questa funzione è utile quando le metriche tracciate hanno dimensioni molto diverse. |
| | Normalizzazione (se applicabile) | Forza le metriche ad adeguarsi alle proporzioni. Questa funzione è utile quando le metriche tracciate hanno dimensioni molto diverse. |
| | Ancoraggio asse Y su zero | Se tutti i valori rappresentati sul grafico sono uniformemente al di sopra dello zero, per impostazione predefinita la parte inferiore dell’asse y sarà NON-ZERO. Attivando questa opzione, l’asse y verrà forzata sullo zero (e il grafico verrà ridisegnato). |
| | Consenti alle anomalie di dimensionare l’asse Y | Se in un grafico sono presenti più metriche, passa il cursore su ogni valore anomalo per visualizzare la relativa banda di valori affidabili. Per rendere la visualizzazione più leggibile, l’intervallo di confidenza del rilevamento delle anomalie non dimensiona automaticamente l’asse y. Questa opzione consente all’intervallo di confidenza di dimensionare la visualizzazione. <p>Per ulteriori informazioni, consulta la sezione [Visualizzare le anomalie in Analysis Workspace](/help/analyze/analysis-workspace/c-anomaly-detection/view-anomalies.md).</p> |
| **[Linee](/help/analyze/analysis-workspace/visualizations/line.md)** | | |
| | Percentuali | Visualizza i valori in percentuale per le visualizzazioni delle linee. |
| | Visualizzazione legenda | Consente di nascondere il testo della legenda dettagliata per la visualizzazione delle linee. |
| | Limite massimo elementi | Riduce il numero di elementi sull’asse X nella visualizzazione delle linee. Può essere utile se disponi di un set di dati di grandi dimensioni. |
| | Visualizza asse doppio (se applicabile) | Applicabile solo in presenza di due metriche. È possibile avere un asse y a sinistra (per una metrica) e un altro a destra (per l’altra metrica). Questa funzione è utile quando le metriche tracciate hanno dimensioni molto diverse. |
| | Normalizzazione (se applicabile) | Forza le metriche ad adeguarsi alle proporzioni. Questa funzione è utile quando le metriche tracciate hanno dimensioni molto diverse. |
| | Mostra asse x | Visualizza l’asse x sul grafico a linee. |
| | Mostra asse y | Visualizza l’asse y sul grafico a linee. |
| | Ancora asse Y | Se tutti i valori rappresentati sul grafico sono uniformemente al di sopra dello zero, per impostazione predefinita la parte inferiore dell’asse y sarà NON-ZERO. Attivando questa opzione, l’asse y verrà forzata sullo zero (e il grafico verrà ridisegnato). |
| | Mostra min | Sovrapponi un’etichetta del valore minimo per evidenziare rapidamente gli avvallamenti in una metrica. Nota: i valori minimi sono derivati dai punti di dati visibili nella visualizzazione e non dall’intero insieme di valori all’interno di una dimensione. |
| | Mostra max | Sovrapponi un’etichetta del valore massimo per evidenziare rapidamente i picchi di una metrica. Nota: i valori massimi sono derivati dai punti di dati visibili nella visualizzazione e non dall’intero insieme di valori all’interno di una dimensione. |
| | Mostra linea di tendenza | Mostra una linea di tendenza di regressione o media mobile della serie di linee. Le linee di tendenza consentono di rappresentare un pattern più chiaro nei dati. |
| **[Coorte](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md)** | | |
| | Granularità | Per le visualizzazioni con tendenze, puoi modificare la granularità temporale (giorno, settimana, mese, trimestre o anno). Questa modifica si applica anche alla tabella dell’origine dati. |
| | Mostra solo percentuale | Rimuove il valore numerico e visualizza solo la percentuale. |
| | Arrotonda percentuale a intero più prossimo | Arrotonda il valore percentuale al numero intero più vicino invece di mostrare il valore decimale. |
| | Mostra riga percentuale media | Inserisce una nuova riga nella parte superiore della tabella, quindi aggiunge la media dei valori all’interno di ogni colonna. |
| | Anteprima coorte | Anteprima dell’aspetto della tavolozza dei colori nella visualizzazione della coorte. |
| | Tavolozza coorte | La tavolozza dei colori utilizzata nella visualizzazione coorte. |
| **[Grafici combinati](/help/analyze/analysis-workspace/visualizations/combo-charts.md)** | | |
| | Mostra asse X | Visualizza l’asse x sul grafico combinato. |
| | Mostra asse Y | Visualizza l’asse y sul grafico combinato. |
| | Visualizza i manubri sulle linee | Mostra i manubri sulle linee nei grafici combinati. |
| **[Riepilogo delle metriche chiave](/help/analyze/analysis-workspace/visualizations/key-metric.md)** | | |
| | Tipo di visualizzazione sintetico | <ul><li>Enfatizza la variazione percentuale</li><li>Enfatizza il valore numerico</li></ul> |
| | Mostra sparkline | Mostra o nascondi i grafici a linee nella parte inferiore del grafico. Quando è nascosta, la legenda non fa più riferimento visivamente alle linee. |
| | Mostra max e min su sparkline | Mostra i valori minimi e massimi nei grafici a linee principali e a linee di confronto. |
| | Mostra confronto | Mostra i dati di confronto. Se nascosti, gli oggetti grafico a linee di confronto e di riepilogo delle modifiche saranno nascosti dalla visualizzazione. |
| | Opzioni per valore numerico | Nella sezione [!UICONTROL **Riepilogo delle metriche chiave**] <ul><li>Mostra variazione percentuale</li><li>Mostra differenza grezza</li>Differenza non elaborata tra il valore totale della metrica nell’intervallo di date principale e l’intervallo di date secondario</ul> |
| **[Fallout](/help/analyze/analysis-workspace/visualizations/fallout/configuring-fallout.md)** | | |
| | Contenitore | Consente di passare da Visita a Visitatore per analizzare il percorso dei visitatori. Il valore predefinito è Visitatore. Queste impostazioni consentono di comprendere il coinvolgimento dei visitatori a livello dei singoli visitatori (attraverso più visite) o di limitare l’analisi a una singola visita. <p>Sono disponibili le seguenti opzioni:</p> <ul><li>Visita</li><li>Visitatore</li></ul> |
| **[Flusso](/help/analyze/analysis-workspace/visualizations/c-flow/create-flow.md)** | | |
| | Contenitore | Nella sezione [!UICONTROL **Flusso**] <ul><li>Visita</li><li>Visitatore</li></ul> |
| | Etichette wrap | Di norma, le etichette degli elementi di Flusso vengono troncate per risparmiare spazio sullo schermo, ma selezionando questa casella puoi rendere visibile l’intera etichetta. Impostazione predefinita = non selezionata. |
| | Includi istanze ripetute | Le visualizzazioni di Flusso si basano su istanze di una dimensione. Questa impostazione offre la possibilità di includere o escludere istanze ripetute, ad esempio i ricaricamenti delle pagine. Tuttavia, le ripetizioni non possono essere rimosse dalle visualizzazioni Flusso che includono dimensioni con più valori, come listVars, listProp, s.product, eVar di merchandising, ecc. Impostazione predefinita = non selezionata. |
| | Mostra descrizioni comandi | Determina se visualizzare le descrizioni comandi contenenti i dati dei nodi quando si passa il mouse sui singoli nodi all’interno di una visualizzazione del flusso. |
| | Numero di colonne | Determina il numero di colonne desiderato nel diagramma di flusso. |
| | Elementi espansi per colonna | Il numero di elementi che desideri inserire in ogni colonna. |
| **Grafici sovrapposti** | | |
| | Sovrapposizione 100% | Applicata alle visualizzazioni Superfici sovrapposte, Barre sovrapposte o Barre orizzontali sovrapposte, questa impostazione converte il grafico in una visualizzazione con sovrapposizione 100%. <p>Per ulteriori informazioni, consulta la sezione [Barre e barre sovrapposte](/help/analyze/analysis-workspace/visualizations/bar.md).</p> |
| **[Istogramma](/help/analyze/analysis-workspace/visualizations/histogram.md)** | | |
| | Numero di bucket | Scegli il numero di intervalli di dati (bucket) nella visualizzazione. Il numero massimo consentito è 50. <p>Per ulteriori informazioni, consulta la sezione [Istogramma](/help/analyze/analysis-workspace/visualizations/histogram.md).</p> |
| | Metodo di conteggio | Scegli tra le seguenti opzioni: <ul><li>Hit</li><li>Visita</li><li>Visitatore</li></ul> <p>Ad esempio, se utilizzato insieme alle visualizzazioni di pagina, puoi scegliere le visualizzazioni di pagina per visitatore, le visualizzazioni di pagina per visita o le visualizzazioni di pagina per hit. Per Hit, “Occorrenze” viene usato come metrica dell’asse y in una tabella a forma libera.</p> |
| **[Mappa](/help/analyze/analysis-workspace/visualizations/map-visualization.md)** | | |
| | Dimensione plotting | <ul><li>Latitudine/longitudine mobile</li><li>Dimensione geografica</li></ul> |
| | Tipo di mappa | <ul><li>Bolle</li><li>Mappa di calore</li></ul> |
| | Tema colore | Scegli tra corallo, rossi, verdi, blu, mappa di calore e positivo/negativo. |
| | Stile mappa | Scegli tra base, strade, luminoso, chiaro, scuro e satellite. |
| **[Variazione di riepilogo](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)** | | |
| | Valore | <!-- Seem to be basically the same options as in "Number value options" --> <ul><li>Variazione percentuale</li><li>Differenza grezza</li></ul> |
| | Percentuali | Visualizza i valori in percentuale per le visualizzazioni Variazione di riepilogo. |
| | Visualizzazione legenda | Consente di nascondere il testo della legenda dettagliata per la visualizzazione Variazione di riepilogo. |
| **[Numero di riepilogo](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)** | | |
| | Percentuali | Visualizza i valori in percentuale per le visualizzazioni Numero di riepilogo. |
| | Visualizzazione legenda | Consente di nascondere il testo della legenda dettagliata per la visualizzazione Numero di riepilogo. |
| | Valore di riepilogo per | Scegli tra Max, Min, Medio, Mediana e Somma. |
| | Abbrevia il valore | Nella sezione [!UICONTROL **Numero di riepilogo**] |
| **[Mappa ad albero](/help/analyze/analysis-workspace/visualizations/treemap.md)** | | |
| | Percentuali | Visualizza i valori in percentuale per le visualizzazioni Mappa ad albero. |
| | Limite massimo elementi | Riduce il numero di elementi sull’asse X nella visualizzazione Mappa ad albero. Può essere utile se disponi di un set di dati di grandi dimensioni. |
| **[Venn](/help/analyze/analysis-workspace/visualizations/venn.md)** | | |
| | Visualizzazione legenda | Consente di nascondere il testo della legenda dettagliata per la visualizzazione Venn. |
| **[A dispersione](/help/analyze/analysis-workspace/visualizations/scatterplot.md)** | | |
| | Percentuali | Visualizza i valori in percentuale per le visualizzazioni A dispersione. |
| | Visualizzazione legenda | Consente di nascondere il testo della legenda dettagliata per la visualizzazione A dispersione. |
| | Limite massimo elementi | Riduce il numero di elementi sull’asse X nella visualizzazione A dispersione. Può essere utile se disponi di un set di dati di grandi dimensioni. |
| | Ancoraggio asse y su zero | Se tutti i valori rappresentati sul grafico sono uniformemente al di sopra dello zero, per impostazione predefinita la parte inferiore dell’asse y sarà NON-ZERO. Attivando questa opzione, l’asse y verrà forzata sullo zero (e il grafico verrà ridisegnato). |

## Ripristina preferenze predefinite

Puoi ripristinare tutte le preferenze utente alle impostazioni predefinite del sistema. Ciò non influisce sulle preferenze dell’amministratore nella scheda Società.

Questa azione non può essere annullata.

1. In Adobe Analytics, seleziona [!UICONTROL **Componenti**] **>** [!UICONTROL **Preferenze**].

   ![Preferenze utente](assets/user-preferences.png)

1. In alto a destra, seleziona **[!UICONTROL Restore defaults]** (Ripristina impostazioni predefinite).

1. Quando richiesto, seleziona **[!UICONTROL Restore defaults]** (Ripristina impostazioni predefinite).

## [!UICONTROL Dark theme]

Se preferisci uno sfondo scuro per l’interfaccia utente di Adobe Analytics, puoi passare a [!UICONTROL Dark theme].

1. Fai clic sull’icona utente Experience Cloud in alto a destra.

   ![tema scuro](assets/dark-theme.png)

1. Sposta **[!UICONTROL Dark theme]** verso destra.

