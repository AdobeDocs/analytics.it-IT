---
title: Metriche comunemente utilizzate su altre piattaforme guida alla traduzione
description: Scopri come estrarre i dati delle metriche per molti rapporti comuni utilizzando una terminologia più familiare agli utenti di Google Analytics.
feature: Third-party Integration
exl-id: e95b0530-8099-4a08-9e2b-75174546277d
TQID: https://experienceleague.adobe.com/0gpsqdwdU6kZjZGLy5YZ1h-b1C4lGUnEwOEKdzvjxyU
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b4dd41a7-ccf8-4e9d-918e-acaab534a307id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 507
ht-degree: 0%

---

# Metriche comunemente utilizzate su altre piattaforme guida alla traduzione

Su altre piattaforme, come Google Analytics, molti rapporti condividono un numero comune di metriche. Utilizzare questa pagina per capire come ricreare le metriche utilizzate in molti rapporti.

Per aggiungere più metriche a una tabella a forma libera dell’area di lavoro, trascina la metrica dall’area dei componenti accanto all’intestazione della metrica nell’area di lavoro:

![Metrica aggiuntiva](/help/technotes/ga-to-aa/assets/new_metric.png)

## Metriche di acquisizione

**Utenti** è approssimativamente uguale a **Visitatori univoci** in Workspace. Per ulteriori dettagli, consulta la metrica [Visitatori univoci](/help/components/metrics/unique-visitors.md) nella guida utente dei Componenti.

**I nuovi utenti** possono essere ottenuti dai seguenti:

1. Trascina la metrica **Visitatori univoci** nell&#39;area di lavoro.
2. Trascina il segmento **Nuovo visitatore** sopra le intestazioni della metrica Visitatori univoci:

   ![Prime visite](../assets/first_time_visits.png)

**Sessioni** equivale approssimativamente a **Visite** in Analysis Workspace. Per ulteriori dettagli, consulta la metrica [Visite](/help/components/metrics/visits.md) nella guida utente dei Componenti.

![Metriche di acquisizione](../assets/acquisition_metrics.png)

## Metriche del comportamento

**Percentuale non recapitate** è prontamente disponibile in Analysis Workspace come metrica. Per ulteriori informazioni, consulta la metrica [Percentuale non recapitate](/help/components/metrics/bounce-rate.md) nella guida utente dei Componenti.

**Pages/Session** è una metrica calcolata. Esso può essere ottenuto:

1. Se hai già creato questa metrica calcolata, individuala in Metriche e trascinala nell’area di lavoro.
2. Se non hai ancora creato questa metrica calcolata, fai clic sull&#39;icona **+** accanto all&#39;elenco delle metriche per aprire il Generatore della metrica calcolata.
3. Assegna al sito il titolo &quot;Visualizzazioni pagina per visita&quot; e, se necessario, una descrizione.
4. Impostate il formato su Decimale (Decimal) e impostate il numero di cifre decimali su 2.
5. Trascina la metrica **Visualizzazioni pagina** e la metrica **Visite** nell&#39;area di definizione.
6. Disporre la definizione in modo che la formula sia **Visualizzazioni pagina divise per Visite**.

   ![Visualizzazioni pagina per visita](/help/technotes/ga-to-aa/assets/page_views_per_visit.png)

7. Fai clic su Salva per tornare all’area di lavoro.
8. Trascina la metrica calcolata appena definita nell’area di lavoro.

   Ulteriori informazioni su [Metriche calcolate](/help/components/calculated-metrics/cm-overview.md) nella guida utente Componenti.

**Media La durata della sessione** è approssimativamente uguale a **Tempo trascorso per visita (secondi)**. Ulteriori informazioni sulle metriche [Tempo trascorso per visita](/help/components/metrics/time-spent-per-visit.md) nella guida utente dei Componenti.

## Metriche delle conversioni

**Tasso di conversione obiettivo**, **Completamenti obiettivo** e **Valore obiettivo** richiedono un&#39;implementazione aggiuntiva su entrambe le piattaforme. Se l’implementazione già supporta la dimensione dei prodotti e l’evento di acquisto, considera i seguenti passaggi:

1. Trascina nell&#39;area di lavoro la metrica **Ordini**, la metrica **Ricavi** e la metrica **Visite**.
1. Crea una metrica calcolata di **Ordini per visita**. Utilizza i comandi Ctrl-clic (Windows) o Comando-clic (Mac) su entrambe le intestazioni di metrica per evidenziarle. Fai clic con il pulsante destro del mouse su una delle intestazioni, seleziona **Crea metrica da selezione**, quindi fai clic su **Dividi**. Questa nuova metrica è simile a un Tasso di conversione obiettivo.
1. Se sono necessarie cifre decimali, modifica la metrica calcolata. Fai clic sul pulsante Info nell’intestazione della metrica, quindi sull’icona della matita. Aggiungi 1 o 2 cifre decimali nella finestra del Generatore di metriche calcolate, quindi fai clic su Salva.

   ![Ordini per visita](/help/technotes/ga-to-aa/assets/orders_per_visit.png)

Se l’implementazione non supporta ancora dati di prodotto o conversione, Adobe consiglia di collaborare con un consulente per l’implementazione per garantire la qualità e l’integrità dei dati.
