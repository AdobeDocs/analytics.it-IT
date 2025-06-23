---
title: Pianificazione delle cartelle di lavoro con Report Builder in Adobe Analytics
description: Scopri come utilizzare la funzione di pianificazione in Report Builder
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 40e1feb0-64bc-40e6-83cb-4a1ea7e2d0cc
source-git-commit: 9ece9f6fcebdf308b6218aa50ab78af4f75ee8e7
workflow-type: tm+mt
source-wordcount: '857'
ht-degree: 69%

---

# Pianificare le cartelle di lavoro condividendo tramite e-mail

>[!NOTE]
>
>Oltre a pianificare le cartelle di lavoro per la condivisione tramite e-mail, come descritto in questa sezione, è possibile pianificare le cartelle di lavoro da esportare nelle destinazioni cloud, come descritto in [Pianificare le cartelle di lavoro per l&#39;esportazione nelle destinazioni cloud](/help/analyze/report-builder/report-builder-export.md).

Dopo aver salvato la cartella di lavoro e completato l’analisi, è possibile condividere facilmente la cartella di lavoro con altri membri del team utilizzando la funzione di pianificazione. La funzione Schedule (Pianifica) consente di creare una pianificazione che aggiorna automaticamente i dati nella cartella di lavoro e invia tramite e-mail il file .xlsx della cartella di lavoro di Excel come allegato al pubblico specificato alla data e all’ora indicate. L’impostazione di una pianificazione fornisce automaticamente ai destinatari aggiornamenti regolari. Puoi anche utilizzare la funzione di pianificazione per inviare la cartella di lavoro una volta senza pianificare gli aggiornamenti automatici.

Puoi creare più pianificazioni per una singola cartella di lavoro. Ad esempio, puoi inviare una cartella di lavoro al team su base giornaliera e inviare la cartella di lavoro al tuo responsabile una volta alla settimana creando due pianificazioni diverse.

La funzione Schedule (Pianifica) consente inoltre di impostare la protezione tramite password per una cartella di lavoro e di modificare le cartelle di lavoro pianificate in precedenza.


>[!BEGINSHADEBOX]

Per un video dimostrativo, consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Pianifica cartelle di lavoro](https://video.tv.adobe.com/v/3417505?quality=12&learn=on&captions=ita){target="_blank"}.

>[!ENDSHADEBOX]


## Pianificare una cartella di lavoro

Utilizzare il pulsante Pianifica nell&#39;hub di Report Builder per creare rapidamente una pianificazione in modo da poter distribuire automaticamente un file di Excel della cartella di lavoro (con estensione xlsx) a un singolo utente o a un gruppo.

1. Fai clic sul pulsante Schedule (Pianifica) nell’hub di Report Builder.

   ![Fare clic sul pulsante Pianifica per creare una pianificazione.](./assets/schedule-button.png){width="55%"}

1. Fai clic su Schedule Workbook (Pianifica cartella di lavoro) o sul pulsante in alto a sinistra per creare una nuova cartella di lavoro pianificata.

   ![Finestra Pianifica cartelle di lavoro.](./assets/schedule-workbook.png){width="55%"}

   Il riquadro di pianificazione mostra alcune informazioni predefinite sulla cartella di lavoro, ad esempio il nome e l’ultima data di modifica della cartella di lavoro.

   ![Riquadro di pianificazione.](./assets/schedule-pane.png){width="55%"}

1. (Facoltativo) Immetti un nome del file.

   Il file della cartella di lavoro viene salvato con il nome della cartella di lavoro per impostazione predefinita, ma può essere modificato. Se la stessa cartella di lavoro viene inviata a più tipi di pubblico e desideri assegnargli un nome più descrittivo per un determinato pubblico, puoi modificare il nome.

1. (Facoltativo) Seleziona **Append time-stamp to file name** (Aggiungi marca temporale al nome del file).

   Puoi aggiungere una marca temporale al nome del file per identificare la data di aggiornamento della cartella di lavoro. È utile per vedere rapidamente quale versione di una cartella di lavoro è stata inviata in una data specifica. **Filename preview** (Anteprima nome file) mostra come verrà visualizzato il nome del file della cartella di lavoro nell’e-mail quando la cartella di lavoro viene distribuita. Il formato della marca temporale è AAAA-MM-GG.

1. (Facoltativo) Seleziona **.zip compression** (compressione .zip) per comprimere il file e proteggerlo tramite password.

   Selezionando questa opzione, viene richiesto di immettere una password per aprire il file. È utile se hai dei dubbi sulla sicurezza dei dati e desideri proteggere la cartella di lavoro tramite password. Per proteggere il file con una password è necessario selezionare **.zip compression** (compressione .zip). La password deve contenere almeno 8 caratteri, un numero e un carattere speciale.

   ![Immettere una password nel campo Proteggi cartella di lavoro tramite password.](./assets/zip-compression.png){width="55%"}

1. Inserisci i destinatari in **Recipients** (Destinatari). Puoi inserire il nome di una persona riconosciuta nell’organizzazione oppure l’indirizzo e-mail di una persona interna o esterna all’organizzazione.

1. Inserisci l’oggetto dell’e-mail in **Subject** (Oggetto) e una descrizione per i destinatari. L’oggetto viene impostato automaticamente sul nome del file della cartella di lavoro, ma puoi modificarlo se necessario. Puoi aggiungere i dettagli nella sezione della descrizione.

   ![Immettere un oggetto nel campo Oggetto.](./assets/recipients-subject.png){width="55%"}

1. Configura le opzioni di pianificazione per impostare la data e l’ora in cui desideri inviare la cartella di lavoro ai destinatari tramite e-mail.

   Scegli le date e ore di inizio e fine e l’arco temporale. Può essere la data odierna o una data futura.

   Scegli la frequenza in **Frequency** (Frequenza) dal menu a discesa. Puoi impostare la frequenza in modo che sia ogni ora, giorno, settimana, mese o anno in un giorno specifico. Ad esempio, puoi impostare una pianificazione per l’invio della cartella di lavoro la prima domenica notte del mese in modo che i destinatari abbiano l’e-mail nella casella in entrata il lunedì mattina.

   ![Selezionare la frequenza di pianificazione del report.](./assets/frequency.png){width="55%"}

1. Dopo aver impostato la pianificazione, fai clic su **Send on schedule** (Invia secondo programma).

   ![Fai clic su Invia secondo programma.](./assets/send-on-schedule.png){width="55%"}

   Nella parte inferiore dell&#39;hub Report Builder viene visualizzato un avviso popup di conferma e la cartella di lavoro pianificata è elencata nella scheda Cartelle di lavoro.

   ![Avviso di conferma](./assets/confirmation-toast.png){width="55%"}

## Pianificare una cartella di lavoro convertita {#converted}

1. Pianifica una cartella di lavoro legacy [convertita](/help/analyze/report-builder/convert-workbooks.md).

   Viene visualizzato un pop-up in cui viene richiesto se si desidera utilizzare la metada di pianificazione della cartella di lavoro precedente per creare una nuova attività pianificata.

1. Se si seleziona **[!UICONTROL Use]**, Report Builder inserisce automaticamente le informazioni di pianificazione legacy.

1. Verifica che queste informazioni siano corrette e pianificate.

1. Se si desidera inviare la cartella di lavoro in base a una pianificazione diversa, pianificare un&#39;attività pianificata completamente aggiornata.


## Inviare la cartella di lavoro una sola volta

Puoi anche inviare la cartella di lavoro una sola volta.

1. Deseleziona **Show scheduling options** (Mostra opzioni di pianificazione)

   ![Fare clic su Deseleziona Mostra opzioni di pianificazione per inviare una cartella di lavoro una sola volta.](./assets/send-now.png){width="40%"}

1. Fai clic su **Send Now** (Invia subito).

## Gestire le cartelle di lavoro pianificate

Per informazioni sulla gestione delle cartelle di lavoro già pianificate, vedere [Gestione delle cartelle di lavoro pianificate](/help/analyze/report-builder/manage-schedules-reportbuilder.md).
