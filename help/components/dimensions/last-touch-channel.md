---
title: Canale di ultimo contatto
description: Il canale di marketing più recente entro la scadenza del coinvolgimento del visitatore.
feature: Dimensions
exl-id: 62a47de5-ee1a-4394-aa63-75cdda92ba6a
source-git-commit: b0d264bb8128f805f5bcb194436e357eef4b6987
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 3%

---

# Canale di ultimo contatto

La dimensione &quot;Canale di ultimo contatto&quot; riporta il canale di marketing più recente con cui un visitatore trova corrispondenza durante il periodo di coinvolgimento del visitatore (30 giorni per impostazione predefinita). Questa dimensione è utile per comprendere quali canali di marketing indirizzano il traffico verso il sito e provocano conversioni, consentendoti di concentrare le attività di marketing nelle aree più efficaci.

## Popola questa dimensione con i dati

Questa quota fa riferimento direttamente ai nomi di canale definiti in [Marketing Channel Manager](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-channels.md).

Ogni hit inviato ai server di raccolta dati Adobe viene eseguito tramite le regole di elaborazione del canale di marketing della suite di rapporti. Esegue l’iterazione di ogni regola in ordine numerico fino a trovare una corrispondenza, in cui il canale di marketing si collega all’hit. Il canale di ultimo contatto persiste con il visitatore finché non visita il sito per un periodo più lungo del periodo di coinvolgimento del visitatore (30 giorni per impostazione predefinita).

Per impostare questa dimensione su un valore specifico, sono necessari i seguenti passaggi:

* Imposta l’elemento dimensionale desiderato come canale nel Gestore dei canali di marketing, in Impostazioni della suite di rapporti.
* Imposta una regola di elaborazione del canale di marketing contenente i criteri desiderati per l’hit.
* L&#39;hit del visitatore per il sito deve corrispondere ai criteri descritti nella regola di elaborazione del canale di marketing.

## Elementi dimensionali

Gli elementi di Dimension includono qualsiasi nome di canale nel Marketing Channel Manager. Per impostazione predefinita, i valori includono `"Paid search"`, `"Natural search"`, `"Display"`, `"Email"`, `"Affiliate"`, `"Direct"`, `"Internal"`, `"Social networks"`, e `"Referring domains"`. Nel Marketing Channel Manager puoi aggiungere o eliminare canali che influiscono sui valori di questa dimensione.
