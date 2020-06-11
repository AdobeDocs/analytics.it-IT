---
title: Fedeltà dei clienti
description: Categorie basate sul numero di acquisti precedenti effettuati da un visitatore.
translation-type: tm+mt
source-git-commit: a8dc233e962a49674a30ff3c9f0b5d0d45b09f24
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 0%

---


# Fedeltà dei clienti

La dimensione &quot;fidelizzazione del cliente&quot; indica il numero di visitatori del sito che hanno effettuato 0 acquisti precedenti, 1 acquisto precedente, 2 acquisti precedenti o 3 acquisti precedenti. Questa dimensione è importante per comprendere in che modo il sito influisce sul comportamento di acquisto. Puoi anche utilizzare questa dimensione in un segmento per concentrarti sui visitatori che tornano per effettuare un acquisto, in modo da incoraggiare un comportamento simile per i nuovi visitatori.

## Compilare questa dimensione con i dati

Adobe compila automaticamente questa dimensione in base all’ [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) evento nell’implementazione. Se implementate l’ `purchase` evento sul sito, questa dimensione funziona sempre.

## Valori dimensione

I valori delle dimensioni includono quanto segue:

* **Non è un cliente**: Al momento dell’hit, il visitatore non ha mai effettuato un acquisto prima.
* **Nuovi clienti**: Al momento dell’hit, il visitatore effettuava un singolo acquisto prima.
* **Restituisci clienti**: Al momento dell’hit, il visitatore ha effettuato due acquisti prima.
* **Clienti** fedeli: Al momento dell’hit, il visitatore ha effettuato tre o più acquisti prima.

Quando un visitatore effettua un acquisto (attiva l’ `purchase` evento), l’hit e tutti gli hit successivi si spostano nel successivo &quot;bucket&quot;. Ad esempio, se un visitatore acquista un prodotto dal sito per la prima volta, passa da &quot;Not a customer&quot; a &quot;New customer&quot;, con l&#39;ordine attribuito a &quot;New customer&quot;. Il valore di dimensione &quot;Not a customer&quot; non può essere attribuito ad esso.
