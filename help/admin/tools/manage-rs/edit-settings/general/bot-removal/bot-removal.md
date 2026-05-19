---
title: Rimozione dei bot in Adobe Analytics
description: Come rimuovere i bot in Adobe Analytics
feature: Bot Removal
role: Admin
exl-id: 6d4b1925-4496-4017-85f8-82bda9e92ff3
TQID: https://experienceleague.adobe.com/oAChv7R7BAOTvI4mKpkHsYLyaxhXSxXDWq4R8ma1n-M
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b4dd41a7-ccf8-4e9d-918e-acaab534a307
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 7d733a6375f6c6009563bc53f5a3ff090dbc48ed
workflow-type: tm+mt
source-wordcount: 770
ht-degree: 60%

---

# Rimozione dei bot in Adobe Analytics

Adobe Analytics fornisce diverse opzioni per rimuovere il traffico da bot dai rapporti:

## Usa regole bot

I metodi di filtro dei bot standard e personalizzati sono supportati in **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Bot Rules]**:

| Tipo di regola | Descrizione |
|--- |--- |
| Regole bot standard IAB | Se si seleziona **[!UICONTROL Enable IAB Bot Filtering Rules]**, per rimuovere il traffico da bot viene utilizzata la lista internazionale Spiders e Bots di [IAB](https://www.iab.com/) (International Advertising Bureau). La maggior parte dei clienti seleziona come minimo questa opzione. |
| Regole bot personalizzate | Puoi definire e aggiungere regole bot personalizzate in base agli agenti utente, agli indirizzi IP o agli intervalli IP. |

Per ulteriori dettagli, consulta [Comprendere e configurare le regole bot](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md).

## Utilizzare una combinazione di strumenti Adobe

Inoltre, dal momento che i bot si stanno evolvendo rapidamente, Adobe offre diverse altre potenti funzionalità che, se combinate correttamente e regolarmente, possono aiutare a dare impulso alla rimozione di questi nemici della qualità dei dati. Tali funzioni sono: servizio Experience Cloud ID, segmentazione, Data Warehouse, attributi cliente e suite di rapporti virtuali. Ecco una panoramica su come utilizzare questi strumenti.

### Passaggio 1: passa l&#39;ID Experience Cloud dei visitatori in un nuovo ID dichiarato

Per iniziare, crea un nuovo ID dichiarato nel [servizio core Persone](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=it). Passa l’ID Experience Cloud del visitatore in questo nuovo ID dichiarato, operazione che può essere eseguita in modo rapido e semplice con i [tag in Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/id-service/overview.html?lang=it). Per l’ID dichiarato utilizzeremo il nome “ECID”.

![](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/assets/bot-cust-attr-setup.png)

Ecco come si può acquisire questo ID tramite l’elemento dati. Assicurati di compilare correttamente l’ID organizzazione CX Enterprise nell’elemento dati.

```return Visitor.getInstance("REPLACE_WITH_YOUR_ECORG_ID@AdobeOrg").getExperienceCloudVisitorID();```

Una volta configurato l’elemento dati, segui [queste istruzioni](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/id-service/overview.html?lang=it) per passare gli ID dichiarati nello strumento ECID utilizzando i tag in Adobe Experience Platform.

### Passaggio 2: utilizza la segmentazione per identificare i bot

Ora che l’ECID del visitatore è passato in un ID dichiarato, puoi utilizzare la [segmentazione in Analysis Workspace](/help/analyze/analysis-workspace/components/segments/t-freeform-project-segment.md) per identificare i visitatori che si comportano come bot. I bot sono spesso definiti dal loro comportamento: visite a accesso singolo, agenti utente insoliti, informazioni sconosciute su dispositivi/browser, assenza di referrer, nuovi visitatori, pagine di destinazione insolite e così via. Utilizza la potenza dei drill-down e della segmentazione di Workspace per identificare i bot che hanno evitato il filtro IAB e le regole bot della suite di rapporti. Ad esempio, questa è la schermata di un segmento che puoi utilizzare:

![](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/assets/bot-filter-seg1.png)

### Passaggio 3: esporta tutti gli [!DNL Experience Cloud IDs] dal segmento tramite Data Warehouse

Dopo aver identificato i bot che utilizzano i segmenti, il passaggio successivo è utilizzare Data Warehouse per estrarre tutti gli ID Experience Cloud associati al segmento specifico. Questa schermata mostra come impostare la richiesta di [Data Warehouse](/help/export/data-warehouse/data-warehouse.md):

![](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/assets/bot-dwh-3.png)

Ricorda di utilizzare l’ID visitatore aziendale CX come dimensione e di applicare il segmento &quot;Bots&quot;.

### Passaggio 4: passa questo elenco ad Adobe come attributo del cliente

Quando arriva il rapporto Data Warehouse, hai un elenco di ECID che devono essere filtrati dai dati storici. Copia e incolla questi ECID in un file .csv vuoto con solo due colonne, ECID e flag bot.

* **ECID**: assicurati che questa intestazione di colonna corrisponda al nome assegnato al nuovo ID dichiarato sopra.
* **Flag bot**: aggiungi &quot;Flag bot&quot; come dimensione dello schema dell&#39;attributo del cliente.

Usa questo file .CSV come file di importazione dell&#39;attributo cliente, quindi abbona le suite di rapporti all&#39;attributo cliente come descritto in questo [post di blog](https://blog.adobe.com/en/publish/2016/10/20/link-digital-behavior-customers).

![](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/assets/bot-csv-4.png)

### Passaggio 5: creare un segmento che sfrutta il nuovo attributo cliente

Una volta elaborato e integrato il set di dati in Analysis Workspace, crea un altro segmento che sfrutta la nuova dimensione dell’attributo del cliente “Bot Flag” e un contenitore [!UICONTROL Exclude]:

![](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/assets/bot-filter-seg2.png)

### Passaggio 6: utilizza questo segmento come filtro della suite di rapporti virtuale

Infine, crea una [Suite di rapporti virtuale](/help/components/vrs/vrs-about.md) che utilizza questo segmento per filtrare i bot identificati:

![](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/assets/bot-vrs.png)

Questa suite di rapporti virtuale appena segmentata darà luogo a un set di dati più pulito, con i bot identificati rimossi.

### Passaggio 7: ripeti regolarmente i passaggi 2, 3 e 4

Imposta almeno un promemoria mensile per identificare e filtrare i nuovi bot, probabilmente prima di un’analisi pianificata regolarmente.

>[!MORELIKETHIS]
>
>* [Blocco Bot Migliore (Parte 1): Nozioni Di Base](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/better-bot-blocking-part-1-the-basics/ba-p/715839)
>* [Migliore blocco dei bot (parte 2): identificazione dei bot e utilizzo di CIDR](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/better-bot-blocking-part-2-identifying-bots-and-leveraging-cidr/ba-p/722132)
>* [Blocco Bot Migliore (Parte 3): Hit Governor](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/better-bot-blocking-part-3-the-hit-governor/ba-p/727051)

