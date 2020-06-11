---
title: Metriche comunemente utilizzate su altre piattaforme Guida alla traduzione
description: Scopri come estrarre i dati delle metriche per molti report comuni utilizzando la terminologia più familiare per gli utenti di Google Analytics.
translation-type: tm+mt
source-git-commit: 6fc8145d9a94427ec942d55776b6029f7dd6f79c
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 0%

---


# Metriche comunemente utilizzate su altre piattaforme Guida alla traduzione

Su altre piattaforme come Google Analytics, molti report condividono un numero comune di metriche. Utilizzare questa pagina per comprendere come ricreare le metriche utilizzate in molti report.

Per aggiungere più metriche a una tabella a forma libera nell’area di lavoro, trascina la metrica dall’area dei componenti accanto all’intestazione della metrica nell’area di lavoro:

![Metrica aggiuntiva](/help/technotes/ga-to-aa/assets/new_metric.png)

## Metriche di acquisizione

**Gli utenti** sono all’incirca uguali a Visitatori **** unici in Workspace. Per ulteriori informazioni, consulta la metrica Visitatori [](/help/components/metrics/unique-visitors.md) unici nella guida utente Componenti.

**I nuovi utenti** possono essere ottenuti tramite:

1. Trascina la metrica Visitatori **** univoci nell’area di lavoro.
2. Trascina il segmento **First Time Visits (Visite** per la prima volta) sopra le intestazioni della metrica Unique Visitors (Visitatori unici):

   ![Prima visita](../assets/first_time_visits.png)

**Le sessioni** equivalgono approssimativamente alle **visite** in Analysis Workspace. Per ulteriori dettagli, consulta la metrica [Visite](/help/components/metrics/visits.md) nella guida utente Componenti.

![Metriche di acquisizione](../assets/acquisition_metrics.png)

## Metriche del comportamento

**Bounce Rate** è facilmente disponibile in Analysis Workspace come metrica. Per ulteriori informazioni, consulta la metrica [Frequenza](/help/components/metrics/bounce-rate.md) rimbalzi nella guida utente Componenti.

**Pages/Session** è una metrica calcolata. Può essere ottenuto tramite:

1. Se hai già creato questa metrica calcolata, individua la metrica in Metriche e trascinala nell’area di lavoro.
2. Se non hai ancora creato questa metrica calcolata, fai clic sull’icona **+** accanto all’elenco delle metriche per aprire il Generatore di metriche calcolate.
3. Assegna un titolo di &#39;Visualizzazioni di pagina per visita&#39; e una descrizione, se necessario.
4. Impostate il formato su Decimale e impostate il numero di posizioni decimali su 2.
5. Trascina la metrica Visualizzazioni **** pagina e **Visite** nell’area di definizione.
6. Disporre la definizione in modo che la formula sia Visualizzazioni di **pagina divise per Visite**.

   ![Visualizzazioni pagina per visita](/help/technotes/ga-to-aa/assets/page_views_per_visit.png)

7. Fate clic su Salva per tornare all’area di lavoro.
8. Trascina nell’area di lavoro la metrica calcolata appena definita.

   Per ulteriori informazioni sulle metriche [calcolate](/help/components/c-calcmetrics/cm-overview.md) , consulta la Guida utente ai componenti.

**Media Durata** sessione: circa **tempo trascorso per visita (secondi)**. Ulteriori informazioni sul [tempo trascorso per visita](/help/components/metrics/time-spent-per-visit.md) metriche nella guida utente Componenti.

## Metriche di conversione

**Tasso** di conversione obiettivo, **completamenti** obiettivo e valore **** obiettivo richiedono un&#39;implementazione aggiuntiva su entrambe le piattaforme. Se l’implementazione include già la dimensione dei prodotti e l’evento di acquisto, effettua i seguenti passaggi:

1. Trascina nell’area di lavoro la metrica **Ordini** , la metrica **Entrate** e la metrica **Visite** .
1. Crea una metrica calcolata di **Ordini per visita**. Per evidenziare entrambe le intestazioni delle metriche, tenete premuto Ctrl (Windows) o Comando (Mac OS) e fate clic. Fai clic con il pulsante destro del mouse su una delle intestazioni, seleziona **Crea metrica dalla selezione**, quindi fai clic su **Dividi**. Questa nuova metrica è simile a un tasso di conversione obiettivo.
1. Se sono necessarie posizioni decimali, modificare la metrica calcolata. Fate clic sul pulsante Informazioni nell’intestazione della metrica, quindi sull’icona della matita. Aggiungere 1 o 2 Posizioni decimali nella finestra Generatore metriche calcolate, quindi fare clic su Salva.

   ![Ordini per visita](/help/technotes/ga-to-aa/assets/orders_per_visit.png)

Se l&#39;implementazione non contiene ancora dati relativi a prodotti o conversioni, Adobe consiglia di collaborare con un consulente di implementazione per garantire la qualità e l&#39;integrità dei dati.
