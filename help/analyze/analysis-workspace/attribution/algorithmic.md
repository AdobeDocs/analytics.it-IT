---
title: Algorithmic Attribution
description: Comprendere i dettagli del modello di attribuzione algoritmica.
feature: Attribution
role: User, Admin
exl-id: dd2b2a5b-9c36-4534-999f-f96604f29eab
TQID: 'https://experienceleague.adobe.com/jPLoQcRU8bpCGjKJ37mioUdZOFDUwNehmyBhdx7lj8c'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
subfeature_v2:
  - id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4
    internal-label: Attribution
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 12464bdfe5e8bf2b7b0d253a27b5ad248716731f
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 36%
---
# Attribuzione algoritmica

>[!NOTE]
>
>È necessario disporre del pacchetto **Ultimate** per utilizzare le funzionalità descritte in questa sezione. Se non sai quale pacchetto Adobe Analytics hai, contatta l’amministratore.

Il [modello di attribuzione](models.md) algoritmica in Analysis Workspace è diverso da altri modelli in quanto utilizza tecniche statistiche per allocare credito tra gli elementi dimensionali nel rapporto o nella tabella a forma libera. Come tutti gli altri modelli di attribuzione in Analysis Workspace, l’attribuzione algoritmica può essere utilizzata su qualsiasi dimensione o metrica. L’attribuzione algoritmica supporta segmentazione e raggruppamenti illimitati e distribuisce il 100% delle conversioni a una o più dimensioni nella tabella (nota anche come attribuzione &quot;frazionaria&quot;).


>[!BEGINSHADEBOX]

Per un video demo, consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Attribuzione algoritmica](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/attribution-iq/algorithmic-model-in-attribution-iq){target="_blank"}.

>[!ENDSHADEBOX]


L’algoritmo utilizzato per l’attribuzione è basato sul dividendo Harsanyi dalla teoria del gioco cooperativo. Il dividendo Harsanyi è una generalizzazione della soluzione del valore di Shapley (dal nome di Lloyd Shapley, un economista premio Nobel) per distribuire credito tra i giocatori in un gioco con contributi disuguali al risultato.

Il calcolo dell’attribuzione del credito di conversione per ogni punto di contatto considera ogni punto di contatto di marketing all’interno di un intervallo di lookback come una coalizione di giocatori. A questa coalizione di giocatori, un surplus deve essere equamente distribuito. La distribuzione del surplus di ciascuna coalizione è determinata dal surplus creato in precedenza in modo ricorsivo da ogni subcoalizione.

Per maggiori dettagli, consulta gli articoli originali di John Harsanyi e Lloyd Shapley:

* Shapley, Lloyd S. (1953). A value for n-person games. *Contributions to the Theory of Games, 2(28)*, 307-317.
* Harsanyi, John C. (1963). A simplified bargaining model for the n-person cooperative game. *International Economic Review 4(2)*, 194-220.

>[!NOTE]
>
>Il risultato dell’attribuzione algoritmica differisce dagli altri modelli solo quando nell’intervallo di lookback sono presenti più punti di contatto. Le conversioni con un singolo punto di contatto ricevono un credito del 100% indipendentemente dal modello di attribuzione.
