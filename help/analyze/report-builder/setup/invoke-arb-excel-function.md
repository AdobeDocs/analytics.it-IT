---
description: Questa funzionalità integra ulteriormente l'utilizzo del Report Builder nel flusso di lavoro naturale di Excel, senza richiedere l'accesso all'interfaccia utente del Report Builder.
title: Richiama delle funzionalità di Report Builder dalle funzioni di Microsoft Excel
uuid: 5342cc4f-085d-4a2d-a498-38b00a3ef4d3
feature: Report Builder
role: User, Admin
exl-id: b412f2b5-affe-4297-af4b-85e8c6dfd257
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 4%

---

# Richiama delle funzionalità di Report Builder dalle funzioni di Microsoft Excel

Questa funzionalità integra ulteriormente l&#39;utilizzo del Report Builder nel flusso di lavoro naturale di Excel, senza richiedere l&#39;accesso all&#39;interfaccia utente del Report Builder.

Ad esempio, potrebbe essere utile aggiornare automaticamente le richieste di Report Builder il cui filtro di input si basa sui dati estratti in Excel da altre origini. È ora possibile utilizzare la stringa RefreshRequestsInCellsRange(..) . Tutte le chiamate sono asincrone. Vengono restituiti immediatamente e non attendono la completa esecuzione di una chiamata.

>[!NOTE]
>
>Per il funzionamento di questa funzionalità è necessario aver installato Report Builder 5.0 (o versione successiva).

Di seguito è riportata una tabella con l’elenco delle funzioni esposte:

| Nome funzione | Descrizione |
|---|---|
| string AsyncRefreshAll() | Aggiorna tutte le richieste di Report Builder presenti in una cartella di lavoro. |
| string AsyncRefreshRange(string rangeAddressInA1Format) | Aggiorna tutte le richieste di Report Builder presenti nell&#39;indirizzo di intervallo di celle specificato (un&#39;espressione stringa che rappresenta un intervallo di celle in formato A1, ad esempio &quot;Foglio1!A2:A10&quot;). |
| string AsyncRefreshRangeAltTextParam() | Aggiorna tutte le richieste di Report Builder presenti nell&#39;intervallo di celle specificato passato tramite il testo alternativo del controllo Form Ms. |
| string AsyncRefreshActiveWorksheet() | Aggiorna tutte le richieste di Report Builder presenti nel foglio di lavoro attivo. |
| string AsyncRefreshWorksheet(string sheetName) | Aggiorna tutte le richieste di Report Builder presenti nel foglio di lavoro specificato (il nome del foglio di lavoro visualizzato nella scheda). |
| string AsyncRefreshWorksheetAltTextParam(); | Aggiorna tutte le richieste di Report Builder presenti nel nome specifico del foglio di lavoro passato tramite il testo alternativo del controllo Ms Form |
| string GetLastRunStatus() | Restituisce una stringa che descrive lo stato dell&#39;ultima esecuzione. |

Per accedere a queste funzioni in Report Builder, vai a [!UICONTROL Formulas] > [!UICONTROL Insert Function]. Nella parte inferiore dell’elenco delle categorie, troverai Adobe.ReportBuilder.Bridge:

![](assets/arb_functions.png)

## Utilizzare queste funzioni in una formula {#section_034311081C8D4D7AA9275C1435A087CD}

Ad esempio, la formula

```
=IF(OR(ISTEXT(P5),ISBLANK(P5)),AsyncRefreshRange("P9"),"")
```

dice &quot;Se il valore nella cella P5 è un testo o è vuoto, aggiornare l&#39;intervallo nella cella P9.&quot;

## Utilizzare le funzioni di Report Builder con il controllo del formato {#section_26123090B5BD49748C8D8ED7A1C5ED84}

È ora possibile assegnare una macro a un controllo creato e tale controllo può essere una funzione che aggiorna una richiesta di cartella di lavoro. Ad esempio, la funzione AsyncRefreshActiveWorksheet aggiornerà tutte le richieste in un foglio di lavoro. Talvolta, tuttavia, potrebbe essere utile aggiornare solo alcune richieste, non tutte.

1. Impostare il parametro della macro.
1. Fare clic con il pulsante destro del mouse sul controllo e selezionare **[!UICONTROL Assign Macro]**.
1. Inserire il nome della funzione di Report Builder (nessun parametro o parentesi).

![](assets/assign_macro.png)

## Trasmettere i parametri alle funzioni del Report Builder tramite il controllo del formato {#section_ECCA1F4990D244619DFD79138064CEF0}

Le due funzioni che accettano un parametro possono essere utilizzate con il controllo Formato, ma solo tramite il campo Testo Alt:

* AsyncRefreshRange(string rangeAddressInA1Format)
* AsyncRefreshWorksheet(string sheetName)

1. Fare clic con il pulsante destro del mouse sul controllo e selezionare **[!UICONTROL Format Control]**.

   ![](assets/format_control.png)

1. Fai clic sulla scheda [!UICONTROL Alt Text].

   ![](assets/alt_text.png)

1. Sotto [!UICONTROL Alternative text], immettere l&#39;intervallo di celle da aggiornare.
1. Apri l’elenco dei parametri di Report Builder in [!UICONTROL Formulas] > [!UICONTROL Insert Function]> [!UICONTROL Adobe.ReportBuilder.Bridge].

1. Selezionate una delle due funzioni che terminano con AltTextParam e fate clic su **[!UICONTROL OK]**.
