---
description: La sincronizzazione delle visualizzazioni consente di individuare la tabella dati o l’origine dati corrispondente a una visualizzazione.
keywords: Analysis Workspace; Sincronizzazione della visualizzazione con l'origine dati
seo-description: La sincronizzazione delle visualizzazioni consente di individuare la tabella dati o l’origine dati corrispondente a una visualizzazione.
seo-title: Gestione delle origini dati
solution: Analytics
title: Gestione delle origini dati
topic: Reports & Analytics
uuid: 7 bacf 497-a 933-463 a-bf 9 d-f 6 d 0 c 5 de 0 cba
translation-type: tm+mt
source-git-commit: 0bd28ea64b4e225b33c1fec7f185c7006bdb7f7c

---


# Gestione delle origini dati

La sincronizzazione delle visualizzazioni consente di individuare la tabella dati o l’origine dati corrispondente a una visualizzazione.

**Suggerimento:** puoi individuare le visualizzazioni correlate dal colore del punto accanto al titolo. Colori uguali indicano che le visualizzazioni si basano sulla stessa origine dati.

La gestione di un’origine dati consente di mostrare l’origine dati o di bloccare la selezione. Queste impostazioni determinano in che modo la visualizzazione cambia o meno con l’arrivo di nuovi dati.

1. [Crea un progetto](../../../analyze/analysis-workspace/build-workspace-project/t-freeform-project.md#task_C2C698ACC7954062A28E4784911E6CF2) con una tabella di dati e una [visualizzazione](../../../analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#concept_09242627629147A88A68F1506954C276).
1. Nella tabella di dati, seleziona le celle (origine dati) che vuoi associare alla visualizzazione.
1. In the visualization, click the dot next to the title to bring up the **[!UICONTROL Data Source]** dialog. Select **[!UICONTROL Show Data Source]** or **[!UICONTROL Lock Selection]**.

   ![](assets/manage-data-source.png)

   La sincronizzazione di una visualizzazione in una cella della tabella crea una nuova tabella (nascosta) e codifica tramite i colori la visualizzazione sincronizzata con quella tabella.

| Elemento | Descrizione |
|--- |--- |
| Visualizzazioni collegate | Se sono presenti visualizzazioni collegate a una tabella a forma libera o di coorti, con il punto in alto a sinistra si apre l’elenco delle visualizzazioni collegate e una casella Mostra permette di mostrare o nascondere la tabella.  Quando si passa il mouse sulla visualizzazione collegata questa viene evidenziata; quando si fa clic, viene aperta. |
| Mostra origine dati | Consente di mostrare (attivando la casella di controllo) o nascondere (disattivandola) la tabella di dati corrispondente alla visualizzazione. |
| Blocca selezione | Selezionate questa impostazione per bloccare la visualizzazione ai dati attualmente selezionati nella tabella di dati corrispondente. Dopo aver abilitato questa impostazione, puoi scegliere tra:  <ul><li>**Posizioni selezionate:** scegli questa opzione se vuoi che la visualizzazione rimanga bloccata sulle posizioni selezionate nella tabella di dati corrispondente. Queste posizioni continueranno ad essere visualizzate, anche nel caso in cui cambiassero gli elementi specifici che occupano tali posizioni. Ad esempio, scegli questa opzione se vuoi visualizzare sempre i migliori cinque nomi di campagne in questa visualizzazione, a prescindere dal nome delle campagne che occupano le prime cinque posizioni.</li> <li>**Elementi selezionati**: scegli questa opzione se vuoi che la visualizzazione rimanga bloccata sugli elementi specifici selezionati nella tabella di dati corrispondente. Questi elementi continueranno a essere visualizzati, anche nel caso in cui cambiassero posizione in graduatoria rispetto agli altri elementi della tabella. Ad esempio, scegli questa opzione se vuoi visualizzare sempre gli stessi cinque nomi di campagne specifiche in questa visualizzazione, a prescindere dalla posizione in graduatoria delle campagne.</li></ul> |

Questa architettura è diversa da quella precedente in cui Analysis Workspace non crea più una tabella nascosta con la selezione bloccata. Ora, l’origine dati fa riferimento alla tabella da cui è stata creata la visualizzazione.

**Esempi di utilizzo:**

* Puoi creare una visualizzazione di riepilogo e bloccarla su una cella nella tabella da cui l’hai creata. Quando abiliti l’opzione Mostra origine dati, viene mostrato esattamente da dove provengono i dati nella tabella. I dati origine sono visualizzati in grigio:

   ![](assets/data-source2.png)&gt;
* Puoi aggiungere numerose visualizzazioni, da diverse celle nella stessa tabella, come indicato di seguito. La tabella è la stessa dell’esempio precedente, ma la cella (e la metrica) di origine è diversa:

   ![](assets/data-source3.png)&gt;
* Per vedere se esistono visualizzazioni collegate a una tabella a forma libera o di coorti, fai clic sul punto in alto a sinistra (Impostazioni origine dati). Passa il mouse sulla visualizzazione collegata per evidenziarla; fai clic per aprirla.

   ![](assets/linked-visualizations.png)&gt;
