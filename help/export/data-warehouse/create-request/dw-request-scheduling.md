---
description: Passaggi che descrivono come creare una richiesta Data Warehouse.
title: Configurare una destinazione di rapporto per una richiesta Data Warehouse
feature: Data Warehouse
source-git-commit: 3b116cb8d0d3f3eb86b512d712f37b29876f2b22
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 11%

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
   | [!UICONTROL **Invia rapporto ora**] | Invia il report come report occasionale. Quando questa opzione è selezionata, tutte le opzioni di pianificazione sono nascoste. |
   | [!UICONTROL **Pianifica per un momento successivo**] | Fornisce opzioni per la pianificazione della consegna dei rapporti. Tutte le opzioni sono descritte di seguito. |
   | [!UICONTROL **Frequenza report**] | La frequenza con cui vengono consegnati i rapporti. <p>Sono disponibili le seguenti opzioni:</p><ul><li>Oraria</li><p>[!UICONTROL **Ogni ora**] è disponibile solo quando [!UICONTROL **Intervalli di date**] opzione sul [!UICONTROL **Impostazioni generali**] è impostato su [!UICONTROL **Ultima ora**].</p><li>Giornaliero</li><li>Settimanale</li><li>Mensile</li><li>Annuale</li></ul><p>Vengono visualizzate opzioni aggiuntive a seconda della frequenza selezionata.</p> |
   | [!UICONTROL **A partire dal**] | La data in cui dovrebbe iniziare la nuova pianificazione. |
   | [!UICONTROL **Ora del giorno**] | Ora del giorno in cui il report deve essere inviato. |
   | [!UICONTROL **Opzioni di consegna finale**] | Scegli quando terminare le consegne programmate. Puoi scegliere di non terminare mai, di terminare dopo un numero specifico di occorrenze o di terminare in una data specifica. |

   {style="table-layout:auto"}

1. Continua a configurare la richiesta Data Warehouse in [!UICONTROL **E-mail di notifica**] scheda. Per ulteriori informazioni, consulta [Configurare un messaggio e-mail di notifica per una richiesta Data Warehouse](/help/export/data-warehouse/create-request/dw-request-email.md).

