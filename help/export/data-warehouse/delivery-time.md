---
title: Risoluzione dei problemi relativi ai tempi di consegna delle richieste di Data warehouse
description: Determinare potenziali problemi con una richiesta di Data warehouse che può prolungare i tempi di consegna.
translation-type: tm+mt
source-git-commit: 6778dd290424651dc959224daa0eef8ebd8196e5
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 0%

---


# Risoluzione dei problemi relativi ai tempi di consegna delle richieste di Data warehouse

Una determinata richiesta di Data warehouse può richiedere da meno di un&#39;ora a più giorni o più. È difficile stimare il tempo esatto necessario per l&#39;elaborazione di una richiesta, a causa dei seguenti fattori:

* Intervallo di date della richiesta
* Quantità di traffico ricevuto dalla suite di rapporti durante il periodo di tempo richiesto
* Il numero di regole all&#39;interno di un segmento e quali variabili all&#39;interno di un segmento utilizzate
* Quanti dati vengono inclusi nel segmento?
* Numero di suddivisioni utilizzate e numero di valori univoci all&#39;interno di ogni suddivisione
* Numero di metriche utilizzate
* Numero di richieste simultanee in fase di elaborazione
* Regole VISTA, se configurate per le richieste di DataWarehouse

Se visualizzate le richieste di data warehouse in modo coerente nel tempo, prendete in considerazione la possibilità di modificare le richieste per includere quanto segue:

* **Utilizza un segmento contenente un esempio di dati** più piccolo: Meno dati funziona una richiesta, più velocemente restituisce un report.
* **Esegui richieste con incrementi di 14 giorni o inferiori**: Le richieste più piccole vengono elaborate più velocemente rispetto alle richieste di grandi dimensioni.
* **Utilizzate meno suddivisioni:** Molte suddivisioni in una richiesta di Data warehouse aumentano esponenzialmente il tempo necessario per l&#39;elaborazione.

>[!IMPORTANT]
>
> *Non c&#39;è modo di accelerare la consegna di una richiesta di Data warehouse.*

Se si richiedono questi tipi di rapporti in modo più tempestivo, prendere in considerazione le seguenti alternative:

* **Analysis Workspace**: Anche se gli elementi dimensionali illimitati non sono disponibili, include quasi tutti gli altri casi di utilizzo forniti dalla Data warehouse.
* **Feed** dati: Prende tutti i dati grezzi in una suite di rapporti ogni giorno e li invia a un sito FTP. Potete quindi importare questi dati nel vostro database ed eseguire query per ottenere i dati desiderati.
* **Soluzione** Custom Engineering Services:  Adobe Engineering Services può fornire una soluzione personalizzata per la vostra organizzazione a un costo aggiuntivo. Per ulteriori informazioni, contattate l&#39;Account Manager della vostra organizzazione.
