---
description: Consente di utilizzare il segmento per attività di marketing nella libreria Audience, Target e Audience Manager.
seo-description: Consente di utilizzare il segmento per attività di marketing nella libreria Audience, Target e Audience Manager.
seo-title: Pubblicare segmenti in Experience Cloud
solution: Analytics
title: Pubblicare segmenti in Experience Cloud
topic: Segmenti
uuid: e 5 ce 20 c 0-ce 43-423 b-a 29 f-ba 66 e 9 e 24 d 27
translation-type: tm+mt
source-git-commit: d362813f497734f3d09def59ad842406ef4bf5aa

---


# Pubblicare segmenti in Experience Cloud

Publishing a segment to the Experience Cloud lets you use the segment for marketing activity in the [!UICONTROL Audience Library], [!DNL Target], [!DNL Audience Manager], and [!DNL Advertising Cloud]. Gli aggiornamenti recenti hanno ottimizzato notevolmente il flusso di lavoro di pubblicazione. In precedenza, la pubblicazione di un segmento utilizzabile richiedeva circa 48 ore. Ora l'elaborazione può richiedere fino a 8 ore, ma in base ad altri traffico e alle dimensioni del segmento, l'elaborazione potrebbe essere ancora più veloce. (Tuttavia, al momento non è possibile informarvi quando il segmento è disponibile, pertanto dovrete effettuare il controllo manualmente.) Abbiamo inoltre aumentato il numero massimo di segmenti pubblicabili a 75 (da 20). Puoi visualizzare i segmenti pubblicati in Componenti &gt; Segmenti.


## Prerequisiti

