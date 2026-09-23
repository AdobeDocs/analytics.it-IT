---
title: Fedeltà del cliente
description: Categorie in base al numero di acquisti precedenti effettuati da un visitatore.
feature: Dimensions
exl-id: 48ac1fdf-9a32-4bcc-8b23-bf58358a3470
TQID: https://experienceleague.adobe.com/Essa0dflFlsqwtTQ4JdaSEOkX6T-zEYrQGhgXBWhfcI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 7%
---
# Fedeltà del cliente

La [dimensione](overview.md) della &quot;Fedeltà del cliente&quot; riporta il numero di visitatori del sito che hanno effettuato 0 acquisti precedenti, 1 acquisto precedente, 2 acquisti precedenti o 3+ acquisti precedenti. Questa dimensione è utile per comprendere in che modo il sito influisce sul comportamento di acquisto. Puoi anche utilizzare questa dimensione in un segmento per concentrarti sui visitatori che ritornano per effettuare un acquisto, in modo da poter incoraggiare un comportamento simile per i nuovi visitatori.

## Popolare questa dimensione con i dati

Adobe calcola questa dimensione lato server dalla cronologia acquisti del visitatore. Nessuna variabile da impostare. Dipende dall&#39;implementazione dell&#39;evento [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) sul sito.

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | Nessuno (calcolato da Adobe) |
| **Campo Web SDK / XDM** | Nessuno (calcolato da Adobe) |
| **Parametro query** | N/D |
| **Tag XML** | N/D |
| **Limite di byte** | N/D |
| **Persistenza** | N/D |

## Elementi dimensionali

Gli elementi di Dimension includono:

* **Non è un cliente**: al momento dell&#39;hit, il visitatore non ha mai effettuato un acquisto in precedenza.
* **Nuovi clienti**: al momento dell&#39;hit, il visitatore ha effettuato un singolo acquisto in precedenza.
* **Clienti di ritorno**: al momento dell&#39;hit, il visitatore ha effettuato due acquisti in precedenza.
* **Clienti fedeli**: al momento dell&#39;hit, il visitatore ha effettuato tre o più acquisti in precedenza.

Quando un visitatore effettua un acquisto (attiva l&#39;evento `purchase`), l&#39;hit e tutti gli hit successivi vengono spostati nel &quot;bucket&quot; successivo. Ad esempio, se un visitatore acquista un prodotto dal sito per la prima volta, passa da &quot;Not a customer&quot; (Non è un cliente) a &quot;New customers&quot; (Nuovi clienti), con l’ordine attribuito a &quot;New customers&quot; (Nuovi clienti). L’elemento dimensionale &quot;Not a customer&quot; (Non cliente) non può avere ordini attribuiti ad esso.
