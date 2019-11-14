---
description: 'Se desideri tenere traccia di informazioni aggiuntive ma non disponi di un numero sufficiente di variabili per farlo, ora puoi accedere ad eVar ed eventi di successo aggiuntivi '
keywords: Analytics Implementation;evars;events;evars number;how many evars;how many events
solution: Analytics
title: eVar ed eventi aggiuntivi
topic: Developer and implementation
uuid: 6f53069b-6941-40f1-9db6-2d1839822b8f
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# eVar ed eventi aggiuntivi

Se desiderate tenere traccia di informazioni aggiuntive, ma non disponete di un numero sufficiente di variabili, ora potete accedere ad eVar ed eventi di successo aggiuntivi:

> [!NOTE] JavaScript H-Code non supporta tali eVar ed eventi aggiuntivi.

## Adesione a dimensioni ed eventi personalizzati {#section_869EC3D8A5614036A9C586F2B74FA7DC}

| Prodotto Adobe Analytics |  |  |  |
|---|---|---|---|
| Adobe Analytics - Foundation | 75 proprietà | 200 eVar | 1000 eventi |
| Adobe Analytics - [Select](https://www.adobe.com/data-analytics-cloud/analytics/select.html) | 75 proprietà | 200 eVar | 1000 eventi |
| Adobe Analytics - [Prime](https://www.adobe.com/data-analytics-cloud/analytics/prime.html) | 75 proprietà | 200 eVar | 1000 eventi |
| Adobe Analytics - [Ultimate](https://www.adobe.com/data-analytics-cloud/analytics/ultimate.html) | 75 proprietà | 250 eVar | 1000 eventi |

## Compilazione di variabili ed eventi {#section_DEA51A22BCBB4B92BDD25814AAD296E4}

* Le variabili possono essere popolate nella raccolta dati se si utilizzano le seguenti versioni di [!DNL AppMeasurement]:

   * AppMeasurement per JavaScript versione 1.4+
   * AppMeasurement per Flash versione 3.9+
   * AppMeasurement per Java versione 1.2.8+
   * AppMeasurement per Silverlight/.NET versione 1.4.2+
   * AppMeasurement per PHP versione 1.2.2+

* Se utilizzi una versione precedente del codice o JavaScript H.*, puoi compilare i dati contestuali e utilizzare le regole di elaborazione per comporre le variabili.
* Tutte le versioni del codice di raccolta dati possono compilare gli eventi 101-1000.
* Le regole di elaborazione possono essere utilizzate per compilare eVar 76-250 in base ai dati contestuali o ad altre variabili.

## Domande frequenti {#section_E915B03236BD47DCA065F1FC5A6E30C6}

* **Tutte le interfacce di Adobe Analytics avranno accesso immediato a queste nuove variabili?** Queste interfacce avranno accesso immediato: [!UICONTROL Analysis Workspace], [!UICONTROL Reports & Analytics], [!UICONTROL Report Builder], [!UICONTROL Ad Hoc Analysis]API e [!UICONTROL Data Workbench].

* **Queste eVar ed eventi aggiuntivi verranno visualizzati automaticamente nei feed di dati?** I feed di dati avranno accesso alle nuove variabili ed eventi una volta attivato. Le nuove colonne eVar verranno visualizzate solo dopo che avrai scelto di includerle. Tuttavia, i nuovi eventi verranno visualizzati nella colonna event_list non appena vengono abilitati e la tabella di ricerca degli eventi contiene i nomi degli eventi per tali ID evento. Non abilitare nuovi eventi a meno che non sia pronto a utilizzarli nei feed di dati.

* **Come posso richiedere nuove colonne di feed di dati?** Per richiedere nuove colonne, fare riferimento a [Configurazione dei feed](https://marketing.adobe.com/resources/help/en_US/sc/clickstream/datafeeds_configure.html)di dati.

* **Cosa succede se sono un cliente Analytics Ultimate che desidera tornare ad Analytics Prime e al momento dispongo di più di 200 eVar abilitate?** Adobe non disattiverà nessuna delle eVar esistenti, ma non potrai abilitarne altre. Se disattivate le eVar, non potrete riattivarle finché non sarete al di sotto del limite Analytics Prime di 200 eVar abilitate.

