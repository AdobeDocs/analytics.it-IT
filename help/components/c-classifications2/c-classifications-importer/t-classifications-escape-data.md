---
description: Procedura che descrive come inserire i dati di classificazione nel file di classificazione.
seo-description: Procedura che descrive come inserire i dati di classificazione nel file di classificazione.
seo-title: Dati di classificazione Escape
solution: Analytics
subtopic: Classificazioni
title: Dati di classificazione Escape
topic: Strumenti di amministrazione
uuid: 724 edcc 5-4990-4 f 24-afbb -9 aef 301791 a 7
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Dati di classificazione Escape

Procedura che descrive come inserire i dati di classificazione nel file di classificazione.

<!--Meike, please check this page against orginal. It might be missing information. -->

1. Accertarsi che il formato di file di classificazione sia v 2.1.

   Se la versione v 2.1 è attivata, viene visualizzata una linea simile a:

   >[!NOTE]
   >
   >To specify a format of v2.1, enable **[!UICONTROL Quoted Output]** when exporting the file on the [!UICONTROL Classification Importer] page ( [!UICONTROL Browser Export] or [!UICONTROL FTP Export]).

1. Surround the field containing special characters in double quotes (`"`).

A double quote character can appear in an escaped cell by replacing it with two double quote characters (`" "`). Ad esempio:

```
My String "of data"
```

Escaped would be:

```
"My String ""of data"""
```
