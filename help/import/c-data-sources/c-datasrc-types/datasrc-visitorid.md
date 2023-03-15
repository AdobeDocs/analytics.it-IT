---
description: Gli ID visitatore possono essere integrati selezionando la categoria Generico (ID transazione).
subtopic: Data sources
title: Visitor ID
topic-fix: Developer and implementation
feature: Data Sources
exl-id: 940af1ba-0d12-4552-a21e-0ceb06427ab2
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 77%

---

# VisitorID

Gli ID visitatore possono essere integrati selezionando la [!UICONTROL Call Center Data] categoria.

Consulta [Integrare dati offline](/help/import/c-data-sources/datasrc-integrating-offline-data.md).

## Dimension VisitorID

| Nome colonna | Descrizione |
|--- |--- |
| [!UICONTROL VisitorID] | (Obbligatorio) Valore univoco che rappresenta un cliente nei sistemi online e offline. |
| [!UICONTROL Date] | Utilizza il seguente formato data: `MM/DD/YYYY/hh/mm/ss` (ad esempio, 07/14/2017/06/00/00) |
| [!UICONTROL Tracking Code] | Nome del codice di tracciamento. |
| [!UICONTROL Category] | Nome della categoria. Se specifichi una categoria, devi anche selezionare un prodotto. |
| [!UICONTROL Channel] | Nome del canale. |
| [!UICONTROL eVar]*n* | Nome eVar *n*. I valori validi per *n* sono numeri interi 1 - 75. |
| [!UICONTROL Product] | Nome del prodotto. |
| [!UICONTROL State] | Nome dello stato. |
| [!UICONTROL Zip] | ZIP name. |

## Metriche ID visitatore

| Nome colonna | Descrizione |
| --- | --- |
| [!UICONTROL Clickthroughs] | Numero di visualizzazioni del codice di tracciamento. |
| [!UICONTROL Cart Adds] | Numero di aggiunte al carrello. |
| [!UICONTROL Cart Opens] | Numero di aperture del carrello. |
| [!UICONTROL Cart Removes] | Numero di rimozioni dal carrello. |
| [!UICONTROL Cart Views] | Numero di visualizzazioni del carrello. |
| [!UICONTROL Checkouts] | Numero di pagamenti. |
| [!UICONTROL Event]*n* | Numero di volte pari *n* si è verificato. I valori validi per n sono numeri interi 1 - 100.  Se si specifica un [!UICONTROL View] devi inoltre specificare la dimensione dati corrispondente (eVar). Ad esempio, se includi visualizzazioni eVar2, devi elencare eVar2 con un valore. |
| [!UICONTROL eVar]*n* Visualizzazioni | Numero di volte in cui è stata visualizzata l&#39;eVar *n*. I valori validi per *n* sono numeri interi 1 - 75. |
| [!UICONTROL Price] | Prezzo del prodotto. |
| [!UICONTROL Orders] | Numero di ordini inseriti. |
| [!UICONTROL Product Views] | Numero di visualizzazioni del prodotto. |
| [!UICONTROL Quantity] | Numero di unità vendute. |
