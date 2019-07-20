---
description: 'Se desiderate tenere traccia di ulteriori informazioni, ma non disponete di abbastanza variabili, potete ora accedere a evar ed eventi di successo aggiuntivi '
keywords: Implementazione di Analytics; evar; eventi; evar number; il numero evar; quanti eventi
seo-description: 'Se desiderate tenere traccia di ulteriori informazioni, ma non disponete di abbastanza variabili, potete ora accedere a evar ed eventi di successo aggiuntivi '
seo-title: Evar ed eventi aggiuntivi
solution: Analytics
title: Evar ed eventi aggiuntivi
topic: Sviluppatore e implementazione
uuid: 6 f 53069 b -6941-40 f 1-9 db 6-2 d 1839822 b 8 f
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# Evar ed eventi aggiuntivi

Se desideri tenere traccia di ulteriori informazioni, ma non hai abbastanza variabili, ora hai accesso a evar ed eventi di successo aggiuntivi:

>[!NOTE]
>
>Javascript H-Code non supporta queste evar ed eventi aggiuntivi.

## Entitlements to Custom Dimensions and Events {#section_869EC3D8A5614036A9C586F2B74FA7DC}

| Prodotto Adobe Analytics |  |  |  |
|---|---|---|---|
| Adobe Analytics - Foundation | 75 prop | 200 Evar | 1000 Eventi |
| Adobe Analytics - [Select](https://www.adobe.com/data-analytics-cloud/analytics/select.html) | 75 prop | 200 Evar | 1000 Eventi |
| Adobe Analytics - [Prime](https://www.adobe.com/data-analytics-cloud/analytics/prime.html) | 75 prop | 200 Evar | 1000 Eventi |
| Adobe Analytics - [Ultimate](https://www.adobe.com/data-analytics-cloud/analytics/ultimate.html) | 75 prop | 250 Evar | 1000 Eventi |

## Populating Variables and Events {#section_DEA51A22BCBB4B92BDD25814AAD296E4}

* Variables can be populated in the data collection library if you are using these versions of [!DNL AppMeasurement]:

   * Appmeasurement per javascript versione 1.4 +
   * Appmeasurement per Flash versione 3.9 +
   * Appmeasurement per Java versione 1.2.8 +
   * Appmeasurement per Silverlight/. NET versione 1.4.2 +
   * Appmeasurement per PHP versione 1.2.2 +

* Se utilizzi una versione precedente del codice o su javascript H. *, puoi compilare i dati contestuali e utilizzare le regole di elaborazione per comporre le variabili.
* Tutte le versioni del codice di raccolta dati possono comporre eventi 101-1000.
* Le regole di elaborazione possono essere utilizzate per compilare evar 76-250 in base ai dati contestuali o ad altre variabili.

## Domande frequenti {#section_E915B03236BD47DCA065F1FC5A6E30C6}

* **Tutte le interfacce di Adobe Analytics avranno accesso immediato a queste nuove variabili?** Queste interfacce avranno accesso immediato: [!UICONTROL Analysis Workspace][!UICONTROL Reports & Analytics][!UICONTROL Report Builder][!UICONTROL Ad Hoc Analysis], API e [!UICONTROL Data Workbench].

* **Queste evar e eventi aggiuntivi vengono automaticamente mostrati nei miei feed di dati?** I feed dati avranno accesso alle nuove variabili ed eventi una volta attivato. Le nuove colonne evar non vengono visualizzate finché non scegliete di includerle. Tuttavia, i nuovi eventi verranno visualizzati nella colonna event_ list non appena sono attivati e la tabella di ricerca degli eventi contiene i nomi degli eventi per gli ID degli eventi. Non abilitare i nuovi eventi a meno che non siano pronti per l'utilizzo nei feed dati.

* **Come si richiedono nuove colonne di feed dati?** Per richiedere nuove colonne, consultate [Configurazione dei feed di dati](https://marketing.adobe.com/resources/help/en_US/sc/clickstream/datafeeds_configure.html).

* **Cosa succede se sono un cliente Analytics Ultimate che desidera tornare ad Analytics Prime e attualmente sono abilitati più di 200 evar?** Adobe non disattiva nessuna delle evar esistenti, ma non potrai abilitare più. Se disattivate evars, non potete riattivarle finché non sei sotto il limite di Analytics Prime di 200 evar abilitati.

