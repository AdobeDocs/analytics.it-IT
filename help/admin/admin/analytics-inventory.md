---
description: Utilizzare l’inventario di Analytics
title: Inventario di Analytics
feature: Admin Tools
role: Admin
hide: true
hidefromtoc: true
exl-id: 9fc985c8-93d7-4838-9342-72a6268ef96f
source-git-commit: 1e52aecdbb26dce0875b2df685ed2fa860eaba85
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 6%

---

# Inventario di Analytics {#analytics-inventory}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory"
>title="Inventario di Analytics"
>abstract="Questa pagina fornisce una panoramica completa dell’ambiente Adobe Analytics, compreso il numero di progetti e componenti, suite di rapporti, utenti e altro ancora. Queste informazioni sono particolarmente utili quando si inizia a preparare l&#39;aggiornamento a Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

L’inventario di Analytics fornisce una panoramica completa dell’ambiente Adobe Analytics, compreso il numero di progetti e componenti, suite di rapporti, utenti e altro ancora. Queste informazioni sono particolarmente utili quando si inizia a preparare l&#39;aggiornamento a Customer Journey Analytics.

L&#39;obiettivo di questa applicazione è quello di aiutarti a rispondere alle seguenti domande:

* Per la tua organizzazione, quali risorse (ad esempio suite di rapporti, segmenti, utenti, progetti Workspace, feed di dati e così via) devi aggiornare e quali risorse puoi lasciare indietro?

* Una volta determinata la risorsa di cui eseguire la migrazione:

   * È necessario eseguire una pulizia delle risorse prima di questo aggiornamento?

   * È necessario eseguire il consolidamento delle risorse come parte del processo?

   * Quale dovrebbe essere la sequenza di aggiornamento per le risorse?

   * Quale gruppo di suite di rapporti devi aggiornare per primo? ultimo?

## Autorizzazioni

L&#39;inventario di Analytics è disponibile per gli utenti con privilegi di amministratore di prodotto Adobe Analytics in [Adobe Admin Console](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-console/admin-roles-in-analytics).

## Accedere a Inventario analisi

1. Scegliere **[!UICONTROL Analytics Inventory]** nel menu **[!UICONTROL Admin]**. Oppure vai a **[!UICONTROL All admin]** > **[!UICONTROL Analytics Inventory]**.

![Analytics-Inventory-menu](assets/an-inventory-menu.png)

1. La schermata principale presenta un inventario completo dell’ambiente Adobe Analytics:

   ![Schermata inventario principale](assets/an_inventory.png)

   Nello specifico, questa schermata viene visualizzata

   * Il numero totale di progetti di scorecard per dispositivi mobili e Analysis Workspace attivi in questa organizzazione per tutti gli utenti.
   * Il numero totale di segmenti e metriche calcolate attivi in questa organizzazione per tutti gli utenti.
   * Numero totale di suite di rapporti di base definite (non sono incluse le suite di rapporti virtuali).
   * Se la funzione Media Analytics è attiva e, in caso affermativo, in quale modalità.
   * Il numero totale di utenti definiti in tale organizzazione.


## Componenti {#components}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory-components"
>title="Componenti"
>abstract="Questa sezione mostra il numero di progetti, segmenti e metriche calcolate esistenti nell’ambiente Adobe Analytics. È possibile migrare progetti e componenti a Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

In questa versione iniziale è possibile visualizzare i numeri di inventario di riepilogo per progetti Workspace, segmenti e metriche calcolate. Le versioni successive consentono di analizzare questi componenti.

## Configurazione e raccolta dati {#data-config}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory-data-config"
>title="Configurazione e raccolta dati"
>abstract="Questa sezione mostra il numero di suite di rapporti nell’ambiente Adobe Analytics e l’accesso a Streaming Media. "

<!-- markdownlint-enable MD034 -->

### di Report Suite Manager

La vista Suite di rapporti mostra tutte le suite di rapporti definite in un’organizzazione. Ti consente di rispondere alle seguenti domande:

* Quali suite di rapporti hanno ricevuto il maggior numero di hit negli ultimi 90 giorni?
* Quali suite di rapporti non hanno ricevuto hit negli ultimi 90 giorni?
* Quali suite di rapporti hanno il maggior numero di dimensioni definito?
* Quali suite di rapporti hanno il maggior numero di metriche definite?

Le risposte a queste domande ti daranno una buona idea su quali suite di rapporti sono i candidati migliori per la migrazione.

1. Per analizzare le suite di rapporti, passa a **[!UICONTROL Data configuration and collection]** > **[!UICONTROL Report suites]** e fai clic su **[!UICONTROL Analyze]**.

   ![Elenco delle suite di rapporti](assets/an_inv_rs.png)

   | Elemento | Descrizione |
   | --- | --- |
   | Nome | Nome della suite di rapporti |
   | ID | ID suite di rapporti (rsid). Specifica un ID univoco; può contenere solo caratteri alfanumerici. Una volta creato, non è possibile modificare questo ID. Adobe imposta il prefisso ID richiesto, che non può essere modificato. |
   | Occorrenze (ultimi 90 giorni) | Quanti hit ha ricevuto questa suite di rapporti negli ultimi 90 giorni? |
   | Metriche | Quante metriche sono definite in questa suite di rapporti? |
   | Dimensioni | Quante dimensioni sono definite in questa suite di rapporti? |
   | Analytics for Target (A4T) abilitato | Questa suite di rapporti è abilitata per [Analytics for Target](https://experienceleague.adobe.com/en/docs/target/using/integrate/a4t/a4t)? |
   | Canali marketing abilitati | Questa suite di rapporti è abilitata per [Canali di marketing](https://experienceleague.adobe.com/en/docs/analytics/components/marketing-channels/c-getting-started-mchannel)? |
   | Connettore Source abilitato | [In fase di sviluppo] questa suite di rapporti è abilitata per il [connettore Source di Adobe Analytics per i dati della suite di rapporti](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/analytics) in Adobe Experience Platform? In altre parole, è possibile migrare questa suite di rapporti a Customer Journey Analytics utilizzando il connettore Source di Analytics? |
   | Tipo di calendario | Per ulteriori informazioni, vedere [Calendari personalizzati](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/custom-calendar#) |

1. Nota che...

### Export to CSV (Esporta in CSV)

1. Per esportare l&#39;elenco delle suite di rapporti in un file .csv, fare clic su **[!UICONTROL Export to CSV]**.

1. Il file .csv verrà visualizzato nella cartella Download.

1. Apri e salva con un’applicazione per fogli di calcolo sul dispositivo.


## Gestione utente {#user-management}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory-user-management"
>title="Gestione utente"
>abstract="Questa sezione mostra il numero di utenti nell’ambiente Adobe Analytics."

<!-- markdownlint-enable MD034 -->

La gestione degli utenti sarà disponibile in una versione successiva dell’inventario di Analytics.