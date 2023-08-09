---
description: Spiega come estrarre in Power BI Desktop le risorse pubblicate dal Report Builder
title: Estrarre risorse pubblicate in Power BI Desktop
feature: Report Builder
role: User, Admin
exl-id: ce6020df-caf4-4cd2-8086-4357309e5bbb
source-git-commit: fb39f906d6c08713e4dc8211c917b2942502868e
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 8%

---

# Estrarre risorse pubblicate in Power BI Desktop

Spiega come estrarre in Power BI Desktop le risorse pubblicate dal Report Builder

## Prerequisiti {#section_BDFDAE1E300B429FB6EBCB21AD1383A0}

* È necessario che sia installata la versione più recente di Power BI Desktop (versione di aprile 2017)
* Questa procedura presuppone che siano già state pubblicate le tabelle o le richieste formattate per il Report Builder inviate al servizio di Power BI.

## Processo {#section_CB03E6E1B066457EA0F6FC08FFF5EFDD}

Nell’aggiornamento di aprile 2017 di Power BI Desktop, Microsoft ha rilasciato la possibilità di connettersi ai set di dati nel servizio Power BI. Questa funzione consente di creare nuovi rapporti di set di dati esistenti già pubblicati nel cloud. Puoi sfruttare questa funzione per collaborare meglio e ridurre le attività duplicate all’interno del team.

1. In Power BI Desktop, vai a **[!UICONTROL File]** > **[!UICONTROL Options and settings]** > **[!UICONTROL Options]** > **[!UICONTROL Preview features.]**
1. Abilita **[!UICONTROL Power BI Service Live Connection]** e fai clic su **[!UICONTROL OK]**. ![Fare clic su Power BI Service Live Connection e quindi su OK. ](assets/bi-preview-features.png)

1. Riavviare Power BI Desktop.
1. Dopo aver riavviato il desktop, passare a **[!UICONTROL Home]** > **[!UICONTROL Get Data]** > **[!UICONTROL More...]**.
1. Cerca e seleziona **[!UICONTROL Power BI service]**.
1. Sotto **[!UICONTROL Microsoft Power BI service]** > **[!UICONTROL My Workspace]**, seleziona il set di dati precedentemente pubblicato dal Report Builder.

Per ulteriori informazioni, consulta [Post di blog di Microsoft](https://powerbi.microsoft.com/en-us/blog/connecting-to-datasets-in-the-power-bi-service-from-desktop/).
