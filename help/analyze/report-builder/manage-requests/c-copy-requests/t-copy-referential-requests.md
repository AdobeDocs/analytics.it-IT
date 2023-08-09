---
description: Scopri come copiare le richieste referenziali.
title: Come copiare le richieste referenziali
uuid: b6f64630-868f-455b-8682-471ff9fc596e
feature: Report Builder
role: User, Admin
exl-id: 3cd77325-7461-4345-a672-64c03ea1ae5b
source-git-commit: fb39f906d6c08713e4dc8211c917b2942502868e
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 0%

---

# Copiare richieste referenziali

Una richiesta referenziale utilizza i valori delle celle come input per i parametri, ad esempio un filtro dati o un filtro relazionale.

Per propagare o copiare e incollare richieste referenziali nel foglio di calcolo:
* Devi creare almeno una richiesta valida nel foglio di calcolo.
* I dati prodotti dalla richiesta devono contenere una cella il cui valore dipende da una richiesta in un’altra cella (utilizzando un filtro di suddivisione o corrispondente) o da un filtro che accetta input dai dati immessi in una cella.

È inoltre possibile creare richieste che fanno riferimento a filtri di input da richieste in fogli di lavoro diversi, ma non in cartelle di lavoro diverse. Ad esempio, una richiesta nel Foglio 2 può utilizzare una suite di rapporti di una determinata cella nel Foglio 1 e un intervallo di date di una cella in una richiesta nel Foglio 2. Il nuovo output può essere inserito in un foglio o in un nuovo foglio all&#39;interno della stessa cartella di lavoro. Quando si incolla una richiesta relativa, se un filtro di input risiede in un foglio di lavoro diverso da quello in cui si trova l&#39;output della richiesta copiato, il filtro viene incollato come filtro assoluto.

>[!NOTE]
>
>Non è possibile generare una singola richiesta in più fogli di lavoro. Inoltre, il sistema non può incollare alcune delle richieste copiate in nuove cartelle di lavoro perché le richieste contengono filtri di input da altri fogli di lavoro. I filtri di input includono suite di rapporti da celle, intervalli di date da celle, filtri da celle e altri parametri correlati.

**Per copiare richieste referenziali**

1. Seleziona le celle contenenti le richieste da copiare, inclusa la cella di input o a cui si fa riferimento.
1. Fare clic con il pulsante destro del mouse all&#39;interno delle celle evidenziate e selezionare **[!UICONTROL Copy Requests]** dal menu di scelta rapida.

   Dopo aver selezionato l’area in cui si trovano le richieste e le celle di input, il sistema evidenzia le celle con questi elementi.
1. Seleziona una cella o un intervallo di celle contigue da riempire con le richieste incollate.

   Verificare che la cella o l&#39;intervallo di celle selezionato non contenga altri dati o richieste.
1. Fare clic con il pulsante destro del mouse sulla singola cella o sulla cella superiore sinistra nell&#39;intervallo di celle e selezionare **[!UICONTROL Paste Requests]**.

   Quando si incollano richieste che includono una cella di input, le opzioni in [!UICONTROL Paste Requests] include:

   **Usa cella di input assoluto:** Incolla una copia delle richieste e della formattazione associate alle celle selezionate nell&#39;area di incollamento evidenziata. La cella di input (la cella a cui fa riferimento una delle richieste originali) non viene incollata. Al contrario, la cella di input rimane nella stessa posizione di prima.

   **Usa cella di input relativa:** Incolla una copia delle richieste e della formattazione associate alle celle selezionate nell&#39;area di incollamento evidenziata, inclusa una copia della cella di input. La relazione spaziale della richiesta o delle richieste con la cella di input è la stessa della richiesta o delle richieste originali. Tuttavia, anche se le celle appena incollate ora dispongono di una copia delle richieste, inizialmente non hanno contenuto. Ciò si verifica perché quando la cella di input viene ricreata nell&#39;operazione Incolla, nessun dato viene associato alla cella di input. Per visualizzare i dati per le richieste appena incollate, è necessario immettere un valore nella cella di input e quindi aggiornare le richieste.
