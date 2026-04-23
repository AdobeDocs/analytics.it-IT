---
description: Learn how to publish segments for marketing activity in Audience Library, Target, and Audience Manager.
title: Publish Segments
feature: Segmentation
exl-id: 0215f896-d3f8-42cc-ac8d-8a94b009927b
source-git-commit: cbfe932eecf2e89d72b1aa373d723de4cf0af073
workflow-type: tm+mt
source-wordcount: '1261'
ht-degree: 45%

---

# Pubblicare segmenti {#publish-segments}

>[!CONTEXTUALHELP]
>id="components_segments_publishing"
>title="Pubblicazione in Experience Cloud"
>abstract="Puoi pubblicare il pubblico nella Libreria pubblico, dove può essere utilizzato per attività di marketing in Target e altre soluzioni Experience Cloud."

>[!CONTEXTUALHELP]
>id="components_segments_audiencelibrary"
>title="Libreria pubblico"
>abstract="I segmenti creati nella Libreria pubblico sono disponibili immediatamente e non dipendono dagli aggiornamenti di Analytics."


Puoi pubblicare un segmento di Adobe Analytics in Experience Cloud. Pertanto, puoi utilizzare il segmento per l’attività di marketing in Audience Manager e in altri canali di attivazione, inclusi Advertising, Target e Campaign.

Puoi pubblicare i segmenti di Analytics in Experience Cloud in meno di 8 ore. Utilizza questi segmenti per attivare il pubblico in Audience Manager per tutte le destinazioni a valle.


>[!BEGINSHADEBOX]

Consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Pubblica segmenti](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/integrations/experience-cloud/improved-experience-cloud-audience-publishing){target="_blank"} per un video dimostrativo.

>[!ENDSHADEBOX]


>[!NOTE]
>
>Adobe Campaign (Classic e Standard) si comporta in modo diverso in quanto è soggetto a una latenza aggiuntiva di 24 ore oltre la latenza di 8 ore.

## Prerequisiti

