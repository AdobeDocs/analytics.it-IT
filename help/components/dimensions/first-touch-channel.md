---
title: Canale di primo contatto
description: Il primo canale di marketing entro la scadenza del coinvolgimento del visitatore.
feature: Dimensions
exl-id: cca9794c-1305-4e54-aa13-809b9ebc6230
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 4%

---

# Canale di primo contatto

La [dimensione](overview.md) del &#39;canale di primo contatto&#39; segnala il primo canale di marketing con cui un visitatore corrisponde durante il periodo di coinvolgimento del visitatore (30 giorni per impostazione predefinita). Questa dimensione è utile per comprendere quali canali di marketing indirizzano il traffico iniziale verso il sito, consentendoti di concentrare le attività di marketing nelle aree più efficaci.

## Popolare questa dimensione con i dati

Questa dimensione fa riferimento direttamente ai nomi di canale definiti in [Marketing Channel Manager](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-channels.md).

Ogni hit inviato ai server di raccolta dati di Adobe viene eseguito tramite le regole di elaborazione del canale di marketing della suite di rapporti. Esegue l’iterazione di ogni regola in ordine numerico fino a trovare una corrispondenza, in cui il canale di marketing si collega all’hit. Il canale di primo contatto persiste con il visitatore finché non visita il sito per un periodo più lungo del periodo di coinvolgimento del visitatore (30 giorni per impostazione predefinita).

Per impostare questa dimensione su un valore specifico, sono necessari i seguenti passaggi:

* Imposta l’elemento dimensionale desiderato come canale nel Gestore dei canali di marketing, in Impostazioni della suite di rapporti.
* Imposta una regola di elaborazione del canale di marketing contenente i criteri desiderati per l’hit.
* L&#39;hit del visitatore per il sito deve corrispondere ai criteri descritti nella regola di elaborazione del canale di marketing. _e_ deve essere il primo valore del canale di marketing a farlo nel periodo di coinvolgimento del visitatore.

Se un hit successivo corrisponde ai criteri di un canale di marketing diverso, questa dimensione non viene sovrascritta con il nuovo canale di marketing.

## Elementi dimensionali

Gli elementi Dimension includono un nome di canale nel Marketing Channel Manager. Per impostazione predefinita, i valori includono `"Paid search"`, `"Natural search"`, `"Display"`, `"Email"`, `"Affiliate"`, `"Direct"`, `"Internal"`, `"Social networks"` e `"Referring domains"`. Nel Marketing Channel Manager puoi aggiungere o eliminare canali che influiscono sui valori di questa dimensione.
