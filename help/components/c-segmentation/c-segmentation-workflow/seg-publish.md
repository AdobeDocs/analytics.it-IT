---
description: Consente di utilizzare il segmento per l'attività di marketing nella libreria Audience, in Target e in Audience Manager.
title: Pubblicare segmenti in Experience Cloud
topic: Segments
uuid: e5ce20c0-ce43-423b-a29f-ba66e9e24d27
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Pubblicare segmenti in Experience Cloud

>[!IMPORTANT]
>
>I miglioramenti in termini di latenza relativi alla pubblicazione dei segmenti e all’interfaccia utente descritti in questa pagina non vengono ancora implementati a tutti i clienti. L'ambiente di produzione corrente è descritto [qui](https://docs.adobe.com/content/help/en/core-services/interface/audiences/t-publish-audience-segment.html).

La pubblicazione di un segmento in Experience Cloud consente di utilizzare il segmento per l'attività di marketing in [!UICONTROL Audience Library], [!DNL Target], [!DNL Audience Manager], [!DNL Advertising Cloud]e [!DNL Campaign]. Aggiornamenti recenti hanno ottimizzato notevolmente il flusso di lavoro di pubblicazione. In precedenza, la pubblicazione di un segmento utilizzabile richiedeva circa 48 ore.

Ora, l'elaborazione può richiedere fino a 8 ore, ma a seconda del traffico e delle dimensioni del segmento, l'elaborazione potrebbe essere ancora più veloce. Tuttavia, al momento non è disponibile un modo per informarvi quando il segmento è disponibile, pertanto dovrete eseguire il controllo manualmente. Abbiamo anche aumentato il numero massimo di segmenti pubblicabili a 75 (da 20). Puoi visualizzare i segmenti pubblicati in Componenti &gt; Segmenti.

> [!NOTE] Adobe Campaign (Classic e Standard) si comporta in modo diverso in quanto richiede una latenza aggiuntiva di 24 ore sopra la latenza di 8 ore.


## Prerequisiti

* Verifica che la suite di rapporti in cui stai salvando questo segmento sia [abilitata per Experience Cloud](https://docs.adobe.com/content/help/en/core-services/interface/audiences/t-publish-audience-segment.html). In caso contrario, non puoi pubblicarlo in Experience Cloud.
* Assicurati di lavorare in una suite di rapporti [mappata sulla tua organizzazione](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html)Experience Cloud.
* Verifica che la tua organizzazione utilizzi gli Experience Cloud ID.
* Prima di poter pubblicare i segmenti, l'amministratore deve assegnare l' [!UICONTROL Segment Publishing] autorizzazione a un profilo di prodotto in [Admin Console](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html)e aggiungerti al profilo di prodotto.


## Considerazioni

* **Limiti** delle suite di rapporti: Puoi pubblicare fino a 75 segmenti per suite di rapporti. Questo limite è imposto. Se hai già 75 segmenti pubblicati, non puoi pubblicare altri segmenti fino a quando non annulli la pubblicazione di un numero sufficiente di segmenti per scendere al di sotto della soglia dei 75 segmenti.
* **Limiti** di appartenenza: Il pubblico condiviso con il [!DNL Experience Cloud] da Analytics non può superare i 20 milioni di membri unici.
* **Privacy** dei dati: Le audience non vengono filtrate in base allo stato di autenticazione di un visitatore. Se un visitatore può navigare nel sito come utente autenticato o non autenticato, le azioni che si verificano per un visitatore non autenticato possono comunque determinare l'inclusione del visitatore nel pubblico. Leggi la privacy [di](https://www.adobe.com/privacy/experience-cloud.html) Adobe Experience Cloud per comprendere le implicazioni sulla privacy derivanti dalla condivisione di tipi di pubblico.
* Per una discussione sulle **differenze tra i segmenti in[!DNL Adobe Analytics]e[!DNL Audience Manager]**, [fai clic qui](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html).

## Cronologia pubblicazione segmenti

| Disponibilità | Quando è disponibile | Dove è disponibile |
|---|---|---|
| Metadati (titolo e definizione del segmento) | Immediatamente dopo la pubblicazione | [!DNL Audience Manager], [!UICONTROL Experience Cloud Audience Library], [!DNL Target] |
| Segmento utilizzabile con appartenenza | ~ 8 ore dopo la pubblicazione | Visitor Profile Viewer in [!DNL Audience Manager] |
| Caratteristiche e popolazione di appartenenza | Entro 24-48 ore | [!DNL Audience Manager] |

## Pubblicare segmenti in [!UICONTROL Segment Builder]

1. Navigate to **[!UICONTROL Analytics > Workspace > Components > Segments]&gt; +**
1. Crea un segmento nel [!UICONTROL Segment Builder].
1. Immetti un titolo e una descrizione per il segmento. In caso contrario non potrai salvarlo.
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

> [!NOTE]**Non** puoi annullare la pubblicazione di un segmento attualmente in uso da una delle seguenti soluzioni Adobe: [!DNL Analytics] (in [!DNL Audience Analytics]), [!DNL Campaign], [!DNL Advertising Cloud] (per clienti [!DNL Core Service] e [!DNL Audience Manager]) e tutti gli altri partner esterni (per i clienti [!DNL Audience Manager]). **Puoi** annullare la pubblicazione di un segmento utilizzato da [!DNL Target].

## Visualizza lo stato di pubblicazione dei segmenti nel pannello [!UICONTROL Segment Manager]

1. Navigate to [!UICONTROL Analytics > Components > Segments].
1. Notate la nuova [!UICONTROL Published] colonna. Sì/No fa riferimento alla pubblicazione o meno del segmento in Experience Cloud.

![](assets/publish-status.png)

## Recuperare l’ [!DNL Audience Manager] UUID

Esistono due modi per acquisire l’UUID AAM attualmente associato al browser:

* Adobe Experience Cloud Debugger
* Strumento di sviluppo nativo nei browser (ad esempio, Chrome Developer Tools)

Le schermate seguenti mostrano come recuperare l’UUID AAM nel browser e utilizzarlo nel visualizzatore dei profili dei visitatori di Audience Manager per convalidare le caratteristiche e i segmenti di appartenenza.

**Metodo 1: Utilizzare Adobe Experience Cloud Debugger**

1. Scarica e installa [Adobe Experience Cloud Debugger](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/debugger.html) in Chrome Web Store.
1. Avviare il debugger quando si carica una pagina.
1. Scorri fino alla sezione Audience Manager e trova l’UUID AAM impostato sulla pagina del browser corrente (`50814298273775797762943354787774730612` nell’esempio seguente)

![](assets/debugger.jpg)

**Metodo 2: Utilizzare Chrome Developer Tools (o altri strumenti per sviluppatori di browser)**

1. Avviare Chrome Developer Tools prima di caricare una pagina
1. Caricate la pagina e selezionate Applicazioni &gt; Cookie. L’UUID AAM deve essere impostato nel cookie 3rd-partyDemdex ([adobe.demdex.net](https://marketing.adobe.com/resources/help/en_US/aam/demdex-calls.html) nell’esempio seguente). Il demdex del campo è l’impostazione AAM UUID nel browser (`50814298273775797762943354787774730612` nell’esempio di seguito).

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

