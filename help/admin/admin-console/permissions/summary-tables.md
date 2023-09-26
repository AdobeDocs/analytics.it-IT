---
title: Autorizzazioni Adobe Analytics - tabelle di riepilogo
description: Tabelle che riepilogano le autorizzazioni Adobe Analytics disponibili in Adobe Admin Console.
exl-id: f1abbdb7-0f76-4d9b-a3ca-b12fa3cecb50
feature: Admin Tools
source-git-commit: f6c1162e6f5e8cc6f38da21b5bc19389ffd1e3c5
workflow-type: tm+mt
source-wordcount: '1302'
ht-degree: 94%

---

# Autorizzazioni Analytics in Admin Console

Utilizza le tabelle di riepilogo seguenti per identificare le autorizzazioni di Adobe Analytics in Adobe Admin Console, per raggruppamenti logici.

## Strumenti delle suite di rapporti

| Strumento Suite di rapporti | Amministrazione | Controlli di accesso | Funzioni solo rapporti | Obsoleto | Descrizione |
| --- | --- | --- | --- | --- | --- |
| Riepilogo account | x |  |  |  | Consente di accedere a Generale > Impostazioni account generali in Report Suite Manager. |
| Canali | x |  |  |  | Consente l’accesso ai canali di marketing, inclusi Marketing Channel Manager, Marketing Channel Processing Rules e Marketing Channel Expiration nel Report Suite Manager. |
| Classificazioni | x |  |  |  | Consente di accedere a tutte le impostazioni di classificazione in Report Suite Manager. Questa voce di autorizzazione include: |
| Variabili di conversione | x |  |  |  | Consente l’accesso a Conversione > Variabili di conversione in Report Suite Manager. |
| Costi | x |  |  |  | Consente l’accesso a Canali di marketing > Costi canale di marketing in Report Suite Manager. |
| Calendario personalizzato | x |  |  |  | Consente di accedere a Generale > Personalizza calendario in Report Suite Manager. |
| Gestione feed dati | x |  |  |  | Consente di accedere ad Admin > Data feeds (Amministrazione > Feed dati) nell’area di navigazione superiore di Analytics. |
| API Data Repair | x |  |  |  | Consente l’accesso all’API Data Repair |
| Gestione origini dati | x |  |  |  | Consente di accedere ad Admin > All admin > Data Sources (Amministrazione > Tutte le attività di amministrazione > Origini dati nella navigazione superiore di Analytics). Richiede l’elemento di autorizzazione “Gestione suite di rapporti”. |
| Metriche predefinite | x |  |  |  | Consente di accedere a Impostazioni suite di rapporti singole > Metriche predefinite in Report Suite Manager. |
| Escludi per indirizzo IP | x |  |  |  | Consente di accedere ad Amministratore > Escludi per IP nella navigazione superiore di Analytics. |
| Metodi di ricerca | x |  |  |  | Consente l’accesso a Conversione > Metodi di ricerca in Report Suite Manager. |
| Variabili elenco | x |  |  |  | Consente l’accesso a Conversione > Elenco variabili in Report Suite Manager. |
| Personalizzazione del menu | x |  |  |  | Consente di accedere a Generale > Personalizza menu in Report Suite Manager. |
| Ricerca a pagamento | x |  |  |  | Consente di accedere a Generale > Rilevamento ricerca a pagamento in Report Suite Manager. |
| Regole di elaborazione | x |  |  |  | Consente l’accesso a Generale > Regole di elaborazione e Generale > Regole bot in Report Suite Manager. |
| Configurazione rapporti in tempo reale | x |  |  |  | Consente l’accesso in tempo reale in Report Suite Manager. Utilizzare la voce di autorizzazione “Rapporto in tempo reale” per concedere l’accesso al report stesso. |
| Gestione delle suite di rapporti | x |  |  |  | Consente l’accesso a Report Suite Manager, ma non consente alcuna modifica. |
| Eventi di successo | x |  |  |  | Consente di accedere a Conversione > Eventi di successo in Report Suite Manager. |
| Variabili di traffico | x |  |  |  | Consente l’accesso a Traffico > Variabili di traffico in Report Suite Manager. |
| Visitatore univoco | x |  |  |  | Consente l’accesso a Conversione > Variabile visitatore univoco. Non viene generalmente utilizzato nelle implementazioni moderne. |
| Filtri URL | x |  |  |  | Consente l’accesso a Generali > Filtri URL interni in Report Suite Manager. |
| Rilevamento delle anomalie |  | x |  |  | Consente l’accesso al rilevamento delle anomalie in Analysis Workspace. |
| Analisi contributi |  | x |  |  | Consente di accedere al menu di scelta rapida “Esegui analisi contributi” in Analysis Workspace. |
| Rapporto Data Warehouse personalizzato |  | x |  |  | Consente di accedere a Strumenti > Data Warehouse nella navigazione superiore di Analytics. |
| Pagine bot |  |  | x |  | Consente di accedere al report Metriche del sito > Bots > Pagine bot in Reports &amp; Analytics. |
| Bot |  |  | x |  | Consente di accedere al report Metriche del sito > Bots > Bots in Reports &amp; Analytics. |
| Rapporto canale |  |  | x |  | Consente l’accesso a Canali di marketing > Report panoramica canale in Reports &amp; Analytics. |
| Visite giornaliere di ritorno |  |  | x |  | Consente di accedere a Conservazione dei visitatori > Visite giornaliere di ritorno in Reports &amp; Analytics. |
| I miei rapporti consigliati |  |  | x |  | Consente di accedere a Metriche del sito > I miei rapporti consigliati in Reports &amp; Analytics. |
| Rapporto in tempo reale |  |  | x |  | Consente di accedere a Metriche del sito > In tempo reale in Reports &amp; Analytics. Utilizza l’elemento di autorizzazione “Configurazione report in tempo reale” per concedere l’accesso per impostare questo report. |
| Visite di ritorno |  |  | x |  | Consente di accedere a Conservazione dei visitatori > Visite di ritorno in Reports &amp; Analytics. |
| Configurazione di Advertising Analytics |  |  |  | x | Non utilizzato. |
| Report di riepilogo della società |  |  |  | x | Non utilizzato. |
| Data Warehouse |  |  |  | x | Non utilizzato. Utilizza invece “Rapporto Data Warehouse personalizzato”. |
| Immagine |  |  |  | x | Non utilizzato. |
| Report KPI/Gage |  |  |  | x | Non utilizzato. |
| Ultimi 100 visitatori |  |  |  | x | Non utilizzato. |
| ClickMap legacy |  |  |  | x | Non utilizzato. In alternativa, utilizza Activity Map in Strumenti di Analytics. |
| Installazione legacy di ClickMap |  |  |  | x | Non utilizzato. In alternativa, utilizza Activity Map in Strumenti di Analytics. |
| Report Panoramica dell’app mobile |  |  |  | x | Non utilizzato. |
| Totali nelle suite di rapporti |  |  |  | x | Non utilizzato. |
| Suite di rapporti (lettura) |  |  |  | x | Non utilizzato. |
| Suite di rapporti (scrittura) |  |  |  | x | Non utilizzato. |
| Site Catalyst |  |  |  | x | Non utilizzato. Al suo posto, utilizza “Accesso ad Analysis Workspace”. |
| Social |  |  |  | x | Non utilizzato. |
| Reportlet testo |  |  |   | x | Non utilizzato. |
| Gestione traffico |  |  |  | x | Non utilizzato. |
| Reportlet riepilogo utilizzo |  |  |  | x | Non utilizzato. |
| Impostazioni video |  |  |  | x | Non utilizzato. |
| Risorse web |  |  |  | x | Non utilizzato. |

