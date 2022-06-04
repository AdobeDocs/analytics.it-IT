---
title: Risolvere i problemi relativi ai tempi di consegna della richiesta di Data Warehouse
description: Determina i potenziali problemi con una richiesta di Data Warehouse che può prolungare i tempi di consegna.
feature: Data Warehouse
exl-id: eed4d172-fffd-453f-ab5b-0fc2a79d5bd0
source-git-commit: 3f4d8df911c076a5ea41e7295038c0625a4d7c85
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 0%

---

# Risolvere i problemi relativi ai tempi di consegna della richiesta di Data Warehouse

Una determinata richiesta di Data Warehouse può richiedere da meno di un&#39;ora a diversi giorni o più. È difficile stimare il tempo esatto necessario per l’elaborazione di una richiesta, a causa dei seguenti fattori:

* Intervallo di date della richiesta
* La quantità di traffico ricevuto dalla suite di rapporti durante il periodo di tempo richiesto
* Il numero di regole all’interno di un segmento e quali variabili all’interno di un segmento hanno utilizzato
* Quanti dati vengono inclusi nel segmento
* Il numero di disaggregazioni utilizzate e il numero di valori univoci all’interno di ciascuna disaggregazione
* Il numero di metriche utilizzate
* Numero di richieste simultanee in fase di elaborazione
* Regole VISTA, se configurate per l&#39;applicazione alle richieste di DataWarehouse

Se le richieste di data warehouse richiedono tempo costante, è consigliabile modificare le richieste per soddisfare le seguenti esigenze:

* **Utilizza un segmento contenente un campione di dati più piccolo**: Minore è il numero di dati con cui una richiesta funziona, più veloce sarà il ritorno di un report.
* **Esegui richieste con incrementi di 14 giorni o meno**: Le richieste più piccole vengono elaborate più rapidamente delle richieste di grandi dimensioni.
* **Utilizza meno raggruppamenti:** Molte suddivisioni in una richiesta di Data Warehouse aumentano esponenzialmente il tempo necessario all’elaborazione.

>[!IMPORTANT]
>
> *Non c&#39;è modo di accelerare la consegna di una richiesta di Data Warehouse.*

Se richiedi questi tipi di report in modo più tempestivo, considera le seguenti alternative:

* **Analysis Workspace**: Anche se non sono disponibili elementi dimensionali illimitati, include quasi tutti gli altri casi d’uso forniti da Data Warehouse.
* **Feed di dati**: Prende tutti i dati non elaborati in una suite di rapporti ogni giorno e li invia a un sito FTP. È quindi possibile importare questi dati nel proprio database ed eseguire query per ottenere i dati desiderati.
* **Soluzione personalizzata di servizi tecnici**: Adobe Engineering Services può fornire una soluzione personalizzata per la tua organizzazione a un costo aggiuntivo. Per ulteriori informazioni, contatta l’Account Manager della tua organizzazione.
