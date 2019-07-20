---
description: Spiega come estrarre risorse pubblicate da Generatore di report in Power BI Desktop
seo-description: Spiega come estrarre risorse pubblicate da Generatore di report in Power BI Desktop
seo-title: Estrai risorse pubblicate in Power BI Desktop
title: Estrai risorse pubblicate in Power BI Desktop
uuid: ef 47 d 5 c 7-31 e 0-44 fc-a 792-bc 9 d 12 bb 089 e
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Estrai risorse pubblicate in Power BI Desktop

Spiega come estrarre risorse pubblicate da Generatore di report in Power BI Desktop

## Prerequisiti {#section_BDFDAE1E300B429FB6EBCB21AD1383A0}

* È necessario disporre della versione Desktop Power BI più recente installata (versione di aprile 2017)
* Questo processo presuppone che siano già state pubblicate tabelle formattate di Generatore di report o richieste al servizio Power BI Service.

## Processo {#section_CB03E6E1B066457EA0F6FC08FFF5EFDD}

Nell'aggiornamento di aprile 2017 di Power BI Desktop, Microsoft ha rilasciato la capacità di connettersi a datasets nel servizio Power BI. Questa funzione consente di creare nuovi rapporti disattivati quelli già pubblicati nel cloud. Potete sfruttare questa funzionalità per collaborare meglio e ridurre le attività duplicate all'interno del team.

1. In Power BI Desktop, go to **[!UICONTROL File]** &gt; **[!UICONTROL Options and settings]** &gt; **[!UICONTROL Options]** &gt; **[!UICONTROL Preview features.]**
1. Enable **[!UICONTROL Power BI Service Live Connection]** and click **[!UICONTROL OK]**. ![](assets/bi-preview-features.png)

1. Riavviate Power BI Desktop.
1. Once you have restarted the desktop, go to **[!UICONTROL Home]** &gt; **[!UICONTROL Get Data]** &gt; **[!UICONTROL More...]**.
1. Search for and select **[!UICONTROL Power BI service]**.
1. Under **[!UICONTROL Microsoft Power BI service]** &gt; **[!UICONTROL My Workspace]**, select the dataset that you had previously published from Report Builder.

For more information, see this [Microsoft blog post](https://powerbi.microsoft.com/en-us/blog/connecting-to-datasets-in-the-power-bi-service-from-desktop/).
