---
description: Aggiungere o gestire tutti gli avvisi di utilizzo. Quando impostate un avviso, questo viene applicato a tutte le suite di rapporti di una società di fatturazione.
seo-description: Aggiungere o gestire tutti gli avvisi di utilizzo. Quando impostate un avviso, questo viene applicato a tutte le suite di rapporti di una società di fatturazione.
seo-title: Avvisi sull'utilizzo della chiamata server
title: Avvisi sull'utilizzo della chiamata server
uuid: 701 fd 542-5 b 24-42 df -97 a 0-08 e 10929 fa 48
translation-type: tm+mt
source-git-commit: f608acafd77fd6469f553f30c45f54484028890a

---


# Avvisi sull'utilizzo della chiamata server

Quando impostate un avviso, questo viene applicato a tutte le suite di rapporti di una società di fatturazione.

## Panoramica

A new alert category called **[!UICONTROL Server Calls Usage Alert]** is part of the the existing [Alert Management](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/intellligent_alerts.html) user interface.

It is pre-populated with **1 default alert** that appears within any login company that has access to the Server Call Usage feature. Questi avvisi attivano una notifica indirizzata a tutti gli amministratori della società di accesso se viene soddisfatto uno dei seguenti criteri:

* " Any "server call use that" is above or equals "100% for any server-call type you are entitled to, OR
* " Any "server call use that" is above or equals "90% for any server-call type you are entitled to, OR
* " Any "server call use that" is above or equals "75% for any server-call type you are entitled to, AND" Usage period spent "" is below or equals "75% of Usage period.

![](assets/alerts.png)

Puoi accedere agli avvisi sull'utilizzo di chiamate server in due modi:

* Click **[!UICONTROL Manage Alerts]** in the upper right corner on the Current Usage tab or the Report Suite usage tab, or
* Navigate to **[!UICONTROL Components]** &gt; **[!UICONTROL Alerts]** in Adobe Analytics.

## Create Server Call Usage Alerts {#section_2A2882C6D48D47C1944D52FB7C766BEC}

Per creare altri avvisi,

1. Click **[!UICONTROL + Add]** and select **[!UICONTROL Server Call Usage Alert]**.

   ![](assets/server_call_alert.png)

1. Definire l'avviso.

   ![](assets/sc_alert.png)

   * **Titolo**: Specificate un nome descrittivo. Non è possibile salvare l'avviso senza un nome.
   * **Granularità tempo**: Indica la frequenza con cui l'avviso viene controllato. *Al momento, supportiamo solo la granularità settimanale.* Questo significa che l'avviso verrà controllato su base settimanale e che sarà visualizzato come risultato dal periodo di utilizzo corrente.
   * **Destinatari**: Specificate chiunque sia presente nell'organizzazione per ottenere un'e-mail quando l'avviso attiva la soglia specificata.
   * **Data di scadenza**: Per impostazione predefinita, la data di scadenza è di un anno dalla data di creazione avvisi.
   * **Invia un avviso quando**:

      * Qualsiasi di questi attivatori
Metriche aggiunge il tipo di chiamata server/s come metrica e specifica la soglia di avviso selezionando il modificatore e la soglia:
         * is above or equals (è superiore o uguale a)
         * is below or equals (è inferiore o uguale a)
      * Con
Specifica la soglia e la condizione (si trova sopra o è uguale o è inferiore o uguale a) per il periodo di utilizzo trascorso.

1. Fai clic su **[!UICONTROL Save]**.

## Manage Server Calls Usage Alerts {#section_8FF98170763C4B5CBEC6DD43F893177A}

![](assets/alert_mgmt.png)

Per gestire gli avvisi:

1. Selezionate la casella di controllo accanto a uno o più avvisi. Le azioni di gestione avvisi vengono visualizzate nella parte superiore.
1. Completare una o più azioni:

   | Azione | Definizione |
   |--- |--- |
   | + Aggiungi | Access the [Alert Builder](../../admin/c-server-call-usage/scu-alerts.md) by clicking  [!UICONTROL + Add]. |
   | Tag | Etichettare i tag per semplificarne l'utilizzo. |
   | Elimina | È possibile eliminare tutti gli avvisi tranne quelli predefiniti. |
   | Rinomina | È possibile rinominare tutti gli avvisi tranne quelli predefiniti. |
   | Approva | Approvare gli avvisi per renderli «ufficiali». |
   | Attiva/Disattiva | Puoi abilitare o disabilitare tutti gli avvisi, anche quelli predefiniti. |
   | Rinnova | Se sono selezionati uno o più avvisi, è possibile rinnovarli. This extends their expiration dates to be 1 year from the day [!UICONTROL Renew] was clicked, regardless of their original expiration date. |
   | Export to CSV (Esporta in CSV) | See [Download Usage Report](../../admin/c-server-call-usage/report-suite-usage.md) |

