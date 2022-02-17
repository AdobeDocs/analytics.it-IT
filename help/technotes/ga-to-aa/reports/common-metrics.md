---
title: Metriche comunemente utilizzate su altre piattaforme guida alla traduzione
description: Scopri come estrarre i dati delle metriche per molti rapporti comuni utilizzando una terminologia più familiare agli utenti di Google Analytics.
feature: Third-party Integration
exl-id: e95b0530-8099-4a08-9e2b-75174546277d
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 1%

---

# Metriche comunemente utilizzate su altre piattaforme guida alla traduzione

Su altre piattaforme come Google Analytics, molti rapporti condividono un numero comune di metriche. Usa questa pagina per capire come ricreare le metriche utilizzate in molti rapporti.

Per aggiungere più metriche a una tabella a forma libera dell’area di lavoro, trascina la metrica dall’area dei componenti accanto all’intestazione della metrica nell’area di lavoro:

![Metrica aggiuntiva](/help/technotes/ga-to-aa/assets/new_metric.png)

## Metriche di acquisizione

**Utenti** è approssimativamente uguale a **Visitatori unici** in Workspace. Consulta la sezione [Visitatori unici](/help/components/metrics/unique-visitors.md) per ulteriori informazioni, consulta la guida utente Componenti .

**Nuovi utenti** possono essere ottenute:

1. Trascina **Visitatori unici** nell’area di lavoro.
2. Trascina **Prime visite** sotto le intestazioni della metrica Visitatori unici:

   ![Prime visite](../assets/first_time_visits.png)

**Sessioni** è approssimativamente uguale a **Visite** in Analysis Workspace. Consulta la sezione [Visite](/help/components/metrics/visits.md) per ulteriori informazioni, consulta la guida utente Componenti .

![Metriche di acquisizione](../assets/acquisition_metrics.png)

## Metriche di comportamento

**Frequenza di rimbalzo** è prontamente disponibile in Analysis Workspace come metrica. Consulta la sezione [Frequenza di rimbalzo](/help/components/metrics/bounce-rate.md) nella guida utente Componenti per ulteriori informazioni.

**Pagine/Sessione** è una metrica calcolata. Può essere ottenuto dal seguente:

1. Se hai già creato questa metrica calcolata, individuala in Metriche e trascinala nell’area di lavoro.
2. Se non hai ancora creato questa metrica calcolata, fai clic sul pulsante **+** vicino all’elenco delle metriche per aprire il Generatore di metriche calcolate.
3. Assegna un titolo a &quot;Visualizzazioni pagina per visita&quot; e una descrizione, se necessario.
4. Imposta il formato su Decimal e imposta il numero di posizioni decimali su 2.
5. Trascina **Visualizzazioni pagina** metrica e **Visite** nell&#39;area di definizione.
6. Disporre la definizione in modo che la formula sia **Visualizzazioni di pagina divise per visite**.

   ![Visualizzazioni pagina per visita](/help/technotes/ga-to-aa/assets/page_views_per_visit.png)

7. Fai clic su Salva per tornare all’area di lavoro.
8. Trascina la metrica appena definita nell’area di lavoro.

   Ulteriori informazioni [Metriche calcolate](/help/components/c-calcmetrics/cm-overview.md) nella guida utente Componenti .

**Media del Durata sessione** è approssimativamente uguale a **Tempo trascorso per visita (secondi)**. Ulteriori informazioni [Tempo trascorso per visita](/help/components/metrics/time-spent-per-visit.md) metriche nella guida utente Componenti .

## Metriche di conversione

**Tasso di conversione obiettivo**, **Completamento obiettivo** e **Valore obiettivo** richiedono un’implementazione aggiuntiva su entrambe le piattaforme. Se l’implementazione gestisce già la dimensione dei prodotti e l’evento di acquisto, considera i seguenti passaggi:

1. Trascina **Ordini** metrica, **Entrate** e **Visite** nell’area di lavoro.
1. Creare una metrica calcolata di **Ordini per visita**. Usa Ctrl+clic (Windows) o Comando+clic (Mac) su entrambe le intestazioni di metrica per evidenziarle. Fai clic con il pulsante destro del mouse su una delle intestazioni, seleziona **Crea metrica dalla selezione**, quindi fai clic su **Dividi**. Questa nuova metrica è simile al tasso di conversione obiettivo.
1. Se sono necessarie posizioni decimali, modifica la metrica calcolata. Fai clic sul pulsante Informazioni nell’intestazione della metrica, quindi sull’icona a forma di matita. Aggiungi 1 o 2 posizioni decimali nella finestra Generatore di metriche calcolate, quindi fai clic su Salva.

   ![Ordini per visita](/help/technotes/ga-to-aa/assets/orders_per_visit.png)

Se l’implementazione non supporta ancora i dati di conversione o di prodotto, Adobe consiglia di lavorare con un consulente di implementazione per garantire la qualità e l’integrità dei dati.
