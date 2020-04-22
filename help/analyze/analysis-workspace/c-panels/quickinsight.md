---
description: nulle
title: Quick Insights Builder
translation-type: tm+mt
source-git-commit: 77b126b2add78113c266265f413240f27f89bced

---


# Quick Insights Builder

>[!IMPORTANT]
>
>Quick Insights è attualmente in fase di test beta e non è ancora generalmente disponibile per tutti i clienti Adobe Analytics.

Approfondimenti rapidi fornisce indicazioni per i non analisti e i nuovi utenti di Analysis Workspace per imparare a rispondere alle domande aziendali in modo rapido e semplice. È anche un ottimo strumento per gli utenti avanzati che desiderano rispondere rapidamente a una semplice domanda senza dover costruire personalmente una tabella.

Quando inizi a utilizzare Analysis Workspace, potresti chiederti quali visualizzazioni sarebbero più utili, quali dimensioni e metriche potrebbero facilitare le informazioni, dove trascinare e rilasciare elementi, dove creare un segmento, ecc.

A tal fine, in base all’utilizzo da parte della propria azienda di componenti dati in Analysis Workspace, Quick Insights sfrutta un algoritmo che ti presenterà le dimensioni, le metriche, i segmenti e gli intervalli di date più diffusi dalla tua azienda.

Approfondimenti rapidi

* Crea una tabella di dati e la relativa visualizzazione in Analysis Workspace.
* Scopri la terminologia e il vocabolario per i componenti e i componenti di base di Analysis Workspace.
* Suddivisioni semplici di dimensioni, aggiunta di metriche multiple o confronto semplice dei segmenti all&#39;interno di una tabella a forma libera.
* Modifica o prova vari tipi di visualizzazione per trovare lo strumento di ricerca per la tua analisi in modo rapido e intuitivo.

## Terminologia chiave di base

Di seguito sono riportati alcuni dei termini di base con cui hai bisogno di avere familiarità. Ogni tabella di dati è composta da 2 o più blocchi costitutivi che puoi utilizzare per raccontare la storia dei tuoi dati.

| Blocco predefinito | Definizione |
|---|---|
| Dimensione | Le dimensioni sono descrizioni o caratteristiche dei dati delle metriche che possono essere visualizzati, suddivisi e confrontati in un progetto. Sono valori non numerici e date che si suddividono in elementi dimensione. Ad esempio, &quot;browser&quot; o &quot;pagina&quot; sono dimensioni. |
| Elemento dimensione | Gli elementi dimensione sono valori singoli per una dimensione. Ad esempio, gli elementi dimensionali per la dimensione del browser sarebbero &quot;Chrome&quot;, &quot;Firefox&quot;, &quot;Edge&quot;, ecc. |
| Metrica | Le metriche sono informazioni quantitative sull&#39;attività del visitatore, come visualizzazioni, click-through, ricariche, tempo medio trascorso, unità, ordini, ricavi e così via. |
| Visualizzazione | Workspace offre [diverse visualizzazioni](/help/analyze/analysis-workspace/visualizations/t-sync-visualization.md) per creare rappresentazioni visive dei dati. |
| Segmento | I segmenti consentono di identificare sottoinsiemi di visitatori in base a caratteristiche o interazioni con siti Web. Ad esempio, puoi creare segmenti di visitatori in base agli attributi: tipo di browser, dispositivo, numero di visite, paese, genere o in base alle interazioni: campagne, ricerca di parole chiave, motore di ricerca o in base a uscite e voci: visitatori da Facebook, una pagina di destinazione definita, un dominio di riferimento o basati su variabili personalizzate: campo modulo, categorie definite, ID cliente. |

## Guida introduttiva a Approfondimenti rapidi

1. Effettuate l&#39;accesso ad Adobe Analytics utilizzando le credenziali fornite.
1. Vai a [!UICONTROL Workspace] e fai clic **[!UICONTROL Create New Project]** e fai clic su **[!UICONTROL Quick Insights Builder]**.

   ![](assets/qibuilder.png)

1. Quando iniziate, seguite la breve esercitazione che illustra alcune delle nozioni di base di Quick Insight Builder. Oppure, fate clic per **[!UICONTROL Skip Tutorial]**.
1. Seleziona i blocchi di generazione (o componenti): dimensioni (arancione), metriche (verde), segmenti (blu) o intervalli di date (viola) È necessario selezionare almeno una dimensione e una metrica affinché una tabella possa essere generata automaticamente.

   ![](assets/qibuilder2.png)

   Sono disponibili tre modi per selezionare i blocchi di generazione:
   * Trascinali e rilasciali dalla barra a sinistra
   * Se sai cosa stai cercando: Inizia a digitare il nome e Quick Insights ti riempirà gli spazi vuoti
   * Fare clic sull&#39;elenco a discesa ed effettuare una ricerca nell&#39;elenco

1. Dopo aver aggiunto almeno una dimensione e una metrica, verrà creato quanto segue:

   * Tabella a forma libera con la dimensione a sinistra (verticale) e le metriche in alto (orizzontale). Consulta questa tabella:

1. (Facoltativo) Per approfondire le dimensioni e vedere gli elementi dimensionali, fai clic sulla freccia destra > accanto alla quota.



## Limitazioni note

Se provate a modificare direttamente all&#39;interno della tabella, il generatore di informazioni rapide (lo strumento di compilazione vuoto) non sarà sincronizzato. È possibile ripristinare le impostazioni di Anteprima precedente, ma in caso contrario, la creazione diretta causerà il funzionamento della tabella come tabella Freeform tradizionale.

