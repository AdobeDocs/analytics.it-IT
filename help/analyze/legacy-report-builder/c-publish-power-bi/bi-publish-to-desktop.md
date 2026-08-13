---
description: Spiega come richiamare in Power BI Desktop le risorse pubblicate in Power Builder
title: Richiamare in Power BI Desktop le risorse pubblicate
feature: Report Builder
role: User, Admin
exl-id: ce6020df-caf4-4cd2-8086-4357309e5bbb
TQID: https://experienceleague.adobe.com/fS1xnUciNh8LdPw2ENYMJTDGLqo3C8u4lu39X-GYuZE
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 196
ht-degree: 100%

---

# Richiamare in Power BI Desktop le risorse pubblicate

{{legacy-arb}}

Spiega come richiamare in Power BI Desktop le risorse pubblicate in Power Builder

## Prerequisiti {#section_BDFDAE1E300B429FB6EBCB21AD1383A0}

* È necessario che sia installata la versione più recente di Power BI Desktop (versione di aprile 2017)
* Questa procedura presuppone che siano già state pubblicate le tabelle formattate o le richieste Report Builder inviate nel servizio di Power BI.

## Processo {#section_CB03E6E1B066457EA0F6FC08FFF5EFDD}

Nell’aggiornamento di aprile 2017 di Power BI Desktop, Microsoft ha introdotto la possibilità di connettersi ai set di dati nel servizio Power BI. Questa funzione consente di creare nuovi rapporti di set di dati esistenti già pubblicati nel cloud. Puoi sfruttare questa funzione per collaborare meglio e ridurre le attività duplicate all’interno del team.

1. In Power BI Desktop, vai a **[!UICONTROL File]** > **[!UICONTROL Options and settings]** > **[!UICONTROL Options]** > **[!UICONTROL Preview features.]**
1. Abilita **[!UICONTROL Power BI Service Live Connection]** e fai clic su **[!UICONTROL OK]**. ![Fai clic su Connessione live al servizio Power BI e quindi su OK. ](assets/bi-preview-features.png)

1. Riavvia Power BI Desktop.
1. Dopo aver riavviato il desktop, passa a **[!UICONTROL Home]** > **[!UICONTROL Get Data]** > **[!UICONTROL More...]**.
1. Cerca e seleziona **[!UICONTROL Power BI service]**.
1. In **[!UICONTROL Microsoft Power BI service]** > **[!UICONTROL My Workspace]**, seleziona il set di dati precedentemente pubblicato da Report Builder.

Per ulteriori informazioni, consulta i [post del blog di Microsoft](https://powerbi.microsoft.com/en-us/blog/connecting-to-datasets-in-the-power-bi-service-from-desktop/).
