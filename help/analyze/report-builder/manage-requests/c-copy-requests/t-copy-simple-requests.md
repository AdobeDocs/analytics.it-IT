---
description: Copiate una richiesta semplice invece di una richiesta referenziale. Una semplice richiesta non contiene riferimenti a un'altra richiesta o al contenuto di una cella.
seo-description: Copiate una richiesta semplice invece di una richiesta referenziale. Una semplice richiesta non contiene riferimenti a un'altra richiesta o al contenuto di una cella.
seo-title: Copia richieste semplici
solution: Analytics
title: Copia richieste semplici
topic: Generatore di report
uuid: ff20560a-01ee-47e7-8bd1-b73edb010456
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Copia richieste semplici

Copiate una richiesta semplice invece di una richiesta referenziale. Una semplice richiesta non contiene riferimenti a un'altra richiesta o al contenuto di una cella.

Una richiesta [](/help/analyze/report-builder/manage-requests/c-copy-requests/t-copy-referential-requests.md) referenziale utilizza i valori delle celle come input per i parametri, ad esempio un filtro dati o un filtro relazionale. Questi filtri utilizzano la corrispondenza o la tendenza e si basano sui risultati di una richiesta precedente o sul contenuto immesso dall'utente di una cella, denominata cella di input.
1. Create una richiesta valida.
1. Fate clic con il pulsante destro del mouse su una delle celle in cui è mappata la richiesta, oppure selezionate un'area di celle contenente richieste.

   Scegliete una cella da cui copiare nel gruppo di celle coperto dalla richiesta. La scelta preferita è la cella superiore e sinistra del set di celle coperto dalla richiesta e funziona da sinistra a destra. Questo perché il foglio di calcolo Excel ha centinaia di colonne e migliaia di righe disponibili per l'espansione verso destra e verso il basso. Se si decide di avviare una copia della richiesta dalla cella più a destra o più in basso in un insieme di celle associate a una richiesta, il sistema non consente di incollare la richiesta se le celle da incollare si estendono oltre il bordo sinistro o superiore del foglio di calcolo.
1. Seleziona **[!UICONTROL Copy Request]**.
1. In un’altra parte del foglio di calcolo, fate clic con il pulsante destro del mouse su una cella vuota (una cella che non contiene richieste).

   Per evitare di perdere o di danneggiare le richieste già create, non è possibile incollare celle contenenti richieste alle celle attualmente associate a richieste. Se copiate o tagliate le celle contenenti richieste, il menu di scelta rapida non rende disponibile l' [!UICONTROL Paste Requests] opzione quando si fa clic con il pulsante destro del mouse sulle celle (o sul set di celle) contenenti richieste. È necessario selezionare una cella diversa come destinazione dell'operazione Incolla in modo che le richieste non si sovrappongano. Ciò si applica sia alla selezione di una cella singola con una richiesta di incolla, sia a un'area di celle contenente richieste.
1. Fai clic su **[!UICONTROL Paste Request]**.

   Una copia della richiesta originale viene inserita nelle celle, in una posizione o nelle posizioni relative alla richiesta originale.

   >[!NOTE]
   >
   >Vengono copiate solo le richieste, non il contenuto delle celle. Se si dispone di altre informazioni non basate sulle richieste, ma pertinenti per comprendere i dati visualizzati nelle celle (come intestazioni di colonna di tabella o identificatori di riga), utilizzare i comandi standard di Excel Copia e Incolla.

   Poiché Excel utilizza Appunti diversi per copiare il contenuto delle celle e copiare le richieste, è possibile copiare sia il contenuto delle celle che le richieste, eseguendo una serie di richieste Copia/Incolla e Copia richieste/Incolla. Tuttavia, se applicate la formattazione alle richieste nel foglio di calcolo e quindi copiate e incollate, il generatore di report riproduce la formattazione originale (come bordi, font, ecc.) nell’area Incolla.

   Modificando una richiesta copiata o tagliata negli Appunti prima di incollare la richiesta, la richiesta viene rimossa dagli Appunti. Pertanto, per mantenere la richiesta nello stato originale, non modificate una richiesta tra il momento in cui la copiate e l’ora in cui la incollate.
