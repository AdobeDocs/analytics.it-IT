---
description: Scopri come copiare una richiesta semplice.
title: Come copiare richieste semplici
uuid: ff20560a-01ee-47e7-8bd1-b73edb010456
feature: Report Builder
role: User, Admin
exl-id: ceed28d5-cb7f-4343-96fd-2ce09f5a3515
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 0%

---

# Copiare richieste semplici

{{legacy-arb}}

Copia una richiesta semplice anziché una richiesta referenziale. Una richiesta semplice è una richiesta che non contiene riferimenti a un’altra richiesta o al contenuto di una cella.

Una [richiesta referenziale](/help/analyze/legacy-report-builder/manage-requests/c-copy-requests/t-copy-referential-requests.md) utilizza i valori delle celle come input per i parametri, ad esempio un filtro dati o un filtro relazionale. Questi filtri utilizzano corrispondenze o tendenze e si basano sui risultati di una richiesta precedente o sul contenuto immesso dall’utente di una cella, denominata cella di input.

Per copiare una richiesta semplice

1. Crea una richiesta valida.
1. Fai clic con il pulsante destro del mouse su una delle celle in cui è mappata la richiesta oppure seleziona un’area di celle contenente richieste.

   Assicurati di scegliere in modo coerente una cella da cui copiare nel gruppo di celle coperto dalla richiesta. La scelta preferita è la cella superiore e la cella più a sinistra dell’insieme di celle coperto dalla richiesta e funziona da sinistra a destra. Questo perché il foglio di calcolo di Excel ha centinaia di colonne e migliaia di righe disponibili per l’espansione verso destra e verso il basso. Se decidi di avviare una copia della richiesta dalla cella più a destra o più in basso di un set di celle associato a una richiesta, il sistema non ti consente di incollare la richiesta se le celle da incollare si estendono oltre il bordo sinistro o superiore del foglio di calcolo.
1. Seleziona **[!UICONTROL Copy Request]**.
1. In un&#39;altra parte del foglio di calcolo, fare clic con il pulsante destro del mouse su una cella vuota, ovvero una cella che non contiene alcuna richiesta.

   Per evitare di perdere o danneggiare le richieste già create, non è possibile incollare celle contenenti richieste in celle attualmente mappate con richieste. Se si copiano o si tagliano celle contenenti richieste, il menu di scelta rapida non rende disponibile l&#39;opzione [!UICONTROL Paste Requests] quando si fa clic con il pulsante destro del mouse sulle celle (o sul set di celle) contenenti richieste. È necessario selezionare una cella diversa come destinazione dell’operazione Incolla in modo che le richieste non si sovrappongano. Ciò vale sia che si selezioni una singola cella con una richiesta da incollare, sia che si selezioni un’area di celle contenente richieste.
1. Fai clic su **[!UICONTROL Paste Request]**.

   Una copia della richiesta originale viene inserita nella cella o nelle celle, in una posizione o nelle posizioni relative alla richiesta originale.

   >[!NOTE]
   >
   >Vengono copiate solo le richieste, non il contenuto delle celle. Se disponi di altre informazioni non basate sulle richieste, ma rilevanti per comprendere i dati visualizzati nelle celle (ad esempio intestazioni di colonna di una tabella o identificatori di riga), utilizza i comandi standard di Excel Copia e Incolla.

   Poiché Excel utilizza Appunti diversi per copiare il contenuto delle celle e le richieste, è possibile copiare sia il contenuto delle celle non richieste che le richieste eseguendo una serie di richieste Copia/Incolla e Copia richieste/Incolla. Tuttavia, se si applica la formattazione alle richieste nel foglio di calcolo e quindi si copia e incolla, il Report Builder riproduce la formattazione originale (ad esempio bordi, caratteri e così via) nell’area incolla.

   Se si modifica una richiesta copiata o tagliata negli Appunti prima di incollarla, la richiesta viene rimossa dagli Appunti. Pertanto, per mantenere la richiesta nello stato originale, non modificare una richiesta tra il momento in cui viene copiata e quello in cui viene incollata.
