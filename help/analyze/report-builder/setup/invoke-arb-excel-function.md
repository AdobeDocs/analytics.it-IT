---
description: Scopri come utilizzare Microsoft Excel con le funzioni di Report Builder senza accedere all’interfaccia utente del Report Builder.
title: Scopri come utilizzare Microsoft Excel con le funzioni di Report Builder
uuid: 5342cc4f-085d-4a2d-a498-38b00a3ef4d3
feature: Report Builder
role: User, Admin
exl-id: b412f2b5-affe-4297-af4b-85e8c6dfd257
source-git-commit: 66b7de0b008364e47253d319785c204ca479ab26
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 3%

---

# Utilizzare le funzioni di Report Builder con Microsoft Excel

È possibile utilizzare le funzioni di Report Builder per accedere alle funzionalità senza accedere all&#39;interfaccia utente del Report Builder.

Ad esempio, per aggiornare automaticamente le richieste di Report Builder con filtri di input basati sui dati estratti in Excel da altre origini, utilizzare la stringa RefreshRequestsInCellsRange(..) . Tutte le chiamate sono asincrone e vengono restituite immediatamente senza attendere la completa esecuzione.

**Requisiti**

* È necessario specificare Report Builder 5.0 (o versione successiva).

Nella tabella seguente sono elencate le funzioni esposte.

| Nome funzione | Tipo | Descrizione |
|:---| --- | ---|
| AsyncRefreshAll() | string | Aggiorna tutte le richieste di Report Builder presenti in una cartella di lavoro. |
| AsyncRefreshRange(string rangeAddressInA1Format) | string | Aggiorna tutte le richieste di Report Builder presenti nell&#39;indirizzo di intervallo di celle specificato (un&#39;espressione stringa che rappresenta un intervallo di celle in formato A1, ad esempio &quot;Foglio1!A2:A10&quot;). |
| AsyncRefreshRangeAltTextParam() | string | Aggiorna tutte le richieste di Report Builder presenti nell&#39;intervallo di celle specificato passato tramite il testo alternativo del controllo Form Ms. |
| AsyncRefreshActiveWorksheet() | string | Aggiorna tutte le richieste di Report Builder presenti nel foglio di lavoro attivo. |
| AsyncRefreshWorksheet(string sheetName) | string | Aggiorna tutte le richieste di Report Builder presenti nel foglio di lavoro specificato (il nome del foglio di lavoro visualizzato nella scheda). |
| AsyncRefreshWorksheetAltTextParam(); | string | Aggiorna tutte le richieste di Report Builder presenti nel nome specifico del foglio di lavoro passato tramite il testo alternativo del controllo Ms Form |
| stringa GetLastRunStatus() | string | Restituisce una stringa che descrive lo stato dell&#39;ultima esecuzione. |

Per accedere alle funzioni del Report Builder, vai a **[!UICONTROL Formulas]** > **[!UICONTROL Insert Function]**. Utilizzare il campo di ricerca per cercare una funzione o selezionare una categoria per elencare le funzioni in tale categoria.

![Schermata che mostra la finestra Inserisci funzione con l&#39;elenco delle categorie espanso.](assets/arb_functions.png)

## Esempio {#section_034311081C8D4D7AA9275C1435A087CD}

L’esempio seguente mostra *Se il valore nella cella P5 è un testo o è vuoto, aggiornare l&#39;intervallo nella cella P9*.

```
=IF(OR(ISTEXT(P5),ISBLANK(P5)),AsyncRefreshRange("P9"),"")
```

## Utilizzare le funzioni di Report Builder con il controllo del formato {#section_26123090B5BD49748C8D8ED7A1C5ED84}

È possibile assegnare una macro a un controllo creato e tale controllo può essere una funzione che aggiorna una richiesta di cartella di lavoro. Ad esempio, la funzione AsyncRefreshActiveWorksheet aggiornerà tutte le richieste in un foglio di lavoro. Talvolta, tuttavia, potrebbe essere utile aggiornare solo alcune richieste.

1. Impostare il parametro della macro.
1. Fare clic con il pulsante destro del mouse sul controllo e selezionare **[!UICONTROL Assign Macro]**.
1. Immettere il nome della funzione di Report Builder (nessun parametro o parentesi).

![Schermata che mostra la finestra Assegna macro.](assets/assign_macro.png)

## Trasmettere i parametri alle funzioni di Report Builder mediante il controllo del formato {#section_ECCA1F4990D244619DFD79138064CEF0}

Due funzioni che accettano un parametro possono essere utilizzate con Controllo formato. È necessario utilizzare il **Testo alternativo:** campo:

* AsyncRefreshRange(string rangeAddressInA1Format)
* AsyncRefreshWorksheet(string sheetName)

Per passare parametri alle funzioni di Report Builder mediante il controllo del formato

1. Fare clic con il pulsante destro del mouse sul controllo e selezionare **[!UICONTROL Format Control]**.

   ![Schermata che mostra il controllo del formato selezionato.](assets/format_control.png)

1. Fai clic sulla scheda **[!UICONTROL Alt Text]**.

   ![Schermata che mostra la scheda Testo alternativo e il campo Testo alternativo:.](assets/alt_text.png)

1. Sotto **[!UICONTROL Alternative text]**, immettere l&#39;intervallo di celle da aggiornare.
1. Apre l&#39;elenco dei parametri di Report Builder in **[!UICONTROL Formulas]** > **[!UICONTROL Insert Function]**> **[!UICONTROL Adobe.ReportBuilder.Bridge]**.

1. Selezionate una delle due funzioni che terminano con AltTextParam e fate clic su **[!UICONTROL OK]**.
