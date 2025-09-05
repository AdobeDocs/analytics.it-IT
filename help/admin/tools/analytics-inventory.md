---
description: Utilizzare l’inventario di Analytics
title: Inventario analitico
feature: Admin Tools
role: Admin
exl-id: 9fc985c8-93d7-4838-9342-72a6268ef96f
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '1160'
ht-degree: 19%

---

# Inventario di Analytics {#analytics-inventory}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory"
>title="Inventario di Analytics"
>abstract="Questa pagina fornisce una panoramica completa dell’ambiente Adobe Analytics, compreso il numero di progetti e componenti, suite di rapporti, utenti e altro ancora. Queste informazioni sono particolarmente utili quando inizi a preparare l’aggiornamento a Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

L’inventario di Analytics fornisce una panoramica completa dell’ambiente Adobe Analytics, compreso il numero di progetti e componenti, suite di rapporti, utenti e altro ancora. Queste informazioni sono particolarmente utili quando inizi a preparare l’aggiornamento a Customer Journey Analytics.

L’obiettivo dell’inventario di Analytics è di aiutarti a rispondere alle seguenti domande:

* Per la tua organizzazione, quali risorse (ad esempio suite di rapporti, segmenti, utenti, progetti Workspace e così via) devi migrare e quali risorse puoi lasciarti dietro?

* Una volta determinata la risorsa di cui eseguire la migrazione:

   * È necessario eseguire una pulizia delle risorse prima di questo aggiornamento?

   * È necessario eseguire il consolidamento delle risorse come parte del processo?

   * Quale dovrebbe essere la sequenza di aggiornamento per le risorse?

   * Quali suite di rapporti devi aggiornare per prime o per ultime?

## Autorizzazioni

L&#39;inventario di Analytics è disponibile per gli utenti con privilegi di amministratore di prodotto Adobe Analytics in [Adobe Admin Console](/help/admin/admin-console/admin-roles-in-analytics.md).

## Accedere a Inventario analisi

1. Scegliere **[!UICONTROL Analytics Inventory]** nel menu **[!UICONTROL Admin]**. Oppure vai a **[!UICONTROL All admin]** > **[!UICONTROL Analytics Inventory]**.

![Analytics-Inventory-menu](assets/an-inventory-menu.png)

1. La schermata principale presenta un inventario completo dell’ambiente Adobe Analytics:

   ![Schermata inventario principale](assets/an_inventory.png)

   In particolare, questa schermata mostra:

   * Il numero totale di progetti di scorecard per dispositivi mobili e Analysis Workspace attivi in questa organizzazione, per tutti gli utenti.
   * Il numero totale di segmenti e metriche calcolate attivi in questa organizzazione, su tutti gli utenti.
   * Numero totale di suite di rapporti di base definite. Le suite di rapporti virtuali non sono incluse.
   * Se la funzione Media Analytics è attiva e, in caso affermativo, in quale modalità.
   * Numero totale di utenti definiti in questa organizzazione.


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
>abstract="Questa sezione mostra il numero di suite di rapporti nell’ambiente Adobe Analytics e l’accesso ai servizi dei file multimediali in streaming."

<!-- markdownlint-enable MD034 -->

### di Report Suite Manager

La vista Suite di rapporti mostra tutte le suite di rapporti definite in un’organizzazione. Ti consente di rispondere alle seguenti domande:

* Quali suite di rapporti hanno ricevuto il maggior numero di hit negli ultimi 90 giorni?
* Quali suite di rapporti non hanno ricevuto hit negli ultimi 90 giorni?
* Quali suite di rapporti hanno il maggior numero di dimensioni definito?
* Quali suite di rapporti hanno il maggior numero di metriche definite?

Le risposte a queste domande ti daranno una buona idea su quali suite di rapporti sono i candidati migliori per la migrazione.

>[!NOTE]
>
>Questa tabella viene compilata lentamente, un valore di cella alla volta.


