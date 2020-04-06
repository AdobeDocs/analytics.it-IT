---
title: account
description: Utilizzate la variabile di account per determinare la suite di rapporti a cui vengono inviati i dati.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# account

>[!IMPORTANT] Questa variabile è ritirata. Utilizzate la [`s.sa()`](../functions/sa-method.md) funzione se la vostra implementazione richiede che modificate la destinazione della suite di rapporti.

Nelle versioni precedenti di Adobe Analytics, la `account` variabile determinava la suite di rapporti a cui si desidera inviare i dati. Per inviare dati ad Adobe Analytics è necessario un ID suite di rapporti.

* Se utilizzi Adobe Experience Platform Launch, le suite di rapporti si trovano sotto la struttura di [!UICONTROL Library Management] navigazione quando configuri l’estensione Adobe Analytics.
* Se utilizzate la [`s_gi()`](../functions/s-gi.md) funzione per creare un&#39;istanza di un oggetto di tracciamento di Analytics, l&#39;ID della suite di rapporti esiste già come argomento obbligatorio nella funzione.
