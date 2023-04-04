---
title: Gestione delle origini dati
description: Passa all’interfaccia Gestisci origini dati .
source-git-commit: e32a7c85e2f0629c04bcd7ed0fa80ec1593bb6e8
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 3%

---

# Gestione delle origini dati

Utilizzare Gestione origini dati per creare, modificare o disattivare le origini dati. Puoi inoltre utilizzare questa interfaccia per tenere traccia dello stato dei file caricati nelle posizioni FTP delle origini dati.

**[!UICONTROL Admin]** > **[!UICONTROL All Admin]** > **[!UICONTROL Data sources]**

Utilizza il selettore suite di rapporti in alto a destra per passare da una suite di rapporti all’altra nell’organizzazione.

Questa interfaccia contiene tre schede principali; **[!UICONTROL Manage]**, **[!UICONTROL Create]** e **[!UICONTROL File Log]**.

## Gestire i  

La **[!UICONTROL Manage]** La scheda gestisce tutte le origini dati create dall’organizzazione. Puoi visualizzare le informazioni FTP, apportare modifiche alle variabili utilizzate nei file modello o disattivare completamente le origini dati.

![Gestire i  ](assets/manage.png)

L&#39;origine dati principale è sempre [!UICONTROL Web Beacon]. Questa origine dati è ciò che utilizzi per la raccolta dati tipica tramite AppMeasurement. Non può essere modificato o disattivato.

Ciascuna origine dati dispone delle seguenti opzioni:

* **[!UICONTROL Restart Processing]**: Riavvia l&#39;elaborazione dell&#39;origine dati precedentemente interrotta a causa di errori. L&#39;elaborazione continua fino al rilevamento dell&#39;errore successivo. Origini dati interrompe l&#39;elaborazione di un file Origini dati solo quando selezioni **[!UICONTROL Stop processing on errors]**.
* **[!UICONTROL Complete Processing]**: Non più utilizzato - questo pulsante è stato utilizzato solo per [Origini dati di elaborazione completa](full-processing-eol.md).
* **[!UICONTROL Stop processing on errors]**: Casella di controllo che indica al server di elaborazione di arrestarsi quando si verifica un errore. L&#39;elaborazione dell&#39;origine dati non riprende fino a quando non si seleziona **[!UICONTROL Restart Processing]**. Quando un’origine dati rileva un errore del file, notifica l’errore. Ad Adobe, sposta il file con l’errore in una cartella denominata `files_with_errors` sul server FTP. Dopo aver risolto il problema, invia nuovamente il file per l&#39;elaborazione.
* **[!UICONTROL Configure]**: Un collegamento che ti porta attraverso la procedura guidata di creazione delle origini dati per questa origine dati. Questa procedura guidata ti consente di rinominare l’origine dati o di riconfigurare le variabili incluse automaticamente durante il download di un file modello.
* **[!UICONTROL FTP Info]**: Collegamento che ti porta all’ultimo passaggio della procedura guidata per la creazione di origini dati in cui vengono visualizzate le credenziali FTP.

Una volta che un’origine dati riceve i dati, viene visualizzata una tabella contenente diverse colonne per i file caricati.

* **[!UICONTROL Files In Processing Queue]**: Nome del file.
* **[!UICONTROL Rows]**: Numero totale di righe nel file.
* **[!UICONTROL Errors]**: Il numero di righe contenenti errori e che non è stato possibile acquisire.
* **[!UICONTROL Warnings]**: Numero di righe contenenti avvisi.
* **[!UICONTROL Received]**: Timestamp della ricezione del file nel fuso orario della suite di rapporti.
* **[!UICONTROL Status]**: Lo stato del file (`Success` o `Failed`).

## Creazione

La **[!UICONTROL Create]** La scheda ti offre un punto di partenza per la creazione guidata Origini dati .

![Creazione](assets/create.png)

La categoria e il tipo di origine dati erano più importanti nelle versioni precedenti di Adobe Analytics. Tuttavia, il loro uso è ancora limitato:

* Il tipo di origine dati viene visualizzato nel [Gestisci](#manage) scheda per l&#39;origine dati stessa e [Registro file](#file-log) scheda per ogni singolo file.
* Alcuni tipi di origine dati includono automaticamente le variabili durante il download del file modello. Tuttavia, puoi includere qualsiasi dimensione o metrica disponibile purché aderisca al [Formato file](file-format.md).

Oltre a questi motivi, tutte le categorie e i tipi di origine dati che è possibile scegliere sono effettivamente identici. Selezionare la categoria e il tipo che meglio rappresenta lo scopo dell&#39;utilizzo delle origini dati.

Con il ritiro di [Origini dati di elaborazione completa](full-processing-eol.md), non è possibile selezionare diverse categorie e tipi. Se selezioni un tipo di origine dati a elaborazione completa, la **[!UICONTROL Activate]** è disattivata.

## Registro file

La **[!UICONTROL File Log]** scheda ti fornisce una visualizzazione aggregata di tutti i file di origine dati caricati per la suite di rapporti specificata.

![Registro file](assets/file-log.png)

È disponibile una barra di ricerca che consente di individuare un’origine dati specifica. La tabella mostra le colonne seguenti:

* **[!UICONTROL Data Source Name]**: Nome dell&#39;origine dati.
* **[!UICONTROL Type]**: Tipo dell&#39;origine dati.
* **[!UICONTROL Filename]**: Nome del file caricato.
* **[!UICONTROL Rows]**: Numero totale di righe nel file.
* **[!UICONTROL Errors]**: Numero di righe contenenti errori.
* **[!UICONTROL Warnings]**: Non più utilizzato. Numero di righe contenenti avvisi.
* **[!UICONTROL Received]**: Data e ora in cui Adobe ha iniziato a elaborare il file.
* **[!UICONTROL Status]**: Lo stato del file (`Success` o `Failed`).
