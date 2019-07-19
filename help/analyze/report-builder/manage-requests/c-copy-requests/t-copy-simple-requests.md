---
description: Copia una richiesta semplice anziché una richiesta referenziale. Una semplice richiesta è una che non contiene riferimenti a un'altra richiesta o al contenuto di una cella.
seo-description: Copia una richiesta semplice anziché una richiesta referenziale. Una semplice richiesta è una che non contiene riferimenti a un'altra richiesta o al contenuto di una cella.
seo-title: Copia richieste semplici
solution: Analytics
title: Copia richieste semplici
topic: Generatore di report
uuid: ff 20560 a -01 ee -47 e 7-8 bd 1-b 73 edb 010456
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Copia richieste semplici

Copia una richiesta semplice anziché una richiesta referenziale. Una semplice richiesta è una che non contiene riferimenti a un'altra richiesta o al contenuto di una cella.

A [referential request](../../../../analyze/report-builder/manage-requests/c-copy-requests/t-copy-referential-requests.md#task_82A145CC2A774F5EA86977D670E07DC8) uses values from cells as input for parameters, such as a data filter or relational filter. Questi filtri usano la corrispondenza o il posizionamento e si basano sui risultati di una richiesta precedente o sul contenuto immesso dall'utente di una cella, detta cella di input.
1. Create una richiesta valida.
1. Fai clic con il pulsante destro del mouse su una delle celle in cui è mappata la richiesta oppure seleziona un'area di celle contenenti richieste.

   Accertatevi di scegliere una cella da copiare nel gruppo di celle coperte dalla richiesta. La scelta preferita è la cella superiore e sinistra del set di celle coperte dalla richiesta e il lavoro da sinistra a destra. poiché il foglio di calcolo Excel dispone di centinaia di colonne e migliaia di righe disponibili per l'espansione a destra e verso il basso. Se decidete di avviare una copia di richiesta dalla cella destra o inferiore in un set di celle associate a una richiesta, il sistema non consente di incollare la richiesta se le celle da incollare si estendono oltre il bordo sinistro o superiore del foglio di calcolo.
1. Select **[!UICONTROL Copy Request]**.
1. In un'altra parte del foglio di calcolo, fate clic con il pulsante destro del mouse su una cella vuota (una cella che non contiene alcuna richiesta).

   Per evitare di perdere o danneggiare le richieste già create, non potete incollare celle contenenti richieste a celle attualmente mappate con richieste. If you copy or cut cells containing requests, the shortcut menu does not make the [!UICONTROL Paste Requests] option available when right clicking on cells (or the set of cells) containing requests. È necessario selezionare una cella diversa come destinazione dell'operazione Incolla, in modo che le richieste non si sovrappongano. Ciò si applica se selezionate una singola cella con una richiesta di incolla o un'area di celle contenenti richieste.
1. Fai clic su **[!UICONTROL Paste Request]**.

   Una copia della richiesta originale viene inserita nelle celle, in una posizione o in posizioni relative alla richiesta originale.

   >[!NOTE]
   >
   >Vengono copiate solo le richieste, non il contenuto delle celle. Se disponete di altre informazioni non basate su richieste, ma in base alla comprensione dei dati visualizzati nelle celle (ad esempio intestazioni di colonna o identificatori delle righe), utilizzate i comandi standard di Excel Copia e Incolla.

   Poiché Excel utilizza Appunti diversi per copiare i contenuti delle celle e le richieste di copia, è possibile copiare sia i contenuti delle celle non richiesti che le richieste, eseguendo una serie di richieste Copia/Incolla e Copia/Incolla in serie. Tuttavia, se applicate la formattazione alle richieste presenti nel foglio di calcolo e quindi copiate e incollate, il generatore di report riproduce la formattazione originale (come bordi, font ecc.) nell'area Incolla.

   La modifica di una richiesta copiata o tagliata negli Appunti prima di incollare la richiesta rimuove la richiesta dagli Appunti. Pertanto, per mantenere la richiesta nello stato originale, non modificate una richiesta tra l'ora in cui la copiate e l'ora in cui la incollate.
