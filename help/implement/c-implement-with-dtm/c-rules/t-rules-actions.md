---
description: Impostate le azioni che desiderate vengano attivate dalla condizione.
keywords: Gestione tag dinamica;regola;crea regola;nuova regola;javascript/tag di terze parti;imposta azioni per condizione;aggiungi nuovo script;javascript non sequenziale;javascript sequenziale;html non sequenziale
seo-description: Impostate le azioni che desiderate vengano attivate dalla condizione.
seo-title: Configurare le azioni per la condizione da attivare
solution: Experience Cloud,Analytics,Target,Gestione tag dinamica
title: Configurare le azioni per la condizione da attivare
uuid: 2e892f0b-7261-41ee-b849-6e3054a38de0
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Configurare le azioni per la condizione da attivare

Impostate le azioni che desiderate vengano attivate dalla condizione.

Dopo aver impostato la condizione, è necessario impostare le azioni che si desidera che la condizione attivi. Tali azioni possono includere [!DNL Analytics] eventi, tag di terze parti e script personalizzati. Questo esempio descrive come impostare script o tag di terze parti.

Oltre a strumenti integrati come [!DNL Adobe Analytics] e Google Analytics, Dynamic Tag Management può attivare qualsiasi tipo di JavaScript o inserire codice HTML nel sito, in pagine selezionate o in scenari specifici.

Ogni regola può attivare tutti gli script o le iniezioni HTML desiderati.

>[!NOTE]
>
>Poiché Gestione dinamica dei tag consente di inserire codice personalizzato nella pagina, fai attenzione a non creare vulnerabilità di scripting tra siti (XSS) (consulta la guida [](https://www.owasp.org/index.php/Cross-site_Scripting_(XSS)) OWASP per ulteriori informazioni). L'utilizzo di elementi di dati all'interno di uno script richiede particolare attenzione. Si supponga sempre che i valori degli elementi di dati provengano da un'origine non attendibile.

**Impostazione di azioni per l'attivazione della condizione**

1. Fare clic **[!UICONTROL JavaScript / Third Party Tags]** per aggiungere un nuovo script alla regola.

   ![](assets/scripts-actions.png)

1. Fai clic su **[!UICONTROL Add New Script]**.

   ![](assets/scripts-actions2.png)

1. Denominare lo script.
1. Specificate come attivare lo script e incollate il contenuto desiderato nell'area di testo. ![](assets/scripts-actions3.png)

1. Fare clic **[!UICONTROL Save Code]** e lo script verrà aggiunto alla coda per la regola. ![](assets/scripts-actions4.png)

