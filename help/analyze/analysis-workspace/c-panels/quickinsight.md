---
description: nulle
title: Generatore di informazioni rapide
translation-type: tm+mt
source-git-commit: 718de88664e9d27ed5973f5269a324ffbc3b5414

---


# Generatore di informazioni rapide

>[!IMPORTANT]
>
>**[!UICONTROL Quick Insights]** attualmente è in fase di test beta e non è ancora disponibile in genere a tutti i clienti di Adobe Analytics.

[!UICONTROL Quick Insights] fornisce indicazioni per i non analisti e i nuovi utenti [!UICONTROL Analysis Workspace] per imparare a rispondere alle domande aziendali in modo rapido e semplice. È anche un ottimo strumento per gli utenti avanzati che desiderano rispondere rapidamente a una semplice domanda senza dover costruire personalmente una tabella.

Quando inizi a utilizzare questo [!UICONTROL Analysis Workspace], potresti chiederti quali visualizzazioni sarebbero più utili, quali dimensioni e metriche potrebbero facilitare le informazioni, dove trascinare e rilasciare elementi, dove creare un segmento, ecc.

A tal fine, e in base all&#39;utilizzo dei componenti dati da parte della propria azienda in [!UICONTROL Analysis Workspace], [!UICONTROL Quick Insights] sfrutta un algoritmo che ti presenterà le dimensioni, le metriche, i segmenti e gli intervalli di date più comuni utilizzati dalla tua azienda.

[!UICONTROL Quick Insights] aiuta

* Crea una tabella di dati e la relativa visualizzazione in [!UICONTROL Analysis Workspace].
* Impara la terminologia e il vocabolario per componenti e pezzi di [!UICONTROL Analysis Workspace]base.
* Suddivisioni semplici di dimensioni, aggiunta di metriche multiple o confronto semplice dei segmenti all&#39;interno di un [!UICONTROL Freeform table].
* Modifica o prova vari tipi di visualizzazione per trovare lo strumento di ricerca per la tua analisi in modo rapido e intuitivo.

## Terminologia chiave di base

Di seguito sono riportati alcuni dei termini di base con cui hai bisogno di avere familiarità. Ogni tabella di dati è composta da 2 o più blocchi (componenti) utilizzati per raccontare la storia dei dati.

| Blocco predefinito (componente) | Definizione |
|---|---|
| [!UICONTROL Dimension] | Le dimensioni sono descrizioni o caratteristiche dei dati delle metriche che possono essere visualizzati, suddivisi e confrontati in un progetto. Sono valori non numerici e date che si suddividono in elementi dimensione. Ad esempio, &quot;browser&quot; o &quot;pagina&quot; sono dimensioni. |
| [!UICONTROL Dimension item] | Gli elementi dimensione sono valori singoli per una dimensione. Ad esempio, gli elementi dimensionali per la dimensione del browser sarebbero &quot;Chrome&quot;, &quot;Firefox&quot;, &quot;Edge&quot;, ecc. |
| [!UICONTROL Metric] | Le metriche sono informazioni quantitative sull&#39;attività del visitatore, come visualizzazioni, click-through, ricariche, tempo medio trascorso, unità, ordini, ricavi e così via. |
| [!UICONTROL Visualization] | Workspace offre [diverse visualizzazioni](/help/analyze/analysis-workspace/visualizations/t-sync-visualization.md) per creare rappresentazioni visive dei dati, ad esempio grafici a barre, grafici ad anello, istogrammi, grafici a linee, mappe, grafici a dispersione e altri elementi. |
| [!UICONTROL Breakdown] | Una suddivisione è un modo per letteralmente suddividere una dimensione per altre dimensioni. Nel nostro esempio, potresti suddividere gli Stati Uniti per dispositivi mobili per ottenere le visite dei dispositivi mobili per stato, per tipo di dispositivo mobile, o per regioni, per campagne interne, ecc. |
| [!UICONTROL Segment] | I segmenti consentono di identificare sottoinsiemi di visitatori in base a caratteristiche o interazioni con siti Web. Ad esempio, puoi creare [!UICONTROL Visitor] segmenti in base agli attributi: tipo di browser, dispositivo, numero di visite, paese, genere o in base alle interazioni: campagne, ricerca di parole chiave, motore di ricerca o in base a uscite e voci: visitatori da Facebook, una pagina di destinazione definita, un dominio di riferimento o basati su variabili personalizzate: campo modulo, categorie definite, ID cliente. |

