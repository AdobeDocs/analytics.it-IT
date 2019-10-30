---
description: Questa funzionalità integra ulteriormente l'utilizzo del Generatore di report nel flusso di lavoro Excel naturale, senza che sia necessario accedere all'interfaccia utente del Generatore di report.
seo-description: Questa funzionalità integra ulteriormente l'utilizzo del Generatore di report nel flusso di lavoro Excel naturale, senza che sia necessario accedere all'interfaccia utente del Generatore di report.
seo-title: Richiama delle funzionalità di Report Builder dalle funzioni di Microsoft Excel
solution: Analytics
title: Richiama delle funzionalità di Report Builder dalle funzioni di Microsoft Excel
topic: Generatore di report
uuid: 5342cc4f-085d-4a2d-a498-38b00a3ef4d3
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Richiama delle funzionalità di Report Builder dalle funzioni di Microsoft Excel

Questa funzionalità integra ulteriormente l'utilizzo del Generatore di report nel flusso di lavoro Excel naturale, senza che sia necessario accedere all'interfaccia utente del Generatore di report.

Ad esempio, potrebbe essere utile aggiornare automaticamente le richieste Generatore di report il cui filtro di input è basato sui dati estratti in Excel da altre origini. Ora è possibile eseguire questa operazione utilizzando la stringa RefreshRequestsInCellsRange(..) . Tutte le chiamate sono asincrone. Essi restituiscono immediatamente e non aspettano che una chiamata venga eseguita completamente.

> [!NOTE] Per poter utilizzare questa funzionalità, è necessario che sia installato Generatore di report 5.0 (o successivo).

Di seguito è riportata una tabella con l'elenco delle funzioni esposte:

| Nome funzione | Descrizione |
|---|---|
| string AsyncRefreshAll() | Aggiorna tutte le richieste del Generatore di report presenti in una cartella di lavoro. |
| string AsyncRefreshRange(string rangeAddressInA1Format) | Aggiorna tutte le richieste del Generatore di report presenti nell'indirizzo specificato dell'intervallo di celle (un'espressione stringa che rappresenta un intervallo di celle in formato A1, ad esempio "Sheet1!A2:A10"). |
| string AsyncRefreshRangeAltTextParam() | Aggiorna tutte le richieste del Generatore di report presenti nell'intervallo di celle specificato che viene passato attraverso il Testo alternativo del controllo Ms Form. |
| string AsyncRefreshActiveWorksheet() | Aggiorna tutte le richieste del Generatore di report presenti nel foglio di lavoro attivo. |
| string AsyncRefreshWorksheet(string foglio di lavoroName) | Aggiorna tutte le richieste del Generatore di report presenti nel foglio di lavoro specificato (il nome del foglio di lavoro visualizzato nella scheda). |
| string AsyncRefreshWorksheetAltTextParam(); | Aggiorna tutte le richieste del Generatore di report presenti nel nome specifico del foglio di lavoro che è stato passato attraverso il Testo alternativo del Controllo del modulo Ms |
| string GetLastRunStatus() | Restituisce una stringa che descrive lo stato dell'ultima esecuzione. |

Per accedere a queste funzioni all'interno del generatore di report, vai a [!UICONTROL Formulas] &gt; [!UICONTROL Insert Function]. In fondo all’elenco delle categorie, troverete Adobe.ReportBuilder.Bridge:

![](assets/arb_functions.png)

## Utilizzare queste funzioni in una formula {#section_034311081C8D4D7AA9275C1435A087CD}

Ad esempio, la formula

```
=IF(OR(ISTEXT(P5),ISBLANK(P5)),AsyncRefreshRange("P9"),"")
```

dice "Se il valore nella cella P5 è testo o è vuoto, aggiorna l’intervallo nella cella P9."

## Utilizzare le funzioni Generatore di report con controllo del formato {#section_26123090B5BD49748C8D8ED7A1C5ED84}

È ora possibile assegnare una macro a un controllo creato e tale controllo può essere una funzione che aggiorna una richiesta di cartella di lavoro. Ad esempio, la funzione AsyncRefreshActiveWorksheet aggiornerà tutte le richieste in un foglio di lavoro. A volte, tuttavia, potrebbe essere utile aggiornare solo alcune richieste, non tutte.

1. Impostare il parametro della macro.
1. Fare clic con il pulsante destro del mouse sul controllo e selezionare **[!UICONTROL Assign Macro]**.
1. Immettere il nome della funzione generatore di report (nessun parametro o parentesi).

![](assets/assign_macro.png)

## Trasmettere i parametri alle funzioni Generatore di report tramite il controllo del formato {#section_ECCA1F4990D244619DFD79138064CEF0}

Le due funzioni che utilizzano un parametro possono essere utilizzate con il controllo del formato, ma solo tramite il campo Testo Alt:

* AsyncRefreshRange(string rangeAddressInA1Format)
* AsyncRefreshWorksheet(string foglio di lavoroName)

1. Fare clic con il pulsante destro del mouse sul controllo e selezionare **[!UICONTROL Format Control]**.

   ![](assets/format_control.png)

1. Fate clic sulla [!UICONTROL Alt Text] scheda.

   ![](assets/alt_text.png)

1. In [!UICONTROL Alternative text]di seguito, immettere l'intervallo di celle da aggiornare.
1. Aprite l'elenco dei parametri del generatore di report in [!UICONTROL Formulas] &gt; [!UICONTROL Insert Function]&gt; [!UICONTROL Adobe.ReportBuilder.Bridge].

1. Selezionare una delle due funzioni che terminano con AltTextParam e fare clic **[!UICONTROL OK]**.

