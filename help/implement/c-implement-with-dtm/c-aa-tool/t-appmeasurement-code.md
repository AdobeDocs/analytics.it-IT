---
description: Inserisci il codice appmeasurement quando distribuisci manualmente Gestione tag dinamica in Adobe Analytics.
keywords: Gestione tag dinamica; account collegati; collegare account; modifica del codice; appmeasurement; codice di misurazione
seo-description: Inserisci il codice appmeasurement quando distribuisci manualmente Gestione tag dinamica in Adobe Analytics.
seo-title: Inserisci codice appmeasurement principale
solution: Marketing Cloud, Analytics, Target, Gestione tag dinamica
title: Inserisci codice appmeasurement principale
uuid: 3 f 83 fbb 1-3 ed 45-888 e -0 a 5-4 a 183 aac 1 a 90
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Inserisci codice appmeasurement principale

Inserisci il codice appmeasurement quando distribuisci manualmente Gestione tag dinamica in Adobe Analytics.

1. On the [!DNL Adobe Analytics] tool page, expand the **[!UICONTROL General]** section, then click **[!UICONTROL Open Editor]**.
1. Unzip the [!DNL AppMeasurement_JavaScript*.zip] file you downloaded in [deploy Adobe Analytics](../../../implement/c-implement-with-dtm/t-analytics-deploy.md#task_3A00639CADF14C9C844F962222077E4E).

   Se si sceglie libreria personalizzata, quando si apre la finestra è già presente la versione del codice più recente. Non è necessario scaricare il file ZIP dall'Admin Console.
1. Open [!DNL AppMeasurement.js] in a text editor.
1. Copy and paste the contents into the **[!UICONTROL Edit Code]** window.

   ![](assets/edit-code.png)

1. Adobe recommends adding the following code above the *`Do Not Alter Anything Below This Line`*:

   ```
   var s_account="INSERT-RSID-HERE"
   var s=s_gi(s_account)
   ```

   >[!IMPORTANT]
   >
   >If you add this code, it is recommended that you also select the **[!UICONTROL Set report suites using custom code below]** checkbox in the overall library settings.

1. Fai clic su **[!UICONTROL Save and Close]**.

   Se usate il modulo File multimediali, Integrate Module (Modulo) o i plug-in di implementazione, potete copiarli anche nella sezione del codice. Il codice gestito in Gestione tag dinamica può essere configurato esattamente come il file javascript in un'implementazione tipica.

