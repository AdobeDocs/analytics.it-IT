---
title: Risolvere i problemi relativi ai tempi di consegna delle richieste Data Warehouse
description: Individua potenziali problemi con una richiesta Data Warehouse che possono prolungare i tempi di consegna.
feature: Data Warehouse
exl-id: eed4d172-fffd-453f-ab5b-0fc2a79d5bd0
source-git-commit: c53f886d5329e2a3b5023f9396c3aa2360a86901
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 0%

---

# Risolvere i problemi relativi ai tempi di consegna delle richieste Data Warehouse

Una determinata richiesta di Data Warehouse può richiedere da meno di un’ora a diversi giorni o più. È difficile stimare il tempo esatto necessario per elaborare una richiesta, a causa dei seguenti fattori:

* L’intervallo di date della richiesta
* La quantità di traffico ricevuto dalla suite di rapporti durante il periodo di tempo richiesto
* Il numero di regole all’interno di un segmento e quali variabili all’interno di un segmento utilizzate
* Quanti dati sono inclusi nel segmento
* Il numero di raggruppamenti utilizzati e il numero di valori univoci all’interno di ogni raggruppamento
* Numero di metriche utilizzate
* Numero di richieste simultanee elaborate
* Regole VISTA, se configurate per essere applicate alle richieste di DataWarehouse

Se vedi che le richieste di data warehouse richiedono molto tempo, puoi modificare le richieste per soddisfare i seguenti requisiti:

* **Utilizza un segmento contenente un campione più piccolo di dati**: meno dati funziona una richiesta, più velocemente restituisce un rapporto.
* **Eseguire richieste con incrementi di 14 giorni o meno**: le richieste più piccole vengono elaborate più rapidamente delle richieste più grandi.
* **Usa meno raggruppamenti:** Molti raggruppamenti in una richiesta Data Warehouse aumentano esponenzialmente il tempo necessario per l’elaborazione.

>[!IMPORTANT]
>
> *Non è possibile accelerare la consegna di una richiesta Data Warehouse.*

Se hai bisogno di questi tipi di rapporti in modo più tempestivo, considera le seguenti alternative:

* **Analysis Workspace**: anche se non sono disponibili elementi dimensionali illimitati, questo include quasi tutti gli altri casi d’uso forniti da Data Warehouse.
* **Feed dati**: prende tutti i dati non elaborati in una suite di rapporti ogni giorno e li invia a un sito FTP. È quindi possibile importare tali dati nel proprio database ed eseguire query per ottenere i dati desiderati.
* **Soluzione personalizzata di Engineering Services**: Adobe Engineering Services può fornire una soluzione personalizzata per la tua organizzazione a un costo aggiuntivo. Per ulteriori informazioni, contatta il team dell’account di Adobe.
