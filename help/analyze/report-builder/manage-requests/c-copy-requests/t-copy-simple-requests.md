---
description: Copia una richiesta semplice invece di una richiesta referenziale. Una richiesta semplice è una richiesta che non contiene riferimenti a un'altra richiesta o al contenuto di una cella.
title: Copiare richieste semplici
uuid: ff20560a-01ee-47e7-8bd1-b73edb010456
feature: Report Builder
role: User, Admin
exl-id: ceed28d5-cb7f-4343-96fd-2ce09f5a3515
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 1%

---

# Copiare richieste semplici

Copia una richiesta semplice invece di una richiesta referenziale. Una richiesta semplice è una richiesta che non contiene riferimenti a un&#39;altra richiesta o al contenuto di una cella.

Una [richiesta referenziale](/help/analyze/report-builder/manage-requests/c-copy-requests/t-copy-referential-requests.md) utilizza i valori delle celle come input per i parametri, ad esempio un filtro dati o un filtro relazionale. Questi filtri utilizzano corrispondenze o tendenze e si basano sui risultati di una richiesta precedente o sul contenuto immesso dall’utente di una cella, denominata cella di input .
1. Crea una richiesta valida.
1. Fai clic con il pulsante destro del mouse su una delle celle in cui è mappata la richiesta oppure seleziona un&#39;area di celle contenente richieste.

   Scegli una cella da cui copiare nel gruppo di celle coperto dalla richiesta. La scelta preferita è la cella più in alto e più a sinistra del set di celle coperto dalla richiesta e funziona da sinistra a destra. Questo perché il foglio di calcolo Excel ha centinaia di colonne e migliaia di righe disponibili per l&#39;espansione verso destra e verso il basso. Se si decide di avviare una copia della richiesta dalla cella più a destra o dalla cella inferiore in un set di celle associato a una richiesta, il sistema non consente di incollare la richiesta se le celle da incollare si estendono oltre il bordo sinistro o superiore del foglio di calcolo.
1. Select **[!UICONTROL Copy Request]**.
1. In un’altra parte del foglio di calcolo, fai clic con il pulsante destro del mouse su una cella vuota (una cella che non contiene richieste).

   Per evitare di perdere o danneggiare le richieste già create, non puoi incollare celle contenenti richieste alle celle attualmente mappate con richieste. Se copi o tagli le celle contenenti richieste, il menu di scelta rapida non rende disponibile l’opzione [!UICONTROL Paste Requests] quando fai clic con il pulsante destro del mouse sulle celle (o sul set di celle) contenenti richieste. È necessario selezionare una cella diversa come destinazione dell&#39;operazione Incolla in modo che le richieste non si sovrappongano. Ciò si applica se si seleziona una singola cella con una richiesta da incollare o una regione di celle contenenti richieste.
1. Fai clic su **[!UICONTROL Paste Request]**.

   Una copia della richiesta originale viene inserita nella cella o nelle celle, in una posizione o in posizioni rispetto alla richiesta originale.

   >[!NOTE]
   >
   >Vengono copiate solo le richieste, non il contenuto delle celle. Se si dispone di altre informazioni non basate su richieste, ma rilevanti per comprendere i dati visualizzati nelle celle (come intestazioni di colonna di tabella o identificatori di riga), utilizzare i comandi standard di Excel Copia e Incolla.

   Poiché in Excel vengono utilizzati diversi Appunti per copiare il contenuto delle celle e le richieste di copia, è possibile copiare sia il contenuto delle celle non richieste che le richieste eseguendo una serie di richieste Copia/Incolla e Copia richieste/Incolla . Tuttavia, se si applica la formattazione alle richieste nel foglio di calcolo e quindi si copia e incolla, Report Builder riproduce la formattazione originale (ad esempio bordi, font, ecc.) nell’area Incolla.

   La modifica di una richiesta copiata o tagliata negli Appunti prima di incollare la richiesta rimuove la richiesta dagli Appunti. Pertanto, per mantenere la richiesta nello stato originale, non modificare una richiesta tra il momento in cui la copia e l&#39;ora in cui la incolla.
