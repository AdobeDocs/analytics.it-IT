---
title: Utilizzo delle macro di Visual Basic in Report Builder
description: Scopri come espandere le funzionalità delle cartelle di lavoro di Excel e di Report Builder utilizzando le macro VBA.
feature: Report Builder
role: User, Admin
exl-id: 0d92bce2-22ae-4b0c-af1d-3d12f2041ddf
TQID: https://experienceleague.adobe.com/RxOpojtJn2vi5uMO8CGzCCm7FcPp4qVwbH-XTEBSRsY
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 195
ht-degree: 0%

---

# Macro di Visual Basic in Report Builder

{{legacy-arb}}

Le macro di Visual Basic (VBA) includono funzionalità che consentono di aggiornare le cartelle di lavoro di Excel. Visual Basic dispone dell&#39;accesso alla cartella di lavoro, a Excel e a Windows.

Prima di eseguire le macro VBA, è necessario eseguire la versione più recente di Report Builder e accedere.

>[!IMPORTANT]
>
>Per motivi di protezione, non è possibile pianificare una cartella di lavoro contenente una macro.

Adobe supporta tre metodi API Report Builder.

## `RefreshAllReportBuilderRequests()`

La macro `RefreshAllReportBuilderRequests()` aggiorna tutte le richieste Report Builder nella cartella di lavoro attiva. Inizia chiamando il componente aggiuntivo COM Report Builder tramite il relativo ID prodotto, quindi chiama il comando API `RefreshAllRequests()`:

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

La macro `RefreshAllReportBuilderRequestsInActiveWorksheet()` aggiorna tutte le richieste Report Builder nel foglio di lavoro attivo. La chiamata API `RefreshWorksheetRequests()` accetta un oggetto foglio di lavoro come argomento. È possibile utilizzare questa chiamata per qualsiasi foglio di lavoro contenente richieste Report Builder:

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

La macro `RefreshAllReportBuilderRequestsInCellsRange()` aggiorna tutte le richieste Report Builder i cui output di cella intersecano l&#39;intervallo di celle specificato. L&#39;intervallo di celle utilizzato in questo esempio punta all&#39;intervallo `B1:B54` del foglio di lavoro &quot;Dati&quot; nella cartella di lavoro attiva. L’espressione di intervallo supporta tutte le espressioni di intervallo di Excel supportate:

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
