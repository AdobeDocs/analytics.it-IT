---
description: Passaggi che descrivono come effettuare l’escape dei dati di classificazione nel file di classificazione.
subtopic: Classifications
title: Esci dai dati di classificazione
feature: Admin Tools
uuid: 724edcc5-4990-4f24-afbb-9aef301791a7
exl-id: 0d3a0e91-5537-43ee-bd28-9907ee6eb331
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 10%

---

# Esci dai dati di classificazione

Passaggi che descrivono come effettuare l’escape dei dati di classificazione nel file di classificazione.

<!--Meike, please check this page against orginal. It might be missing information. -->

1. Assicurati che il formato del file di classificazione sia v2.1.

   Se la versione v2.1 è abilitata, verrà visualizzata una riga simile alla seguente:

   >[!NOTE]
   >
   >Per specificare un formato v2.1, abilita **[!UICONTROL Quoted Output]** durante l’esportazione del file nella pagina [!UICONTROL Classification Importer] ( [!UICONTROL Browser Export] o [!UICONTROL FTP Export]).

1. Circonda il campo contenente caratteri speciali tra virgolette doppie (`"`).

Le virgolette doppie possono comparire in una cella di escape sostituendola con due virgolette doppie (`" "`). Ad esempio:

```
My String "of data"
```

Fuggito sarebbe:

```
"My String ""of data"""
```
