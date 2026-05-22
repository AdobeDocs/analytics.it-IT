---
title: Risolvere i problemi relativi ai tempi di consegna delle richieste di Data Warehouse
description: Individua potenziali problemi con una richiesta Data Warehouse che possono prolungare i tempi di consegna.
feature: Data Warehouse
exl-id: eed4d172-fffd-453f-ab5b-0fc2a79d5bd0
TQID: 'https://experienceleague.adobe.com/oWkM-wTuJ75sR6AzkjD8WfY9DYLUdtToSGyu8hJIXVk'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: f47edbe0-f963-46ff-a667-71011396f5f3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 358
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
