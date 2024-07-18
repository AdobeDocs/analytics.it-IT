---
description: Scopri come copiare un foglio di calcolo da una cartella di lavoro di origine a una o più cartelle di lavoro di destinazione.
title: Come copiare richieste e fogli di lavoro tra le cartelle di lavoro
uuid: 6b2c4259-d8cb-430e-819f-38e213dd2661
feature: Report Builder
role: User, Admin
exl-id: 1a2363da-603e-4d1d-aefa-14ce71554247
source-git-commit: d218d07ec16e981d7e148092b91fbbd5711e840f
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 1%

---

# Copiare richieste e fogli di lavoro tra le cartelle di lavoro

Copiare un intero foglio di calcolo in una cartella di lavoro di origine in un foglio di calcolo in una o più cartelle di lavoro di destinazione. A tale scopo, è necessario che nella stessa istanza di Excel siano aperte almeno due cartelle di lavoro:
* La prima cartella di lavoro di origine contiene un foglio di calcolo (foglio di lavoro) con richieste mappate alle celle.
* Le altre cartelle di lavoro di destinazione sono le destinazioni. Per ogni nuova cartella di lavoro di destinazione, è necessario accedere alla stessa suite di rapporti della cartella di lavoro di origine prima di poter incollare fogli di calcolo contenenti richieste.

>[!NOTE]
>
>È necessario accedere alla cartella di lavoro di destinazione utilizzando la stessa suite di rapporti della cartella di lavoro di origine. Le richieste in entrambe le cartelle di lavoro devono essere create utilizzando lo stesso accesso alla suite di rapporti.

1. Fare clic con il pulsante destro del mouse sul foglio di calcolo nella cartella di lavoro di origine e selezionare **[!UICONTROL Copy Worksheet w/Requests]**.
1. Nella cartella di lavoro di destinazione fare clic con il pulsante destro del mouse sul foglio di calcolo e selezionare **[!UICONTROL Paste Worksheet w/Requests]**.

   La stessa istanza di Excel indica che nel computer è in esecuzione un solo processo di Excel ( [!DNL excel.exe]) alla volta. Se si avviano due istanze di Excel e si tenta di copiare un foglio di lavoro da una cartella di lavoro nella prima istanza di Excel a una cartella di lavoro nella seconda istanza di Excel, Report Builder non presenta l&#39;opzione per incollare un foglio di lavoro nel menu di scelta rapida della seconda istanza di Excel.

   Se si accede alle cartelle di lavoro di origine e di destinazione utilizzando suite di rapporti diverse, gli unici risultati visualizzati dall&#39;operazione Incolla sono quelli che influiscono sulla formattazione della cartella di lavoro di destinazione. Nel Report Builder viene visualizzato un messaggio che indica che le informazioni per le richieste derivate da una suite di rapporti specificata (nella cartella di lavoro di origine) non sono disponibili nella cartella di lavoro di destinazione. Per visualizzare le richieste incollate nella cartella di lavoro di destinazione, è necessario accedere alla cartella di lavoro di destinazione utilizzando la stessa suite di rapporti della cartella di lavoro di origine.

   È possibile copiare e incollare una o più richieste da un foglio di calcolo in una cartella di lavoro a un foglio di calcolo in un&#39;altra cartella di lavoro, purché la seconda cartella di lavoro sia aperta come un altro documento nella stessa istanza di Excel. Le richieste in entrambe le cartelle di lavoro devono essere create utilizzando lo stesso accesso alla suite di rapporti.
