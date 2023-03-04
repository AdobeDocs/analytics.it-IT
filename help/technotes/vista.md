---
title: Regole VISTA in Adobe Analytics
description: Ulteriori informazioni sulle regole VISTA e sulle relative funzionalità.
exl-id: fab2acc3-b037-48f9-bb20-625ccb75b4cc
source-git-commit: c53f886d5329e2a3b5023f9396c3aa2360a86901
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 81%

---

# Regole VISTA in Adobe Analytics

Le regole VISTA sono una forma alternativa di modifica dei dati personalizzati che puoi applicare tra la raccolta e l’elaborazione dei dati. Per ulteriori informazioni sulla fase esatta nella pipeline dei dati a cui si applicano le regole VISTA, consulta [Ordine di elaborazione](processing-order.md). Le regole VISTA influiscono solo sui dati correnti durante la raccolta; non alterano i dati esistenti.

Alcuni casi d’uso comuni delle regole VISTA includono:

* Copiare un hit di Analytics da una suite di rapporti a un’altra, modificando facoltativamente i dati nella suite di rapporti copiata
* Personalizzare l‘esclusione IP che supera i casi d’uso offerti da [Escludi per IP](/help/admin/admin/exclude-ip.md)
* Modificare qualsiasi valore della variabile in modo condizionale o globale
* Duplicare i valori della variabile in altre variabili
* Caricare file su un sito FTP di Adobe che può influenzare i valori delle variabili

Molti casi d’uso per le regole VISTA sono già offerti dalle [Regole di elaborazione](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md), [Regole bot](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md), [Suite di rapporti virtuali](/help/components/vrs/vrs-about.md) o semplicemente aggiornando l‘implementazione di Adobe Analytics. Adobe consiglia di applicare le regole VISTA solo come ultima risorsa.

>[!IMPORTANT]
>
>Le regole VISTA richiedono un accordo a pagamento tra la tua organizzazione e Adobe Professional Services. Contatta il team dell’account Adobe se desideri creare o aggiornare una regola VISTA.

## Creare una regola VISTA

Per creare una regola VISTA, devi utilizzare Adobe Professional Services. Se desideri creare una regola VISTA, contatta il team dell’account di Adobe.

## Visualizzare le regole VISTA esistenti

Adobe non offre un’interfaccia utente per visualizzare le regole VISTA esistenti. Contatta il team dell’account Adobe o l’Assistenza clienti con la suite di rapporti desiderata per recuperare un elenco delle regole VISTA esistenti.
