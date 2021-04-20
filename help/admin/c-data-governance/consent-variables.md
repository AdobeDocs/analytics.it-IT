---
description: Variabili per la generazione di rapporti sulla privacy in Privacy dei dati.
title: Variabili per la generazione di rapporti sulla privacy
feature: Admin Tools
exl-id: 3f7980a4-d826-4554-a9a0-673fd5b79653
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 100%

---

# Variabili per la generazione di rapporti sulla privacy

Per fornire ulteriore assistenza nella gestione dei dati sulla privacy, è disponibile una serie di variabili riservate da utilizzare insieme a variabili di dati di contesto specifiche.
Tali variabili per segnalazioni relative alla privacy forniscono un’infrastruttura di facile utilizzo per l’acquisizione dello stato di privacy su ogni hit di analisi.

## Variabili

* Gestione del consenso Opt-Out
   * Variabile riservata: List Prop
   * Tipo: stringa delimitata da virgole
   * Contiene:
      * `contextData.['cm.ssf']=1` visualizzato come SSF
      * `contextData.['opt.dmp']=N` visualizzato come DMP
      * `contextData.['opt.sell']=N` visualizzato come SELL

* Gestione del consenso Opt-in
   * Variabile riservata: List Prop
   * Tipo: stringa delimitata da virgole
   * Contiene:
      * `contextData.['opt.dmp']=Y` visualizzato come DMP
      * `contextData.['opt.sell']=Y` visualizzato come SELL

## Generazione di rapporti

Puoi abilitare le variabili per segnalazioni relative alla privacy tramite una nuova impostazione Privacy disponibile nell’Admin Console di Analytics.

Ogni suite di rapporti può essere configurata come segue:
1. In Reports &amp; Analytics fai clic su **[!UICONTROL Admin > Report Suites]**.
1. Seleziona le suite di rapporti in cui stai raccogliendo dati multimediali e fai clic su **[!UICONTROL Edit Settings > Privacy Management]**.

   ![](assets/rsm-privacy-select.png)

1. Fai clic sul pulsante **[!UICONTROL Enable Data Privacy Reports]**.

   >[!NOTE]
   >
   >Una volta abilitate, queste variabili non possono essere disattivate.

   ![](assets/rsm-privacy-enable.png)

1. Una volta abilitate, verrà visualizzato un messaggio di conferma.

   ![](assets/rsm-privacy-config.png)

1. Le variabili riservate sono ora disponibili per l’analisi in Reports &amp; Analytics e Workspace. Consulta Consent Management Opt-Out e Consent Management Opt-In.

   ![](assets/consent-management.png)

## Implementazione

Tre variabili di dati di contesto sono state predefinite per l’utilizzo con le variabili riservate per la gestione dei rapporti sulla privacy.  È compito di ogni tecnico dell’implementazione determinare come gestire e mantenere l’impostazione di tali variabili.

Consulta [Variabili di dati di contesto](https://docs.adobe.com/content/help/it-IT/analytics/implementation/vars/page-vars/contextdata.html) per informazioni generali sull’implementazione delle variabili di dati di contesto.

### SSF

* Dati contestuali: `contextData.['cm.ssf']`
* Valori accettati:
   * 1: quando si invia il valore “1”, indica che l’inoltro lato server è in stato opt-out. Il valore “1” associato a questa variabile bloccherà la condivisione dell’hit con Adobe Audience Manager. Consulta [Conformità ePrivacy AAM](https://docs.adobe.com/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/ssf-gdpr.html).
   * 0: facoltativo. Utilizza il valore “0” per i clienti che hanno acconsentito al marketing mirato. Si ottengono gli stessi risultati anche senza impostare la variabile.

### DMP

* Dati contestuali: `contextData.['opt.dmp']`
* Valori accettati:
   * N: quando si invia il valore “N”, questo indica che il consumatore sta rinunciando alla condivisione sulle piattaforme di gestione dei dati.  **Nota**: a partire dal 15 gennaio 2020, l’impostazione di questa variabile su “N” blocca la condivisione lato server dell’hit in AAM.
   * Y: quando si invia il valore “Y”, indica che il consumatore sta accettando la condivisione sulle piattaforme di gestione dei dati.

### SELL

* Dati contestuali: `contextData.['opt.sell']`
* Valori accettati:
   * N: quando si invia il valore “N”, indica che il consumatore sta rinunciando alla condivisione o alla vendita dei dati a terzi.
   * Y: quando si invia il valore “Y”, indica che il consumatore sta accettando la condivisione o la vendita dei dati a terzi.