1. Per analizzare le suite di rapporti, passa a **[!UICONTROL Data configuration and collection]** > **[!UICONTROL Report suites]** e fai clic su **[!UICONTROL Analyze]**.

   ![Elenco delle suite di rapporti](assets/an_inv_rs.png)

   | Elemento | Descrizione |
   | --- | --- |
   | Nome | Nome della suite di rapporti |
   | ID | ID suite di rapporti (rsid). Specifica un ID univoco; può contenere solo caratteri alfanumerici. Una volta creato, non è possibile modificare questo ID. Adobe imposta il prefisso ID richiesto, che non può essere modificato. |
   | Occorrenze (ultimi 90 giorni) | La metrica &quot;Occorrenze&quot; mostra il numero di hit in cui una determinata dimensione è stata impostata o persistita. Quanti hit ha ricevuto questa suite di rapporti negli ultimi 90 giorni? |
   | Metriche | Quante metriche sono definite in questa suite di rapporti? |
   | Dimensioni | Quante dimensioni sono definite in questa suite di rapporti? |
   | Analytics for Target (A4T) abilitato | [Nascosto per impostazione predefinita] Questa suite di rapporti è abilitata per [Analytics for Target](https://experienceleague.adobe.com/en/docs/target/using/integrate/a4t/a4t)? |
   | Canali marketing abilitati | [Nascosto per impostazione predefinita] Questa suite di rapporti è abilitata per [Canali di marketing](/help/components/c-marketing-channels/c-getting-started-mchannel.md)? |
   | Connettore Source abilitato | Questa suite di rapporti è abilitata per [Adobe Analytics Source Connector per i dati della suite di rapporti](https://experienceleague.adobe.com/it/docs/experience-platform/sources/connectors/adobe-applications/analytics) in Adobe Experience Platform? In altre parole, è possibile migrare questa suite di rapporti a Customer Journey Analytics utilizzando il connettore Source di Analytics? |
   | Tipo di calendario | [Nascosto per impostazione predefinita] Per ulteriori informazioni, fare riferimento a [Calendari personalizzati](/help/admin/tools/manage-rs/edit-settings/general/custom-calendar.md) |

#### Analizzare le dimensioni

Questa schermata fornisce una visualizzazione dettagliata di tutte le dimensioni definite per una specifica suite di rapporti. Da questa vista puoi rispondere alle seguenti domande:

* Quali dimensioni sono abilitate per questa suite di rapporti?
* Quali sono i dieci elementi dimensionali principali degli ultimi 90 giorni per questa dimensione?

1. Fai clic sul collegamento **[!UICONTROL Dimensions]** nella pagina Suite di rapporti.

   | Elemento | Descrizione |
   | --- | --- |
   | Nome | Nome della dimensione |
   | ID | ID dimensione. |
   | Tipo | Tipo di dimensione. I valori possibili includono Conversione, Traffico, Navigazione, Origini del traffico, Clienti, Data o dimensioni specifiche per il prodotto Adobe come AEM, Audience, Adobe Campaign, App mobile, ecc. |
   | Descrizione | Non tutte le dimensioni hanno descrizioni. |
   | Connettore Source abilitato | Questa dimensione è abilitata per [Adobe Analytics Source Connector per i dati della suite di rapporti](https://experienceleague.adobe.com/it/docs/experience-platform/sources/connectors/adobe-applications/analytics) in Adobe Experience Platform? In altre parole, è possibile migrare questa dimensione a Customer Journey Analytics utilizzando il connettore Source di Analytics? |

1. Determina quali dimensioni hanno senso migrare a CJA.


#### Analizzare le metriche

Questa schermata fornisce una visualizzazione dettagliata di tutte le metriche definite per una specifica suite di rapporti. Da questa vista puoi rispondere alle seguenti domande:

* Quali metriche sono abilitate per questa suite di rapporti?
* Quali sono le dieci metriche principali per gli ultimi 90 giorni?

1. Fai clic sul collegamento **[!UICONTROL Metrics]** nella pagina Suite di rapporti.


   | Elemento | Descrizione |
   | --- | --- |
   | Nome | Nome della metrica |
   | ID | ID della metrica. |
   | Tipo | Il tipo di metrica. I valori possibili includono Conversione, Traffico, Navigazione, Origini del traffico, Clienti, Data o dimensioni specifiche per il prodotto Adobe come AEM, Audience, Adobe Campaign, App mobile, ecc. |
   | Descrizione | Non tutte le dimensioni hanno descrizioni. |
   | Connettore Source abilitato | Questa metrica è abilitata per [Adobe Analytics Source Connector per i dati della suite di rapporti](https://experienceleague.adobe.com/it/docs/experience-platform/sources/connectors/adobe-applications/analytics) in Adobe Experience Platform? In altre parole, è possibile migrare questa metrica a Customer Journey Analytics utilizzando il connettore Source di Analytics? |

1. Determinare quali metriche hanno senso migrare a CJA.

### Export to CSV (Esporta in CSV)

1. Per esportare l&#39;elenco delle suite di rapporti, delle dimensioni o delle metriche in un file .csv, fare clic su **[!UICONTROL Export to CSV]**.

1. Il file .csv verrà visualizzato nella cartella Download.

1. Apri e salva con un’applicazione per fogli di calcolo sul dispositivo.

>[!NOTE]
>
>Gli elementi e le colonne esclusi non vengono esportati nel file .csv.


### Filtrare, cercare, ordinare e navigare

* Puoi cercare nella tabella.
* Nella barra a sinistra, fai clic sull’icona Filtro per filtrare in base a &quot;Tipo&quot;. Oppure fai clic su **[!UICONTROL Hide Filter]**.
* Puoi ordinare tutte le colonne in ordine crescente/decrescente (solo ordinamento a colonna singola).
* Puoi fare clic sugli elementi nella breadcrumb per passare a un’altra schermata.

## Gestione degli utenti {#user-management}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory-user-management"
>title="Gestione degli utenti"
>abstract="Questa sezione mostra il numero di utenti nell’ambiente Adobe Analytics."

<!-- markdownlint-enable MD034 -->

La gestione degli utenti sarà disponibile in una versione successiva dell’inventario di Analytics.

## Migrare componenti

Utilizzando [Migrazione componenti](/help/admin/tools/component-migration/component-migration.md), gli amministratori di Adobe Analytics possono eseguire la migrazione dei progetti Analytics e dei relativi componenti a Customer Journey Analytics.

Il processo di migrazione include:

* mappatura dei progetti Adobe Analytics in Customer Journey Analytics;

* mappatura di dimensioni e metriche dalle suite di rapporti di Adobe Analytics alle dimensioni e alle metriche nelle visualizzazioni dati in Customer Journey Analytics.