{style="table-layout:auto"}

## Strumenti di Analytics

| Strumento di Analytics | Amministrazione | Controlli di accesso | Funzioni solo rapporti | Obsoleto | Descrizione |
| --- | --- | --- | --- | --- | --- |
| Gestione codici | x |  |  |  | Mantenuto per scopi legacy. Consente di accedere ad Admin > All admin > Code manager (Amministrazione > Tutte le attività di amministrazione > Gestione codici). Nella maggior parte dei casi, utilizza le librerie incluse nell’estensione Adobe Analytics in Raccolta dati di Adobe Experience Platform. |
| Gestione codici - Servizi web | x |  |  |  | Consente di accedere a Gestione codici tramite l’API 1.4. |
| Nascondere suite di rapporti | x |  |  |  | Consente di accedere ad Admin > All admin > Company settings > Hide Report Suites (Amministrazione > Tutte le attività di amministrazione > Impostazioni società > Nascondi suite di rapporti). Consente di nascondere qualsiasi suite di rapporti nell’organizzazione, indipendentemente dall’accesso alla suite di rapporti. |
| Integrazioni (creare) | x |  |  |  | Consente di accedere ad Admin > All admin > Data connectors (Amministrazione > Tutte le attività di amministrazione > Connettori dati) e di creare connettori dati. |
| Integrazioni (eliminare) | x |  |  |  | Consente di accedere ad Admin > All admin > Data connectors (Amministrazione > Tutte le attività di amministrazione > Connettori dati) e di eliminare i connettori dati. |
| Integrazioni (aggiornamento) | x |  |  |  | Consente di accedere ad Admin > All admin > Data connectors (Amministrazione > Tutte le attività di amminsitrazione > Connettori dati) e di modificare le configurazioni dei connettori esistenti. |
| Registri | x |  |  |  | Consente di accedere ad Admin > All admin > Log (Amministrazione > Tutte le attività di amministrazione > Registri). |
| Registri - Servizi Web | x |  |  |  | Consente di accedere ai registri di pull tramite l’API 1.4. |
| Azioni in sospeso | x |  |  |  | Consente di accedere ad Admin > All admin > Company settings > Pending Actions (Amministrazione > Tutte le attività di amministrazione > Impostazioni società > Azioni in sospeso). |
| Sicurezza | x |  |  |  | Consente di accedere ad Admin > All admin > Company settings > Security Manager (Amministrazione > Tutte le attività di amministrazione > Impostazioni società > Gestione sicurezza). |
| Utilizzo chiamate al server | x |  |  |  | Consente di accedere ad Admin > Server call usage (Amministrazione > Utilizzo chiamate al server). |
| Supporto | x |  |  |  | Consente di accedere ad Admin > All admin > Company settings > Support Information (Amministrazione > Tutte le attività di amministrazione > Impostazioni società > Informazioni di supporto). |
| Gestione traffico | x |  |  |  | Consente di accedere ad Admin > All admin > Traffic management (Amministrazione > Tutte le attività di amministrazione > Gestione traffico). |
| Servizi web | x |  |  |  | Consente di accedere ad Admin > All admin > Company settings > Web Services (Amministrazione > Tutte le attività di amministrazione > Impostazioni società > Servizi web). |
| Condividere Collegamenti Al Progetto Con Chiunque | x |  |  |  | Consente agli utenti di condividere con chiunque nell&#39;ambito di un progetto Workspace -> Condividere -> Condividere con chiunque. |
| Activity Map |  | x |  |  | Consente di accedere a Tools > Activity Map (Strumenti > Activity Map). Consente di utilizzare l’estensione Activity Map. |
| Utenti con licenza Ad Hoc Analysis |  | x |  |  | Ad Hoc Analysis è stato terminato. [Ulteriori informazioni](https://spark.adobe.com/page/S9Bhp66VJ2fEn/). |
| Accesso ad Analysis Workspace |  | x |  |  | Consente di accedere ad Analysis Workspace. Per utilizzare Adobe Analytics, gli utenti devono appartenere a questo gruppo (preferito) o al gruppo Accesso a Reports &amp; Analytics. |
| Analysis Workspace: Salva come modello |  | x |  |  | Consente di accedere a Progetto > Salva come modello in Analysis Workspace. |
| Creazione di metriche calcolate |  | x |  |  | Consente di creare metriche calcolate in tutte le funzionalità di Analytics. |
| Accesso a Labs |  | x |  |  | Consente di accedere a Labs. |
| Report Builder |  | x |  |  | Abilita il pulsante di download in Strumenti > Report Builder e consente di eseguire l’autenticazione in Microsoft Excel. |
| Creazione di segmenti |  | x |  |  | Consente di creare e condividere segmenti in tutte le funzionalità di Analytics. |
| Pubblicazione dei segmenti |  | x |  |  | Consente di usare un segmento come pubblico Experience Cloud durante la creazione o la modifica di un segmento. |
| Accesso al servizio web |  | x |  |  | Consente di utilizzare l’API, inclusa l’autenticazione con siti di terze parti e l’invio di chiamate API. |
| Dati correnti |  |  | x |  | Abilita l’opzione per visualizzare i dati correnti nei rapporti di Reports &amp; Analytics. |
| Accesso a Reports &amp; Analytics |  |  | x |  | Consente di accedere a Reports &amp; Analytics. Per utilizzare Adobe Analytics, gli utenti devono appartenere a questo gruppo o al gruppo Accesso ad Analysis Workspace (opzione preferita). |
| Gestione di Advertising Analytics |  |  |  | x | Non utilizzato. |
| Co-branding |  |  |  | x | Non più utilizzato. Consente di accedere ad Admin > All admin > Company settings > Co-Branding (Amministrazione > Tutte le attività di amministrazione > Impostazioni società > Co-branding). |
| Utenti con licenza Excel |  |  |  | x | Non utilizzato. |
| Amministrazione app mobili |  |  |  | x | Non utilizzato. |
| Gestione autorizzazioni |  |  |  | x | Non più utilizzato. Consente di accedere all’interfaccia di gestione utenti legacy in Admin > All admin > User management (Amministrazione > Tutte le attività di amministrazione > Gestione utenti). |
| Autorizzazioni (lettura) - Servizi web |  |  |  | x | Non più utilizzato. Consente di visualizzare le autorizzazioni legacy di Analytics utilizzando l’API di amministrazione. Al suo posto, utilizza Adobe Admin Console. |
| Autorizzazioni (scrittura) - Servizi web |  |  |  | x | Non più utilizzato. Consente di modificare le autorizzazioni legacy di Analytics utilizzando l’API di amministrazione. Al suo posto, utilizza Adobe Admin Console. |
| Preferenze |  |  |  | x | Non utilizzato. |
| Single Sign-On |  |  |  | x | Non più utilizzato. Consente di accedere al servizio Single Sign-On obsoleto. |

{style="table-layout:auto"}