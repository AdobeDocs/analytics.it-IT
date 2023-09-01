---
title: Come utilizzare le macro di Visual Basic nel Report Builder
description: Scopri come espandere le funzionalità delle cartelle di lavoro e del Report Builder di Excel utilizzando le macro VBA.
feature: Report Builder
role: User, Admin
exl-id: 0d92bce2-22ae-4b0c-af1d-3d12f2041ddf
source-git-commit: 66b7de0b008364e47253d319785c204ca479ab26
workflow-type: tm+mt
source-wordcount: '194'
ht-degree: 0%

---

# Macro di Visual Basic nel Report Builder

Le macro di Visual Basic (VBA) includono funzionalità che consentono di aggiornare le cartelle di lavoro di Excel. Visual Basic dispone dell&#39;accesso alla cartella di lavoro, a Excel e a Windows.

Prima di eseguire le macro VBA, è necessario eseguire la versione più recente del Report Builder e accedere.

>[!IMPORTANT]
>
>Per motivi di protezione, non è possibile pianificare una cartella di lavoro contenente una macro.

Adobe supporta tre metodi API di Report Builder.

## `RefreshAllReportBuilderRequests()`

Il `RefreshAllReportBuilderRequests()` la macro aggiorna tutte le richieste di Report Builder nella cartella di lavoro attiva. Inizia chiamando il componente aggiuntivo COM di Report Builder tramite il relativo ID prodotto, quindi chiama `RefreshAllRequests()` Comando API:

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

Il `RefreshAllReportBuilderRequestsInActiveWorksheet()` macro aggiorna tutte le richieste di Report Builder nel foglio di lavoro attivo. Il `RefreshWorksheetRequests()` La chiamata API accetta un oggetto del foglio di lavoro come argomento. È possibile utilizzare questa chiamata per qualsiasi foglio di lavoro contenente richieste di Report Builder:

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

Il `RefreshAllReportBuilderRequestsInCellsRange()` macro aggiorna tutte le richieste di Report Builder i cui output di cella intersecano l&#39;intervallo di celle specificato. L&#39;intervallo di celle utilizzato in questo esempio punta all&#39;intervallo `B1:B54` del foglio di lavoro &quot;Dati&quot; nella cartella di lavoro attiva. L’espressione di intervallo supporta tutte le espressioni di intervallo di Excel supportate:

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
