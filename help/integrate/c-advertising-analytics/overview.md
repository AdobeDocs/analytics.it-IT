---
description: nulle
seo-description: nulle
seo-title: Panoramica su Advertising Analytics
title: Panoramica su Advertising Analytics
uuid: 00e461ff-3e17-4071-818b-93fd1e4b36f1
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Panoramica su Advertising Analytics

Analisi della pubblicità consente di visualizzare i dati Google e Bing Paid Search affiancati, in Adobe Analytics. In precedenza, qualsiasi dato di Google AdWords/DFA o Microsoft Bing Ads doveva essere visualizzato in Adobe Advertising Cloud (AMO) o in Google/Bing. Ora riceverai i seguenti dati in Adobe Analytics: Impressioni, clic, costi, punteggio di qualità e posizione media direttamente dai motori di ricerca, nonché dalle istanze di ID AMO (fate clic su Istanze).

> [!NOTE] Yahoo Gemini è stato assorbito da Microsoft Bing il 31 marzo 2019. Di conseguenza, l’opzione per l’account per annunci Yahoo Gemini non è più disponibile.

Riunendo i dati di questi motori di ricerca in Adobe Analytics, puoi analizzare gli stessi dati utilizzando l’efficacia di Analysis Workspace. Un nuovo modello di prestazioni [della ricerca a](../../integrate/c-advertising-analytics/c-adanalytics-workflow/aa-report-ad-data-an.md#concept_E29B25BEE60C4A64B66E9255D7612254) pagamento in Workspace facilita l’analisi.

![](assets/aa_aw.png)

Questa integrazione è destinata ai seguenti tipi di pubblico:

* L’ **analista** che deve raccogliere i rapporti sulle prestazioni per l’esperto di marketing di ricerca a pagamento.
* L’ **esperto di marketing** per la ricerca a pagamento cerca le risposte alle seguenti domande: Quanto traffico sto inviando al nostro sito e i clienti stanno convertendo? Quali sono le mie campagne pubblicitarie a costi contenuti?

## Prerequisiti {#section_C25E0CA3474C4EDEAEAA9A5B8AAC9299}

* Analisi della pubblicità è disponibile solo per gli SKU Adobe Analytics [Select](https://www.adobe.com/data-analytics-cloud/analytics/select.html), [Prime](https://www.adobe.com/data-analytics-cloud/analytics/prime.html)e [Ultimate](https://www.adobe.com/data-analytics-cloud/analytics/ultimate.html) .

* Questa funzionalità è disponibile per i clienti non-Advertising Cloud e non-AMO.
* Per poter accedere ad Analisi della pubblicità, devi essere un amministratore di Adobe Analytics. Successivamente, potete [concedere autorizzazioni](../../integrate/c-advertising-analytics/overview.md#section_FCC58EB635954A32990D4E67B52B4369) di accesso agli utenti non amministratori.
* Qualsiasi suite di rapporti Analytics in cui desideri visualizzare i dati di ricerca Google/Bing deve essere [mappata alla tua organizzazione](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html)Experience Cloud.
* Per qualsiasi suite di rapporti in cui desideri visualizzare i dati di ricerca Google/Bing, devi [abilitare tali suite di rapporti per Analisi](../../integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md#concept_BE491B2A2CAE4D818C218033B985A0FB) pubblicitaria ( **[!UICONTROL Admin]** &gt; **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Advertising Analytics Configuration]**).

* È necessario disporre delle credenziali di accesso per un utente con autorizzazioni di modifica per gli account di ricerca che si desidera integrare con Adobe Analytics, ad esempio un ID account Google e una password.
* Nel caso di Bing Ads, è necessario anche il Bing Customer ID.
* Se si utilizza Internet Explorer 11 (o versioni precedenti), non sarà possibile [impostare correttamente un account](../../integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md#concept_1958E8C15C334E8B9DC510EC8D5DCA7C) pubblicitario per i tre motori di ricerca. Utilizzate altri browser Web.

## Autorizzazioni per l'analisi della pubblicità {#section_FCC58EB635954A32990D4E67B52B4369}

Analytics dispone di due autorizzazioni che vengono concesse automaticamente agli amministratori di Analytics. Gli amministratori possono quindi scegliere di concedere queste autorizzazioni agli utenti non amministratori.

<table id="table_86256AD8B4554F369439A8FDF2F545E1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Autorizzazione </th> 
   <th colname="col2" class="entry"> Definizione </th> 
   <th colname="col3" class="entry"> Concedere l'autorizzazione in Adobe Analytics </th> 
   <th colname="col4" class="entry"> Concedi l'autorizzazione se hai effettuato l'accesso ad Adobe Experience Cloud </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Gestione dell'analisi pubblicitaria </p> </td> 
   <td colname="col2"> <p>Consente agli utenti di configurare, modificare e visualizzare gli account di ricerca per la pubblicità. </p> </td> 
   <td colname="col3"><span class="ignoretag"><span class="uicontrol"> Amministratore</span> &gt; <span class="uicontrol"> Gestione</span> utente &gt; <span class="uicontrol"> Gruppi</span> &gt; <span class="uicontrol"> Modifica accesso</span> a tutti i rapporti &gt; <span class="uicontrol"> Personalizza strumenti</span> di Analytics &gt; Gestione <span class="uicontrol"> dell'analisi della pubblicità</span></span> </td> 
   <td colname="col4"><span class="ignoretag"><span class="uicontrol"> Accedete ad adminconsole.adobe.com</span> &gt; <span class="uicontrol"> Prodotti</span> &gt; <span class="uicontrol"> Profilo</span> di prodotto &gt; scheda <span class="uicontrol"> Autorizzazioni &gt;</span> Strumenti <span class="uicontrol"> di Analytics &gt; Gestione dell'analisi della</span> <span class="uicontrol"> pubblicità</span></span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Configurazione dell'analisi pubblicitaria </p> </td> 
   <td colname="col2"> <p>Consente agli utenti di configurare le suite di rapporti per il provisioning per Analisi della pubblicità. </p> </td> 
   <td colname="col3"><span class="ignoretag"><span class="uicontrol"> Admin</span> &gt; <span class="uicontrol"> User Management</span> &gt; <span class="uicontrol"> Groups</span> &gt; <span class="uicontrol"> Edit All Report Access (Modifica accesso</span> a tutti i rapporti) &gt; <span class="uicontrol"> Customize Report Suite Tools (Personalizza strumenti</span> delle suite di rapporti) &gt; <span class="uicontrol"> Advertising Analytics Configuration (Configurazione analisi pubblicità)</span></span> </td> 
   <td colname="col4"><span class="ignoretag"><span class="uicontrol"> Accedete ad adminconsole.adobe.com</span> &gt; <span class="uicontrol"> Prodotti</span> &gt; <span class="uicontrol"> Profilo</span> di prodotto &gt; scheda <span class="uicontrol"> Autorizzazioni &gt;</span> Strumenti <span class="uicontrol"> delle suite di rapporti &gt; Configurazione</span> <span class="uicontrol"> Analisi della pubblicità</span></span> </td> 
  </tr> 
 </tbody> 
</table>

## Metriche e dimensioni dell'analisi pubblicitaria {#section_C0DF4A08EA9E46ADABE9E465AFC11E32}

Analisi della pubblicità aggiunge le dimensioni e le metriche seguenti ad Analysis Workspace, Reporting e analisi, Generatore di report e API di reporting di Analytics.

**Dimensioni**

>[!IMPORTANT]
>
>Questa integrazione crea un nuovo set di dimensioni attraverso classificazioni della variabile ID AMO. Queste nuove dimensioni non influiscono né modificano i canali di marketing esistenti o le dimensioni variabili di tracciamento delle campagne. L'ID AMO è collegato al profilo di un visitatore quando il visitatore arriva sul sito da un annuncio di ricerca a pagamento. Di conseguenza, le dimensioni AMO possono essere utilizzate per suddividere sia le metriche AMO fornite da questa integrazione, sia i dati acquisiti a valle dal visitatore (visite, visitatori, visualizzazioni di pagina, tasso di rimbalzo, ordini, ricavi, eventi personalizzati, ecc.). Possono anche essere suddivisi per altre dimensioni quando si esegue il reporting su altre metriche on-site.
>
>Le classificazioni per queste metriche vengono aggiornate ogni giorno. Di conseguenza, se si apportano modifiche ai metadati in un motore di ricerca, tali modifiche potrebbero non essere visibili fino al giorno successivo in cui le classificazioni vengono aggiornate.

| Nome classificazione (dimensione) | Definizione |
|--- |--- |
| Tipo di corrispondenza delle parole chiave (AMO ID) | Il tipo di corrispondenza della parola chiave. I valori in genere sono ampi, espressi, esatti o nessun valore se il tipo di annuncio non ha un tipo di corrispondenza. |
| Piattaforma annunci (AMO ID) | Nome del motore di ricerca. I valori possono includere Google AdWords o Microsoft Bing Ads. |
| Account (AMO ID) | Nome dell’account del motore di ricerca che viene tracciato. |
| Campagna (AMO ID) | Nome della campagna nel vostro account del motore di ricerca. |
| Gruppi di annunci (AMO ID) | Nome del gruppo di annunci nelle campagne del motore di ricerca. |
| Annunci (AMO ID) | Titolo annuncio + Descrizione annuncio utilizzato sull'annuncio. |
| Parola chiave (ID AMO) | Il valore della parola chiave dall'account del motore di ricerca |
| Tipo di corrispondenza (ID AMO) | Tipo di corrispondenza parola chiave assegnato alla parola chiave. I valori in genere sono ampi, espressi, esatti o nessun valore se il tipo di annuncio non ha un tipo di corrispondenza. |
| Tipo di annuncio (AMO ID) | Il tipo di annuncio che viene distribuito, che in genere è "Text Ad". |
| Titolo annuncio (ID AMO) | L'oggetto Title utilizzato nell'annuncio. |
| Descrizione annuncio (AMO ID) | L'oggetto Ad Description utilizzato nel tuo annuncio. |
| URL visualizzazione annuncio (AMO ID) | L'oggetto URL di visualizzazione annuncio utilizzato nell'annuncio. |
| URL destinazione annuncio (AMO ID) | L'URL della pagina di destinazione o l'URL finale assegnato al tuo annuncio. |
| Rete (AMO ID) | La rete su cui viene servito l'annuncio. Per Analisi della pubblicità, questo valore è sempre "Search". |
| Posizionamento (ID AMO) | Il sito Web di posizionamento gestito (per le reti di contenuti). Questa dimensione viene utilizzata solo dai posizionamenti gestiti. |
| Destinazione prodotto (ID AMO) | Nome del target del prodotto utilizzato sugli annunci PLA (non il prodotto acquistato). |
| Ottimizzazione (ID AMO) | Non viene utilizzato da Advertising Analytics. Viene utilizzato solo dai clienti di Advertising Cloud. |
| Dispositivo (ID AMO) | Non usato oggi. Segnaposto per il potenziale miglioramento futuro del prodotto per il tipo di dispositivo di destinazione indicato (ad es. mobile, desktop) di annuncio (non il dispositivo effettivo del visitatore). |

**Metriche**

>[!IMPORTANT]
>
>Le metriche fornite da Analisi della pubblicità (elencate di seguito) sono dati di livello sintetico provenienti dai motori di ricerca. Non sono connessi ai profili visitatore di Analytics. Sono collegate solo alla variabile AMO ID e alle relative dimensioni di classificazione. Di conseguenza, non devono essere segnalate da dimensioni/segmenti diversi da quelli basati sulle dimensioni dell’ID AMO. In questo modo in Analytics verranno visualizzati degli zeri per i dati. Puoi includerli nelle metriche calcolate con altre metriche, ma anche queste metriche calcolate devono essere suddivise solo per le dimensioni dell’ID AMO.
>
>Queste metriche sono dati originati su base giornaliera, pertanto non avranno dati per il giorno corrente. Inoltre, non devono essere segnalati con una granularità inferiore a quella giornaliera.
>
>Esiste una metrica Istanze AMO ID che viene impostata quando l’ID AMO è impostato su una pagina di destinazione (ad es. un clic). Questa metrica viene acquisita in tempo reale con l’hit della pagina di destinazione ed è disponibile per le suddivisioni con altre dimensioni impostate anche sulla pagina di destinazione.

| Nome della metrica | Definizione |
|--- |--- |
| Impressioni AMO | Il numero di ad impression come riportato dal motore di ricerca. |
| Clic AMO | Il numero di clic sugli annunci come riportato dal motore di ricerca. |
| Costo AMO | Il costo pagato per ogni parola chiave/annuncio come riportato dal motore di ricerca. |
| Media Pos | Una metrica calcolata che riflette la posizione media degli annunci come segnalato dal motore di ricerca. |
| Media Punteggio di qualità | Una metrica calcolata che riflette il punteggio medio di qualità riportato dal motore di ricerca. |