## Guida introduttiva a Approfondimenti rapidi

1. Effettuate l&#39;accesso ad Adobe Analytics utilizzando le credenziali fornite.
1. Vai a [!UICONTROL Workspace] e fai clic **[!UICONTROL Create New Project]** e fai clic su **[!UICONTROL Quick Insights Builder]**.

   ![](assets/qibuilder.png)

1. Quando iniziate, seguite la breve esercitazione che illustra alcune delle [!UICONTROL Quick Insights Builder] nozioni di base. Oppure, fate clic per **[!UICONTROL Skip Tutorial]**.
1. Seleziona i blocchi di generazione (o componenti): dimensioni (arancione), metriche (verde), segmenti (blu) o intervalli di date (viola) È necessario selezionare almeno una dimensione e una metrica affinché una tabella possa essere generata automaticamente.

   ![](assets/qibuilder2.png)

   Sono disponibili tre modi per selezionare i blocchi di generazione:
   * Trascinali e rilasciali dalla barra a sinistra.
   * Se sai cosa stai cercando: Iniziate a digitare il nome e [!UICONTROL Quick Insights Builder] riempite gli spazi vuoti.
   * Fare clic sull&#39;elenco a discesa ed effettuare una ricerca nell&#39;elenco.

1. Dopo aver aggiunto almeno una dimensione e una metrica, verrà creato quanto segue:

   * Tabella a forma libera con la dimensione (qui, Stati Uniti) verticale e la metrica (qui, Visite) orizzontalmente nella parte superiore. Consulta questa tabella:
   ![](assets/qibuilder3.png)

   * Una visualizzazione associata, in questo caso un grafico a [barre](/help/analyze/analysis-workspace/visualizations/bar.md). La visualizzazione generata si basa sul tipo di dati aggiunto alla tabella. Puoi modificare il tipo di visualizzazione facendo clic sulla freccia a discesa accanto a **[!UICONTROL Bar]**.


1. (Facoltativo) Per approfondire le dimensioni e vedere gli elementi dimensionali, fai clic sulla freccia destra > accanto alla quota.

1. Provate ad aggiungere altri miglioramenti come descritto di seguito in &quot;Altre opzioni utili&quot;.

## Altre opzioni utili

Altri utili suggerimenti compariranno nel pannello, alcuni [!UICONTROL Quick Insights Builder]a seconda dell’ultima azione.

* **Prova a trascinare**: Se, ad esempio, è stato utilizzato il menu a discesa per selezionare il blocco predefinito, potrebbe essere visualizzato quanto segue:

   ![](assets/qibuilder4.png)

* **Modifica della visualizzazione**: invita a provare diverse rappresentazioni visive dei tuoi dati fino a trovare quella che risplende davvero. Esempio di grafico a linee:

   ![](assets/qibuilder8.png)

* **Suddivisione per**: Puoi utilizzare fino a 3 livelli di analisi approfondite sulle dimensioni per espandere i dati effettivamente necessari.

   ![](assets/qibuilder5.png)

* **Aggiungi altre metriche**: Puoi aggiungere fino a 2 ulteriori metriche utilizzando l&#39;operatore AND per aggiungerle alla tabella.

   ![](assets/qibuilder6.png)

* **Aggiungi altri segmenti**: Puoi aggiungere fino a 2 segmenti utilizzando gli operatori AND o OR per aggiungerli alla tabella. Osserva cosa succede alla tabella quando aggiungi Utenti mobili O Visitatori fedeli. Si trovano l&#39;uno accanto all&#39;altro, sopra le metriche. Se hai aggiunto Utenti mobili e Visitatori fedeli, vedrai i risultati di entrambi i segmenti insieme e saranno sovrapposti l’uno all’altro nella tabella.

   ![](assets/qibuilder7.png)

## Limitazioni note

Se si tenta di modificare direttamente all&#39;interno della tabella, la sincronizzazione non sarà possibile [!UICONTROL Quick Insights Builder] (lo strumento di compilazione). È possibile ripristinare le impostazioni di Anteprima precedente andando **[!UICONTROL Help > Tutorials]** oppure cancellare la tabella facendo clic **[!UICONTROL Resync Builder]** in alto a destra nel pannello Approfondimenti rapidi.

In caso contrario, la creazione diretta della tabella ora si comporta come una tabella a forma libera tradizionale, senza le funzioni utili per i nuovi utenti.

