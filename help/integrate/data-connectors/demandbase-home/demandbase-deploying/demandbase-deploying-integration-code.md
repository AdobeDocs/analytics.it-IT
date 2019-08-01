---
description: Dopo aver completato la procedura guidata di integrazione, dovete distribuire il codice di integrazione nel codice di distribuzione di Adobe Analytics (s_ code).
seo-description: Dopo aver completato la procedura guidata di integrazione, dovete distribuire il codice di integrazione nel codice di distribuzione di Adobe Analytics (s_ code).
seo-title: Distribuzione del codice di integrazione
title: Distribuzione del codice di integrazione
uuid: b 3 fbda 0 b -4 ed 3-4967-84 ee -6 c 66564606 e 7
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Deploying the Integration Code{#deploying-the-integration-code}

Dopo aver completato la procedura guidata di integrazione, dovete distribuire il codice di integrazione nel codice di distribuzione di Adobe Analytics (s_ code).

>[!NOTE]
>
>Se hai usato Adobe tagmanager o Gestione tag dinamica per implementare Adobe Analytics, puoi aggiungere facilmente il codice di integrazione utilizzando uno di questi strumenti.

1. Go to the **[!UICONTROL Support]** tab and download and save the `integration code v2_0_1` resource from the Resources area of the integration.

1. If applicable, make any necessary modifications to the code For more information, see [Modifying the Integration Code](../../demandbase-home/demandbase-deploying/demandbase-deploying-integration-code.md#concept-2e9e56282c9940d78e879aa45f70d855).
1. Se non è già presente nel codice di distribuzione Adobe Analytics, includete il modulo Integra. For more information, see [Including the Integrate Module](../../demandbase-home/demandbase-deploying/demandbase-including-integrate-module.md#concept-2cc81dff010a4da89b097a59476f8b6e).
1. Distribuite il codice utilizzando uno dei seguenti metodi:

   * Utilizza Adobe tagmanager o Gestione tag dinamica per aggiungere il codice.
   * In alternativa, distribuite il codice alla risorsa aziendale responsabile dell'aggiornamento del codice di distribuzione Adobe Analytics.

>[!IMPORTANT]
>
>Assicuratevi di testare la distribuzione per questa integrazione in un ambiente di sviluppo/staging prima di distribuirla in un ambiente di produzione.

