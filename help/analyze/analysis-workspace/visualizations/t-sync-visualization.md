---
description: La sincronizzazione delle visualizzazioni consente di individuare la tabella dati o l’origine dati corrispondente a una visualizzazione.
keywords: Analysis Workspace, sincronizzazione di una visualizzazione con un’origine dati
title: Gestire le origini dati delle visualizzazioni
feature: Visualizations
role: User, Admin
exl-id: 0500b27a-032e-4dc8-98b7-58519ef59368
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 80%

---

# Gestire le origini dati delle visualizzazioni

La sincronizzazione delle visualizzazioni consente di individuare la tabella dati o l’origine dati corrispondente a una visualizzazione.

**Suggerimento:** puoi individuare le visualizzazioni correlate dal colore del punto accanto al titolo. Colori uguali indicano che le visualizzazioni si basano sulla stessa origine dati.

La gestione di un’origine dati consente di mostrare l’origine dati o di bloccare la selezione. Queste impostazioni determinano in che modo la visualizzazione cambia o meno con l’arrivo di nuovi dati.

1. [Crea un progetto](/help/analyze/analysis-workspace/home.md) con una tabella di dati e una [visualizzazione](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md).
1. Nella tabella di dati, seleziona le celle (origine dati) che vuoi associare alla visualizzazione.
1. Nella visualizzazione, fai clic sul punto accanto al titolo per visualizzare la finestra di dialogo **[!UICONTROL Data Source]** (Gestisci origini dati). Seleziona **[!UICONTROL Show Data Source]** (Mostra origine dati) o **[!UICONTROL Lock Selection]** (Blocca selezione).

   ![](assets/manage-data-source.png)

   La sincronizzazione di una visualizzazione in una cella della tabella crea una nuova tabella (nascosta) e codifica tramite i colori la visualizzazione sincronizzata con quella tabella.

## Impostazioni dell’origine dati


>[!BEGINSHADEBOX]

Per un video demo, vedi ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Impostazioni origine dati](https://video.tv.adobe.com/v/23729?quality=12&learn=on){target="_blank"}.

>[!ENDSHADEBOX]


| Elemento | Descrizione |
| --- | --- |
| Visualizzazioni collegate | Se sono presenti visualizzazioni collegate a una tabella a forma libera o a coorte, il punto in alto a sinistra si apre per elencare le visualizzazioni connesse e dispone di una casella di controllo &quot;mostra&quot; per mostrare o nascondere la tabella. Passando il mouse sulla visualizzazione collegata questa viene evidenziata; facendo clic, viene aperta. |
| Mostra origine dati | Consente di mostrare (attivando la casella di controllo) o nascondere (disattivandola) la tabella di dati corrispondente alla visualizzazione. |
| Blocca selezione | Selezionate questa impostazione per bloccare la visualizzazione ai dati attualmente selezionati nella tabella di dati corrispondente. Dopo aver abilitato questa impostazione, puoi scegliere tra:<ul><li>**Posizioni selezionate:** scegli questa opzione se vuoi che la visualizzazione rimanga bloccata sulle posizioni selezionate nella tabella di dati corrispondente. Queste posizioni continuano a essere visualizzate, anche se gli elementi specifici in queste posizioni cambiano. Ad esempio, scegli questa opzione se vuoi visualizzare sempre i migliori cinque nomi di campagne in questa visualizzazione, a prescindere dal nome delle campagne che occupano le prime cinque posizioni.</li><li>**Elementi selezionati**: scegli questa opzione se vuoi che la visualizzazione rimanga bloccata sugli elementi specifici selezionati nella tabella di dati corrispondente. Questi elementi continuano a essere visualizzati, anche se modificano la classificazione tra gli elementi della tabella. Ad esempio, scegli questa opzione se vuoi visualizzare sempre gli stessi cinque nomi di campagne specifiche in questa visualizzazione, a prescindere dalla posizione in graduatoria delle campagne.</li></ul> |

A differenza dell’architettura precedente, con questa architettura Analysis Workspace non crea più un livello duplicato nascosto in cui viene memorizzata la selezione bloccata. Ora, l’origine dati fa riferimento alla tabella da cui è stata creata la visualizzazione.

## Casi d’uso di esempio

* Puoi creare una visualizzazione di riepilogo e bloccarla su una cella nella tabella da cui l’hai creata. Quando abiliti l’opzione Mostra origine dati, viene mostrato esattamente da dove provengono i dati nella tabella. I dati di origine sono disattivati:

  ![](assets/data-source2.png)>
* Puoi aggiungere numerose visualizzazioni, da diverse celle nella stessa tabella, come indicato di seguito. La tabella è la stessa dell’esempio precedente, ma la cella (e la metrica) di origine è diversa:

  ![](assets/data-source3.png)>
* Per verificare se sono presenti visualizzazioni connesse a una tabella a forma libera o a coorte, fai clic sul punto in alto a sinistra (Impostazioni Data Source). Passando il mouse sulla visualizzazione collegata questa viene evidenziata; facendo clic, viene aperta.

  ![](assets/linked-visualizations.png)>
