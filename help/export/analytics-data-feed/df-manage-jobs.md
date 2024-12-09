---
title: Gestisci processi feed dati
description: Scopri come gestire singoli lavori nei feed dati. Naviga nell’interfaccia, utilizza i filtri e cerca, quindi trova le definizioni delle colonne.
feature: Data Feeds
exl-id: b17e333e-290f-42e4-b304-1e34282237a7
source-git-commit: 0eef1b1269dcfbc7648127602bdfe24d4789f4b7
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 1%

---

# Gestire i lavori sui feed dati

I job sono singole attività che generano un file compresso. Sono create e gestite dai feed.

Accedi alla gestione dei processi dei feed dati seguendo questi passaggi:

1. Accedi a [experiencecloud.adobe.com](https://experiencecloud.adobe.com).
2. Fai clic sul menu a 9 griglie in alto a destra, quindi fai clic su [!UICONTROL Analytics].
3. Nel menu principale, fare clic su [!UICONTROL Admin] > [!UICONTROL Data Feeds].
4. Fai clic sulla scheda Processi accanto alla parte superiore.

![Menu feed dati](assets/AdminMenu.png)

## Navigazione nell’interfaccia

Un processo di feed dati è una singola istanza in cui Adobe elabora e restituisce un file compresso per una determinata finestra di reporting. Il job manager fornisce una vista perfezionata per visualizzare lo stato dei singoli job.

![Processi](assets/jobs.jpg)

### Filtri e ricerca

Utilizza i filtri e cerca per individuare il processo esatto che stai cercando.

A sinistra, fai clic sull’icona del filtro per mostrare o nascondere le opzioni di filtro. I filtri sono organizzati per categoria. Fai clic sulla freccia per comprimere o espandere le categorie di filtro. Fai clic sulla casella di controllo per applicare il filtro.

![Filtro](assets/jobs-filter.jpg)

Utilizzare la ricerca per individuare un processo in base al nome.

![Ricerca](assets/search.jpg)

### Feed e processi

Fai clic sulla scheda Feed per visualizzare i feed generali che creano questi processi. Consulta [Gestire i feed dati](df-manage-feeds.md).

### Colonne

Ogni processo mostra diverse colonne che forniscono informazioni al riguardo. Fai clic su un’intestazione di colonna per ordinarla in ordine crescente. Fai di nuovo clic su un’intestazione di colonna per ordinarla in ordine decrescente. Se non riesci a visualizzare una colonna specifica, fai clic sull’icona della colonna in alto a destra.

![Icona colonna](assets/job-cols.jpg)

* **ID feed**: visualizza l&#39;ID feed, un identificatore univoco. I processi creati dallo stesso feed hanno lo stesso ID feed.
* **ID processo**: un identificatore univoco per il processo. Tutti i processi hanno un ID processo diverso.
* **Nome feed**: colonna obbligatoria. Visualizza il nome del feed. I processi creati dallo stesso feed hanno lo stesso nome di feed.
* **Suite di rapporti**: la suite di rapporti da cui il processo fa riferimento ai dati.
* **ID suite di rapporti**: identificatore univoco della suite di rapporti.
* **Ora inizio**: ora di inizio del processo. La data e l’ora vengono visualizzate nel fuso orario della suite di rapporti con offset GMT. I feed giornalieri in genere iniziano vicino alla mezzanotte nel fuso orario della suite di rapporti.
* **Stato**: lo stato del feed.
   * In attesa di dati: il processo è operativo e i dati per l’intervallo di reporting sono in fase di raccolta.
   * Elaborazione: il processo sta creando i file di dati e si sta preparando per inviarli.
   * Completato: il processo è stato completato senza alcun problema.
   * Non riuscito: processo non completato. Consulta [Risoluzione dei problemi dei feed di dati](troubleshooting.md) per determinare la causa dell&#39;errore.
   * In attesa di esportazione: i dati per l’intervallo di reporting non sono ancora stati completamente elaborati.
   * Nessun dato: non sono presenti dati nella suite di rapporti per l’intervallo di reporting richiesto.
* **Ora di completamento**: l&#39;ora in cui il processo è stato completato. La data e l’ora vengono visualizzate nel fuso orario della suite di rapporti con offset GMT.
* **Data richiesta**: l&#39;intervallo di reporting del file. I feed giornalieri in genere mostrano le 00:00 - 23:59 con una differenza GMT, che indica un giorno completo in base al fuso orario della suite di rapporti. I feed orari mostrano la singola ora a cui il processo è destinato.
