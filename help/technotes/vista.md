---
title: Regole VISTA in Adobe Analytics
description: Ulteriori informazioni sulle regole VISTA e sulle relative funzionalità.
exl-id: fab2acc3-b037-48f9-bb20-625ccb75b4cc
feature: Analytics Basics
source-git-commit: b1c22031b9254ff077dfdc04ab90ab231b504299
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 57%

---

# Regole VISTA in Adobe Analytics

Le regole VISTA sono una forma alternativa di modifica dei dati personalizzati che puoi applicare tra la raccolta e l’elaborazione dei dati. Per ulteriori informazioni sulla fase esatta nella pipeline dei dati a cui si applicano le regole VISTA, consulta [Ordine di elaborazione](processing-order.md). Le regole VISTA influiscono solo sui dati correnti durante la raccolta; non alterano i dati esistenti.

Alcuni casi d’uso comuni delle regole VISTA includono:

* Copiare un hit di Analytics da una suite di rapporti a un’altra, modificando facoltativamente i dati nella suite di rapporti copiata
* Personalizzare l‘esclusione IP che supera i casi d’uso offerti da [Escludi per IP](/help/admin/tools/exclude-ip.md)
* Modificare qualsiasi valore della variabile in modo condizionale o globale
* Duplicare i valori della variabile in altre variabili
* Caricare file su un sito FTP di Adobe che può influenzare i valori delle variabili

Molti casi d’uso per le regole VISTA sono già offerti dalle [Regole di elaborazione](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md), [Regole bot](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md), [Suite di rapporti virtuali](/help/components/vrs/vrs-about.md) o semplicemente aggiornando l‘implementazione di Adobe Analytics. Adobe consiglia di applicare le regole VISTA solo come ultima risorsa.

>[!IMPORTANT]
>
>L’implementazione e la configurazione delle regole VISTA richiedono un accordo a pagamento tra l’organizzazione e Adobe Professional Services. Contatta il team del tuo account Adobe se desideri creare o aggiornare una regola VISTA.
>
>Nota:
>
>* La creazione di regole VISTA include solo l’implementazione iniziale. La manutenzione continua o gli aggiornamenti delle regole VISTA richiedono un impegno a pagamento separato.
>
>* Le regole VISTA si basano su condizioni specifiche nei dati. Ad esempio, le modifiche all’implementazione di Adobe Analytics, i tipi di dati o le lunghezze delle stringhe raccolte, le modifiche alle tabelle utilizzate per DB VISTA o altre modifiche ai pattern di dati di input potrebbero causare l’interruzione del funzionamento previsto di una regola VISTA. Adobe consiglia di rivedere regolarmente le regole VISTA per determinare se sono necessari aggiornamenti o rimozione.

## Creare una regola VISTA {#create}

Per creare una regola VISTA, devi utilizzare Adobe Professional Services. Contatta il team del tuo account Adobe se desideri creare una regola VISTA.

## Visualizzare le regole VISTA esistenti {#see}

Adobe non offre un’interfaccia utente per visualizzare le regole VISTA esistenti. Contatta il team dell’account Adobe o l’Assistenza clienti con la suite di rapporti desiderata per recuperare un elenco delle regole VISTA esistenti.
