---
description: Ti consente di utilizzare il segmento per l’attività di marketing nella Libreria tipi di pubblico, Target e nell’Audience Manager.
title: Pubblicare segmenti in Experience Cloud
feature: Segmentation
exl-id: 0215f896-d3f8-42cc-ac8d-8a94b009927b
source-git-commit: 25eccb2b9fe3827e62b0ae98d9bebf7a97b239f5
workflow-type: tm+mt
source-wordcount: '1253'
ht-degree: 15%

---

# Pubblicare segmenti in Experience Cloud

La pubblicazione di un segmento di Adobe Analytics nell’Experience Cloud consente di utilizzare il segmento per l’attività di marketing in [!DNL Audience Manager] e in altri canali di attivazione, compreso il Adobe [!DNL Advertising Cloud], [!DNL Target] e [!DNL Campaign]. Gli aggiornamenti recenti hanno ottimizzato in modo significativo il flusso di lavoro di pubblicazione. Ora puoi pubblicare i segmenti di Analytics in Experience Cloud in meno di 8 ore. Utilizza questi segmenti per attivare i tipi di pubblico in Audience Manager per tutte le destinazioni a valle.

Inoltre, è stato aumentato il numero massimo di segmenti Adobe Analytics pubblicabili a 75 (da 20). Puoi visualizzare i segmenti pubblicati in [!UICONTROL Analytics > Components > Segments].

Per ulteriori informazioni, consulta questo video:

