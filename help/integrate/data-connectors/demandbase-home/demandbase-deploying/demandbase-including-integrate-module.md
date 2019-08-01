---
description: Il codice di integrazione richiede che il modulo Integrazione esista nella vostra distribuzione Adobe Analytics.
seo-description: Il codice di integrazione richiede che il modulo Integrazione esista nella vostra distribuzione Adobe Analytics.
seo-title: Inclusione del modulo Integra
title: Inclusione del modulo Integra
uuid: e 574 f 3 db -49 fa -4 f 72-bbcf-fd 98540 d 3198
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Including the Integrate Module{#including-the-integrate-module}

Il codice di integrazione richiede che il modulo Integrazione esista nella vostra distribuzione Adobe Analytics.

Se non disponete già del modulo Integra come parte della distribuzione, completate i passaggi seguenti in base al tipo di implementazione disponibile.

## For AppMeasurement v1.0+ {#section-f28d090bf2404cabaae34cd9c66fc575}

1. Unzip the AppMeasurement zip file that you downloaded from **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL CodeManager]**.

1. Open the file named [!DNL AppMeasurement_Module_Integrate.js].
1. Copy and paste the contents of this file into your primary [!DNL AppMeasurement.js] file.

   >[!NOTE]
   >
   >Incolla immediatamente prima del commento NON MODIFICA sotto il commento LINE all'interno del file.

## For Legacy Code (H-code) {#section-bba8ad8c715e4f97883e7de3269f681a}

1. Scarica il modulo Integra dall'area «Risorse» nell'interfaccia utente Connettori dati (nella scheda Assistenza).

   ![](assets/h_code.png)

1. Copy and paste the contents of that file into your [!DNL s_code] file.

   >[!NOTE]
   >
   >Incolla immediatamente prima del commento NON MODIFICA sotto il commento LINE all'interno del file.

