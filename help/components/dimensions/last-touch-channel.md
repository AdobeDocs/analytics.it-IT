---
title: Canale di ultimo contatto
description: Il canale di marketing più recente entro la scadenza del coinvolgimento del visitatore.
feature: Dimensions
exl-id: 62a47de5-ee1a-4394-aa63-75cdda92ba6a
TQID: https://experienceleague.adobe.com/wUNsv-0snBfk6EE6yeCEuT8-hGvBu9U8tjKDfxhVRA0
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
    internal-label: Marketing Channels
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
    internal-label: Report Suite settings
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 6%
---
# Canale di ultimo contatto

La [dimensione](overview.md) del &quot;canale di ultimo contatto&quot; riporta il canale di marketing più recente con cui un visitatore trova corrispondenza durante il periodo di coinvolgimento del visitatore (30 giorni per impostazione predefinita). Questa dimensione è utile per comprendere quali canali di marketing indirizzano il traffico verso il sito e provocano conversioni, consentendoti di concentrare le attività di marketing nelle aree più efficaci.

## Popolare questa dimensione con i dati

Questa dimensione viene derivata dalle regole di elaborazione del canale di marketing. Fa riferimento direttamente ai nomi di canale definiti in [Marketing Channel Manager](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-channels.md). Ogni hit scorre attraverso le regole di elaborazione del canale di marketing della suite di rapporti in ordine numerico fino a quando non trova una corrispondenza che lega il canale di marketing all’hit. Nessuna variabile da impostare.

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | Nessuno (derivato dalle regole di elaborazione del canale di marketing) |
| **Campo Web SDK / XDM** | Nessuno (derivato dalle regole di elaborazione del canale di marketing) |
| **Parametro query** | N/D |
| **Tag XML** | N/D |
| **Limite di byte** | N/D |
| **Persistenza** | Configurabile |

Il canale di ultimo contatto persiste con il visitatore finché non visita il sito per un periodo più lungo del periodo di coinvolgimento del visitatore (30 giorni per impostazione predefinita).

Per impostare questa dimensione su un valore specifico, sono necessari i seguenti passaggi:

* Imposta l’elemento dimensionale desiderato come canale nel Gestore dei canali di marketing, in Impostazioni della suite di rapporti.
* Imposta una regola di elaborazione del canale di marketing contenente i criteri desiderati per l’hit.
* L&#39;hit del visitatore per il sito deve corrispondere ai criteri descritti nella regola di elaborazione del canale di marketing.

>[!TIP]
>
>L&#39;utilizzo di questa dimensione con metriche che utilizzano l&#39;attribuzione di partecipazione [](/help/analyze/analysis-workspace/attribution/models.md) può attribuire il credito a `None` quando altri modelli di attribuzione non lo fanno. Le metriche di partecipazione richiedono un canale di marketing [istanza](../metrics/instances.md) nell&#39;intervallo di reporting per ricevere credito. Se il canale di marketing è stato inizialmente impostato al di fuori dell&#39;intervallo di reporting ed esiste solo il valore persistente nell&#39;intervallo di reporting, le metriche di partecipazione attribuiscono il credito a `None`. Altri modelli di attribuzione attribuiscono il merito al valore persistente. Se in questo scenario si desidera evitare l&#39;attribuzione a `None`, è consigliabile utilizzare un modello di attribuzione di non partecipazione.

## Elementi dimensionali

Gli elementi Dimension includono un nome di canale nel Marketing Channel Manager. Per impostazione predefinita, i valori includono `"Paid search"`, `"Natural search"`, `"Display"`, `"Email"`, `"Affiliate"`, `"Direct"`, `"Internal"`, `"Social networks"` e `"Referring domains"`. Nel Marketing Channel Manager puoi aggiungere o eliminare canali che influiscono sui valori di questa dimensione.
