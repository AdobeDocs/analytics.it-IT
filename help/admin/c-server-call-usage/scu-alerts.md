---
description: Aggiungi o gestisci tutti gli avvisi di utilizzo del server. Quando configurate un avviso, questo si applica a tutte le suite di rapporti in tutte le società di accesso di una società di fatturazione.
seo-description: Aggiungi o gestisci tutti gli avvisi di utilizzo del server. Quando configurate un avviso, questo si applica a tutte le suite di rapporti in tutte le società di accesso di una società di fatturazione.
seo-title: Avvisi sull’utilizzo delle chiamate server
title: Avvisi sull’utilizzo delle chiamate server
uuid: 701fd542-5b24-42df-97a0-08e10929fa48
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Avvisi sull’utilizzo delle chiamate server

Quando configurate un avviso, questo si applica a tutte le suite di rapporti in tutte le società di accesso di una società di fatturazione.

## Panoramica

Una nuova categoria di avvisi denominata **[!UICONTROL Server Calls Usage Alert]** fa parte dell'interfaccia utente [Gestione](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/intellligent_alerts.html) avvisi esistente.

Viene precompilato con **1 avviso** predefinito che viene visualizzato all’interno di qualsiasi società di accesso che dispone dell’accesso alla funzione Utilizzo chiamate server. Questi avvisi attivano una notifica indirizzata a tutti gli amministratori della società di accesso se uno dei seguenti criteri è soddisfatto:

* "Qualsiasi" utilizzo di chiamate server "superiore o uguale a" 100% per qualsiasi tipo di chiamata server a cui si ha diritto, OPPURE
* "Qualsiasi" utilizzo di chiamate server "superiore o uguale a" 90% per qualsiasi tipo di chiamata server a cui si ha diritto, OPPURE
* "Qualsiasi" utilizzo di chiamate server "superiore o uguale a" 75% per qualsiasi tipo di chiamata server a cui si ha diritto, E "Il periodo di utilizzo trascorso" "è inferiore o uguale" al 75% del periodo di utilizzo.

![](assets/alerts.png)

Puoi accedere agli avvisi di utilizzo delle chiamate server in due modi:

* Fate clic **[!UICONTROL Manage Alerts]** nell'angolo superiore destro della scheda Utilizzo corrente o della scheda Utilizzo suite di rapporti oppure
* Passa a **[!UICONTROL Components]** &gt; **[!UICONTROL Alerts]** in Adobe Analytics.

## Create Server Call Usage Alerts {#section_2A2882C6D48D47C1944D52FB7C766BEC}

Per creare avvisi aggiuntivi,

1. Fate clic **[!UICONTROL + Add]** e selezionate **[!UICONTROL Server Call Usage Alert]**.

   ![](assets/server_call_alert.png)

1. Definire l’avviso.

   ![](assets/sc_alert.png)

   * **Titolo**: Specificate un nome descrittivo. Non è possibile salvare l’avviso senza un nome.
   * **Granularità** tempo: Indica la frequenza con cui verrà controllato l’avviso. *Al momento supportiamo solo la granularità settimanale.* Questo significa che l'avviso verrà controllato su base settimanale e che guarderà indietro ai dati del periodo di utilizzo corrente.
   * **Destinatari**: Specifica chiunque nell'organizzazione debba ricevere un'e-mail quando l'avviso attiva la soglia specificata.
   * **Data** di scadenza: Per impostazione predefinita, la data di scadenza è un anno dalla data di creazione dell’avviso.
   * **Invia un avviso quando**:

      * Uno qualsiasi di questi attivatori di metriche: aggiungi il tipo di chiamate server come metrica e specifica la soglia di avviso selezionando il modificatore e la soglia:
         * is above or equals (è superiore o uguale a)
         * is below or equals (è inferiore o uguale a)
      * Con: consente di specificare la soglia e la condizione (è superiore o uguale a, inferiore o uguale a) per il periodo di utilizzo trascorso.

1. Fai clic su **[!UICONTROL Save]**.

## Gestione avvisi utilizzo chiamate server {#section_8FF98170763C4B5CBEC6DD43F893177A}

![](assets/alert_mgmt.png)

Per gestire gli avvisi:

1. Seleziona la casella di controllo accanto a uno o più avvisi. Le azioni di gestione degli avvisi vengono visualizzate nella parte superiore.
1. Effettuare una o più delle seguenti operazioni:

   | Azione | Definizione |
   |--- |--- |
   | + Aggiungi | Access the [Alert Builder](../../admin/c-server-call-usage/scu-alerts.md) by clicking  [!UICONTROL + Add]. |
   | Tag | Assegnare tag agli avvisi per organizzarli in modo semplice. |
   | Elimina | È possibile eliminare tutti gli avvisi tranne quelli predefiniti. |
   | Rinomina | È possibile rinominare tutti gli avvisi tranne quelli predefiniti. |
   | Approva | Approvare gli avvisi per renderli "ufficiali". |
   | Attiva/Disattiva | Puoi attivare o disattivare tutti gli avvisi, anche quelli predefiniti. |
   | Rinnova | Se sono selezionati uno o più avvisi, è possibile rinnovarli. This extends their expiration dates to be 1 year from the day [!UICONTROL Renew] was clicked, regardless of their original expiration date. |
   | Export to CSV (Esporta in CSV) | Consultate [Download del rapporto sull'utilizzo](../../admin/c-server-call-usage/report-suite-usage.md) |

