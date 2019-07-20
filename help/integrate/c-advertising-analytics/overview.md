---
description: nulle
seo-description: nulle
seo-title: Panoramica sulla pubblicità di Analytics
title: Panoramica sulla pubblicità di Analytics
uuid: 00 e 461 ff -3 e 17-4071-818 b -93 fd 1 e 4 b 36 f 1
translation-type: tm+mt
source-git-commit: e3b1ac3139f26ca3a97f3d2228276e690ec4cb79

---


# Panoramica sulla pubblicità di Analytics

Analisi pubblicità consente di visualizzare tutti i dati Google e Bing Paid Search, affiancati, all'interno di Adobe Analytics. In precedenza, eventuali dati Google adwords/DFA o Microsoft Bing Ads dovevano essere visualizzati in Adobe Advertising Cloud (AMO) o in Google/Bing. In Adobe Analytics sono ora disponibili i seguenti dati: Impression, clic, costi, punteggio di qualità e posizione media direttamente dai motori di ricerca e da istanze ID di AMO (fate clic su Istanze).

>[!NOTE]
>
>Yahoo Gemini è stato assorbito da Microsoft Bing il 31 marzo 2019. Di conseguenza, l’opzione per l’account per annunci Yahoo Gemini non è più disponibile.

Inserendo i dati di questi motori di ricerca in Adobe Analytics, puoi analizzare gli stessi dati utilizzando la potenza di Analysis Workspace. A new [Paid Search Performance](../../integrate/c-advertising-analytics/c-adanalytics-workflow/aa-report-ad-data-an.md#concept_E29B25BEE60C4A64B66E9255D7612254) template in Workspace facilitates this analysis.

![](assets/aa_aw.png)

Questa integrazione è indirizzata ai seguenti tipi di pubblico:

* **Analista** che deve raccogliere i rapporti sulle prestazioni per Marketing Search Marketer.
* The **Paid Search Marketer** who seeks answers to these questions: How much traffic am I sending to our site and are customers converting? Quali sono le campagne pubblicitarie convenienti?

## Prerequisiti {#section_C25E0CA3474C4EDEAEAA9A5B8AAC9299}

* Advertising Analytics is available for Adobe Analytics [Select](https://www.adobe.com/data-analytics-cloud/analytics/select.html), [Prime](https://www.adobe.com/data-analytics-cloud/analytics/prime.html), and [Ultimate](https://www.adobe.com/data-analytics-cloud/analytics/ultimate.html) SKUs only.

* Questa funzionalità è disponibile per i clienti non-Advertising Cloud e non AMO.
* Per poter accedere ad Analytics pubblicitari, devi essere un amministratore di Adobe Analytics. Subsequently, you can [grant access permissions](../../integrate/c-advertising-analytics/overview.md#section_FCC58EB635954A32990D4E67B52B4369) to non-admins.
* Any Analytics report suite where you want to view Google/Bing search data has to be [mapped to your Experience Cloud organization](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html).
* For any report suite where you want to view Google/Bing search data, you must [enable those report suite/s for Advertising Analytics](../../integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md#concept_BE491B2A2CAE4D818C218033B985A0FB) ( **[!UICONTROL Admin]** &gt; **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Advertising Analytics Configuration]**).

* Per un utente con autorizzazioni di accesso, dovete disporre delle credenziali di accesso all'account di ricerca che desiderate integrare con Adobe Analytics, ad esempio un ID account Google e una password.
* Nel caso di Bing Ads, è necessario anche l'ID cliente Bing.
* If you use Internet Explorer 11 (or earlier), you will not be able to successfully [set up an advertising account](../../integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md#concept_1958E8C15C334E8B9DC510EC8D5DCA7C) for any of the three search engines. Utilizzare invece altri browser Web.

## Advertising Analytics Permissions {#section_FCC58EB635954A32990D4E67B52B4369}

Analytics dispone di due autorizzazioni concesse automaticamente agli amministratori di Analytics. Gli amministratori possono quindi scegliere di concedere queste autorizzazioni a non amministratori.

<table id="table_86256AD8B4554F369439A8FDF2F545E1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Autorizzazione </th> 
   <th colname="col2" class="entry"> Definizione </th> 
   <th colname="col3" class="entry"> Concedere l'autorizzazione all'interno di Adobe Analytics </th> 
   <th colname="col4" class="entry"> Concedere l'autorizzazione se hai effettuato l'accesso ad Adobe Experience Cloud </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Gestione analisi analisi </p> </td> 
   <td colname="col2"> <p>Consente agli utenti di configurare/modificare/visualizzare gli account di ricerca pubblicitari. </p> </td> 
   <td colname="col3"><span class="ignoretag"><span class="uicontrol"> Amministratore</span> &gt; <span class="uicontrol"> Gestione</span> utente &gt; <span class="uicontrol"> Gruppi</span> &gt; <span class="uicontrol"> Modifica accesso a tutti i rapporti</span> &gt; <span class="uicontrol"> Personalizza strumenti</span> Analytics &gt; <span class="uicontrol"> Gestione analisi pubblicità</span></span> </td> 
   <td colname="col4"><span class="ignoretag"><span class="uicontrol"> Accedi a adminconsole.adobe.com</span> &gt; <span class="uicontrol"> Prodotti</span> &gt; Profilo <span class="uicontrol"> di prodotto</span> &gt; <span class="uicontrol"> scheda Autorizzazioni</span> &gt; <span class="uicontrol"> Strumenti</span> Analytics &gt; <span class="uicontrol"> Gestione annunci pubblicitari</span></span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Configurazione analisi analisi </p> </td> 
   <td colname="col2"> <p>Consente agli utenti di configurare suite di rapporti per il provisioning per Analytics pubblicitario. </p> </td> 
   <td colname="col3"><span class="ignoretag"><span class="uicontrol"> Amministratore</span> &gt; <span class="uicontrol"> Gestione</span> utente &gt; <span class="uicontrol"> Gruppi</span> &gt; <span class="uicontrol"> Modifica accesso a tutti i rapporti</span> &gt; <span class="uicontrol"> Personalizza strumenti</span> suite di rapporti &gt; <span class="uicontrol"> Configurazione analisi annunci</span></span> </td> 
   <td colname="col4"><span class="ignoretag"><span class="uicontrol"> Accedi a adminconsole.adobe.com</span> &gt; <span class="uicontrol"> Prodotti</span> &gt; Profilo <span class="uicontrol"> di prodotto</span> &gt; <span class="uicontrol"> scheda Autorizzazioni</span> &gt; <span class="uicontrol"> Strumenti suite di rapporti</span> &gt; <span class="uicontrol"> Configurazione analisi annunci</span></span> </td> 
  </tr> 
 </tbody> 
</table>

## Advertising Analytics Dimensions and Metrics {#section_C0DF4A08EA9E46ADABE9E465AFC11E32}

Analisi pubblicità aggiunge le dimensioni e le metriche seguenti ad Analysis Workspace, Reporting e analisi, Generatore di report e l'API di reporting di Analytics.

**Dimensioni**

>[!IMPORTANT]
>
>Questa integrazione crea un nuovo set di dimensioni tramite classificazioni della variabile AMO ID. Queste nuove dimensioni non influiscono o modificano i canali di marketing esistenti o le dimensioni variabili di tracciamento campagna. L'ID AMO è connesso al profilo di un visitatore quando un visitatore accede sul sito da un annuncio di ricerca a pagamento. Di conseguenza, le dimensioni AMO possono essere utilizzate per suddividere le metriche AMO fornite dall'integrazione così come i dati acquisiti a valle dal visitatore (visite, visitatori, visualizzazioni pagina, tassi rimbalzi, ordini, entrate, eventi personalizzati, ecc…). Possono anche essere suddivisi per altre dimensioni durante il reporting su altre metriche onsite.
>
>Le classificazioni per queste metriche vengono aggiornate ogni giorno. Pertanto, se apportate modifiche ai metadati in un motore di ricerca, potrebbe non essere visualizzato che le modifiche si riflettono fino al giorno successivo quando le classificazioni vengono aggiornate.

| Nome classificazione (Dimensione) | Definizione |
|--- |--- |
| Tipo di corrispondenza delle parole chiave (AMO ID) | Tipo di corrispondenza parola chiave. I valori in genere saranno ampi, frasi, esatto o nessun valore se il tipo di annuncio non ha un tipo di corrispondenza. |
| Piattaforma annunci (AMO ID) | Il nome del motore di ricerca. I valori possono includere Google adwords o Microsoft Bing Ads. |
| Account (AMO ID) | Nome dell'account del motore di ricerca tracciato. |
| Campagna (AMO ID) | Nome della campagna nell'account del motore di ricerca. |
| Gruppi di annunci (AMO ID) | Nome del gruppo di annunci nelle campagne del motore di ricerca. |
| Annunci (AMO ID) | Titolo annuncio + Descrizione annuncio utilizzata nell'annuncio. |
| Parola chiave (ID AMO) | Il valore Parola chiave dall'account del motore di ricerca |
| Tipo di corrispondenza (ID AMO) | Tipo di corrispondenza parola chiave assegnato alla parola chiave. I valori in genere saranno ampi, frasi, esatto o nessun valore se il tipo di annuncio non ha un tipo di corrispondenza. |
| Tipo di annuncio (AMO ID) | Tipo di annuncio in uso, in genere «Testo ad». |
| Titolo annuncio (ID AMO) | L'oggetto Titolo utilizzato nell'annuncio. |
| Descrizione annuncio (ID AMO) | L'oggetto Annuncio pubblicitario utilizzato nell'annuncio. |
| URL visualizzazione annunci (AMO) | L'oggetto URL di visualizzazione annunci utilizzato nell'annuncio. |
| URL destinazione annuncio (ID AMO) | URL della pagina di destinazione o URL finale assegnato all'annuncio. |
| Rete (ID AMO) | La rete sulla quale viene distribuito l'annuncio. Per Analytics pubblicitario, questo valore è sempre «Cerca». |
| Placement (AMO ID) | Sito Web postplacement gestito (per le reti di contenuto). Solo le placche gestite utilizzano questa dimensione. |
| Target di prodotto (AMO) | Nome della destinazione di prodotto utilizzata sugli annunci PLA (non sul prodotto acquistato). |
| Ottimizzazione (ID AMO) | Questa funzione non viene utilizzata da Analisi pubblicità. Viene utilizzata solo dai clienti di Advertising Cloud. |
| Dispositivo (ID AMO) | Non utilizzato oggi. Segnaposto per un potenziale miglioramento del prodotto futuro al tipo di dispositivo di destinazione (ad es. mobile, desktop) di annuncio (non il dispositivo effettivo del visitatore). |

**Metriche**

>[!IMPORTANT]
>
>Le metriche fornite da Analisi della pubblicità (elencate di seguito) sono dati a livello di riepilogo dai motori di ricerca. Non sono collegati ai profili dei visitatori di Analytics. Sono connessi solo alla variabile AMO ID e alle relative dimensioni di classificazione. Pertanto, non devono essere segnalati per dimensioni/segmenti diversi da quelli basati sulle dimensioni ID AMO. In tal modo, Analytics potrebbe visualizzare degli zeri per i dati. Puoi includerli nelle metriche calcolate con altre metriche, ma anche queste metriche calcolate devono essere suddivise solo dalle dimensioni ID di AMO.
>
>Queste metriche sono dati ricavati su base giornaliera, pertanto non avranno dati per il giorno corrente. Inoltre, non devono essere segnalati su una granularità inferiore al giorno.
>
>Esiste una metrica di Istanze ID AMO impostata quando l'ID AMO è impostato su una pagina di destinazione (ad es. un clickthrough). Questa metrica viene acquisita in tempo reale con l'hit della pagina di destinazione ed è disponibile per le suddivisioni con altre dimensioni anche sulla pagina di destinazione.

| Nome della metrica | Definizione |
|--- |--- |
| AMO Impression | Il numero di ad impression come indicato dal motore di ricerca. |
| AMO Click | Il numero di clic su annunci segnalati dal motore di ricerca. |
| AMO Costo | Costo pagato per ogni parola chiave/annuncio indicato dal motore di ricerca. |
| Avg. Pos | Una metrica calcolata che riflette la posizione media degli annunci segnalati dal motore di ricerca. |
| Avg. Punteggio di qualità | Una metrica calcolata che riflette la valutazione media di qualità indicata dal motore di ricerca. |