* Assicurati che la suite di rapporti in cui stai salvando il segmento sia [abilitata per Experience Cloud](/help/components/segmentation/segmentation-workflow/seg-publish.md). In caso contrario, non puoi pubblicarlo in Experience Cloud.
* Assicurati che la tua organizzazione utilizzi gli ID di Experience Cloud.
* Prima che possa pubblicare i segmenti, l’amministratore deve assegnare l’autorizzazione [!UICONTROL Segment Publishing] a un profilo di prodotto nin [Admin Console](https://experienceleague.adobe.com/it/docs/core-services/interface/administration/admin-tool-experience-cloud) e aggiungerti al profilo di prodotto.

## Considerazioni

* **Limiti delle suite di rapporti**: puoi pubblicare fino a 75 segmenti per suite di rapporti. Questo limite viene sempre applicato. Se hai già pubblicato 75 segmenti, non puoi pubblicarne altri finché non annulli la pubblicazione di un numero di segmenti tale da scendere al di sotto della soglia di 75 segmenti.
* **Limiti di appartenenza**: i tipi di pubblico condivisi con [!DNL Experience Cloud] da Adobe Analytics non possono superare i 20 milioni di membri univoci.
* **Privacy dei dati**: i tipi di pubblico non vengono filtrati sulla base dello stato di autenticazione di un visitatore. Un visitatore potrebbe essere in grado di navigare nel sito come utente autenticato o non autenticato. Actions that occur when a visitor is un-authenticated can still cause a visitor to be included in an audience. Consulta [Privacy di Adobe Experience Cloud](https://www.adobe.com/it/privacy/experience-cloud.html) per comprendere tutte le implicazioni in materia di privacy derivanti dalla condivisione dei tipi di pubblico.
* For a discussion about the **differences between segments in [!DNL Adobe Analytics] and[!DNL Audience Manager]**, see [Understand segments in Analytics and Audience Manager](/help/integrate/c-audience-analytics/aam-analytics-segments.md).

## Timeline per la pubblicazione dei segmenti

| Dati disponibili | Quando sono disponibili | Dove sono disponibili |
|---|---|---|
| Metadati (titolo e definizione del segmento) | Immediatamente dopo la pubblicazione | [!DNL Audience Manager], [!UICONTROL Experience Cloud Audience Library], [!DNL Target] |
| Segmento utilizzabile con appartenenza | ~8 ore dopo la pubblicazione | Visualizzatore del profilo del visitatore in [!DNL Audience Manager] |
| Popolazione per caratteristiche e appartenenza | Entro 24-48 ore | [!DNL Audience Manager] |

>[!NOTE]
>Una volta alla settimana, tutti i dati vengono sincronizzati completamente per tenere conto di eventuali delta o discrepanze non acquisite nella settimana precedente.

## Pubblicare i segmenti in [!UICONTROL Segment builder]

1. In Adobe Analytics, go to **[!UICONTROL Components]** > **[!UICONTROL Segments]**
1. Seleziona **[!UICONTROL Add]** per creare un nuovo segmento.
   ![Pubblicare in Experience Cloud](assets/publish-ec.png)
1. Fornisci un titolo e una descrizione per il segmento. Questi campi sono necessari prima di poter salvare il segmento.
1. Nella sezione **[!UICONTROL Experience Cloud publishing]**, seleziona l&#39;opzione **[!UICONTROL Publish this segment to the Experience Cloud (for *suite di rapporti *)]**.

   >[!IMPORTANT]
   >
   >Make sure that you monitor **[!UICONTROL Visitors with Experience Cloud ID]** in the **[!UICONTROL Data Preview]** instead of the **[!UICONTROL Unique Visitors]**  when you compare Adobe Analytics numbers to Audience Manager numbers.
   >

| Elemento | Descrizione |
|---|---|
| **[!UICONTROL Publish this segment to the Experience Cloud (for *suite di rapporti *)]** | Quando questa opzione è abilitata, il titolo e la definizione del segmento vengono condivisi istantaneamente con Experience Cloud, mentre l’appartenenza al segmento viene valutata e condivisa ogni 4 ore. <br>Quando quel pubblico viene associato a un’attività in [!DNL Target], ad esempio, [!DNL Analytics] inizia a inviare ID per i visitatori idonei per quel pubblico di Experience Cloud [!DNL Target]. A questo punto, il nome del pubblico e i dati corrispondenti iniziano a essere visualizzati sulla pagina [!DNL Audience Library] in Experience Cloud. </br> |
| **[!UICONTROL Audience Creation Window]** | L’intervallo di tempo selezionato viene utilizzato per creare il pubblico su base di calendario continuo. Ad esempio, **[!UICONTROL Last 30 days]** (impostazione predefinita) include i visitatori idonei per il pubblico negli ultimi 30 giorni dalla data odierna (NON dalla data originale di creazione del segmento). |
| **[!UICONTROL Create in Audience Library]** | I segmenti creati e pubblicati possono essere resi disponibili senza latenza nella pagina [!DNL Audience Library] in Experience Cloud. Non dipendono dagli aggiornamenti di Analytics. Questi segmenti non vengono conteggiati rispetto al limite di 75 segmenti pubblicati. |
| **[!UICONTROL x of 75 Published]** | Il numero di segmenti pubblicati in Experience Cloud. Fai clic sul collegamento per visualizzare un elenco dei segmenti pubblicati e della suite di rapporti e del relativo proprietario associati. |
| **[!UICONTROL Save]** | Salva questo segmento. |

## Annullare la pubblicazione o eliminare segmenti

>[!CAUTION]
>
>To delete a segment that has been published to Experience Cloud, you have to unpublish the segment first. To unpublish a segment, just unselect **[!UICONTROL Publish this segment to the Experience Cloud (for *report suite *)]**.


>[!NOTE]
>
>You **cannot** unpublish a segment that is currently in use by any of the following Adobe solutions: Analytics (in Audience Analytics), Campaign, Advertising (for Core Service and Audience Manager customers) and all other external partners (for Audience Manager customers). You **can** unpublish a segment that is in use by Target.

## Visualizzare lo stato di pubblicazione dei segmenti

The maximum number of publishable Adobe Analytics segments is 75.

To view published segments:

1. In Adobe Analytics, go to **[!UICONTROL Components]** > **[!UICONTROL Segments]**.

1. View the **[!UICONTROL Published]** column. **[!UICONTROL Yes]** in this column indicates that the segment is published to Experience Cloud. **[!UICONTROL No]** indicates that the segment is not published.

## Recupera l’UUID di [!DNL Audience Manager]

Esistono due modi per acquisire l’UUID di Adobe Audience Manager attualmente associato al browser:

* Adobe Experience Cloud Debugger
* Strumento per sviluppatori nativo nei browser (ad esempio, Strumenti per sviluppatori di Chrome)

Le schermate seguenti mostrano come recuperare l’UUID di Adobe Audience Manager nel browser e utilizzarlo nel Visualizzatore del profilo del visitatore di Audience Manager per convalidare le caratteristiche e l’iscrizione al segmento.

### Metodo 1: utilizzare Adobe Experience Cloud Debugger

1. Scarica e installa [Adobe Experience Cloud Debugger](/help/implement/validate/debugger.md) nel web store di Chrome.
1. Avvia il debugger durante il caricamento di una pagina.
1. Scorri fino alla sezione Audience Manager e trova l’UUID di Adobe Audience Manager impostato nella pagina del browser corrente
(`35721780439475290181087231320657663953` nell&#39;esempio seguente)

   ![Debugger](assets/aepdebugger.png)

### Metodo 2: utilizzare gli strumenti per sviluppatori di Chrome (o altri strumenti per sviluppatori del browser)

1. Avvia gli strumenti per sviluppatori di Chrome prima di caricare una pagina
1. Carica la pagina e seleziona Applicazioni > Cookie. The Adobe Audience Manager UUID should be set in the third-party
Demdex cookie ([adobe.demdex.net](https://experienceleague.adobe.com/en/docs/audience-manager/user-guide/reference/demdex-calls) in the example below). The field demdex is the Adobe Audience Manager UUID set
on the browser (`35721780439475290181087231320657663953` in the example below).

   ![Strumenti per gli sviluppatori di Chrome](assets/devtools.png)

## Utilizza il [!UICONTROL Visitor Profile Viewer] di Audience Manager

L&#39;UUID di Adobe Audience Manager nel browser è per impostazione predefinita quando viene caricato [!UICONTROL Visitor Profile Viewer]. If you verify trait realizations for other users, input a UUID in the UUID field and click [!UICONTROL Refresh]. Per ulteriori informazioni, consulta il [Visualizzatore del profilo del visitatore](https://experienceleague.adobe.com/en/docs/audience-manager/user-guide/features/visitor-profile-viewer).

## Visualizzare le caratteristiche del segmento in [!DNL Audience Manager]

In Adobe Audience Manager, the list of visitors with ECIDs for a given segment is evaluated while Analytics shares segments with Experience Cloud.

1. In [!DNL Audience Manager], go to **[!UICONTROL Audience Data]** > **[!UICONTROL Traits]** > **[!UICONTROL Analytics Traits]**. You see a folder for each Analytics reports suite that is mapped to your Experience Cloud organization. Queste cartelle (per Caratteristiche, Segmenti e Origini dati) sono create quando viene avviato o eseguito il provisioning del servizio principale Profili e Tipi di pubblico/Persone.
1. Seleziona la cartella per la suite di rapporti in cui hai creato in precedenza il segmento che desideri condividere con [!DNL Audience Manager]. Puoi vedere il segmento/pubblico creato. Quando condividi un segmento, si verificano 2 cose in [!DNL Audience Manager]:
   * viene creata una caratteristica, all’inizio senza dati. Circa 8 ore dopo la pubblicazione del segmento in [!DNL Analytics], l’elenco degli ECID viene acquisito e condiviso con [!DNL Audience Manager] e altre soluzioni Experience Cloud.

     ![Caratteristiche di Audience Manager](assets/aam-traits.png)

   * Viene creato un segmento con una caratteristica. Utilizza l’origine dati associata alla suite di rapporti in cui hai pubblicato il segmento.
   * La scadenza delle caratteristiche ora è impostata su 16 giorni (in precedenza era di 2 giorni).

## Visualizzare il segmento in [!DNL Adobe Target]

The **[!UICONTROL Publish this segment to the Experience Cloud]** allows the segment to be available within the Adobe Target&#39;s custom audience library. Puoi utilizzare un segmento creato in Analytics o Audience Manager per attività in Target. Ad esempio, puoi creare campagne sulla base delle metriche di conversione di Analytics e sui segmenti di pubblico creati in Analytics.

In Adobe Target:

1. Seleziona **[!UICONTROL Audiences]**.
1. Nella pagina **[!UICONTROL Audiences]**, individua il pubblico ottenuto da [!DNL Experience Cloud]. Questi tipi di pubblico sono disponibili per l’utilizzo nelle attività di [!DNL Target].

   ![Target audiences](assets/target-audiences.png)
