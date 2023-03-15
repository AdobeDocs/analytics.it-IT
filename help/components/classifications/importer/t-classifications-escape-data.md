---
description: Passaggi che descrivono come eliminare i dati di classificazione nel file di classificazione.
title: Esci dai dati di classificazione
feature: Classifications
exl-id: 0d3a0e91-5537-43ee-bd28-9907ee6eb331
source-git-commit: ce7f953b8f7f1f7d0616074454e4401937fcc0c7
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 8%

---

# Esci dai dati di classificazione

Per eseguire l’escape dei dati di classificazione nel file di classificazione:

<!--Meike, please check this page against orginal. It might be missing information. -->

1. Assicurati che il formato del file di classificazione sia v2.1.

   Se v2.1 è abilitato, verrà visualizzata una riga simile alla seguente:

   >[!NOTE]
   >
   >Per specificare un formato v2.1, abilita **[!UICONTROL Quoted Output]** durante l&#39;esportazione del file su [!UICONTROL Classification Importer] page ( [!UICONTROL Browser Export] o [!UICONTROL FTP Export]).

1. Racchiudi il campo contenente caratteri speciali tra virgolette doppie (`"`).

Un carattere virgolette doppie può essere visualizzato in una cella con escape sostituendola con due virgolette doppie (`" "`). Ad esempio:

```
My String "of data"
```

Con escape:

```
"My String ""of data"""
```
