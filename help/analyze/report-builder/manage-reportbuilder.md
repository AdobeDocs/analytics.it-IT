---
title: Come gestire i blocchi di dati utilizzando Report Builder
description: Descrive come utilizzare la funzione di gestione nel Report Builder
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 63e169b3-7e13-405e-83a4-17f2a9917ed2
source-git-commit: 3d1a26b960988020391e75b3d01af0f9b806d33b
workflow-type: tm+mt
source-wordcount: '627'
ht-degree: 59%

---

# Gestire i blocchi di dati nel Report Builder

Puoi visualizzare e gestire tutti i blocchi di dati in una cartella di lavoro utilizzando il Data Block Manager (Gestore dei blocchi di dati). Il Data Block Manager (Gestore dei blocchi di dati) fornisce funzionalità di ricerca, filtro e ordinamento che consentono di individuare rapidamente blocchi di dati specifici. Dopo aver selezionato uno o più blocchi di dati, puoi modificare, eliminare o aggiornare i blocchi di dati selezionati.

![Schermata Gestione blocchi di dati.](./assets/image52.png)

## Visualizzare blocchi di dati

Fai clic su **Gestisci** per visualizzare un elenco di tutti i blocchi di dati presenti in una cartella di lavoro.

![Opzione Gestisci per visualizzare un elenco di tutti i blocchi di dati.](./assets/image53.png)

Nel Data Block Manager (Gestore dei blocchi di dati) sono elencati tutti i blocchi di dati presenti in una cartella di lavoro. 

## Ordinare l’elenco di blocchi di dati

Puoi ordinare l’elenco di blocchi di dati in base a una colonna visualizzata. Ad esempio, puoi ordinare l’elenco Bloccati di dati per suite di rapporti, segmenti, intervallo di date e altre variabili.

Per ordinare l’elenco di blocchi di dati, fai clic su un’intestazione di colonna.

![Ordinamento dei blocchi di dati.](./assets/image54.png)

## Ricerca nell’elenco di blocchi di dati

Utilizza il campo di ricerca per individuare qualsiasi elemento nella tabella dei blocchi di dati. Ad esempio, puoi cercare le metriche contenute nei blocchi di dati o nella suite di rapporti. Puoi inoltre cercare le date visualizzate nelle colonne dell’intervallo di date, della data di modifica o dell’ultima esecuzione.

![Utilizzo del campo di ricerca per individuare qualsiasi elemento nella tabella dei blocchi di dati.](./assets/image55.png)

## Modificare blocchi di dati

Puoi modificare la suite di rapporti, l’intervallo di date o i segmenti applicati a uno o più blocchi di dati.

Ad esempio, puoi sostituire un segmento esistente con un nuovo segmento in uno o più blocchi di dati.

1. Seleziona i blocchi di dati da aggiornare. Puoi selezionare la casella di controllo di primo livello per selezionare tutti i blocchi di dati oppure selezionare i singoli blocchi di dati.

   ![Icona modifica matita](./assets/image56.png)

1. Fai clic sull’icona di modifica per visualizzare la finestra di modifica rapida.

   ![Finestra di modifica rapida](./assets/image58.png)

1. Seleziona un collegamento a un segmento per aggiornare suite di rapporti, intervalli di date o segmenti.

   ![Il campo Aggiungi segmento nella finestra di modifica rapida](./assets/image59.png)

## Aggiornare blocchi di dati

Fai clic sull’icona di aggiornamento per aggiornare i blocchi di dati nell’elenco.

<img src="./assets/refresh-icon.png" width="15%" alt="Icona Aggiorna"/>

Per verificare se un blocco di dati è stato aggiornato, visualizza l’icona di stato dell’aggiornamento.

Un blocco di dati aggiornato correttamente mostra un segno di spunta in un cerchio verde: <img src="./assets/refresh-success.png" width="5%" alt="Cerchio verde con icona segno di spunta"/>.

Un blocco di dati che non è stato aggiornato visualizza un’icona di avviso: <img src="./assets/refresh-failure.png" width="5%" alt="Triangolo rosso con icona punto esclamativo"/>.Questo consente di identificare facilmente se eventuali blocchi di dati presentano errori.


![Gestione blocchi di dati con stato di aggiornamento per ogni blocco di dati elencato.](./assets/image512.png)

## Eliminare un blocco di dati

Fai clic sull’icona del cestino per eliminare un blocco di dati selezionato.

## Raggruppare blocchi di dati

Puoi raggruppare i blocchi di dati utilizzando il menu a discesa **Raggruppa per** oppure fare clic sul titolo di una colonna. Per ordinare i blocchi di dati per colonna, fai clic sul titolo della colonna. Per raggruppare i blocchi di dati per gruppi, seleziona un nome di gruppo dal menu a discesa **Raggruppa per**. Ad esempio, la schermata seguente mostra i blocchi di dati raggruppati per Sheet (Foglio). I blocchi di dati sono raggruppati per Sheet1 (Foglio1) e Sheet2 (Foglio2). Ciò è utile, ad esempio, nel caso di sostituzione del segmento. Se a ciascun blocco di dati sono applicati più segmenti, è utile creare un gruppo contenente tutti i blocchi di dati che desideri sostituire. Puoi quindi selezionarli e modificarli tutti in una sola volta.

![Gestione blocchi di dati con l&#39;elenco Raggruppa per foglio.](./assets/group-data-blocks.png)

## Modificare la visualizzazione del Data Block Manager (Gestore dei blocchi di dati)

Puoi modificare le colonne visibili nella finestra del Data Block Manager (Gestore dei blocchi di dati).


Fai clic sull’icona dell’elenco delle colonne <img src="./assets/image515.png" width="3%" alt="Icona elenco colonne"/> per selezionare le colonne elencate nel Data Block Manager (Gestore dei blocchi di dati). Seleziona il nome di una colonna per visualizzarla. Deseleziona il nome della colonna per rimuoverla dalla visualizzazione.

![Gestione blocchi dati con elenco colonne](./assets/image516.png)
