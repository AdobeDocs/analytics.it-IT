---
description: Scopri come pubblicare segmenti per le attività di marketing in Libreria tipi di pubblico, Target e Audience Manager.
title: Pubblicare segmenti
feature: Segmentation
exl-id: 0215f896-d3f8-42cc-ac8d-8a94b009927b
TQID: https://experienceleague.adobe.com/JP5OI6SzaJ1xQpFY8iIgT-DNTVxofdSu93XmWI1vtsU
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: eddd9b14-83bd-4ff4-9072-54a4a484abb7id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: d2fb5ded5ce49c6e7143897de2ee9d3b6b494bf9
workflow-type: tm+mt
source-wordcount: 1349
ht-degree: 32%

---

# Pubblicare segmenti {#publish-segments}

>[!CONTEXTUALHELP]
>id="components_segments_publishing"
>title="Pubblicazione per CX Enterprise"
>abstract="Se viene pubblicato nella Libreria pubblico, sarà possibile utilizzare il pubblico per attività di marketing in Target e altre soluzioni CX Enterprise."

>[!CONTEXTUALHELP]
>id="components_segments_audiencelibrary"
>title="Libreria pubblico"
>abstract="I segmenti creati nella Libreria pubblico sono disponibili immediatamente e non dipendono dagli aggiornamenti di Analytics."


È possibile pubblicare un segmento di Adobe Analytics in CX Enterprise. Pertanto, puoi utilizzare il segmento per l’attività di marketing in Audience Manager e in altri canali di attivazione, inclusi Advertising, Target e Campaign.

Puoi pubblicare i segmenti di Analytics in CX Enterprise in meno di 8 ore. Utilizza questi segmenti per attivare il pubblico in Audience Manager per tutte le destinazioni a valle.


>[!BEGINSHADEBOX]

Consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Pubblica segmenti](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/integrations/experience-cloud/improved-experience-cloud-audience-publishing){target="_blank"} per un video dimostrativo.

>[!ENDSHADEBOX]


>[!NOTE]
>
>Adobe Campaign (Classic e Standard) si comporta in modo diverso in quanto è soggetto a una latenza aggiuntiva di 24 ore oltre la latenza di 8 ore.

## Prerequisiti

