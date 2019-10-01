---
description: Consente di utilizzare il segmento per l'attività di marketing nella libreria Audience, in Target e in Audience Manager.
seo-description: Consente di utilizzare il segmento per l'attività di marketing nella libreria Audience, in Target e in Audience Manager.
seo-title: Pubblicare segmenti in Experience Cloud
solution: Analytics
title: Pubblicare segmenti in Experience Cloud
topic: Segmenti
uuid: e5ce20c0-ce43-423b-a29f-ba66e9e24d27
translation-type: tm+mt
source-git-commit: d65a7582546a96856790dcbe481757ad3f5500a4

---


# Pubblicare segmenti in Experience Cloud

>[!IMPORTANT]
>
>I miglioramenti in termini di latenza relativi alla pubblicazione dei segmenti e all’interfaccia utente descritti in questa pagina non vengono ancora implementati a tutti i clienti. The current production environment is described [here](https://docs.adobe.com/content/help/en/core-services/interface/audiences/t-publish-audience-segment.html).

Publishing a segment to the Experience Cloud lets you use the segment for marketing activity in the , , , and . [!UICONTROL Audience Library][!DNL Target][!DNL Audience Manager][!DNL Advertising Cloud] Recent updates have significantly optimized the publishing workflow. Previously, publishing a usable segment took approximately 48 hours.

Now, processing can take up to 8 hours, but depending on other traffic and on the segment size, processing may be even faster. (However, we currently do not have a way to inform you when the segment is available, so you will have to check manually.) We have also increased the maximum number of publishable segments to 75 (from 20). You can view published segments in Components &gt; Segments.


## Prerequisiti

* Ensure that the report suite that you are saving this segment to is enabled for the Experience Cloud. [](https://docs.adobe.com/content/help/en/core-services/interface/audiences/t-publish-audience-segment.html) Otherwise you cannot publish it to the Experience Cloud.
* Make sure you are working in a report suite that is mapped to your Experience Cloud organization.[](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html)
* Ensure that your organization is using Experience Cloud IDs.
* Prima di poter pubblicare i segmenti, l'amministratore deve assegnare l' [!UICONTROL Segment Publishing] autorizzazione a un profilo di prodotto in [Admin Console](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html)e aggiungerti al profilo di prodotto.


## Considerazioni

* **Limiti** delle suite di rapporti: Puoi pubblicare fino a 75 segmenti per suite di rapporti. Questo limite è imposto. Se hai già 75 segmenti pubblicati, non puoi pubblicare altri segmenti fino a quando non annulli la pubblicazione di un numero sufficiente di segmenti per scendere al di sotto della soglia dei 75 segmenti.
* **Limiti** di appartenenza: Il pubblico condiviso con il [!DNL Experience Cloud] da Analytics non può superare i 20 milioni di membri unici.
* **Privacy** dei dati: Le audience non vengono filtrate in base allo stato di autenticazione di un visitatore. Se un visitatore può navigare nel sito come utente autenticato o non autenticato, le azioni che si verificano per un visitatore non autenticato possono comunque determinare l'inclusione del visitatore nel pubblico. Review Adobe Experience Cloud privacy to understand the full privacy implications of audience sharing.[](https://www.adobe.com/privacy/experience-cloud.html)
* For a discussion about the **differences between segments in[!DNL Adobe Analytics]and[!DNL Audience Manager]**, go [here](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html).

## Segment publishing timeline

| Disponibilità | Quando è disponibile | Dove è disponibile |
|---|---|---|
| Metadati (titolo e definizione del segmento) | Immediatamente dopo la pubblicazione | [!DNL Audience Manager], [!UICONTROL Experience Cloud Audience Library], [!DNL Target] |
| Segmento utilizzabile con appartenenza | ~ 8 ore dopo la pubblicazione | Visitor Profile Viewer in [!DNL Audience Manager] |
| Caratteristiche e popolazione di appartenenza | Entro 24-48 ore | [!DNL Audience Manager] |

## Pubblicare segmenti in [!UICONTROL Segment Builder]

1. Passa a **[!UICONTROL Analytics > Workspace > Components > Segments]&gt; +**
1. Crea un segmento nel [!UICONTROL Segment Builder].
1. Immetti un titolo e una descrizione per il segmento. Altrimenti non potrai salvarlo.
1. Controlla suite **[!UICONTROL Publish this segment to the Experience Cloud (for *di *rapporti)]**.

![](assets/publish-ec.png)

>[!IMPORTANT]
>
>Quando confronti i numeri di Adobe Analytics con i numeri di Audience Manager, accertati di utilizzare "Visitatori con Experience Cloud ID" per visualizzare le anteprime dei segmenti in Analytics invece dell'anteprima totale dei segmenti "Visitatori unici":
>
>![](assets/seg-vis-ecid.png)

| Elemento | Descrizione |
|---|---|
| **[!UICONTROL Publish this segment to the Experience Cloud (for *<report suite>*)]** | Quando questa opzione è abilitata, il titolo e la definizione del segmento (ovvero il pubblico shell, come spesso utilizzato nelle piattaforme di annunci) vengono condivisi istantaneamente con Experience Cloud, mentre l'iscrizione al segmento viene valutata e condivisa ogni 4 ore. <br> Quando quel pubblico è associato a un'attività, [!DNL Target]ad esempio, [!DNL Analytics] inizia a inviare ID per i visitatori idonei per quel Experience Cloud e per quel [!DNL Target] pubblico. A questo punto, il nome del pubblico e i dati corrispondenti iniziano a essere visualizzati sulla pagina di Experience Cloud Audiences. </br> |
| **[!UICONTROL Audience Creation Window]** | L'intervallo di tempo selezionato viene utilizzato per creare l'audience su base di calendario continuo. Ad esempio, "Ultimi 30 giorni" (impostazione predefinita) include i visitatori che hanno aderito al pubblico negli ultimi 30 giorni dalla data odierna (NON dalla data originale in cui è stato creato il segmento). |
| **[!UICONTROL Create in Audience Library]** | I segmenti creati e pubblicati possono essere resi disponibili senza latenza nella Libreria Pubblico di Experience Cloud. Non dipendono dagli aggiornamenti di Analytics. Questi segmenti non vengono conteggiati rispetto al limite di 75 segmenti pubblicati. |
| **[!UICONTROL x of 75 Published]** | Mostra il numero di segmenti che hai pubblicato in Experience Cloud. Fai clic sul collegamento per visualizzare un elenco dei segmenti pubblicati e la suite di rapporti e il proprietario associati. |
| **[!UICONTROL Save]** | Salva questo segmento. |

## Annullamento della pubblicazione o eliminazione di segmenti

Per eliminare un segmento pubblicato in Experience Cloud, devi prima annullarne la pubblicazione. Per annullare la pubblicazione di un segmento, **deseleziona** la casella di controllo utilizzata per pubblicarlo.

>[!NOTE]
>
>**Non** puoi annullare la pubblicazione di un segmento attualmente in uso da una delle seguenti soluzioni Adobe: [!DNL Analytics] (in [!DNL Audience Analytics]), [!DNL Campaign], [!DNL Advertising Cloud] (per clienti [!DNL Core Service] e [!DNL Audience Manager]) e tutti gli altri partner esterni (per i clienti [!DNL Audience Manager]). **Puoi** annullare la pubblicazione di un segmento utilizzato da [!DNL Target].

## View segment publishing status in the [!UICONTROL Segment Manager]

1. Navigate to .[!UICONTROL Analytics > Components > Segments]
1. Notice the new  column. [!UICONTROL Published] Yes/No refers to whether the segment has been published to the Experience Cloud or not.

![](assets/publish-status.png)

## Retrieve the  UUID[!DNL Audience Manager]

There are two ways to capture the AAM UUID currently associated with the browser:

* Adobe Experience Cloud Debugger
* Native developer tool in browsers (e.g., Chrome Developer Tools)

The following screenshots show you how to retrieve the AAM UUID on your browser and use it in Audience Manager Visitor Profile Viewer to validate trait &amp; segment membership.

**Method 1: Use Adobe Experience CLoud Debugger**

1. Download and install Adobe Experience Cloud Debugger in the Chrome Web Store.[](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/debugger.html)
1. Launch the debugger when loading a page.
1. Scroll to the Audience Manager section and find the AAM UUID set on the current browser page
( in the example below)`50814298273775797762943354787774730612`

![](assets/debugger.jpg)

**Method 2: Use Chrome Developer Tools (or other browser developer tools)**

1. Launch Chrome Developer Tools before loading a page
1. Load the page and check Applications &gt; Cookies. L’UUID AAM deve essere impostato nel cookie 3rd-partyDemdex ([adobe.demdex.net](https://marketing.adobe.com/resources/help/en_US/aam/demdex-calls.html) nell’esempio seguente). Il demdex del campo è l’impostazione AAM UUID nel browser (`50814298273775797762943354787774730612` nell’esempio di seguito).

![Chrome Developer Tools](assets/ggogle-uuid.png)

## Utilizzo di Audience Manager [!UICONTROL Visitor Profile Viewer]

L'UUID AAM nel browser verrà utilizzato per impostazione predefinita quando [!UICONTROL Visitor Profile Viewer] viene caricato. Se verifica le realizzazioni delle caratteristiche per altri utenti, immetti un UUID nel campo UUID e fai clic su [!UICONTROL Refresh]. Per ulteriori informazioni, consulta Visualizzatore [profilo](https://marketing.adobe.com/resources/help/en_US/aam/t_visitor_profile_viewer.html) visitatori.

![](assets/aam-vpv.png)

## Visualizzare le caratteristiche del segmento in [!DNL Audience Manager]

In AAM, l'elenco di visitatori con ECID per un determinato segmento viene valutato in streaming come segmenti condivisi da Analytics con Experience Cloud.

1. In [!DNL Audience Manager], vai a [!UICONTROL Audience Data > Traits > Analytics Traits]. Vedrai una cartella per ogni suite di rapporti di Analytics mappata alla tua organizzazione Experience Cloud. Queste cartelle (per Caratteristiche, Segmenti e Origini dati) vengono create quando il servizio di base Profili e pubblico/Persone viene avviato o fornito.
1. Selezionate la cartella per la suite di rapporti in cui avete creato in precedenza il segmento con cui desiderate condividere [!DNL Audience Manager]. Vedrai il segmento/pubblico creato. Quando condividete un segmento, si verificano 2 cose in [!DNL Audience Manager]:
* Viene creata una caratteristica, prima senza alcun dato. Circa 8 ore dopo che il segmento viene pubblicato in [!DNL Analytics], l’elenco di ECID viene configurato e condiviso con [!DNL Audience Manager] e altre soluzioni Experience Cloud.

![](assets/aam-traits.png)

* Viene creato un segmento con una sola caratteristica. Utilizza l’origine dati associata alla suite di rapporti in cui hai pubblicato il segmento.

## Visualizza il segmento in [!DNL Adobe Target]

The [!UICONTROL Publish this segment to the Experience Cloud] checkbox during the segment creation process in Adobe Analytics allows the segment to be available within the Adobe Target's custom audience library. Puoi utilizzare un segmento creato in Analytics o Audience Manager per attività in Target. Ad esempio, puoi creare campagne sulla base delle metriche di conversione di Analytics e sui segmenti di pubblico creati in Analytics.
], click [!UICONTROL Audiences].
1. On the [!UICONTROL Audiences] page, locate the audience sourced from the [!DNL Experience Cloud]. These audiences are available for use in [!DNL Target] activities.

