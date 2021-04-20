---
description: Una richiesta referenziale utilizza i valori delle celle come input per i parametri, ad esempio un filtro dati o un filtro relazionale.
title: Copiare richieste referenziali
uuid: b6f64630-868f-455b-8682-471ff9fc596e
feature: Report Builder
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 1%

---


# Copiare richieste referenziali

Una richiesta referenziale utilizza i valori delle celle come input per i parametri, ad esempio un filtro dati o un filtro relazionale.

Per propagare o copiare e incollare le richieste referenziali nel foglio di calcolo, devi aver creato almeno una richiesta valida nel foglio di calcolo. Inoltre, i dati prodotti dalla richiesta devono contenere una cella il cui valore dipende da una richiesta in un’altra cella (utilizzando un filtro di suddivisione o di corrispondenza) o da un filtro che riceve input dai dati immessi in una cella.

È inoltre possibile creare richieste che fanno riferimento a filtri di input da richieste in fogli di lavoro diversi, ma non in cartelle di lavoro diverse. Ad esempio, una richiesta nel foglio 2 può utilizzare una suite di rapporti di una determinata cella nel foglio 1 e un intervallo di date da una cella in una richiesta nel foglio 2. Il nuovo output può essere posizionato in un foglio o in un nuovo foglio all&#39;interno della stessa cartella di lavoro. Quando si incolla una richiesta relativa, se un filtro di input risiede in un foglio di lavoro diverso dal foglio di lavoro in cui si trova l&#39;output della richiesta copiata, il filtro viene incollato come filtro assoluto.

>[!NOTE]
>
>Non è possibile inviare una singola richiesta in più fogli di lavoro. Inoltre, il sistema non può incollare alcune delle richieste copiate in nuove cartelle di lavoro perché le richieste contengono filtri di input da altri fogli di lavoro. I filtri di input includono suite di rapporti da celle, intervalli di date da celle, filtri da celle e altri parametri correlati.

**Per copiare le richieste referenziali**

1. Seleziona le celle contenenti le richieste da copiare, inclusa la cella di input o la cella a cui si fa riferimento.
1. Fai clic con il pulsante destro del mouse all’interno delle celle evidenziate e seleziona **[!UICONTROL Copy Requests]** dal menu di scelta rapida.

   Dopo aver selezionato l&#39;area in cui si trovano le richieste e le celle di input, il sistema evidenzia le celle con questi elementi.
1. Seleziona una cella o un intervallo di celle contigue da riempire con le richieste incollate.

   Assicurati che la cella o l’intervallo di celle selezionato non contenga altri dati o richieste.
1. Fare clic con il pulsante destro del mouse sulla cella singola o sulla cella più in alto a sinistra nell&#39;intervallo di celle e selezionare **[!UICONTROL Paste Requests]**.

   Quando si incollano richieste che includono una cella di input, le opzioni sotto [!UICONTROL Paste Requests] includono:

   **Usa cella di input assoluto:** invia una copia delle richieste e della formattazione associate alle celle selezionate all’area di incolla evidenziata. La cella di input (la cella a cui si fa riferimento in una delle richieste originali) non viene incollata. Al contrario, la cella di input rimane nella stessa posizione di prima.

   **Usa cella di input relativa:** invia una copia delle richieste e della formattazione associate alle celle selezionate all’area di incolla evidenziata, inclusa una copia della cella di input. La relazione spaziale della richiesta o delle richieste con la cella di input è la stessa della richiesta o delle richieste originali. Tuttavia, mentre le celle appena incollate ora hanno una copia delle richieste, inizialmente non hanno contenuto. Questo perché quando la cella di input viene ricreato nell’operazione Incolla, non vengono associati dati alla cella di input. Per visualizzare i dati delle richieste appena incollate, è necessario immettere un valore nella cella di input, quindi aggiornare le richieste.
