---
description: Crea uno strumento Adobe Analytics per la distribuzione tramite Gestione tag dinamica. Questa procedura descrive un'implementazione manuale (legacy).
keywords: Dynamic Tag Management
seo-description: Crea uno strumento Adobe Analytics per la distribuzione tramite Gestione tag dinamica. Questa procedura descrive un'implementazione manuale (legacy).
seo-title: Implementazione manuale di Adobe Analytics (legacy)
solution: Marketing Cloud, Analytics, Target, Gestione tag dinamica
title: Implementazione manuale di Adobe Analytics (legacy)
uuid: d 3 ad 2035-393 d -4 a 77-81 f 6-e 749 ee 717 c 09
translation-type: tm+mt
source-git-commit: 6250335d05c8e7799802fce26192896a7a6598fe

---


# Implementazione manuale di Adobe Analytics (legacy)

Create an Adobe Analytics tool for deployment using [!UICONTROL Dynamic Tag Management]. Questa procedura descrive un'implementazione manuale (legacy).

For information about automatic implementation management, see [Add Adobe Analytics Tool](../../implement/c-implement-with-dtm/c-aa-tool/analytics-dtm.md#concept_FBA6679A0B79490F8296437F11E5E4F8).

If you want to change a manual configuration to automatic, edit a tool and click **[!UICONTROL Enable Automatic Configuration]**.

1. Scarica il codice di misurazione di Analytics:
   1. In Analytics, click **[!UICONTROL Admin]** &gt; **[!UICONTROL Code Manager]**.
   1. Click **[!UICONTROL JavaScript (new)]** to download the code locally.
1. In [!UICONTROL Dynamic Tag Management], [create a web property](../../implement/c-implement-with-dtm/t-create-web-property.md#task_960467FBB7A54499AC228CB3AA3C4123).

   ![](assets/dtm-property.png)

   After you create the web property, it is available for editing on the [!UICONTROL Web Properties] tab on the [!UICONTROL Dashboard]. L'attivazione della proprietà Web non è necessaria.

1. Aggiungi uno strumento Analytics alla proprietà:
   1. On the **[!UICONTROL Web Properties]** tab, click the property.
   1. On the **[!UICONTROL Overview]** tab, click **[!UICONTROL Add a Tool]**.
   1. From the **[!UICONTROL Tool Type]** menu, select **[!UICONTROL Adobe Analytics]**.

      ![](assets/dtm-add-analytics-tool.png)

   1. Configura i campi seguenti:

      | Elemento | Descrizione |
      |---|---|
      | Tipo di strumento | La soluzione Experience Cloud, come Analytics, Target, Social e così via. |
      | Nome dello strumento | Nome per questo strumento. This name displays on the [!UICONTROL Overview] tab under [!UICONTROL Installed Tools]. |
      | ID account produzione | Un numero per l'account di produzione per la raccolta dati. Gestione tag dinamica installa automaticamente l'account corretto nell'ambiente di produzione e di staging. |
      | ID account di verifica | Numero utilizzato nell'ambiente di sviluppo o di prova. Un account di verifica mantiene i dati di verifica separati dalla produzione. |

1. Fai clic su **[!UICONTROL Create Tool]**.

   The installed tool displays on the [!UICONTROL Overview] tab.

1. To configure the code, click **[!UICONTROL Settings]** ![](assets/settings_gear.png).

   At a minimum, click **[!UICONTROL Cookies]** and configure your tracking server and SSL tracking server.

1. Click **[!UICONTROL General]** and [insert the core AppMeasurement code](../../implement/c-implement-with-dtm/c-aa-tool/t-appmeasurement-code.md#task_068D72664B2743359A64ADB8692D3658).
1. Define a [page load rule](../../implement/c-implement-with-dtm/c-rules/t-rules-create.md#task_B7FB5ED415AF430C952265AC2835C0DB) to collect [!DNL Analytics]data.

   Sei pronto per definire le regole per la raccolta dei dati di analisi. Potreste decidere di definire prima alcuni elementi di dati. Gli elementi di dati consentono di estrarre dati dalla pagina che puoi utilizzare per configurare la regola. To get started, you can define a page load rule that does not have any conditions to collect [!DNL Analytics] data on each page.
1. [Aggiungere l'intestazione e il codice piè di pagina](../../implement/c-implement-with-dtm/c-headers-footers/t-header-footer-code.md#task_43C8DD699A514638B0620775C06423E5) nella scheda Incorpora.

   Per staging, potete lasciare l'opzione di hosting Amazon predefinita. Potete modificarlo, se necessario, prima dell'implementazione della produzione.
1. (Optional) Click **[!UICONTROL Settings]** ![](assets/settings_gear.png) on the Options tab, and configure the Adobe Analytics code.

   >[!NOTE]
   >
   >The settings on the [!UICONTROL Adobe Analytics] page (General, Cookies, and so on) override settings in your `s_code`. If these settings exist in your `s_code`, there is no need to reiterate them here.

