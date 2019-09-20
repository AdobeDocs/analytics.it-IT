---
description: Crea uno strumento Adobe Analytics per la distribuzione tramite Gestione tag dinamica. Questa procedura descrive un'implementazione manuale (legacy).
keywords: Dynamic Tag Management
seo-description: Crea uno strumento Adobe Analytics per la distribuzione tramite Gestione tag dinamica. Questa procedura descrive un'implementazione manuale (legacy).
seo-title: Implementazione manuale di Adobe Analytics (legacy)
solution: Experience Cloud,Analytics,Target,Gestione tag dinamica
title: Implementazione manuale di Adobe Analytics (legacy)
uuid: d3ad2035-393d-4a77-81f6-e749ee717c09
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Implementazione manuale di Adobe Analytics (legacy)

Crea uno strumento Adobe Analytics per la distribuzione tramite [!UICONTROL Dynamic Tag Management]. Questa procedura descrive un'implementazione manuale (legacy).

Per informazioni sulla gestione automatica dell'implementazione, consultate [Aggiunta di Adobe Analytics Tool](../../implement/c-implement-with-dtm/c-aa-tool/analytics-dtm.md#concept_FBA6679A0B79490F8296437F11E5E4F8).

Se si desidera modificare la configurazione manuale in automatico, modificare uno strumento e fare clic su **[!UICONTROL Enable Automatic Configuration]**.

1. Scarica il codice di misura di Analytics:
   1. In Analytics, fai clic su **[!UICONTROL Admin]** &gt; **[!UICONTROL Code Manager]**.
   1. Fate clic **[!UICONTROL JavaScript (new)]** per scaricare localmente il codice.
1. In [!UICONTROL Dynamic Tag Management], [create una proprietà](../../implement/c-implement-with-dtm/t-create-web-property.md#task_960467FBB7A54499AC228CB3AA3C4123)Web.

   ![](assets/dtm-property.png)

   Dopo aver creato la proprietà Web, questa è disponibile per la modifica nella [!UICONTROL Web Properties] scheda del [!UICONTROL Dashboard]. L'attivazione della proprietà Web non è richiesta.

1. Aggiungere uno strumento Analytics alla proprietà:
   1. Nella **[!UICONTROL Web Properties]** scheda fare clic sulla proprietà.
   1. Nella **[!UICONTROL Overview]** scheda fare clic su **[!UICONTROL Add a Tool]**.
   1. Dal **[!UICONTROL Tool Type]** menu, selezionare **[!UICONTROL Adobe Analytics]**.

      ![](assets/dtm-add-analytics-tool.png)

   1. Configura i campi seguenti:

      | Elemento | Descrizione |
      |---|---|
      | Tipo di strumento | La soluzione Experience Cloud, come Analytics, Target, Social e così via. |
      | Nome dello strumento | Nome dello strumento. Questo nome viene visualizzato sulla [!UICONTROL Overview] scheda sotto [!UICONTROL Installed Tools]. |
      | ID account produzione | Un numero per l'account di produzione per la raccolta dei dati. Gestione tag dinamica installa automaticamente l'account corretto nell'ambiente di produzione e di staging. |
      | ID account di gestione temporanea | Numero utilizzato nell'ambiente di sviluppo o di test. Un account di verifica mantiene i dati di test separati dalla produzione. |

1. Fai clic su **[!UICONTROL Create Tool]**.

   Lo strumento installato viene visualizzato nella [!UICONTROL Overview] scheda.

1. Per configurare il codice, fate clic su **[!UICONTROL Settings]**![](assets/settings_gear.png).

   Come minimo, fai clic su **[!UICONTROL Cookies]** e configura il server di tracciamento e il server di tracciamento SSL.

1. Fai clic **[!UICONTROL General]** e [inserisci il codice](../../implement/c-implement-with-dtm/c-aa-tool/t-appmeasurement-code.md#task_068D72664B2743359A64ADB8692D3658)AppMeasurement principale.
1. Definire una regola [di caricamento](../../implement/c-implement-with-dtm/c-rules/t-rules-create.md#task_B7FB5ED415AF430C952265AC2835C0DB) pagina per raccogliere [!DNL Analytics]i dati.

   È ora possibile definire regole per la raccolta dei dati di analisi. Potrebbe essere necessario definire prima alcuni elementi di dati. Gli elementi dati consentono di estrarre dati dalla pagina che è possibile utilizzare per configurare la regola. Per iniziare, puoi definire una regola di caricamento della pagina che non ha condizioni per raccogliere [!DNL Analytics] dati su ciascuna pagina.
1. [Aggiungere l'intestazione e il codice](../../implement/c-implement-with-dtm/c-headers-footers/t-header-footer-code.md#task_43C8DD699A514638B0620775C06423E5) piè di pagina nella scheda Incorpora.

   Per lo staging, potete lasciare l'opzione di hosting Amazon predefinita. Potete modificarlo se necessario prima dell’implementazione della produzione.
1. (Facoltativo) Fai clic **[!UICONTROL Settings]** ![](assets/settings_gear.png) sulla scheda Opzioni e configura il codice Adobe Analytics.

   >[!NOTE]
   >
   >Le impostazioni della [!UICONTROL Adobe Analytics] pagina (Generale, Cookie e così via) sostituiscono le impostazioni presenti nella `s_code`. Se queste impostazioni sono presenti nel vostro `s_code`, non è necessario ripeterle qui.

