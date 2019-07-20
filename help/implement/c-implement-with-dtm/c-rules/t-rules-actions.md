---
description: Configurare azioni che devono essere attivate.
keywords: Gestione tag dinamica; rule; create rule; new rule; tag javascript/third party; configurare azioni per la condizione; aggiungere un nuovo script; javascript non sequenziale; javascript sequenziale; HTML non sequenziale
seo-description: Configurare azioni che devono essere attivate.
seo-title: Configurare le azioni per la condizione da attivare
solution: Marketing Cloud, Analytics, Target, Gestione tag dinamica
title: Configurare le azioni per la condizione da attivare
uuid: 2 e 892 f 0 b -7261-41 ee-b 849-6 e 3054 a 38 de 0
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Configurare le azioni per la condizione da attivare

Configurare azioni che devono essere attivate.

Dopo aver configurato la condizione, è necessario configurare le azioni che si desidera attivare. These actions can include [!DNL Analytics] events, third-party tags, and custom scripts. Questo esempio descrive come configurare script o tag di terze parti.

Beyond integrated tools like [!DNL Adobe Analytics] and Google Analytics, Dynamic Tag Management can trigger any type of JavaScript or inject HTML into your site, in select pages or in specific scenarios.

Ogni regola può attivare tutti gli script o le integrazioni HTML desiderate.

>[!NOTE]
>
>Because DTM allows you to inject custom code into your page, please take care not to create cross-site scripting (XSS) vulnerabilities (see [OWASP’s guide](https://www.owasp.org/index.php/Cross-site_Scripting_(XSS)) for more info). L'uso di elementi di dati all'interno di uno script richiede particolare attenzione. È sempre possibile che i valori degli elementi dati vengano tratti da una fonte non affidabile.

**Impostazione delle azioni per la condizione da attivare**

1. Click **[!UICONTROL JavaScript / Third Party Tags]** to add a new script to your rule.

   ![](assets/scripts-actions.png)

1. Fai clic su **[!UICONTROL Add New Script]**.

   ![](assets/scripts-actions2.png)

1. Assegnare un nome allo script.
1. Specify how you want the script to trigger, and paste the desired content into the text area. ![](assets/scripts-actions3.png)

1. Click **[!UICONTROL Save Code]**, and the script will be added to the queue for the rule. ![](assets/scripts-actions4.png)

