---
description: La sincronizzazione delle visualizzazioni consente di individuare la tabella dati o l’origine dati corrispondente a una visualizzazione.
keywords: Analysis Workspace;Synchronize visualization with data source
title: Gestione delle origini dati
translation-type: tm+mt
source-git-commit: 6eda9e3e5bd450213253a8181042c24c318c0300

---


# Gestione delle origini dati

La sincronizzazione delle visualizzazioni consente di individuare la tabella dati o l’origine dati corrispondente a una visualizzazione.

**Suggerimento:** puoi individuare le visualizzazioni correlate dal colore del punto accanto al titolo. Colori corrispondenti indicano che le visualizzazioni si basano sulla stessa origine dati.

La gestione di un&#39;origine dati consente di mostrare l&#39;origine dati o bloccare la selezione. Queste impostazioni determinano il modo in cui la visualizzazione cambia (o non cambia) quando entrano nuovi dati.

1. [Crea un progetto](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md) con una tabella di dati e una [visualizzazione](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md).
1. Nella tabella di dati, seleziona le celle (origine dati) che vuoi associare alla visualizzazione.
1. Nella visualizzazione, fai clic sul punto accanto al titolo per visualizzare la finestra di dialogo **[!UICONTROL Data Source]** (Gestisci origini dati). Seleziona **[!UICONTROL Show Data Source]** (Mostra origine dati) o **[!UICONTROL Lock Selection]** (Blocca selezione).

   ![](assets/manage-data-source.png)

   La sincronizzazione di una visualizzazione con una cella della tabella crea una nuova tabella (nascosta) e codifica tramite i colori la visualizzazione sincronizzata con tale tabella.

| Elemento | Descrizione |
|--- |--- |
| Visualizzazioni collegate | Se sono presenti visualizzazioni collegate a una tabella a forma libera o di coorti, con il punto in alto a sinistra si apre l’elenco delle visualizzazioni collegate e una casella “mostra” permette di mostrare o nascondere la tabella.  Quando si passa il mouse sulla visualizzazione collegata viene evidenziata e si fa clic su di essa. |
| Mostra origine dati | Consente di mostrare (attivando la casella di controllo) o nascondere (disattivando) la tabella di dati corrispondente alla visualizzazione. |
| Blocca selezione | Attiva questa impostazione per bloccare la visualizzazione ai dati attualmente selezionati nella tabella di dati corrispondente. Una volta attivato, scegliete tra:  <ul><li>**Posizioni selezionate:** scegli questa opzione se vuoi che la visualizzazione rimanga bloccata sulle posizioni selezionate nella tabella di dati corrispondente. Queste posizioni continueranno a essere visualizzate, anche se cambiano gli elementi specifici in queste posizioni. Ad esempio, scegli questa opzione se vuoi visualizzare sempre i primi cinque nomi di campagne in questa visualizzazione, indipendentemente dai nomi delle campagne che compaiono nelle prime cinque.</li> <li>**Elementi selezionati**: scegli questa opzione se vuoi che la visualizzazione rimanga bloccata sugli elementi specifici selezionati nella tabella di dati corrispondente. Questi elementi continueranno a essere visualizzati, anche se cambiano la loro classificazione tra gli elementi nella tabella. Ad esempio, scegli questa opzione se vuoi visualizzare sempre gli stessi cinque nomi di campagne specifiche in questa visualizzazione, indipendentemente dalla posizione di classifica delle campagne.</li></ul> |

A differenza dell’architettura precedente, con questa architettura Analysis Workspace non crea più un livello duplicato nascosto in cui viene memorizzata la selezione bloccata. Ora, l’origine dati fa riferimento alla tabella da cui è stata creata la visualizzazione.

**Esempi di utilizzo:**

* Puoi creare una visualizzazione di riepilogo e bloccarla su una cella della tabella da cui l’hai creata. Quando si abilita l&#39;opzione &quot;Mostra origine dati&quot;, viene visualizzata esattamente la provenienza di tali informazioni nella tabella. I dati di origine saranno disabilitati:

   ![](assets/data-source2.png)>
* Puoi aggiungere numerose visualizzazioni e ricalcare le voci da celle diverse nella stessa tabella, come mostrato di seguito. La tabella è la stessa dell&#39;esempio precedente, ma la cella (e la metrica) di origine è diversa:

   ![](assets/data-source3.png)>
* Puoi vedere se esistono visualizzazioni collegate a una tabella a forma libera o di coorti facendo clic sul punto in alto a sinistra (Impostazioni origine dati). Quando passi il mouse sulla visualizzazione collegata viene evidenziata, quando fai clic su di essa potrai aprirla.

   ![](assets/linked-visualizations.png)>
