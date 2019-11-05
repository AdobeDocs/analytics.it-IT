---
description: Variabili per la generazione di rapporti sulla privacy in Privacy dei dati.
seo-description: Variabili per la generazione di rapporti sulla privacy in Privacy dei dati.
seo-title: Variabili per la generazione di rapporti sulla privacy
solution: Analytics
title: Variabili per la generazione di rapporti sulla privacy
topic: Strumenti di amministrazione
translation-type: tm+mt
source-git-commit: 57fe1f6d613b9f54a5191ac8684d36bccfebf4e5

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
1. In Reports &amp; Analytics fai clic su **[!UICONTROL Admin > Report Suites.]**
1. Seleziona le suite di rapporti in cui stai raccogliendo dati multimediali e fai clic su **[!UICONTROL Edit Settings > Privacy Management.]**

   ![](assets/rsm-privacy-select.png)

1. Fai clic sul pulsante **[!UICONTROL Enable Data Privacy Reports]**. **Nota:** una volta abilitate queste variabili non possono essere disattivate.

   ![](assets/rsm-privacy-enable.png)

1. Una volta attivata, verrà visualizzato un messaggio di conferma.

   ![](assets/rsm-privacy-config.png)

1. Le variabili riservate sono ora disponibili per la generazione di rapporti.  Consulta Consent Management Opt-Out e Consent Management Opt-In.

   ![](assets/rsm-privacy-reports.png)

## Implementazione

Tre variabili di dati di contesto sono state predefinite per l’utilizzo con le variabili riservate per la gestione dei rapporti sulla privacy.  È compito di ogni tecnico dell’implementazione determinare come gestire e mantenere l’impostazione di tali variabili.

Consulta [Variabili di dati di contesto](https://docs.adobe.com/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/context-data-variables.html) per informazioni generali sull’implementazione delle variabili di dati di contesto.

### SSF

* Dati contestuali: `contextData.['cm.ssf']`
* Valori accettati:
   * 1: quando si invia il valore “1”, indica che l’inoltro lato server è in stato opt-out. Il valore “1” associato a questa variabile bloccherà la condivisione dell’hit con Adobe Audience Manager. Consulta [Conformità ePrivacy AAM.](https://docs.adobe.com/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/ssf-gdpr.html)
   * Nessun altro valore è accettato per questo parametro.

### DMP

* Dati contestuali: `contextData.['opt.dmp']`
* Valori accettati:
   * N: quando si invia il valore “N”, indica che il consumatore sta rinunciando alla condivisione sulle piattaforme di gestione dei dati. **Nota:** l’impostazione di questa variabile su “N” al momento non blocca la condivisione su AAM, tuttavia, il blocco delle chiamate alla funzionalità AAM verrà aggiunto all’inizio del 2020. Per il momento Adobe consiglia di impostare `c.cm.ssf=1` e `c.opt.dmp=N` per bloccare l’invio degli hit ad AAM.
   * Y: quando si invia il valore “Y”, indica che il consumatore sta accettando la condivisione sulle piattaforme di gestione dei dati.

### SELL

* Dati contestuali: `contextData.['opt.sell']`
* Valori accettati:
   * N: quando si invia il valore “N”, indica che il consumatore sta rinunciando alla condivisione o alla vendita dei dati a terzi.
   * Y: quando si invia il valore “Y”, indica che il consumatore sta accettando la condivisione o la vendita dei dati a terzi.
