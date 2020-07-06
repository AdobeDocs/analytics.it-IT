---
description: Impostate le azioni che desiderate vengano attivate dalla condizione.
keywords: Dynamic Tag Management;rule;create rule;new rule;javascript/third party tags;set up actions for condition;add new script;non-sequential javascript;sequential javascript;non-sequential html
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: Configurare le azioni per la condizione da attivare
uuid: 2e892f0b-7261-41ee-b849-6e3054a38de0
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 7%

---


# Configurare le azioni per la condizione da attivare

Impostate le azioni che desiderate vengano attivate dalla condizione.

Dopo aver impostato la condizione, è necessario impostare le azioni che si desidera che venga attivata dalla condizione. Tali azioni possono includere [!DNL Analytics] eventi, tag di terze parti e script personalizzati. Questo esempio descrive come impostare script o tag di terze parti.

Oltre a strumenti integrati come [!DNL Adobe Analytics] e Google  Analytics, Gestione tag dinamica può attivare qualsiasi tipo di JavaScript o inserire codice HTML nel sito, in pagine selezionate o in scenari specifici.

Ogni regola può attivare tutti gli script o le iniezioni HTML desiderati.

>[!NOTE]
>
>Poiché Gestione dinamica dei tag consente di inserire codice personalizzato nella pagina, fai attenzione a non creare vulnerabilità di scripting tra siti (XSS) (consulta la guida [](https://www.owasp.org/index.php/Cross-site_Scripting_(XSS)) OWASP per ulteriori informazioni). L&#39;utilizzo di elementi di dati all&#39;interno di uno script richiede particolare attenzione. Si supponga sempre che i valori degli elementi di dati provengano da un&#39;origine non attendibile.

**Impostazione di azioni per l&#39;attivazione della condizione**

1. Fare clic **[!UICONTROL JavaScript / Third Party Tags]** per aggiungere un nuovo script alla regola.

   ![](assets/scripts-actions.png)

1. Fai clic su **[!UICONTROL Add New Script]**.

   ![](assets/scripts-actions2.png)

1. Denominare lo script.
1. Specificate come attivare lo script e incollate il contenuto desiderato nell&#39;area di testo. ![](assets/scripts-actions3.png)

1. Fare clic **[!UICONTROL Save Code]** e lo script verrà aggiunto alla coda per la regola. ![](assets/scripts-actions4.png)

