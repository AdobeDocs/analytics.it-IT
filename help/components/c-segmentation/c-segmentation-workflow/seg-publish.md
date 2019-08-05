---
description: Consente di utilizzare il segmento per attività di marketing nella libreria Audience, Target e Audience Manager.
seo-description: Consente di utilizzare il segmento per attività di marketing nella libreria Audience, Target e Audience Manager.
seo-title: Pubblicare segmenti in Experience Cloud
solution: Analytics
title: Pubblicare segmenti in Experience Cloud
topic: Segmenti
uuid: e 5 ce 20 c 0-ce 43-423 b-a 29 f-ba 66 e 9 e 24 d 27
translation-type: tm+mt
source-git-commit: 6298c00cf4c74a493b6ba6266763d693897d5299

---


# Pubblicare segmenti in Experience Cloud

>[!IMPORTANT]
>
>I miglioramenti della latenza relativi alla pubblicazione dei segmenti e l'interfaccia utente descritta in questa pagina non vengono ancora distribuiti a tutti i clienti. L'ambiente di produzione corrente è descritto [](https://docs.adobe.com/content/help/en/core-services/interface/audiences/t-publish-audience-segment.html)qui.

La pubblicazione di un segmento in Experience Cloud consente di utilizzare il segmento per attività di marketing nell ' [!UICONTROL Audience Library][!DNL Target][!DNL Audience Manager], e [!DNL Advertising Cloud]. Gli aggiornamenti recenti hanno ottimizzato notevolmente il flusso di lavoro di pubblicazione. In precedenza, la pubblicazione di un segmento utilizzabile richiedeva circa 48 ore.

Ora l'elaborazione può richiedere fino a 8 ore, ma in base ad altri traffico e alle dimensioni del segmento, l'elaborazione potrebbe essere ancora più veloce. (Tuttavia, al momento non è possibile informarvi quando il segmento è disponibile, pertanto dovrete effettuare il controllo manualmente.) Abbiamo inoltre aumentato il numero massimo di segmenti pubblicabili a 75 (da 20). Puoi visualizzare i segmenti pubblicati in Componenti &gt; Segmenti.


## Prerequisiti

* Assicurati che la suite di rapporti in cui stai salvando il segmento sia [abilitata per Experience Cloud](https://docs.adobe.com/content/help/en/core-services/interface/audiences/t-publish-audience-segment.html). In caso contrario, non potete pubblicarlo in Experience Cloud.
* Assicurati di lavorare in una suite di rapporti [mappata sulla tua organizzazione Experience Cloud](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html).
* Prima di pubblicare i segmenti, l'amministratore deve assegnare l' [!UICONTROL Segment Publishing] autorizzazione a un profilo di prodotto in [Admin Console](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html)e aggiungerti al profilo di prodotto.


## Considerazioni

* **Limiti di suite di rapporti**: Puoi pubblicare fino a 75 segmenti per suite di rapporti. Questo limite viene imposto. Se hai già pubblicato 75 segmenti, non puoi pubblicare altri segmenti fino a quando non ripubblichi abbastanza segmenti per scendere sotto la soglia di 75 segmenti.
* **Limiti di iscrizione**: I tipi di pubblico condivisi [!DNL Experience Cloud] con Analytics non possono superare i 20 milioni di membri unici.
* **Privacy dei dati**: Le audience non vengono filtrate in base allo stato di autenticazione di un visitatore. Se un visitatore può navigare nel sito come utente autenticato o non autenticato, le azioni che si verificano per un visitatore non autenticato possono comunque determinare l'inclusione del visitatore nel pubblico. Leggi [la privacy di Adobe Experience Cloud](https://www.adobe.com/privacy/experience-cloud.html) per comprendere le implicazioni sulla privacy relative alla condivisione di tipi di pubblico.
* Per una discussione sulle differenze tra i segmenti, [!DNL Adobe Analytics][!DNL Audience Manager]fai clic [qui](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html).

## Cronologia di pubblicazione segmenti

| Informazioni disponibili | Quando disponibile | Dove è disponibile |
|---|---|---|
| Metadati (titolo del segmento e definizione) | Subito dopo la pubblicazione | [!DNL Audience Manager], [!UICONTROL Experience Cloud Audience Library], [!DNL Target] |
| Segmento utilizzabile con appartenenza | ~ 8 ore dopo la pubblicazione | Visualizzatore profilo visitatore in [!DNL Audience Manager] |
| Popolazione e popolazione di appartenenza | Entro 24 ore | [!DNL Audience Manager] |

## Pubblicare segmenti in [!UICONTROL Segment Builder]

1. Passa a [!UICONTROL Analytics > Workspace > Components > Segments] &gt; +
1. Crea un segmento in [!UICONTROL Segment Builder].
1. Fornite un titolo e una descrizione del segmento; non potrete salvarlo in altro modo.
1. Check [!UICONTROL Publish this segment to the Experience Cloud (for *report suite *)].

![](assets/publish-ec.png)

| Elemento | Descrizione |
|---|---|
| Pubblica questo segmento in Experience Cloud (per `<report suite>`) | Quando questa opzione è attivata, il titolo e la definizione del segmento (ovvero l'audience shell utilizzata spesso nelle piattaforme pubblicitarie) vengono condivisi con Experience Cloud, mentre l'iscrizione al segmento viene valutata e condivisa ogni 4 ore. <br> Quando quel pubblico viene associato a un'attività in, [!DNL Target]ad esempio, [!DNL Analytics] inizia a inviare ID per i visitatori idonei per Experience Cloud e [!DNL Target] audience. A questo punto, il nome del pubblico e i dati corrispondenti iniziano a essere visualizzati sulla pagina di Experience Cloud Audiences. </br> |
| Finestra Creazione pubblico | Il periodo di tempo selezionato viene utilizzato per creare il pubblico su base lineare. Ad esempio, «Ultimi 30 giorni (predefinito) include i visitatori che hanno qualificato l'audience negli ultimi 30 giorni dalla data odierna (NON dalla data originale alla creazione del segmento). |
| Crea nella libreria Pubblico | I segmenti creati e pubblicati possono essere resi disponibili senza latenza nella Libreria Pubblico di Experience Cloud. Non dipendono dagli aggiornamenti di Analytics. Questi segmenti non vengono conteggiati rispetto al limite di 75 segmenti pubblicati. |
| x di 75 Pubblicato | Mostra il numero di segmenti pubblicati in Experience Cloud. Fai clic sul collegamento per visualizzare un elenco dei segmenti pubblicati e della suite di rapporti e del proprietario associati. |
| Salva | Salva questo segmento. |

## Annullare la pubblicazione o eliminare i segmenti

Per eliminare un segmento pubblicato in Experience Cloud, devi annullarne la pubblicazione. Per annullare la pubblicazione di un segmento, **deseleziona** la casella di controllo utilizzata per pubblicarla.

>[!NOTE]
>
>**Non** puoi annullare la pubblicazione di un segmento attualmente in uso da una delle seguenti soluzioni Adobe: [!DNL Analytics] (in [!DNL Audience Analytics]), [!DNL Campaign]( [!DNL Advertising Cloud] per [!DNL Core Service] &amp; [!DNL Audience Manager] clienti) e tutti gli altri partner esterni (per [!DNL Audience Manager] i clienti). **** Puoi annullare la pubblicazione di un segmento utilizzato da [!DNL Target].

## Visualizza lo stato di pubblicazione del segmento nella variabile [!UICONTROL Segment Manager]

1. [!UICONTROL Analytics > Components > Segments]Passa a.
1. Osservate la nuova [!UICONTROL Published] colonna. Sì/No indica se il segmento è stato pubblicato in Experience Cloud o meno.

![](assets/publish-status.png)

## Recupera l' [!DNL Audience Manager] UUID

Esistono 2 modi per acquisire l'UUID AAM attualmente associato al browser:

* Adobe Experience Cloud Debugger
* Strumento nativo per sviluppatori nei browser (ad esempio, Chrome Developer Tools)

Le seguenti schermate mostrano come recuperare l'UUID AAM sul browser e utilizzarlo nel visualizzatore di profilo visitatore di Audience Manager per convalidare l'appartenenza a tratti e segmenti.

**Metodo 1: Utilizzare Adobe Experieence CLoud Debugger**

1. Scarica e installa [Adobe Experience Cloud Debugger](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/debugger.html) in Chrome Web Store.
1. Avviare il debugger quando si carica una pagina.
1. Scorri fino alla sezione Audience Manager e trova il set AAM AAM impostato sulla pagina
del browser corrente (`50814298273775797762943354787774730612` nell'esempio di seguito)

![](assets/debugger.jpg)

**Metodo 2: Utilizzare gli strumenti per sviluppatori Chrome (o altri strumenti per sviluppatori di browser)**

1. Avviare Chrome Developer Tools prima di caricare una pagina
1. Caricate la pagina e verificate Applicazioni &gt; Cookie. L'UUID AAM deve essere impostato nel cookie 3 rd-party
Demdex ([adobe. demdex. net](https://marketing.adobe.com/resources/help/en_US/aam/demdex-calls.html) nell'esempio di seguito). Il campo demdex è il set di UAM AAM impostato
sul browser (`50814298273775797762943354787774730612` nell'esempio di seguito).

![Strumenti per sviluppatori Chrome](assets/ggogle-uuid.png)

## Utilizzo di Audience Manager [!UICONTROL Visitor Profile Viewer]

L'UUID AAM sul browser verrà utilizzato per impostazione predefinita quando [!UICONTROL Visitor Profile Viewer] viene caricato. Se verifica le realizzazioni delle caratteristiche per altri utenti, immetti un UUID nel campo UUID e fai clic [!UICONTROL Refresh]. Per [ulteriori informazioni, consultate Visualizzatore](https://marketing.adobe.com/resources/help/en_US/aam/t_visitor_profile_viewer.html) profilo visitatore.

![](assets/aam-vpv.png)

## Visualizza le caratteristiche del segmento in [!DNL Audience Manager]

In AAM, l'elenco di visitatori con ECID per un determinato segmento viene valutato in streaming quando Analytics condivide segmenti con Experience Cloud.

1. In [!DNL Audience Manager], vai a [!UICONTROL Audience Data > Traits > Analytics Traits]. Vedrai una cartella per ogni suite di rapporti di Analytics mappata sulla tua organizzazione Experience Cloud. Queste cartelle (per Caratteristiche, Segmenti e Origini dati) vengono create quando i servizi di base Profili e Pubblico/Persone vengono avviati o sottoposti a provisioning.
1. Seleziona la cartella per la suite di rapporti in cui hai creato in precedenza il segmento con [!DNL Audience Manager]cui vuoi condividere. Vedrai il segmento/pubblico che hai creato. Quando condividi un segmento, 2 cose avvengono in [!DNL Audience Manager]:
* Viene creato un trait, prima senza dati. Circa. 8 ore dopo la pubblicazione del segmento [!DNL Analytics], l'elenco di ECID viene caricato e condiviso con [!DNL Audience Manager] e con altre soluzioni Experience Cloud.

![](assets/aam-traits.png)

* Viene creato un segmento con caratteristiche. Utilizza l'origine dati associata alla suite di rapporti in cui hai pubblicato il segmento.

## Visualizza il segmento in [!DNL Adobe Target]

The [!UICONTROL Publish this segment to the Experience Cloud] checkbox during the segment creation process in Adobe Analytics allows the segment to be available within the Adobe Target's custom audience library. Puoi utilizzare un segmento creato in Analytics o Audience Manager per attività in Target. Ad esempio, puoi creare campagne sulla base delle metriche di conversione di Analytics e sui segmenti di pubblico creati in Analytics.
], click [!UICONTROL Audiences].
1. On the [!UICONTROL Audiences] page, locate the audience sourced from the [!DNL Experience Cloud]. These audiences are available for use in [!DNL Target] activities.
