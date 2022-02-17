---
description: Passaggi che descrivono come effettuare l’escape dei dati di classificazione nel file di classificazione.
title: Esci dai dati di classificazione
feature: Classifications
exl-id: 0d3a0e91-5537-43ee-bd28-9907ee6eb331
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 8%

---

# Esci dai dati di classificazione

Passaggi che descrivono come effettuare l’escape dei dati di classificazione nel file di classificazione.

<!--Meike, please check this page against orginal. It might be missing information. -->

1. Assicurati che il formato del file di classificazione sia v2.1.

   Se la versione v2.1 è abilitata, verrà visualizzata una riga simile alla seguente:

   >[!NOTE]
   >
   >Per specificare un formato v2.1, abilita **[!UICONTROL Quoted Output]** durante l’esportazione del file nel [!UICONTROL Classification Importer] page ( [!UICONTROL Browser Export] o [!UICONTROL FTP Export]).

1. Racchiude il campo contenente caratteri speciali tra virgolette (`"`).

Una doppia citazione può apparire in una cella di escape sostituendola con due virgolette doppie (`" "`). Ad esempio:

```
My String "of data"
```

Fuggito sarebbe:

```
"My String ""of data"""
```