* Ensure that the report suite that you are saving this segment to is [enabled for the Experience Cloud](https://docs.adobe.com/content/help/en/core-services/interface/audiences/t-publish-audience-segment.html). In caso contrario, non potete pubblicarlo in Experience Cloud.
* Make sure you are working in a report suite that is [mapped to your Experience Cloud organization](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html).
* Before you can publish segments, your Admin needs to assign the [!UICONTROL Segment Creation] and the [!UICONTROL Segment Publishing] permissions to a product profile in the [Admin Console](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html), and add you to the product profile.


## Considerazioni

* **Limiti di suite di rapporti**: Puoi pubblicare fino a 75 segmenti per suite di rapporti. Questo limite viene imposto. Se hai già pubblicato 75 segmenti, non puoi pubblicare altri segmenti fino a quando non ripubblichi abbastanza segmenti per scendere sotto la soglia di 75 segmenti.
* **Limiti di iscrizione**: I tipi di pubblico condivisi [!DNL Experience Cloud] con Analytics non possono superare i 20 milioni di membri unici.
* **Privacy dei dati**: Le audience non vengono filtrate in base allo stato di autenticazione di un visitatore. Se un visitatore può navigare nel sito come utente autenticato o non autenticato, le azioni che si verificano per un visitatore non autenticato possono comunque determinare l'inclusione del visitatore nel pubblico. Review [Adobe Experience Cloud privacy](https://www.adobe.com/privacy/experience-cloud.html) to understand the full privacy implications of audience sharing.
* For a discussion about the differences between segments in [!DNL Adobe Analytics] and [!DNL Audience Manager], go [here](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html).
* In Analytics puoi modificare o eliminare un segmento pubblicato. Se il segmento è in uso, quando modifichi un segmento compare un messaggio di avviso. Non puoi eliminare un segmento modificato che risulta in uso in Adobe [!DNL Target].

## Cronologia di pubblicazione segmenti

| Informazioni disponibili | Quando disponibile | Dove è disponibile |
|---|---|---|
| Metadati (titolo del segmento e definizione) | Subito dopo la pubblicazione | [!DNL Audience Manager], [!UICONTROL Experience Cloud Audience Library], [!DNL Target] |
| Segmento utilizzabile con appartenenza | ~ 8 ore dopo la pubblicazione | Visitor Profile Viewer in [!DNL Audience Manager] |
| Popolazione e popolazione di appartenenza | entro 24 ore | [!DNL Audience Manager] |

## Publish segments in [!UICONTROL Segment Builder]

1. Navigate to [!UICONTROL Analytics > Workspace > Components > Segments] &gt; +
1. Create a segment in the [!UICONTROL Segment Builder].
1. Fornite un titolo e una descrizione del segmento; non potrete salvarlo in altro modo.
1. Check [!UICONTROL Publish this segment to the Experience Cloud (for *report suite *)].

![](assets/publish-ec.png)

| Elemento | Descrizione |
|---|---|
| Publish this segment to the Experience Cloud (for *report suite*) | Quando questa opzione è attivata, il titolo e la definizione del segmento (ovvero l'audience shell utilizzata spesso nelle piattaforme pubblicitarie) vengono condivisi con Experience Cloud, mentre l'iscrizione al segmento viene valutata e condivisa ogni 4 ore. <br> Quando quell'audience viene associata a un'attività in Target, ad esempio, Analytics inizia a inviare ID per i visitatori idonei per quel pubblico Experience Cloud e Target. A questo punto, il nome del pubblico e i dati corrispondenti iniziano a essere visualizzati sulla pagina di Experience Cloud Audiences. </br> |
| Finestra Creazione pubblico | Il periodo di tempo selezionato viene utilizzato per creare il pubblico su base lineare. Ad esempio, «Ultimi 30 giorni (predefinito) include i visitatori che hanno qualificato l'audience negli ultimi 30 giorni dalla data odierna (NON dalla data originale alla creazione del segmento). |
| Crea nella libreria Pubblico | I segmenti creati e pubblicati possono essere resi disponibili senza latenza nella Libreria Pubblico di Experience Cloud. Non dipendono dagli aggiornamenti di Analytics. Questi segmenti non vengono conteggiati rispetto al limite di 75 segmenti pubblicati. |
| x di 75 Pubblicato | Mostra il numero di segmenti pubblicati in Experience Cloud. Fai clic sul collegamento per visualizzare un elenco dei segmenti pubblicati e della suite di rapporti e del proprietario associati. |
| Salva | Salva questo segmento. |

## Annullare la pubblicazione di segmenti

To unpublish a segment, just **unclick** the checkbox that you used to publish it.

## View segment publishing status in the [!UICONTROL Segment Manager]

1. [!UICONTROL Analytics > Components > Segments]Passa a.
1. Notice the new [!UICONTROL Published] column. Sì/No indica se il segmento è stato pubblicato in Experience Cloud o meno.

![](assets/publish-status.png)

## Retrieve the [!DNL Audience Manager] UUID and use Visitor Profile Viewer

Esistono 2 modi per acquisire l'UUID AAM attualmente associato al browser:

* Adobe Experience Cloud Debugger
* Strumento nativo per sviluppatori nei browser (ad esempio, Chrome Developer Tools)

Le seguenti schermate mostrano come recuperare l'UUID AAM sul browser e utilizzarlo nel
visualizzatore di profilo visitatore di Audience Manager per convalidare l'appartenenza a tratti e segmenti.

### Metodo 1: Utilizzare Adobe Experieence CLoud Debugger

1. Download and install [Adobe Experience Cloud Debugger](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/debugger.html) in the Chrome Web Store.
1. Avviare il debugger quando si carica una pagina.
1. Scroll to the Audience Manager section and find the AAM UUID set on the current browser page
(`50814298273775797762943354787774730612` in the example below)

![](assets/debugger.jpg)

### Metodo 2: Utilizzare gli strumenti per sviluppatori Chrome (o altri strumenti per sviluppatori di browser)

1. Avviare Chrome Developer Tools prima di caricare una pagina
1. Caricate la pagina e verificate Applicazioni &gt; Cookie. The AAM UUID should be set in the 3rd-party
Demdex cookie ([adobe.demdex.net](https://marketing.adobe.com/resources/help/en_US/aam/demdex-calls.html) in the example below). The field demdex is the AAM UUID set
on the browser (`50814298273775797762943354787774730612` in the example below)

## View the segment traits in [!DNL Audience Manager]

In AAM, l'elenco di visitatori con ECID per un determinato segmento viene valutato in streaming quando Analytics condivide segmenti con Experience Cloud.

1. In [!DNL Audience Manager], go to [!UICONTROL Audience Data > Traits > Analytics Traits]. Vedrai una cartella per ogni suite di rapporti di Analytics mappata sulla tua organizzazione Experience Cloud. Queste cartelle (per Caratteristiche, Segmenti e Origini dati) vengono create quando i servizi di base Profili e Pubblico/Persone vengono avviati o sottoposti a provisioning.
1. Select the folder for the report suite in which you previously created the segment you wanted to share with [!DNL Audience Manager]. Vedrai il segmento/pubblico che hai creato. When you share a segment, 2 things happen in [!DNL Audience Manager]:
* Viene creato un trait, prima senza dati. Circa. 8 hours after the segment gets published in [!DNL Analytics], the list of ECIDs gets onboarded and shared with [!DNL Audience Manager] and other Experience Cloud solutions.

![](assets/aam-traits.png)

* Viene creato un segmento con caratteristiche. Utilizza l'origine dati associata alla suite di rapporti in cui hai pubblicato il segmento.

## View the segment in [!DNL Adobe Target]

The [!UICONTROL Publish this segment to the Experience Cloud] checkbox during the segment creation process in Adobe Analytics allows the segment to be available within the Adobe Target's custom audience library. Puoi utilizzare un segmento creato in Analytics o Audience Manager per attività in Target. Ad esempio, puoi creare campagne sulla base delle metriche di conversione di Analytics e sui segmenti di pubblico creati in Analytics.
], click [!UICONTROL Audiences].
1. On the [!UICONTROL Audiences] page, locate the audience sourced from the [!DNL Experience Cloud]. These audiences are available for use in [!DNL Target] activities.
