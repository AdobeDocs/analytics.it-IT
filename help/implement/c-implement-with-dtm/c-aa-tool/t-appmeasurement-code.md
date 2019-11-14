---
description: Inserisci il codice AppMeasurement quando distribuisci manualmente Gestione tag dinamica in Adobe Analytics.
keywords: Dynamic Tag Management;linked accounts;linking accounts;edit code;appmeasurement;appmeasurement code
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: Inserire codice AppMeasurement principale
uuid: 3f83fbb1-3ed5-4e45-888a-0a183aac1a90
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Inserire codice AppMeasurement principale

Inserisci il codice AppMeasurement quando distribuisci manualmente Gestione tag dinamica in Adobe Analytics.

1. Nella pagina [!DNL Adobe Analytics] degli strumenti, espandete la **[!UICONTROL General]** sezione e fate clic su **[!UICONTROL Open Editor]**.
1. Decomprimete il [!DNL AppMeasurement_JavaScript*.zip] file scaricato nella [distribuzione di Adobe Analytics](/help/implement/c-implement-with-dtm/t-analytics-deploy.md).

   Se scegliete una libreria personalizzata, quando aprite la finestra sarà già presente la versione di codice più recente. Non è necessario scaricare il file ZIP da Admin Console.
1. Aprite [!DNL AppMeasurement.js] in un editor di testo.
1. Copiate e incollate i contenuti nella **[!UICONTROL Edit Code]** finestra.

   ![](assets/edit-code.png)

1. Adobe consiglia di aggiungere il seguente codice sopra *`Do Not Alter Anything Below This Line`*:

   ```
   var s_account="INSERT-RSID-HERE"
   var s=s_gi(s_account)
   ```

   >[!IMPORTANT]
   >
   >Se aggiungete questo codice, è consigliabile selezionare anche la **[!UICONTROL Set report suites using custom code below]** casella di controllo nelle impostazioni generali della libreria.

1. Fai clic su **[!UICONTROL Save and Close]**.

   Se utilizzate i plug-in per modulo multimediale, modulo integrato o implementazione, potete copiarli anche nella sezione codice. Il codice gestito in Gestione tag dinamica può essere configurato esattamente come il file JavaScript in un'implementazione tipica.

