---
title: Metriche comunemente utilizzate su altre piattaforme guida alla traduzione
description: Scopri come estrarre i dati delle metriche per molti rapporti comuni utilizzando una terminologia più familiare agli utenti Google Analytics.
feature: Third-party Integration
exl-id: e95b0530-8099-4a08-9e2b-75174546277d
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 1%

---

# Metriche comunemente utilizzate su altre piattaforme guida alla traduzione

Su altre piattaforme, come le Google Analytics, molti rapporti condividono un numero comune di metriche. Utilizzare questa pagina per capire come ricreare le metriche utilizzate in molti rapporti.

Per aggiungere più metriche a una tabella a forma libera dell’area di lavoro, trascina la metrica dall’area dei componenti accanto all’intestazione della metrica nell’area di lavoro:

![Metrica aggiuntiva](/help/technotes/ga-to-aa/assets/new_metric.png)

## Metriche di acquisizione

**Utenti** è approssimativamente uguale a **Visitatori univoci** in Workspace. Consulta la [Visitatori univoci](/help/components/metrics/unique-visitors.md) metrica nella guida utente dei Componenti per ulteriori dettagli.

**Nuovi utenti** può essere ottenuto:

1. Trascina **Visitatori univoci** nell&#39;area di lavoro.
2. Trascina **Prime visite** segmento sopra le intestazioni della metrica Visitatori univoci:

   ![Prime visite](../assets/first_time_visits.png)

**Sessioni** è approssimativamente uguale a **Visite** in Analysis Workspace. Consulta la [Visite](/help/components/metrics/visits.md) metrica nella guida utente dei Componenti per ulteriori dettagli.

![Metriche di acquisizione](../assets/acquisition_metrics.png)

## Metriche del comportamento

**Percentuale non recapitate** è prontamente disponibile in Analysis Workspace come metrica. Consulta la [Percentuale non recapitate](/help/components/metrics/bounce-rate.md) nella guida utente dei Componenti per ulteriori informazioni.

**Pagine/Sessione** è una metrica calcolata. Esso può essere ottenuto:

1. Se hai già creato questa metrica calcolata, individuala in Metriche e trascinala nell’area di lavoro.
2. Se non hai ancora creato questa metrica calcolata, fai clic sul pulsante **+** vicino all’elenco delle metriche per aprire il Generatore di metrica calcolata.
3. Assegna al sito il titolo &quot;Visualizzazioni pagina per visita&quot; e, se necessario, una descrizione.
4. Impostate il formato su Decimale (Decimal) e impostate il numero di cifre decimali su 2.
5. Trascina **Visualizzazioni pagina** metrica e **Visite** nell&#39;area di definizione.
6. Disporre la definizione in modo che la formula sia **Visualizzazioni di pagina divise per visite**.

   ![Visualizzazioni pagina per visita](/help/technotes/ga-to-aa/assets/page_views_per_visit.png)

7. Fai clic su Salva per tornare all’area di lavoro.
8. Trascina la metrica calcolata appena definita nell’area di lavoro.

   Ulteriori informazioni su [Metriche calcolate](/help/components/c-calcmetrics/cm-overview.md) nella guida utente Componenti.

**Media Durata sessione** è approssimativamente uguale a **Tempo trascorso per visita (secondi)**. Ulteriori informazioni su [Tempo trascorso per visita](/help/components/metrics/time-spent-per-visit.md) nella guida utente dei Componenti.

## Metriche delle conversioni

**Tasso di conversione obiettivo**, **Completamenti obiettivo**, e **Valore obiettivo** richiedono un’implementazione aggiuntiva su entrambe le piattaforme. Se l’implementazione già supporta la dimensione dei prodotti e l’evento di acquisto, considera i seguenti passaggi:

1. Trascina **Ordini** metrica, **Ricavi** metrica e **Visite** nell&#39;area di lavoro.
1. Creare una metrica calcolata di **Ordini per visita**. Utilizza i comandi Ctrl-clic (Windows) o Comando-clic (Mac) su entrambe le intestazioni di metrica per evidenziarle. Fai clic con il pulsante destro del mouse su una delle intestazioni, seleziona **Crea metrica da selezione**, quindi fai clic su **Dividi**. Questa nuova metrica è simile a un Tasso di conversione obiettivo.
1. Se sono necessarie cifre decimali, modifica la metrica calcolata. Fai clic sul pulsante Info nell’intestazione della metrica, quindi sull’icona della matita. Aggiungi 1 o 2 cifre decimali nella finestra del Generatore di metriche calcolate, quindi fai clic su Salva.

   ![Ordini per visita](/help/technotes/ga-to-aa/assets/orders_per_visit.png)

Se l’implementazione non supporta ancora i dati di prodotto o conversione, Adobe consiglia di collaborare con un consulente per l’implementazione per garantire la qualità e l’integrità dei dati.
