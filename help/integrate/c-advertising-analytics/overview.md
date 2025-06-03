---
description: Scopri tutto quello che puoi fare con Advertising Analytics, comprese le autorizzazioni richieste e le dimensioni e le metriche disponibili.
title: Advertising Analytics
feature: Advertising Analytics
exl-id: bc18b74a-0317-4871-b2e0-ec0977ef1731
source-git-commit: 6bedfb9b1333a442bf17cf71dad1e0883b97fd45
workflow-type: tm+mt
source-wordcount: '1007'
ht-degree: 78%

---

# Advertising Analytics

Advertising Analytics ti consente di visualizzare tutti i tuoi dati di ricerca a pagamento Google Ads e Microsoft Advertising in Adobe Analytics. In precedenza, qualsiasi dato di Google Ads o Microsoft Advertising doveva essere visualizzato in Adobe Advertising Cloud (AMO) o in ogni rispettiva interfaccia pubblicitaria. Ora è possibile ottenere dati su impression, clic e costi direttamente dai motori di ricerca e dalle istanze AMO ID (Istanze di clic).

Riunendo i dati di questi motori di ricerca in Adobe Analytics è possibile analizzarli servendosi della potenza di Analysis Workspace. L’analisi è facilitata da un nuovo modello di [Prestazioni di Paid Search](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-report-ad-data-an.md) in Workspace.

![](assets/aa_aw.png)

Questa integrazione è destinata ai seguenti tipi di pubblico:

* L’**analista** incaricato di raccogliere i rapporti sulle prestazioni per l’esperto di Paid Search Marketing.
* L’**esperto di Paid Search Marketing** che cerca le risposte alle seguenti domande: quanto traffico sto inviando al sito? I clienti si stanno convertendo? Quali sono le mie campagne pubblicitarie più redditizie?


## Prerequisiti {#prerequisites}

* Advertising Analytics è disponibile solo per gli SKU di Adobe Analytics [Select](https://www.adobe.com/it/data-analytics-cloud/analytics/select.html), [Prime](https://www.adobe.com/it/data-analytics-cloud/analytics/prime.html) e [Ultimate](https://www.adobe.com/it/data-analytics-cloud/analytics/ultimate.html).
* Questa funzionalità è disponibile per chi non è cliente Advertising Cloud e AMO.
* Devi essere un amministratore di Adobe Analytics per poter accedere ad Advertising Analytics o appartenere a un profilo di prodotto a cui è stato concesso l&#39;[accesso](/help/integrate/c-advertising-analytics/overview.md#permissions) ad Advertising Analytics.
* Per ogni suite di rapporti in cui desideri visualizzare i dati di ricerca di Google Ads o Microsoft Advertising, devi [abilitare le suite di rapporti per Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md) ( **[!UICONTROL Admin]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Advertising Analytics Configuration]**).
* È necessario disporre di credenziali di accesso per utenti con autorizzazioni di modifica per gli account di ricerca che si desidera integrare con Adobe Analytics, ad esempio l’ID e la password di un account Google.
* Nel caso di Microsoft Advertising, sono necessari anche [[!UICONTROL Account ID] e [!UICONTROL Manager Account ID]](c-adanalytics-workflow/aa-locate-account-id.md).

## Autorizzazioni Advertising Analytics {#permissions}

Analytics dispone di due autorizzazioni che vengono concesse automaticamente agli amministratori di Analytics. Gli amministratori possono quindi scegliere di concedere queste autorizzazioni agli utenti non amministratori.

