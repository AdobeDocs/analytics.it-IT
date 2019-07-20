---
description: Copiare un intero foglio di calcolo in una cartella di lavoro sorgente in un foglio di calcolo in una o più cartelle di lavoro di destinazione.
seo-description: Copiare un intero foglio di calcolo in una cartella di lavoro sorgente in un foglio di calcolo in una o più cartelle di lavoro di destinazione.
seo-title: Copiare richieste e fogli di lavoro tra le cartelle di lavoro
solution: Analytics
title: Copiare richieste e fogli di lavoro tra le cartelle di lavoro
topic: Generatore di report
uuid: 6 b 2 c 4259-d 8 cb -430 e -819 f -38 e 213 dd 2661
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Copiare richieste e fogli di lavoro tra le cartelle di lavoro

Copiare un intero foglio di calcolo in una cartella di lavoro sorgente in un foglio di calcolo in una o più cartelle di lavoro di destinazione.

Per farlo, devono essere aperte almeno due cartelle di lavoro nella stessa istanza di Excel: la prima cartella di lavoro sorgente contiene un foglio di lavoro (foglio di lavoro) con richieste mappate alle celle, mentre le cartelle di lavoro di destinazione sono le destinazioni. Per ogni nuova cartella di lavoro di destinazione, è necessario accedere alla stessa suite di rapporti della cartella di lavoro sorgente prima di poter incollare fogli di calcolo contenenti richieste.
1. Right-click the spreadsheet in the source workbook and select **[!UICONTROL Copy Worksheet w/Requests]**.
1. In the destination workbook, right-click the spreadsheet and select **[!UICONTROL Paste Worksheet w/Requests]**.

   The same instance of Excel means that only a single Excel process ( [!DNL excel.exe]) is running on your computer at a time. Se avviate due istanze di Excel e tentate di copiare un foglio di lavoro da una cartella di lavoro della prima istanza di Excel a una cartella di lavoro nella seconda istanza di Excel, il generatore di report non presenta l'opzione per incollare un foglio di lavoro nel menu di scelta rapida della seconda istanza di Excel.

   Se effettuate l'accesso ai documenti di lavoro sorgente e destinazione utilizzando suite di rapporti diverse, gli unici risultati visualizzati dall'operazione Incolla riguardano la formattazione della cartella di lavoro di destinazione. Generatore di report visualizza un messaggio che indica che le informazioni per le richieste derivate da una suite di rapporti specificata (nella cartella di lavoro sorgente) non sono disponibili nella cartella di lavoro di destinazione. Per visualizzare le richieste incollate nella cartella di lavoro di destinazione, dovete accedere alla cartella di lavoro di destinazione utilizzando la stessa suite di rapporti della cartella di lavoro sorgente.

   Potete copiare e incollare una o più richieste da un foglio di calcolo in un'altra cartella di lavoro in un'altra cartella di lavoro, a condizione che la seconda cartella di lavoro sia aperta come un altro documento nella stessa istanza di Excel. Le richieste in entrambi i documenti di lavoro devono essere create utilizzando lo stesso login suite di rapporti.
