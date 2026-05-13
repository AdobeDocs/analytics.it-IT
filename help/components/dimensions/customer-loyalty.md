---
title: Fedeltà del cliente
description: Categorie in base al numero di acquisti precedenti effettuati da un visitatore.
feature: Dimensions
exl-id: 48ac1fdf-9a32-4bcc-8b23-bf58358a3470
TQID: https://experienceleague.adobe.com/Essa0dflFlsqwtTQ4JdaSEOkX6T-zEYrQGhgXBWhfcI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 246
ht-degree: 4%

---

# Fedeltà del cliente

La [dimensione](overview.md) della &quot;Fedeltà del cliente&quot; riporta il numero di visitatori del sito che hanno effettuato 0 acquisti precedenti, 1 acquisto precedente, 2 acquisti precedenti o 3+ acquisti precedenti. Questa dimensione è utile per comprendere in che modo il sito influisce sul comportamento di acquisto. Puoi anche utilizzare questa dimensione in un segmento per concentrarti sui visitatori che ritornano per effettuare un acquisto, in modo da poter incoraggiare un comportamento simile per i nuovi visitatori.

## Popolare questa dimensione con i dati

Adobe compila automaticamente questa dimensione in base all&#39;evento [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) nell&#39;implementazione. Se implementi l&#39;evento `purchase` sul sito, questa dimensione funziona sempre.

## Elementi dimensionali

Gli elementi di Dimension includono:

* **Non è un cliente**: al momento dell&#39;hit, il visitatore non ha mai effettuato un acquisto in precedenza.
* **Nuovi clienti**: al momento dell&#39;hit, il visitatore ha effettuato un singolo acquisto in precedenza.
* **Clienti di ritorno**: al momento dell&#39;hit, il visitatore ha effettuato due acquisti in precedenza.
* **Clienti fedeli**: al momento dell&#39;hit, il visitatore ha effettuato tre o più acquisti in precedenza.

Quando un visitatore effettua un acquisto (attiva l&#39;evento `purchase`), l&#39;hit e tutti gli hit successivi vengono spostati nel &quot;bucket&quot; successivo. Ad esempio, se un visitatore acquista un prodotto dal sito per la prima volta, passa da &quot;Not a customer&quot; (Non è un cliente) a &quot;New customers&quot; (Nuovi clienti), con l’ordine attribuito a &quot;New customers&quot; (Nuovi clienti). L’elemento dimensionale &quot;Not a customer&quot; (Non cliente) non può avere ordini attribuiti ad esso.
