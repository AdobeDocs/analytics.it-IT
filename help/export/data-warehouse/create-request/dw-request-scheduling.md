---
description: Passaggi che descrivono come creare una richiesta di Data Warehouse.
title: Configurare una destinazione di rapporto per una richiesta di Data Warehouse
feature: Data Warehouse
exl-id: e5f8acaa-156f-41fb-a0fc-bc5475f1f3b7
source-git-commit: ca84a5f807545d7196e2e0e90d3209c32d3fd789
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 32%

---

# Configurare le opzioni di pianificazione per una richiesta Data Warehouse

Durante la creazione di una richiesta di Data Warehouse, sono disponibili varie opzioni di configurazione. Le informazioni seguenti descrivono come configurare le opzioni di pianificazione per la richiesta.

Per informazioni su come iniziare a creare una richiesta, nonché collegamenti ad altre importanti opzioni di configurazione, consulta [Creare una richiesta di Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

Per configurare le opzioni di pianificazione per una richiesta Data Warehouse:

1. Se non l’hai ancora fatto, inizia a creare una richiesta in Adobe Analytics selezionando **[!UICONTROL Tools]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Aggiungi**].

   Per ulteriori dettagli, consulta [Creare una richiesta di Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Nella pagina Nuova richiesta Data Warehouse selezionare la scheda [!UICONTROL **Opzioni di pianificazione**].

   ![Scheda destinazione report](assets/dw-scheduling-options.png) <!-- update screenshot -->

1. Completa i campi seguenti:

   | Opzione | Funzione |
   |---------|----------|
   | [!UICONTROL **Invia rapporto ora**] | Invia il report come report occasionale. Quando questa opzione è selezionata, tutte le opzioni di pianificazione sono nascoste. |
   | [!UICONTROL **Pianificazione per dopo**] | Fornisce opzioni per la pianificazione della consegna dei rapporti. Tutte le opzioni sono descritte di seguito. |
   | [!UICONTROL **Frequenza report**] | La frequenza con cui vengono consegnati i rapporti. <p>Sono disponibili le seguenti opzioni:</p><ul><li>Oraria</li><p>[!UICONTROL **Oraria**] è disponibile solo quando l&#39;opzione [!UICONTROL **Intervalli di date**] nella scheda [!UICONTROL **Impostazioni generali**] è impostata su [!UICONTROL **Ultima ora**].</p><li>Giornaliero</li><li>Settimanale</li><li>Mensile</li><li>Annuale</li></ul><p>Vengono visualizzate opzioni aggiuntive a seconda della frequenza selezionata.</p> |
   | [!UICONTROL **A partire da**] | La data in cui dovrebbe iniziare la nuova pianificazione. |
   | [!UICONTROL **Ora del giorno**] | Ora del giorno in cui il report deve essere inviato. |
   | [!UICONTROL **Opzioni di fine consegna**] | Scegli quando terminare le consegne programmate. Puoi scegliere di non terminare mai, di terminare dopo un numero specifico di occorrenze o di terminare in una data specifica. |

   {style="table-layout:auto"}

1. Continua a configurare la tua richiesta Data Warehouse nella scheda [!UICONTROL **E-mail di notifica**]. Per ulteriori informazioni, vedere [Configurare un&#39;e-mail di notifica per una richiesta Data Warehouse](/help/export/data-warehouse/create-request/dw-request-email.md).
