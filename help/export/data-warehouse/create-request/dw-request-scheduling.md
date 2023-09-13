---
description: Passaggi che descrivono come creare una richiesta Data Warehouse.
title: Configurare una destinazione di rapporto per una richiesta Data Warehouse
feature: Data Warehouse
source-git-commit: 0abf0c76f38b481c0b72d113fe49e0da03ddd8cd
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 9%

---

# Configurare le opzioni di pianificazione per una richiesta Data Warehouse

>[!AVAILABILITY]
>
>Alcune delle funzioni di Data Warehouse descritte in questo articolo (e in altri articoli di Data Warehouse presenti in questa sezione) sono disponibili solo nella fase di test limitato del rilascio e potrebbero non essere ancora disponibili nel tuo ambiente.
>
>Per informazioni sulle funzioni non ancora disponibili per tutti i clienti e sulle tempistiche di rilascio, vedi la [note sulla versione](/help/release-notes/latest.md).
>
>Questa nota verrà rimossa non appena la funzionalità sarà disponibile a livello generale. Per informazioni sul processo di rilascio di Analytics, consulta [Rilascio delle funzioni di Adobe Analytics](/help/release-notes/releases.md).

Durante la creazione di una richiesta Data Warehouse sono disponibili varie opzioni di configurazione. Le informazioni seguenti descrivono come configurare le opzioni di pianificazione per la richiesta.

Per informazioni su come iniziare a creare una richiesta, nonché collegamenti ad altre importanti opzioni di configurazione, vedi [Creare una richiesta Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

Per configurare le opzioni di pianificazione per una richiesta Data Warehouse:

1. Inizia a creare una richiesta in Adobe Analytics selezionando **[!UICONTROL Tools]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Aggiungi**].

   Per ulteriori dettagli, vedi [Creare una richiesta Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Nella pagina Nuova richiesta Data Warehouse, seleziona la [!UICONTROL **Opzioni di pianificazione**] scheda.

   ![Scheda Destinazione rapporto](assets/dw-scheduling-options.png) <!-- update screenshot -->

1. Completa i campi seguenti:

   | Opzione | Funzione |
   |---------|----------|
   | Invia rapporto ora | Invia il report come report occasionale. Quando questa opzione è selezionata, tutte le opzioni di pianificazione sono nascoste. |
   | Pianifica per un momento successivo | Fornisce opzioni per la pianificazione della consegna dei rapporti. Tutte le opzioni sono descritte di seguito. |
   | Frequenza report | La frequenza con cui vengono consegnati i rapporti. <p>Sono disponibili le seguenti opzioni:</p><ul><li>Oraria</li><p>[!UICONTROL **Ogni ora**] è disponibile solo quando [!UICONTROL **Intervalli di date**] opzione sul [!UICONTROL **Impostazioni generali**] è impostato su [!UICONTROL **Ultima ora**].</p><li>Giornaliero</li><li>Settimanale</li><li>Mensile</li><li>Annuale</li></ul>  <!-- Is this valid? Was in the old docs: "To schedule Data Warehouse requests for Daily, Weekly, Monthly, or Yearly, make sure *Preset* is correctly selected" --> |
   | Ricorrenza mensile | L’intervallo tra i mesi in cui viene inviato il rapporto. |
   | Giorno del mese | La data ogni mese in cui viene inviato il rapporto.<p>Quando questa opzione è disponibile, il [!UICONTROL **Settimana del mese**] e [!UICONTROL **Giorno della settimana**] le opzioni non lo sono. Seleziona la [!UICONTROL **Formato alternativo**] per passare da un pulsante all&#39;altro. </p> |
   | Settimana del mese | La settimana di ogni mese in cui il rapporto deve essere inviato. <p>Sono disponibili le seguenti opzioni:</p><ul><li>Primo</li><li>Secondi</li><li>Terzo</li><li>Quarto</li><p>Invia il rapporto alla 4a settimana, anche nei mesi con 5 settimane. Scegli [!UICONTROL **Ultimo**] se desideri che il rapporto venga inviato l’ultima settimana di ogni mese.</p><li>Last (Ultimo)</li></ul><p>Quando questa opzione è disponibile, il [!UICONTROL **Giorno del mese**] L&#39;opzione non è. Seleziona la [!UICONTROL **Formato alternativo**] per passare da un pulsante all&#39;altro. </p> |
   | Giorno della settimana | Il giorno della settimana in cui il report deve essere inviato. <p>Quando questa opzione è disponibile, il [!UICONTROL **Giorno del mese**] L&#39;opzione non è. Seleziona la [!UICONTROL **Formato alternativo**] per passare da un pulsante all&#39;altro. </p> |
   | A partire dal | La data in cui dovrebbe iniziare la nuova pianificazione. |
   | Ora del giorno | Ora del giorno in cui il report deve essere inviato. |
   | Opzioni di consegna finale | Scegli quando terminare le consegne programmate. Puoi scegliere di non terminare mai, di terminare dopo un numero specifico di occorrenze o di terminare in una data specifica. |

   {style="table-layout:auto"}

1. Continua a configurare la richiesta Data Warehouse in [!UICONTROL **E-mail di notifica**] scheda. Per ulteriori informazioni, consulta [Configurare un messaggio e-mail di notifica per una richiesta Data Warehouse](/help/export/data-warehouse/create-request/dw-request-email.md).

