---
title: Macro di Visual Basic in Report Builder
description: Espandere le funzionalità delle cartelle di lavoro e del Report Builder Excel utilizzando VBA.
translation-type: tm+mt
source-git-commit: b569f87dde3b9a8b323e0664d6c4d1578d410bb7
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 0%

---


# Macro di Visual Basic in Report Builder

Le macro VBA, note anche come macro di Visual Basic, consentono di manipolare le cartelle di lavoro in modo che Microsoft Excel da solo non possa. Visual Basic ha accesso alla cartella di lavoro, a Excel e persino a Windows.

 Adobe supporta tre metodi API Report Builder. Prima di eseguire le macro, verificare che sia installata la versione più recente del generatore di report ed eseguire il login.

>[!IMPORTANT]
>
>Per motivi di sicurezza, non è possibile pianificare una cartella di lavoro contenente una macro.

## `RefreshAllReportBuilderRequests()`

La `RefreshAllReportBuilderRequests()` macro aggiorna tutte le richieste di Report Builder nella cartella di lavoro attiva. Inizia chiamando il componente aggiuntivo COM del Report Builder tramite il relativo ID prodotto, quindi chiama il comando `RefreshAllRequests()` API:

```vba
Sub RefreshAllReportBuilderRequests()
 
 Dim addIn As COMAddIn
 Dim automationObject As Object
 Dim success As String
 Set addIn = Application.COMAddIns("ReportBuilderAddIn.Connect")
 Set automationObject = addIn.Object
 success = automationObject.RefreshAllRequests(ActiveWorkbook)
 
End Sub
```

## `RefreshAllReportBuilderRequestsInActiveWorksheet()`

La `RefreshAllReportBuilderRequestsInActiveWorksheet()` macro aggiorna tutte le richieste di Report Builder nel foglio di lavoro attivo. La chiamata `RefreshWorksheetRequests()` API prende un oggetto foglio di lavoro come argomento. Puoi utilizzare questa chiamata per qualsiasi foglio di lavoro contenente richieste di Report Builder:

```vba
Sub RefreshAllReportBuilderRequestsInActiveWorksheet()
 
 Dim addIn As COMAddIn
 Dim automationObject As Object
 Dim success As String
 Set addIn = Application.COMAddIns("ReportBuilderAddIn.Connect")
 Set automationObject = addIn.Object
 success = automationObject.RefreshWorksheetRequests(ActiveWorkbook.ActiveSheet)
 
End Sub
```

## `RefreshAllReportBuilderRequestsInCellsRange()`

La `RefreshAllReportBuilderRequestsInCellsRange()` macro aggiorna tutte le richieste di Report Builder i cui output della cella intersecano l&#39;intervallo di celle specificato. L&#39;intervallo di celle utilizzato in questo esempio fa riferimento all&#39;intervallo `B1:B54` del foglio di lavoro &quot;Dati&quot; all&#39;interno della cartella di lavoro attiva. L&#39;espressione intervallo supporta tutte le espressioni di intervallo Excel supportate:

```vba
Sub RefreshAllReportBuilderRequestsInCellsRange()
 
 Dim addIn As COMAddIn
 Dim automationObject As Object
 Dim success As String
 Set addIn = Application.COMAddIns("ReportBuilderAddIn.Connect")
 Set automationObject = addIn.Object
 success = automationObject.RefreshRequestsInCellsRange("'Data'!B1:B54")
  
End Sub
```
