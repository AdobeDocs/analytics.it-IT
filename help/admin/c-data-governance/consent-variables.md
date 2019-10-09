---
description: Variabili per la gestione del consenso in Privacy dei dati.
seo-description: Variabili per la gestione del consenso in Privacy dei dati.
seo-title: Variabili di gestione del consenso
solution: Analytics
title: Variabili di gestione del consenso
topic: Strumenti di amministrazione
translation-type: tm+mt
source-git-commit: 492e9405c82183f6beb6588cd0dc039fe15350f7

---


# Variabili di gestione del consenso

Per fornire ulteriore assistenza nella gestione dei dati sulla privacy, è disponibile una serie di variabili riservate da utilizzare insieme a variabili di dati di contesto specifiche.
Queste variabili di gestione del consenso forniscono un framework di facile utilizzo per acquisire lo stato del consenso su ogni hit di analisi.

## Variabili

* Gestione del consenso Opt-Out
   * Variabile riservata: Prop elenco
   * Tipo: Stringa delimitata da virgole
   * Contiene:
      * `contextData.['cm.ssf']=1` visualizzato come SSF
      * `contextData.['opt.dmp']=N` visualizzato come DMP
      * `contextData.['opt.sell']=N` visualizzato come SELL

* Gestione del consenso Opt-in
   * Variabile riservata: Prop elenco
   * Tipo: Stringa delimitata da virgole
   * Contiene:
      * `contextData.['opt.dmp']=Y` visualizzato come DMP
      * `contextData.['opt.sell']=Y` visualizzato come SELL

## Generazione di rapporti  

Le variabili di gestione del consenso possono essere abilitate tramite una nuova impostazione Privacy disponibile nell’Admin Console di Analytics.

Ogni suite di rapporti può essere configurata per:
1. In Reporting e analisi fate clic su Admin (Amministratore) &gt; Report Suites (Suite di rapporti).
1. Selezionate le suite di rapporti in cui state raccogliendo i dati multimediali e fate clic su [!UICONTROL Edit Settings > Privacy Management]

   ![](assets/rsm-privacy-select.png)

1. Click the [!UICONTROL Enable Data Privacy Reports] button.  Nota: Una volta abilitate queste variabili non possono essere disattivate.

   ![](assets/rsm-privacy-enable.png)

1. Una volta attivato, verrà visualizzato un messaggio di conferma.

   ![](assets/rsm-privacy-config.png)

1. Le variabili riservate ora sono disponibili per il reporting.  Consulta Consent Management Opt-Out and Consent Management Opt-In (Rifiuto e consenso della gestione del consenso).

   ![](assets/rsm-privacy-reports.png)

## Implementazione

Sono state predefinite tre variabili di dati di contesto per l’utilizzo delle variabili riservate per la gestione del consenso.  È compito di ogni tecnico dell'implementazione determinare come gestire e mantenere l'impostazione di queste variabili.

Consulta Variabili [di dati](https://docs.adobe.com/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/context-data-variables.html) contestuali per informazioni generali sull'implementazione delle variabili di dati di contesto.

### SSF

* Dati contestuali: `contextData.['cm.ssf']`
* Valori accettati:
   * `1` - Quando si invia il valore `1`, ciò indica che l'inoltro lato server è in stato di rifiuto. Il valore associato `1` a questa variabile bloccherà la condivisione dell’hit con Adobe Audience Manager. Consulta Conformità [AAM ePrivacy.](https://docs.adobe.com/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/ssf-gdpr.html)
   * Nessun altro valore accettato per questo parametro

### DMP

* Dati contestuali: `contextData.['opt.dmp']`
* Valori accettati:
   * `N` - Quando si invia il valore `N`, ciò indica che il consumatore sta rinunciando alla condivisione sulle piattaforme di gestione dei dati. Nota: la condivisione del blocco corrente non è in AAM.  Utilizzare SSF per tale funzionalità.
   * `Y` - Quando si invia il valore `Y`, ciò indica che il consumatore sta optando per la condivisione su piattaforme di gestione dati.

### VENDITA

* Dati contestuali: `contextData.['opt.sell']`
* Valori accettati:
   * `N` - Quando si invia il valore `N`, ciò indica che il consumatore rinuncia alla condivisione o alla vendita dei dati a terzi.
   * `Y` - Quando si invia il valore `Y`, ciò indica che il consumatore sta optando per la condivisione o la vendita dei dati a terzi.
