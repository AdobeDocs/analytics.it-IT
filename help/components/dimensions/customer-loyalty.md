---
title: Fedeltà del cliente
description: Categorie basate sul numero di acquisti precedenti effettuati da un visitatore.
feature: Dimensions
exl-id: 48ac1fdf-9a32-4bcc-8b23-bf58358a3470
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 1%

---

# Fedeltà del cliente

La dimensione &quot;Fedeltà cliente&quot; indica il numero di visitatori del sito che hanno effettuato 0 acquisti precedenti, 1 acquisto precedente, 2 acquisti precedenti o 3 acquisti precedenti. Questa dimensione è utile per comprendere in che modo il sito influisce sul comportamento d’acquisto. Puoi anche utilizzare questa dimensione in un segmento per concentrarti sui visitatori che ritornano per effettuare un acquisto, in modo da incoraggiare comportamenti simili per i nuovi visitatori.

## Popolare questa dimensione con i dati

Adobe compila automaticamente questa dimensione in base al [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) nella tua implementazione. Se implementi la `purchase` sul sito, questa dimensione funziona sempre.

## Elementi Dimension

Gli elementi di Dimension includono:

* **Non cliente**: Al momento dell’hit, il visitatore non ha mai effettuato un acquisto prima.
* **Nuovi clienti**: Al momento dell’hit, il visitatore ha effettuato un singolo acquisto in precedenza.
* **Clienti di ritorno**: Al momento dell’hit, il visitatore ha effettuato due acquisti in precedenza.
* **Clienti fedeli**: Al momento dell’hit, il visitatore ha effettuato tre o più acquisti in precedenza.

Quando un visitatore effettua un acquisto (attiva la `purchase` , tale hit e tutti gli hit successivi passano al successivo &quot;bucket&quot;. Ad esempio, se un visitatore acquista un prodotto dal sito per la prima volta, passa da &quot;Non cliente&quot; a &quot;Nuovi clienti&quot;, con l’ordine attribuito a &quot;Nuovi clienti&quot;. L’elemento dimensione &quot;Not a customer&quot; (Non cliente) non può ricevere ordini attribuiti.
