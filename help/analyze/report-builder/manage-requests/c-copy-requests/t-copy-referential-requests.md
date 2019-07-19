---
description: Una richiesta referenziale utilizza valori dalle celle come input per parametri, ad esempio un filtro dati o un filtro relazionale.
seo-description: Una richiesta referenziale utilizza valori dalle celle come input per parametri, ad esempio un filtro dati o un filtro relazionale.
seo-title: Copia richieste referenti
solution: Analytics
title: Copia richieste referenti
topic: Generatore di report
uuid: b 6 f 64630-868 f -455 b -8682-471 ff 9 fc 596 e
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Copia richieste referenti

Una richiesta referenziale utilizza valori dalle celle come input per parametri, ad esempio un filtro dati o un filtro relazionale.

Per propagare o copiare e incollare richieste referenti nel foglio di calcolo, è necessario che nel foglio di calcolo sia stato creato almeno una richiesta valida. Inoltre, i dati generati dalla richiesta devono contenere una cella il cui valore dipende da una richiesta in un'altra cella (utilizzando una suddivisione o un filtro corrispondente) o in base a un filtro che prende input dai dati immessi in una cella.

Potete anche creare richieste di input di input da richieste in diversi fogli di lavoro, ma non in diverse cartelle di lavoro. Ad esempio, una richiesta in Foglio 2 può utilizzare una suite di rapporti da una determinata cella nel Foglio 1 e un intervallo di date da una cella in una richiesta nel Foglio 2. Il nuovo output può essere inserito in un foglio o in un nuovo foglio all'interno della stessa cartella di lavoro. Quando incollate una richiesta relativa, se un filtro di input risiede in un foglio di lavoro diverso dal foglio di lavoro in cui si trova l'output della richiesta copiata, il filtro viene incollato come filtro assoluto.

>[!NOTE]
>
>Non potete inviare una singola richiesta in più fogli di lavoro. Inoltre, il sistema non incolla alcune richieste copiate in nuove cartelle di lavoro, poiché le richieste contengono filtri di input da altri fogli di lavoro. I filtri di input includono suite di rapporti dalle celle, intervalli di date dalle celle, filtri dalle celle e altri parametri correlati.

**Per copiare le richieste referenti**

1. Selezionate le celle contenenti le richieste da copiare, inclusa la cella di input o il riferimento alla cella.
1. Right-click within the highlighted cells and select **[!UICONTROL Copy Requests]** from the shortcut menu.

   Dopo aver selezionato l'area in cui si trovano le richieste e le celle di input, il sistema evidenzia le celle con questi elementi.
1. Selezionate una cella o una serie di celle contigue da compilare con le richieste incollate.

   Accertatevi che la cella o l'intervallo di celle selezionato non contenga altri dati o richieste.
1. Right-click the single cell or the top left-most cell in the range of cells and select **[!UICONTROL Paste Requests]**.

   When pasting requests that include an input cell, the options under [!UICONTROL Paste Requests] include:

   **Usa cella di input assoluta:** Incolla una copia delle richieste e la formattazione associata alle celle selezionate all'area incolla che evidenzia. La cella di input (la cella a cui si fa riferimento in una delle richieste originali) non viene incollato. La cella di input resta nella stessa posizione di prima.

   **Usa cella di input relativa:** Incolla una copia delle richieste e la formattazione associata alle celle selezionate all'area incolla evidenziata, inclusa una copia della cella di input. La relazione spaziale delle richieste alla cella di input è identica a quella delle richieste originali. Tuttavia, sebbene le celle appena incollate abbiano una copia delle richieste, inizialmente non hanno contenuto. poiché quando la cella di input viene ricreata nell'operazione Incolla, nessun dato è associato alla cella di input. Per visualizzare i dati per le richieste appena incollate, è necessario immettere un valore nella cella di input, quindi aggiornare le richieste.
