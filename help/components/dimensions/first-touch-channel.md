---
title: Canale di primo contatto
description: Il primo canale di marketing entro la scadenza del coinvolgimento del visitatore.
feature: Dimensions
exl-id: cca9794c-1305-4e54-aa13-809b9ebc6230
source-git-commit: ee27311cac5b61dea4d8e850e67126e5fe1d649d
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 2%

---

# Canale di primo contatto

La dimensione &quot;Canale primo contatto&quot; indica il primo canale di marketing a cui un visitatore corrisponde durante il periodo di coinvolgimento del visitatore (30 giorni per impostazione predefinita). Questa dimensione è utile per comprendere quali canali di marketing veicolano il traffico iniziale verso il sito, consentendoti di concentrare le attività di marketing nelle aree più efficaci.

## Popolare questa dimensione con i dati

Questa dimensione fa riferimento direttamente ai nomi dei canali definiti nella [Marketing Channel Manager](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels-admin.md).

Ogni hit inviato ai server di raccolta dati di Adobe viene eseguito tramite le regole di elaborazione del canale di marketing della suite di rapporti. Ripete ogni regola in ordine numerico fino a quando non trova una corrispondenza, in cui quel canale di marketing si collega all’hit. Il canale di primo contatto persiste con il visitatore finché non visita il sito per un periodo di tempo superiore al periodo di coinvolgimento del visitatore (30 giorni per impostazione predefinita).

Se desideri impostare questa dimensione su un valore specifico, sono necessari i seguenti passaggi:

* Imposta l’elemento dimensionale desiderato come canale nel gestore del canale di marketing in Impostazioni suite di rapporti.
* Imposta una regola di elaborazione del canale di marketing che contiene i criteri desiderati per l’hit.
* L’hit del visitatore per il sito deve corrispondere ai criteri descritti nella regola di elaborazione del canale di marketing, _e_ deve essere il primo valore del canale di marketing a farlo nel periodo di coinvolgimento del visitatore.

Se un hit successivo corrisponde ai criteri in un canale di marketing diverso, questa dimensione non viene sovrascritta con il nuovo canale di marketing.

## Elementi dimensionali

Gli elementi di Dimension includono qualsiasi nome di canale nel Marketing Channel Manager. Per impostazione predefinita, i valori includono `"Paid search"`, `"Natural search"`, `"Display"`, `"Email"`, `"Affiliate"`, `"Direct"`, `"Internal"`, `"Social networks"`e `"Referring domains"`. Puoi aggiungere o eliminare canali nel gestore di canali di marketing, che influiscono sui valori di questa dimensione.
