---
description: Copiare un intero foglio di calcolo in una cartella di lavoro di origine in un foglio di calcolo in una o più cartelle di lavoro di destinazione.
seo-description: Copiare un intero foglio di calcolo in una cartella di lavoro di origine in un foglio di calcolo in una o più cartelle di lavoro di destinazione.
seo-title: Copiare richieste e fogli di lavoro tra le cartelle di lavoro
solution: Analytics
title: Copiare richieste e fogli di lavoro tra le cartelle di lavoro
topic: Generatore di report
uuid: 6b2c4259-d8cb-430e-819f-38e213dd2661
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Copiare richieste e fogli di lavoro tra le cartelle di lavoro

Copiare un intero foglio di calcolo in una cartella di lavoro di origine in un foglio di calcolo in una o più cartelle di lavoro di destinazione.

A questo scopo, è necessario che siano aperte almeno due cartelle di lavoro nella stessa istanza di Excel: la prima cartella di lavoro di origine contiene un foglio di calcolo (foglio di lavoro) con le richieste mappate alle celle, mentre le destinazioni sono le cartelle di lavoro di destinazione aggiuntive. Per ogni nuova cartella di lavoro di destinazione, è necessario accedere alla stessa suite di rapporti della cartella di lavoro di origine prima di poter incollare fogli di calcolo contenenti richieste.
1. Fare clic con il pulsante destro del mouse sul foglio di calcolo nella cartella di lavoro di origine e selezionare **[!UICONTROL Copy Worksheet w/Requests]**.
1. Nella cartella di lavoro di destinazione, fare clic con il pulsante destro del mouse sul foglio di calcolo e selezionare **[!UICONTROL Paste Worksheet w/Requests]**.

   La stessa istanza di Excel indica che sul computer è in esecuzione un solo processo Excel ( [!DNL excel.exe]) alla volta. Se si avviano due istanze di Excel e si tenta di copiare un foglio di lavoro da una cartella di lavoro della prima istanza di Excel in una cartella di lavoro della seconda istanza di Excel, il generatore di report non presenta l'opzione di incollare un foglio di lavoro nel menu di scelta rapida della seconda istanza di Excel.

   Se si accede alle cartelle di lavoro di origine e di destinazione utilizzando suite di rapporti diverse, l'unico risultato visualizzato dall'operazione Incolla sono quelli che influiscono sulla formattazione della cartella di lavoro di destinazione. Generatore di report visualizza un messaggio che indica che le informazioni per le richieste derivate da una suite di rapporti specificata (nella cartella di lavoro di origine) non sono disponibili nella cartella di lavoro di destinazione. Per visualizzare le richieste incollate nella cartella di lavoro di destinazione, è necessario accedere alla cartella di lavoro di destinazione utilizzando la stessa suite di rapporti della cartella di lavoro di origine.

   È possibile copiare e incollare una o più richieste da un foglio di calcolo in una cartella di lavoro a un foglio di calcolo in un'altra cartella di lavoro, purché la seconda cartella di lavoro sia aperta come un altro documento nella stessa istanza di Excel. Le richieste in entrambe le cartelle di lavoro devono essere create utilizzando lo stesso accesso alla suite di rapporti.
