---
description: Passaggi che descrivono la modalità di escape dei dati di classificazione nel file di classificazione.
subtopic: Classifications
title: Esci dai dati di classificazione
topic: Admin tools
uuid: 724edcc5-4990-4f24-afbb-9aef301791a7
translation-type: tm+mt
source-git-commit: 6778dd290424651dc959224daa0eef8ebd8196e5
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 8%

---


# Esci dai dati di classificazione

Passaggi che descrivono la modalità di escape dei dati di classificazione nel file di classificazione.

<!--Meike, please check this page against orginal. It might be missing information. -->

1. Assicurarsi che il formato del file di classificazione sia v2.1.

   Se la versione v2.1 è abilitata, verrà visualizzata una riga simile alla seguente:

   >[!NOTE]
   >
   >Per specificare un formato v2.1, attivare **[!UICONTROL Quoted Output]** durante l’esportazione del file sulla [!UICONTROL Classification Importer] pagina ( [!UICONTROL Browser Export] o [!UICONTROL FTP Export]).

1. Circondare il campo contenente caratteri speciali tra virgolette (`"`).

Una doppia citazione può essere visualizzata in una cella con escape sostituendola con due virgolette doppie (`" "`). Ad esempio:

```
My String "of data"
```

La fuga sarebbe:

```
"My String ""of data"""
```
