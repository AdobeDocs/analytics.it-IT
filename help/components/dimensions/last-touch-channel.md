---
title: Canale di ultimo contatto
description: Il canale di marketing più recente entro la scadenza del coinvolgimento del visitatore.
feature: Dimensions
exl-id: 62a47de5-ee1a-4394-aa63-75cdda92ba6a
source-git-commit: 31c3f83f1142a4ba92a390e35ca8dcae66dfa660
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 3%

---

# Canale di ultimo contatto

La [dimensione](overview.md) del &quot;canale di ultimo contatto&quot; riporta il canale di marketing più recente con cui un visitatore trova corrispondenza durante il periodo di coinvolgimento del visitatore (30 giorni per impostazione predefinita). Questa dimensione è utile per comprendere quali canali di marketing indirizzano il traffico verso il sito e provocano conversioni, consentendoti di concentrare le attività di marketing nelle aree più efficaci.

## Popolare questa dimensione con i dati

Questa dimensione fa riferimento direttamente ai nomi di canale definiti in [Marketing Channel Manager](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-channels.md).

Ogni hit inviato ai server di raccolta dati di Adobe viene eseguito tramite le regole di elaborazione del canale di marketing della suite di rapporti. Esegue l’iterazione di ogni regola in ordine numerico fino a trovare una corrispondenza, in cui il canale di marketing si collega all’hit. Il canale di ultimo contatto persiste con il visitatore finché non visita il sito per un periodo più lungo del periodo di coinvolgimento del visitatore (30 giorni per impostazione predefinita).

Per impostare questa dimensione su un valore specifico, sono necessari i seguenti passaggi:

* Imposta l’elemento dimensionale desiderato come canale nel Gestore dei canali di marketing, in Impostazioni della suite di rapporti.
* Imposta una regola di elaborazione del canale di marketing contenente i criteri desiderati per l’hit.
* L&#39;hit del visitatore per il sito deve corrispondere ai criteri descritti nella regola di elaborazione del canale di marketing.

>[!TIP]
>
>L&#39;utilizzo di questa dimensione con metriche che utilizzano l&#39;attribuzione di partecipazione [](/help/analyze/analysis-workspace/attribution/models.md) può attribuire il credito a `None` quando altri modelli di attribuzione non lo fanno. Le metriche di partecipazione richiedono un canale di marketing [istanza](../metrics/instances.md) nell&#39;intervallo di reporting per ricevere credito. Se il canale di marketing è stato inizialmente impostato al di fuori dell&#39;intervallo di reporting ed esiste solo il valore persistente nell&#39;intervallo di reporting, le metriche di partecipazione attribuiscono il credito a `None`. Altri modelli di attribuzione attribuiscono il merito al valore persistente. Se in questo scenario si desidera evitare l&#39;attribuzione a `None`, è consigliabile utilizzare un modello di attribuzione di non partecipazione.

## Elementi dimensionali

Gli elementi Dimension includono un nome di canale nel Marketing Channel Manager. Per impostazione predefinita, i valori includono `"Paid search"`, `"Natural search"`, `"Display"`, `"Email"`, `"Affiliate"`, `"Direct"`, `"Internal"`, `"Social networks"` e `"Referring domains"`. Nel Marketing Channel Manager puoi aggiungere o eliminare canali che influiscono sui valori di questa dimensione.
