---
description: Una richiesta referenziale utilizza i valori delle celle come input per i parametri, ad esempio un filtro dati o un filtro relazionale.
title: Copia richieste referenziali
topic: Report builder
uuid: b6f64630-868f-455b-8682-471ff9fc596e
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '535'
ht-degree: 1%

---


# Copia richieste referenziali

Una richiesta referenziale utilizza i valori delle celle come input per i parametri, ad esempio un filtro dati o un filtro relazionale.

Per propagare o copiare e incollare le richieste referenziali nel foglio di calcolo, è necessario che nel foglio di calcolo sia stata creata almeno una richiesta valida. Inoltre, i dati prodotti dalla richiesta devono contenere una cella il cui valore dipende da una richiesta in un&#39;altra cella (utilizzando un filtro di suddivisione o di corrispondenza) oppure da un filtro che preleva i dati immessi in una cella.

È inoltre possibile creare richieste che fanno riferimento a filtri di input da richieste in fogli di lavoro diversi, ma non in cartelle di lavoro diverse. Ad esempio, una richiesta nel Foglio 2 può utilizzare una suite di rapporti di una determinata cella nel Foglio 1 e un intervallo di date da una cella in una richiesta nel Foglio 2. Il nuovo output può essere inserito in un foglio o in un nuovo foglio all&#39;interno della stessa cartella di lavoro. Quando incollate una richiesta relativa, se un filtro di input risiede in un foglio di lavoro diverso dal foglio di lavoro in cui si trova l&#39;output della richiesta copiata, il filtro viene incollato come filtro assoluto.

>[!NOTE]
>
>Non è possibile inviare una singola richiesta in più fogli di lavoro. Inoltre, il sistema non è in grado di incollare alcune delle richieste copiate in nuove cartelle di lavoro perché le richieste contengono filtri di input da altri fogli di lavoro. I filtri di input includono suite di rapporti da celle, intervalli di date da celle, filtri da celle e altri parametri correlati.

**Per copiare le richieste di riferimento**

1. Selezionare le celle contenenti le richieste che si desidera copiare, inclusa la cella di input o cui si fa riferimento alla cella.
1. Fare clic con il pulsante destro del mouse all&#39;interno delle celle evidenziate e selezionare **[!UICONTROL Copy Requests]** dal menu di scelta rapida.

   Dopo aver selezionato l&#39;area in cui si trovano le richieste e le celle di input, il sistema evidenzia le celle con questi elementi.
1. Selezionate una cella o un intervallo di celle contigue da riempire con le richieste incollate.

   Assicurarsi che l&#39;intervallo di celle o celle selezionato non contenga altri dati o richieste.
1. Fare clic con il pulsante destro del mouse sulla cella singola o sulla cella più in alto a sinistra nell&#39;intervallo di celle, quindi selezionare **[!UICONTROL Paste Requests]**.

   Quando si incollano richieste che includono una cella di input, le opzioni sotto [!UICONTROL Paste Requests] includono:

   **Usa cella di input assoluta:** Incolla una copia delle richieste e della formattazione associate alle celle selezionate nell&#39;area Incolla evidenziata. La cella di input (la cella cui si fa riferimento in una delle richieste originali) non viene incollata. Al contrario, la cella di input rimane nella stessa posizione di prima.

   **Usa cella di input relativa:** Incolla una copia delle richieste e della formattazione associate alle celle selezionate nell&#39;area evidenziata, inclusa una copia della cella di input. La relazione spaziale delle richieste con la cellula di input è la stessa delle richieste originali. Tuttavia, mentre le celle appena incollate dispongono ora di una copia delle richieste, inizialmente non hanno contenuto. Questo perché quando la cella di input viene ricreata nell&#39;operazione Incolla, non viene associato alcun dato alla cella di input. Per visualizzare i dati delle richieste appena incollate, è necessario immettere un valore nella cella di input e aggiornare le richieste.
