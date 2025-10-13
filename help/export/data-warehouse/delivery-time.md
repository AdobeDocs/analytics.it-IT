---
title: Risolvere i problemi relativi ai tempi di consegna delle richieste di Data Warehouse
description: Individua potenziali problemi con una richiesta Data Warehouse che possono prolungare i tempi di consegna.
feature: Data Warehouse
exl-id: eed4d172-fffd-453f-ab5b-0fc2a79d5bd0
source-git-commit: d929e97a9d9623a8255f16729177d812d59cec05
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 0%

---

# Risolvere i problemi relativi ai tempi di consegna delle richieste Data Warehouse

Una determinata richiesta Data Warehouse può richiedere da meno di un’ora a diversi giorni o più. È difficile stimare il tempo esatto necessario per elaborare una richiesta, a causa dei seguenti fattori:

* L’intervallo di date della richiesta
* La quantità di traffico ricevuto dalla suite di rapporti durante il periodo di tempo richiesto
* Il numero di regole all’interno di un segmento e quali variabili all’interno di un segmento utilizzate
* Quanti dati sono inclusi nel segmento
* Il numero di raggruppamenti utilizzati e il numero di valori univoci all’interno di ogni raggruppamento
* Numero di metriche utilizzate
* Numero di richieste simultanee elaborate
* Regole VISTA, se configurate per essere applicate alle richieste Datawarehouse

## Modificare le richieste per velocizzare la consegna

Se le richieste di Data Warehouse richiedono molto tempo, puoi modificarle. La modifica di una richiesta è l’unico modo per velocizzare la consegna di una richiesta Data Warehouse.

Per accelerare la consegna di una richiesta Data Warehouse, puoi modificarla in uno dei seguenti modi:

* **Utilizzare un segmento contenente un campione di dati più piccolo**: minore è il numero di dati utilizzati da una richiesta, più veloce sarà la restituzione di un report.
* **Esegui richieste con incrementi di 14 giorni o meno**: le richieste più piccole vengono elaborate più rapidamente delle richieste più grandi.
* **Usa meno raggruppamenti:** Molti raggruppamenti in una richiesta aumentano esponenzialmente il tempo necessario per elaborarla.

## Utilizzare un metodo alternativo

Se hai bisogno di questi tipi di rapporti in modo più tempestivo, considera le seguenti alternative:

* **Analysis Workspace**: sebbene non siano disponibili elementi dimensione illimitati, include quasi tutti gli altri casi d&#39;uso forniti da Data Warehouse.
* **Feed dati**: prende tutti i dati non elaborati in una suite di rapporti ogni giorno e li invia a una destinazione cloud. È quindi possibile importare i dati nel proprio database ed eseguire query per ottenere i dati necessari.
* **Soluzione di servizi tecnici personalizzati**: Adobe Engineering Services può fornire una soluzione personalizzata per la tua organizzazione a un costo aggiuntivo. Per ulteriori informazioni, contatta il team del tuo account di Adobe.
