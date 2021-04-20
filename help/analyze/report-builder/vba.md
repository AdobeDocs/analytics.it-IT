---
title: Macro di Visual Basic in Report Builder
description: Espandere le funzionalità delle cartelle di lavoro e del Report Builder Excel utilizzando VBA.
feature: Report Builder
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 0%

---


# Macro di Visual Basic in Report Builder

Le macro VBA, note anche come macro di Visual Basic, consentono di manipolare le cartelle di lavoro in modo che Microsoft Excel da solo non possa. Visual Basic dispone dell&#39;accesso alla cartella di lavoro, a Excel e persino a Windows.

Adobe supporta tre metodi API Report Builder. Assicurati che sia installata la versione più recente di Report Builder e accedi prima di eseguire qualsiasi macro.

>[!IMPORTANT]
>
>Per motivi di sicurezza, non è possibile pianificare una cartella di lavoro contenente una macro.

## `RefreshAllReportBuilderRequests()`

La macro `RefreshAllReportBuilderRequests()` aggiorna tutte le richieste di Report Builder nella cartella di lavoro attiva. Inizia chiamando il componente aggiuntivo COM del Report Builder tramite il relativo ID prodotto, quindi chiama il comando `RefreshAllRequests()` API :

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

La macro `RefreshAllReportBuilderRequestsInActiveWorksheet()` aggiorna tutte le richieste di Report Builder nel foglio di lavoro attivo. La chiamata API `RefreshWorksheetRequests()` considera un oggetto foglio di lavoro come un argomento. Puoi utilizzare questa chiamata per qualsiasi foglio di lavoro contenente richieste di Report Builder:

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

La macro `RefreshAllReportBuilderRequestsInCellsRange()` aggiorna tutte le richieste di Report Builder i cui output di cella intersecano l&#39;intervallo di celle specificato. L&#39;intervallo di celle utilizzato in questo esempio fa riferimento all&#39;intervallo `B1:B54` del foglio di lavoro &quot;Dati&quot; all&#39;interno della cartella di lavoro attiva. L&#39;espressione intervallo supporta tutte le espressioni di intervallo Excel supportate:

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
