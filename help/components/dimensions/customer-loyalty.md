---
title: Fedeltà del cliente
description: Categorie in base al numero di acquisti precedenti effettuati da un visitatore.
feature: Dimensions
exl-id: 48ac1fdf-9a32-4bcc-8b23-bf58358a3470
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '246'
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