| Autorizzazione | Definizione | Concedere l’autorizzazione se è stato effettuato l’accesso ad Adobe Experience Cloud |
| --- | --- | --- |
| Gestione di Advertising Analytics | Consente agli utenti di configurare, modificare e visualizzare gli account per annunci e di ricerca. | Accedi a [adminconsole.adobe.com](https://adminconsole.adobe.com) > [!UICONTROL Products] > [!UICONTROL Adobe Analytics] > [!UICONTROL Product Profile] > scheda [!UICONTROL Permissions] > [!UICONTROL Analytics Tools] > [!UICONTROL Advertising Analytics Management] |
| Configurazione di Advertising Analytics | Consente agli utenti di configurare suite di rapporti su cui effettuare il provisioning per Advertising Analytics. | Accedi a [adminconsole.adobe.com](https://adminconsole.adobe.com) > [!UICONTROL Products] > [!UICONTROL Adobe Analytics] > [!UICONTROL Product Profile] > scheda [!UICONTROL Permissions] > [!UICONTROL Analytics Tools] > [!UICONTROL Advertising Analytics Configuration] |

## Dimensioni e metriche di Advertising Analytics {#dimensions-metrics}

Advertising Analytics aggiunge le dimensioni e le metriche seguenti ad Analysis Workspace, Report Builder e all’API di reporting di Analytics.

### Dimensioni

>[!IMPORTANT]
>
>Questa integrazione crea un nuovo set di dimensioni attraverso classificazioni della variabile AMO ID. Le nuove dimensioni non influiscono né modificano i canali di marketing esistenti o le dimensioni variabili di tracciamento delle campagne. L’AMO ID è connesso al profilo di un visitatore quando questo arriva sul sito da un annuncio di ricerca a pagamento. Di conseguenza, le dimensioni AMO possono essere utilizzate per suddividere sia le metriche AMO fornite da questa integrazione che i dati acquisiti a valle dal visitatore (visite, visitatori, visualizzazioni di pagina, frequenza di rimbalzo, ordini, ricavi, eventi personalizzati, ecc.). È possibile suddividere questi dati anche per altre dimensioni quando si generano rapporti su altre metriche nel sito.
>
>Le classificazioni per queste metriche vengono aggiornate ogni giorno. Pertanto, se si apportano modifiche ai metadati in un motore di ricerca, tali modifiche potrebbero non essere visibili fino al giorno successivo nel momento in cui le classificazioni vengono aggiornate.

| Nome classificazione (dimensione) | Definizione |
| --- | --- |
| **[!UICONTROL Keyword MatchType (AMO ID)]** | Il tipo di corrispondenza delle parole chiave. Il tipo di corrispondenza può essere generico, a frase, esatto o nullo se il tipo di annuncio non ha un tipo di corrispondenza. |
| **[!UICONTROL Ad Platform (AMO ID)]** | Il nome del motore di ricerca. I valori possono includere Google AdWords o Microsoft Bing Ads. |
| **[!UICONTROL Account (AMO ID)]** | Il nome dell’account del motore di ricerca che viene tracciato. |
| **[!UICONTROL Campaign (AMO ID)]** | Il nome della campagna nell’account del motore di ricerca. |
| **[!UICONTROL Ad Group (AMO ID)]** | Il nome del gruppo di annunci nelle campagne del motore di ricerca. |
| **[!UICONTROL Ad (AMO ID)]** | Il titolo e la descrizione usati nell’annuncio. |
| **[!UICONTROL Keyword (AMO ID)]** | Il valore della parola chiave dall’account del motore di ricerca. |
| **[!UICONTROL Match Type (AMO ID)]** | Tipo di corrispondenza assegnato alla parola chiave. Il tipo di corrispondenza può essere generico, a frase, esatto o nullo se il tipo di annuncio non ha un tipo di corrispondenza. |
| **[!UICONTROL Ad Type (AMO ID)]** | Il tipo di annuncio che viene distribuito, che in genere è “Annuncio di testo”. |
| **[!UICONTROL Ad Title (AMO ID)]** | L’oggetto titolo utilizzato nell’annuncio. |
| **[!UICONTROL Ad Description (AMO ID)]** | L’oggetto descrizione utilizzato nell’annuncio. |
| **[!UICONTROL Ad Display URL (AMO ID)]** | L’oggetto URL di visualizzazione utilizzato nell’annuncio. |
| **[!UICONTROL Ad Destination URL (AMO ID)]** | L’URL della pagina di destinazione o l’URL finale assegnato all’annuncio. |
| **[!UICONTROL Network (AMO ID)]** | La rete su cui viene servito l’annuncio. Per Advertising Analytics questo valore è sempre “Search”. |
| **[!UICONTROL Placement (AMO ID)]** | Il sito web di posizionamento gestito (per le reti di contenuti). Questa dimensione viene utilizzata solo per i posizionamenti gestiti. |
| **[!UICONTROL Product Target (AMO ID)]** | Nome del target di prodotto utilizzato sugli annunci PLA (non il prodotto effettivamente acquistato). |
| **[!UICONTROL Optimization (AMO ID)]** | Questa dimensione non viene utilizzata da Advertising Analytics, ma solo dai clienti di Advertising Cloud. |
| **[!UICONTROL Device (AMO ID)]** | Non è in uso al momento. È un segnaposto per un potenziale miglioramento futuro del prodotto per il tipo di dispositivo di destinazione indicato dell’annuncio (ad es. mobile, desktop), non il dispositivo effettivo del visitatore. |

### Metriche

>[!IMPORTANT]
>
>Le metriche fornite da Advertising Analytics (elencate di seguito) sono dati di riepilogo provenienti dai motori di ricerca. Non sono connesse ai profili visitatore di Analytics. Sono collegate solo alla variabile AMO ID e alle dimensioni di classificazione associate a essa. Di conseguenza, non devono essere segnalate da dimensioni/segmenti diversi da quelli basati sulle dimensioni dell’AMO ID. Fare ciò porterebbe Analytics a mostrare degli zeri in corrispondenza dei dati. Puoi includerle nelle metriche calcolate con altre metriche, ma anche queste ultime devono essere suddivise solo per le dimensioni dell’AMO ID.
>
>Queste metriche sono dati originati su base giornaliera, pertanto non contengono dati per il giorno corrente. Inoltre, non devono essere segnalate con una granularità inferiore a quella giornaliera.
>
>Esiste una metrica Istanze AMO ID che viene attivata quando l’AMO ID è impostato su una pagina di destinazione (ad esempio un clickthrough). Questa metrica viene acquisita in tempo reale con l’hit della pagina di destinazione ed è disponibile per raggruppamenti con altre dimensioni impostate a loro volta sulla pagina di destinazione.

| Nome della metrica | Definizione |
| --- | --- |
| **[!UICONTROL AMO Impressions]** | Il numero di ad impression riportato dal motore di ricerca. |
| **[!UICONTROL AMO Clicks]** | Il numero di clic sugli annunci riportato dal motore di ricerca. |
| **[!UICONTROL AMO Cost]** | Il costo di ogni parola chiave/annuncio riportato dal motore di ricerca. |