* Verificare che la suite di rapporti in cui si sta salvando il segmento sia [abilitata per CX Enterprise](/help/components/segmentation/segmentation-workflow/seg-publish.md). In caso contrario, non è possibile pubblicarlo su CX Enterprise.
* Assicurati che la tua organizzazione utilizzi gli ID di Experience Cloud.
* Prima che possa pubblicare i segmenti, l’amministratore deve assegnare l’autorizzazione [!UICONTROL Segment Publishing] a un profilo di prodotto nin [Admin Console](https://experienceleague.adobe.com/it/docs/core-services/interface/administration/admin-tool-experience-cloud) e aggiungerti al profilo di prodotto.

## Considerazioni

* **Limiti delle suite di rapporti**: puoi pubblicare fino a 75 segmenti per suite di rapporti. Questo limite viene sempre applicato. Se hai già pubblicato 75 segmenti, non puoi pubblicarne altri finché non annulli la pubblicazione di un numero di segmenti tale da scendere al di sotto della soglia di 75 segmenti.
* **Limiti di appartenenza**: il pubblico condiviso con CX Enterprise da Adobe Analytics non può superare i 20 milioni di membri univoci.
* **Privacy dei dati**: i tipi di pubblico non vengono filtrati sulla base dello stato di autenticazione di un visitatore. Un visitatore potrebbe essere in grado di navigare nel sito come utente autenticato o non autenticato. Le azioni che si verificano quando un visitatore non è autenticato possono comunque determinare l’inclusione del visitatore nel pubblico. Rivedi [Privacy di Adobe CX Enterprise](https://www.adobe.com/it/privacy/experience-cloud.html) per comprendere tutte le implicazioni in materia di privacy derivanti dalla condivisione dei tipi di pubblico.
* Per una discussione sulle **differenze tra i segmenti in [!DNL Adobe Analytics] e Audience Manager**, vedi [Comprendere i segmenti in Analytics e Audience Manager](/help/integrate/c-audience-analytics/aam-analytics-segments.md).

## Timeline per la pubblicazione dei segmenti

| Dati disponibili | Quando sono disponibili | Dove sono disponibili |
|---|---|---|
| Metadati (titolo e definizione del segmento) | Immediatamente dopo la pubblicazione | Audience Manager, libreria di tipi di pubblico aziendali CX, Target |
| Segmento utilizzabile con appartenenza | ~8 ore dopo la pubblicazione | Visualizzatore del profilo del visitatore in Audience Manager |
| Popolazione per caratteristiche e appartenenza | Entro 24-48 ore | Audience Manager |

>[!NOTE]
>Una volta alla settimana, tutti i dati vengono sincronizzati completamente per tenere conto di eventuali delta o discrepanze non acquisite nella settimana precedente.

## Pubblicare i segmenti in [!UICONTROL Segment builder]

1. In Adobe Analytics, vai a **[!UICONTROL Components]** > **[!UICONTROL Segments]**
1. Seleziona **[!UICONTROL Add]** per creare un nuovo segmento.
   ![Pubblica CX Enterprise](assets/publish-ec.png)
1. Fornisci un titolo e una descrizione per il segmento. Questi campi sono necessari prima di poter salvare il segmento.
1. Nella sezione **[!UICONTROL Experience Cloud publishing]**, seleziona l&#39;opzione **[!UICONTROL Publish this segment to Experience Cloud (for *suite di rapporti *)]**.

   >[!IMPORTANT]
   >
   >Verificare di monitorare **[!UICONTROL Visitors with Experience Cloud ID]** in **[!UICONTROL Data Preview]** anziché **[!UICONTROL Unique Visitors]** quando si confrontano i numeri di Adobe Analytics con i numeri di Audience Manager.
   >

| Elemento | Descrizione |
|---|---|
| **[!UICONTROL Publish this segment to the Experience Cloud (for *suite di rapporti *)]** | Quando questa opzione è abilitata, il titolo e la definizione del segmento vengono condivisi istantaneamente con CX Enterprise, mentre l&#39;appartenenza al segmento viene valutata e condivisa ogni 4 ore. <br> Quando quel pubblico viene associato a un&#39;attività in Target, ad esempio, [!DNL Analytics] inizia a inviare ID per i visitatori idonei per quel pubblico CX Enterprise e Target. A questo punto, il nome del pubblico e i dati corrispondenti iniziano a essere visualizzati sulla pagina [!DNL Audience Library] di CX Enterprise. </br> |
| **[!UICONTROL Audience Creation Window]** | L’intervallo di tempo selezionato viene utilizzato per creare il pubblico su base di calendario continuo. Ad esempio, **[!UICONTROL Last 30 days]** (impostazione predefinita) include i visitatori idonei per il pubblico negli ultimi 30 giorni dalla data odierna (NON dalla data originale di creazione del segmento). |
| **[!UICONTROL Create in Audience Library]** | I segmenti creati e pubblicati possono essere resi disponibili senza latenza nella pagina [!DNL Audience Library] di CX Enterprise. Non dipendono dagli aggiornamenti di Analytics. Questi segmenti non vengono conteggiati rispetto al limite di 75 segmenti pubblicati. |
| **[!UICONTROL x of 75 Published]** | Il numero di segmenti pubblicati in CX Enterprise. Fai clic sul collegamento per visualizzare un elenco dei segmenti pubblicati e della suite di rapporti e del relativo proprietario associati. |
| **[!UICONTROL Save]** | Salva questo segmento. |

## Annullare la pubblicazione o eliminare segmenti

>[!CAUTION]
>
>Per eliminare un segmento pubblicato in CX Enterprise, è necessario prima annullare la pubblicazione del segmento. Per annullare la pubblicazione di un segmento, deseleziona **[!UICONTROL Publish this segment to the Experience Cloud (for *suite di rapporti *)]**.


>[!NOTE]
>
>**impossibile** annullare la pubblicazione di un segmento attualmente in uso da una delle seguenti soluzioni Adobe: Analytics (in Audience Analytics), Campaign, Advertising (per i clienti del servizio core e di Audience Manager) e tutti gli altri partner esterni (per i clienti di Audience Manager). **puoi** annullare la pubblicazione di un segmento utilizzato da Target.

## Visualizzare lo stato di pubblicazione dei segmenti

Il numero massimo di segmenti Adobe Analytics pubblicabili è 75.

Per visualizzare i segmenti pubblicati:

1. In Adobe Analytics, vai a **[!UICONTROL Components]** > **[!UICONTROL Segments]**.

1. Visualizza la colonna **[!UICONTROL Published]**. **[!UICONTROL Yes]** in questa colonna indica che il segmento è pubblicato in CX Enterprise. **[!UICONTROL No]** indica che il segmento non è pubblicato.

## Recuperare l’UUID di Audience Manager

Esistono due modi per acquisire l’UUID di Adobe Audience Manager attualmente associato al browser:

* Adobe CX Enterprise Debugger
* Strumento per sviluppatori nativo nei browser (ad esempio, Strumenti per sviluppatori di Chrome)

Le schermate seguenti mostrano come recuperare l’UUID di Adobe Audience Manager nel browser e utilizzarlo nel Visualizzatore del profilo del visitatore di Audience Manager per convalidare le caratteristiche e l’iscrizione al segmento.

### Metodo 1: utilizzare Adobe CX Enterprise Debugger

1. Scarica e installa [Adobe CX Enterprise Debugger](/help/implement/validate/debugger.md) nel Web store di Chrome.
1. Avvia il debugger durante il caricamento di una pagina.
1. Scorri fino alla sezione Audience Manager e trova l’UUID di Adobe Audience Manager impostato nella pagina del browser corrente
(`35721780439475290181087231320657663953` nell&#39;esempio seguente)

   ![Debugger](assets/aepdebugger.png)

### Metodo 2: utilizzare gli strumenti per sviluppatori di Chrome (o altri strumenti per sviluppatori del browser)

1. Avvia gli strumenti per sviluppatori di Chrome prima di caricare una pagina
1. Carica la pagina e seleziona Applicazioni > Cookie. L’UUID di Adobe Audience Manager deve essere impostato nel componente di terze parti
Cookie demdex ([adobe.demdex.net](https://experienceleague.adobe.com/en/docs/audience-manager/user-guide/reference/demdex-calls) nell&#39;esempio seguente). Il campo demdex è l’UUID di Adobe Audience Manager impostato
nel browser (`35721780439475290181087231320657663953` nell&#39;esempio seguente).

   ![Strumenti per gli sviluppatori di Chrome](assets/devtools.png)

## Utilizza il [!UICONTROL Visitor Profile Viewer] di Audience Manager

L&#39;UUID di Adobe Audience Manager nel browser è per impostazione predefinita quando viene caricato [!UICONTROL Visitor Profile Viewer]. Se verifichi le realizzazioni delle caratteristiche per altri utenti, inserisci un UUID nel campo UUID e fai clic su [!UICONTROL Refresh]. Per ulteriori informazioni, consulta il [Visualizzatore del profilo del visitatore](https://experienceleague.adobe.com/en/docs/audience-manager/user-guide/features/visitor-profile-viewer).

## Visualizzare le caratteristiche del segmento in Audience Manager

In Adobe Audience Manager, viene valutato l’elenco dei visitatori con ECID per un dato segmento, mentre Analytics condivide i segmenti con CX Enterprise.

1. In Audience Manager, vai a **[!UICONTROL Audience Data]** > **[!UICONTROL Traits]** > **[!UICONTROL Analytics Traits]**. Viene visualizzata una cartella per ogni suite di rapporti di Analytics mappata alla tua organizzazione CX Enterprise. Queste cartelle (per Caratteristiche, Segmenti e Origini dati) sono create quando viene avviato o eseguito il provisioning del servizio principale Profili e Tipi di pubblico/Persone.
1. Seleziona la cartella per la suite di rapporti in cui hai creato in precedenza il segmento da condividere con Audience Manager. Puoi vedere il segmento/pubblico creato. Quando condividi un segmento, si verificano 2 cose in Audience Manager:
   * viene creata una caratteristica, all’inizio senza dati. Circa 8 ore dopo la pubblicazione del segmento in [!DNL Analytics], l&#39;elenco degli ECID viene acquisito e condiviso con Audience Manager e altre soluzioni CX Enterprise.

     ![Caratteristiche di Audience Manager](assets/aam-traits.png)

   * Viene creato un segmento con una caratteristica. Utilizza l’origine dati associata alla suite di rapporti in cui hai pubblicato il segmento.
   * La scadenza delle caratteristiche ora è impostata su 16 giorni (in precedenza era di 2 giorni).

## Visualizzare il segmento in [!DNL Adobe Target]

**[!UICONTROL Publish this segment to the Experience Cloud]** consente di rendere disponibile il segmento nella libreria dei tipi di pubblico personalizzata di Adobe Target. Puoi utilizzare un segmento creato in Analytics o Audience Manager per attività in Target. Ad esempio, puoi creare campagne sulla base delle metriche di conversione di Analytics e sui segmenti di pubblico creati in Analytics.

In Adobe Target:

1. Seleziona **[!UICONTROL Audiences]**.
1. Nella pagina **[!UICONTROL Audiences]**, individuare il pubblico ottenuto da CX Enterprise. Questi tipi di pubblico sono disponibili per l’utilizzo nelle attività di Target.

   ![Pubblico di destinazione](assets/target-audiences.png)
