---
description: Passaggi che descrivono come creare una richiesta Data Warehouse.
title: Configurare una destinazione di rapporto per una richiesta Data Warehouse
feature: Data Warehouse
exl-id: e5f8acaa-156f-41fb-a0fc-bc5475f1f3b7
source-git-commit: 1bd46f104c5ebcca78d624b49c56b2992c3d62cb
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 5%

---

# Configurare le opzioni di pianificazione per una richiesta Data Warehouse

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
