---
description: Aggiungi o gestisci gli avvisi di utilizzo delle chiamate al server. Quando imposti un avviso, viene applicato a tutte le suite di rapporti in tutte le aziende di login di un’azienda di fatturazione.
title: Avvisi di utilizzo delle chiamate al server
feature: Server Call Usage
exl-id: 35926566-c570-4ed2-9bbc-0906518bcf64
source-git-commit: 72bd67179e003b70233d863d34153fec77548256
workflow-type: ht
source-wordcount: '508'
ht-degree: 100%

---

# Avvisi di utilizzo delle chiamate al server

Quando imposti un avviso, viene applicato a tutte le suite di rapporti in tutte le aziende di login di un’azienda di fatturazione.

## Panoramica

Una nuova categoria di avvisi denominata **[!UICONTROL Server Calls Usage Alert]** fa parte dell’interfaccia utente esistente per [Gestione avvisi](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/intelligent-alerts/intellligent-alerts.html?lang=it).

È precompilata con **1 avviso predefinito** che viene visualizzato in tutte le aziende di login che hanno accesso alla funzione di utilizzo delle chiamate al server. Gli avvisi attivano una notifica indirizzata a tutti gli amministratori dell’azienda di login se uno dei seguenti criteri è soddisfatto:

* “Qualsiasi” utilizzo di chiamate al server che “è superiore o uguale al” 100% per qualsiasi tipo di chiamata al server a cui hai diritto OPPURE
* “Qualsiasi” utilizzo di chiamate al server che “è superiore o uguale al” 90% per qualsiasi tipo di chiamata al server a cui hai diritto OPPURE
* “Qualsiasi” utilizzo di chiamate al server che “è superiore o uguale al” 75% per qualsiasi tipo di chiamata al server a cui hai diritto E il “periodo di utilizzo trascorso” “è inferiore o uguale al” 75% del periodo di utilizzo.

![](assets/alerts.png)

È possibile accedere agli avvisi di utilizzo delle chiamate al server in due modi:

* Fai clic su **[!UICONTROL Manage Alerts]** nell’angolo in alto a destra nella scheda Utilizzo corrente o nella scheda Utilizzo suite di rapporti, oppure
* Passa a **[!UICONTROL Components]** > **[!UICONTROL Alerts]** in Adobe Analytics.

## Creare avvisi di utilizzo delle chiamate al server {#section_2A2882C6D48D47C1944D52FB7C766BEC}

Per creare avvisi aggiuntivi:

1. Fai clic su **[!UICONTROL + Add]** e seleziona **[!UICONTROL Server Call Usage Alert]**.

   ![](assets/server_call_alert.png)

1. Definisci l’avviso.

   ![](assets/sc_alert.png)

   * **Titolo**: specifica un nome descrittivo. Non è possibile salvare l’avviso senza un nome.
   * **Granularità del tempo**: indica la frequenza con cui verrà controllato l’avviso. *Al momento è supportata solo la granularità settimanale.* Ciò significa che l’avviso verrà controllato settimanalmente e riguarderà i dati del periodo di utilizzo corrente.
   * **Destinatari**: specifica gli utenti dell’organizzazione che devono ricevere un’e-mail quando l’avviso attiva la soglia specificata.
   * **Data di scadenza**: per impostazione predefinita, la data di scadenza è un anno dalla data di creazione dell’avviso.
   * **Invia un avviso quando**:

      * Uno di questi trigger di metriche
Aggiungi il tipo di chiamate al server come metrica e specifica la soglia di avviso selezionando il modificatore e la soglia:
         * is above or equals (è superiore o uguale a)
         * is below or equals (è inferiore o uguale a)
      * Con
Specifica la soglia e la condizione (è superiore o uguale a oppure inferiore o uguale a) per il periodo di utilizzo trascorso.

1. Fai clic su **[!UICONTROL Save]**.

## Gestire gli avvisi di utilizzo delle chiamate al server {#section_8FF98170763C4B5CBEC6DD43F893177A}

![](assets/alert_mgmt.png)

Per gestire gli avvisi:

1. Seleziona la casella di controllo accanto a uno o più avvisi. Le azioni di gestione degli avvisi vengono visualizzate nella parte superiore.
1. Completa una o più delle seguenti azioni:

   | Azione | Definizione |
   |--- |--- |
   | + Aggiungi | Accedi al  [generatore di avvisi](/help/admin/c-server-call-usage/scu-alerts.md) facendo clic su [!UICONTROL + Add]. |
   | Tag | Assegna tag agli avvisi per organizzarli in modo semplice e intuitivo. |
   | Elimina | È possibile eliminare tutti gli avvisi tranne quelli predefiniti. |
   | Rinomina | È possibile rinominare tutti gli avvisi tranne quelli predefiniti. |
   | Approva | Approva gli avvisi per renderli “ufficiali”. |
   | Abilita/Disabilita | Puoi abilitare o disabilitare tutti gli avvisi, anche quelli predefiniti. |
   | Rinnova | Se sono selezionati uno o più avvisi, è possibile rinnovarli. In questo modo le rispettive date di scadenza vengono spostate a 1 anno dal giorno in cui si è fatto clic su [!UICONTROL Renew], indipendentemente dalla data di scadenza originale. |
   | Esporta in CSV | Vedi [Download del rapporto di utilizzo](/help/admin/c-server-call-usage/report-suite-usage.md) |