>[!VIDEO](https://video.tv.adobe.com/v/32842/?quality=12)

>[!NOTE]
>
>Adobe Campaign (Classic e Standard) si comporta in modo diverso in quanto assorbe una latenza aggiuntiva di 24 ore al di sopra della latenza di 8 ore.

## Prerequisiti

* Assicurati che la suite di rapporti in cui stai salvando il segmento sia [abilitato per l&#39;Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/audiences/t-publish-audience-segment.html). In caso contrario, non puoi pubblicarlo nell’Experience Cloud.
* Assicurati che la tua organizzazione utilizzi gli ID Experience Cloud.
* Prima di pubblicare i segmenti, l’amministratore deve assegnare le [!UICONTROL Segment Publishing] autorizzazione a un profilo di prodotto nel [Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=it)e aggiungilo al profilo di prodotto.

## Considerazioni

* **Limiti delle suite di rapporti**: Puoi pubblicare fino a 75 segmenti per suite di rapporti. Questo limite viene applicato. Se hai già pubblicato 75 segmenti, non puoi pubblicarli finché non annulli la pubblicazione di un numero sufficiente di segmenti per scendere al di sotto della soglia di 75 segmenti.
* **Limiti di adesione**: Tipi di pubblico condivisi con [!DNL Experience Cloud] da Adobe Analytics non può superare i 20 milioni di membri unici.
* **Privacy dei dati**: I tipi di pubblico non vengono filtrati in base allo stato di autenticazione di un visitatore. Se un visitatore può navigare nel sito come utente autenticato o non autenticato, le azioni che si verificano per un visitatore non autenticato possono comunque determinare l&#39;inclusione del visitatore nel pubblico. Revisione [Privacy Adobe Experience Cloud](https://www.adobe.com/it/privacy/experience-cloud.html) per comprendere tutte le implicazioni in materia di privacy derivanti dalla condivisione dei tipi di pubblico.
* Per una discussione sul **differenze tra i segmenti [!DNL Adobe Analytics] e[!DNL Audience Manager]**, vai [qui](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html).

## Timeline per la pubblicazione dei segmenti

| Informazioni disponibili | Quando è disponibile | Dove è disponibile |
|---|---|---|
| Metadati (titolo e definizione del segmento) | Immediatamente dopo la pubblicazione | [!DNL Audience Manager], [!UICONTROL Experience Cloud Audience Library], [!DNL Target] |
| Segmento utilizzabile con appartenenza | ~ 8 ore dopo la pubblicazione | Visualizzatore del profilo del visitatore in [!DNL Audience Manager] |
| Popolazione di caratteristiche e di appartenenza | Entro 24-48 ore | [!DNL Audience Manager] |

>[!NOTE]
>Una volta alla settimana, tutti i dati saranno sincronizzati completamente per tenere conto di eventuali ritardi o discrepanze non acquisiti nella settimana precedente.

## Pubblicare segmenti in [!UICONTROL Segment Builder]

1. Passa a **[!UICONTROL Analytics > Workspace > Components > Segments]> +**
1. Crea un segmento nel [!UICONTROL Segment Builder].
1. Specifica un titolo e una descrizione per il segmento. In caso contrario non potrai salvarlo.
1. Controlla **[!UICONTROL Publish this segment to the Experience Cloud (for *suite di rapporti *)]**.

![Experience Cloud di pubblicazione](assets/publish-ec.png)

>[!IMPORTANT]
>Assicurati di utilizzare &quot;Visitatori con ID Experience Cloud&quot; quando visualizzi le anteprime dei segmenti in Analytics invece dell&#39;anteprima dei segmenti &quot;visitatori unici&quot; totali quando confronti i numeri di Adobe Analytics con i numeri di Audience Manager:
>
>![Segmenta i visitatori con ECID](assets/seg-vis-ecid.png)

| Elemento | Descrizione |
|---|---|
| **[!UICONTROL Publish this segment to the Experience Cloud (for *`<report suite>`*)]** | Quando questa opzione è abilitata, il titolo e la definizione del segmento (ovvero il pubblico della shell spesso utilizzato nelle piattaforme di annunci) vengono condivisi istantaneamente con l’Experience Cloud, mentre l’appartenenza al segmento viene valutata e condivisa ogni 4 ore. <br> Quando quel pubblico è associato a un&#39;attività in [!DNL Target]ad esempio, [!DNL Analytics] inizia a inviare ID per i visitatori idonei per quell’Experience Cloud e [!DNL Target] pubblico. A questo punto, il nome del pubblico e i dati corrispondenti iniziano a essere visualizzati sulla pagina di Experience Cloud Audiences. </br> |
| **[!UICONTROL Audience Creation Window]** | L&#39;intervallo di tempo selezionato viene utilizzato per creare il pubblico su base continua. Ad esempio, &quot;Ultimi 30 giorni&quot; (impostazione predefinita) include i visitatori che si sono qualificati per il pubblico negli ultimi 30 giorni dalla data odierna (NON dalla data originale di creazione del segmento). |
| **[!UICONTROL Create in Audience Library]** | I segmenti creati e pubblicati possono essere resi disponibili senza latenza nella libreria Pubblico di Experience Cloud. Non dipendono dagli aggiornamenti di Analytics. Questi segmenti non vengono conteggiati rispetto al limite di 75 segmenti pubblicati. |
| **[!UICONTROL x of 75 Published]** | Mostra il numero di segmenti pubblicati nell’Experience Cloud. Fai clic sul collegamento per visualizzare un elenco dei segmenti pubblicati e della suite di rapporti e del relativo proprietario associati. |
| **[!UICONTROL Save]** | Salva questo segmento. |

## Annullare o eliminare segmenti

Per eliminare un segmento pubblicato in Experience Cloud, devi prima annullarne la pubblicazione. Per annullare la pubblicazione di un segmento, **deseleziona** la casella di controllo utilizzata per pubblicarlo.

>[!NOTE]
>
>**Non** puoi annullare la pubblicazione di un segmento attualmente in uso da una delle seguenti soluzioni Adobe: [!DNL Analytics] (in [!DNL Audience Analytics]), [!DNL Campaign], [!DNL Advertising Cloud] (per clienti [!DNL Core Service] e [!DNL Audience Manager]) e tutti gli altri partner esterni (per i clienti [!DNL Audience Manager]). **Puoi** annullare la pubblicazione di un segmento utilizzato da [!DNL Target].

## Visualizza lo stato di pubblicazione dei segmenti nel [!UICONTROL Segment Manager]

1. Passa a [!UICONTROL Analytics > Components > Segments].
1. Osserva la nuova [!UICONTROL Published] colonna. Sì/No indica se il segmento è stato pubblicato nell’Experience Cloud o meno.

![Stato di pubblicazione](assets/publish-status.png)

## Recupera il [!DNL Audience Manager] UUID

Esistono due modi per acquisire l’UUID AAM attualmente associato al browser:

* Adobe Experience Cloud Debugger
* Strumento per sviluppatori nativo nei browser (ad esempio, Chrome Developer Tools)

Le schermate seguenti mostrano come recuperare l’UUID AAM sul browser e utilizzarlo in Visualizzatore profilo visitatore di Audience Manager per convalidare le caratteristiche e l’appartenenza al segmento.

### Metodo 1: Utilizzare Adobe Experience Cloud Debugger

1. Scarica e installa [Debugger Adobe Experience Cloud](/help/implement/validate/debugger.md) in Chrome Web Store.
1. Avvia il debugger durante il caricamento di una pagina.
1. Scorri fino alla sezione Audience Manager e trova l’UUID AAM impostato nella pagina del browser corrente (`50814298273775797762943354787774730612` nell&#39;esempio seguente)

![Debugger](assets/debugger.jpg)

### Metodo 2: Utilizzare Chrome Developer Tools (o altri strumenti per sviluppatori di browser)

1. Avviare Chrome Developer Tools prima di caricare una pagina
1. Carica la pagina e controlla Applicazioni > Cookie. L’UUID AAM deve essere impostato nel cookie demdex di terze parti ([adobe.demdex.net](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/demdex-calls.html?lang=it) nell&#39;esempio seguente). Il campo demdex è l’UUID AAM impostato sul browser (`50814298273775797762943354787774730612` nell&#39;esempio seguente).

![Strumenti per sviluppatori Chrome](assets/ggogle-uuid.png)

## Usa Audience Manager [!UICONTROL Visitor Profile Viewer]

L’UUID AAM nel browser verrà utilizzato per impostazione predefinita quando [!UICONTROL Visitor Profile Viewer] è caricato. Se verifichi le realizzazioni delle caratteristiche per altri utenti, inserisci un UUID nel campo UUID e fai clic su [!UICONTROL Refresh]. Fai riferimento a [Visualizzatore del profilo del visitatore](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/visitor-profile-viewer.html) per ulteriori informazioni.

![Visualizzatore di profili di Audience Manager](assets/aam-vpv.png)

## Visualizzare le caratteristiche del segmento in [!DNL Audience Manager]

In AAM, l’elenco dei visitatori con ECID per un dato segmento viene valutato in streaming, in quanto Analytics condivide ad Experience Cloud i segmenti.

1. In [!DNL Audience Manager], vai a [!UICONTROL Audience Data > Traits > Analytics Traits]. Vedrai una cartella per ogni suite di rapporti di Analytics mappata alla tua organizzazione Experience Cloud. Queste cartelle (per Caratteristiche, Segmenti e Origini dati) vengono create quando viene avviato o eseguito il provisioning del servizio principale Profili e pubblico/Persone .
1. Seleziona la cartella per la suite di rapporti in cui hai creato in precedenza il segmento con cui desideri condividere [!DNL Audience Manager]. Vedrai il segmento/pubblico creato. Quando condividi un segmento, si verificano 2 cose in [!DNL Audience Manager]:
   * Viene creata una caratteristica, prima senza alcun dato. Circa 8 ore dopo la pubblicazione del segmento in [!DNL Analytics], l’elenco degli ECID viene integrato e condiviso con [!DNL Audience Manager] e altre soluzioni di Experience Cloud.

      ![Caratteristiche di Audience Manager](assets/aam-traits.png)

   * Viene creato un segmento con una caratteristica. Utilizza l’origine dati associata alla suite di rapporti in cui hai pubblicato il segmento.
   * La scadenza delle caratteristiche ora è impostata su 16 giorni (in precedenza era di 2 giorni).

## Visualizza il segmento in [!DNL Adobe Target]

La [!UICONTROL Publish this segment to the Experience Cloud] durante il processo di creazione del segmento in Adobe Analytics, consente di rendere disponibile il segmento nella libreria di tipi di pubblico personalizzata di Adobe Target. Puoi utilizzare un segmento creato in Analytics o Audience Manager per attività in Target. Ad esempio, puoi creare campagne sulla base delle metriche di conversione di Analytics e sui segmenti di pubblico creati in Analytics.

1. Fai clic su [!UICONTROL Audiences].
1. Sulla [!UICONTROL Audiences] individuare il pubblico ottenuto dalla [!DNL Experience Cloud]. Questi tipi di pubblico sono disponibili per l’utilizzo in [!DNL Target] attività.
