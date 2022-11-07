---
title: Rimozione dei bot in Adobe Analytics
description: Come rimuovere i bot in Adobe Analytics
feature: Bot Removal
exl-id: 6d4b1925-4496-4017-85f8-82bda9e92ff3
source-git-commit: ac9e4934cee0178fb00e4201cc3444d333a74052
workflow-type: tm+mt
source-wordcount: '776'
ht-degree: 100%

---

# Rimozione dei bot in Adobe Analytics

In Adobe Analytics, hai diverse opzioni per rimuovere il traffico da bot dai rapporti:

## Usa regole bot

I metodi di filtro dei bot standard e personalizzati sono supportati in **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Bot Rules]**:

| Tipo di regola | Descrizione |
|--- |--- |
| Regole bot standard IAB | Se si seleziona **[!UICONTROL Enable IAB Bot Filtering Rules]**, per rimuovere il traffico da bot viene utilizzata la lista internazionale Spiders e Bots di [IAB](https://www.iab.com/) (International Advertising Bureau). La maggior parte dei clienti seleziona come minimo questa opzione. |
| Regole bot personalizzate | Puoi definire e aggiungere regole bot personalizzate in base agli agenti utente, agli indirizzi IP o agli intervalli IP. |

Per ulteriori dettagli, consulta la [panoramica delle regole bot](/help/admin/admin/bot-removal/bot-rules.md).

## Utilizza il plug-in [!UICONTROL websiteBot] per identificare i bot

Il plug-in [!UICONTROL websiteBot] consente di verificare dinamicamente se i visitatori del desktop sono bot. Puoi utilizzare questi dati per ottenere una maggiore precisione in tutti i tipi di reportistica e quindi un modo migliore per misurare il traffico del sito legittimo.

Questo plug-in esegue due verifiche:

* In primo luogo, determina se il dispositivo è un dispositivo desktop o mobile utilizzando la variabile navigator.UserAgent. I dispositivi mobili vengono ignorati.
* Se si tratta di un dispositivo desktop, aggiunge un listener di eventi per il movimento del mouse.

Per ulteriori informazioni, consulta la [Guida all’implementazione di Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/vars/plugins/websitebot.html?lang=it).

## Utilizzare una combinazione di strumenti Adobe

Inoltre, dal momento che i bot si stanno evolvendo rapidamente, Adobe offre diverse altre potenti funzionalità che, se combinate correttamente e regolarmente, possono aiutare a dare impulso alla rimozione di questi nemici della qualità dei dati. Tali funzionalità sono: Experience Cloud ID Service, segmentazione, Data Warehouse, attributi cliente e suite di rapporti virtuali. Ecco una panoramica su come utilizzare questi strumenti.

### Passaggio 1: passa l&#39;ID Experience Cloud dei visitatori in un nuovo ID dichiarato

Per iniziare, crea un nuovo ID dichiarato nel [servizio core Persone](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=it). Passa l’ID Experience Cloud del visitatore in questo nuovo ID dichiarato, operazione che può essere eseguita in modo rapido e semplice con i [tag in Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/id-service/overview.html?lang=it). Per l’ID dichiarato utilizzeremo il nome “ECID”.

![](assets/bot-cust-attr-setup.png)

Ecco come si può acquisire questo ID tramite l’elemento dati. Assicurati di compilare correttamente l’ID organizzazione di Experience Cloud nell’elemento dati.

```return Visitor.getInstance("REPLACE_WITH_YOUR_ECORG_ID@AdobeOrg").getExperienceCloudVisitorID();```

Una volta configurato l’elemento dati, segui [queste istruzioni](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/id-service/overview.html) per passare gli ID dichiarati nello strumento ECID utilizzando i tag in Adobe Experience Platform.

### Passaggio 2: utilizza la segmentazione per identificare i bot

Ora che l’ECID del visitatore è passato in un ID dichiarato, puoi utilizzare la [segmentazione in Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/t-freeform-project-segment.html?lang=it) per identificare i visitatori che si comportano come bot. I bot sono spesso definiti dal loro comportamento: visite a accesso singolo, agenti utente insoliti, informazioni sconosciute su dispositivi/browser, mancanza di referrer, nuovi visitatori, pagine di destinazione insolite e così via. Utilizza la potenza dei drill-down e della segmentazione di Workspace per identificare i bot che hanno evitato il filtro IAB e le regole bot della suite di rapporti. Ad esempio, questa è la schermata di un segmento che puoi utilizzare:

![](assets/bot-filter-seg1.png)

### Passaggio 3: esporta tutti gli [!DNL Experience Cloud IDs] dal segmento tramite Data Warehouse

Dopo aver identificato i bot che utilizzano i segmenti, il passaggio successivo è utilizzare Data Warehouse per estrarre tutti gli ID Experience Cloud associati al segmento specifico. Questa schermata mostra come impostare la richiesta di [Data Warehouse](/help/export/data-warehouse/data-warehouse.md):

![](assets/bot-dwh-3.png)

Ricorda di utilizzare l’ID visitatore Experience Cloud come dimensione e di applicare il segmento “Bots”.

### Passaggio 4: passa questo elenco ad Adobe come attributo del cliente

Quando arriva il rapporto Data Warehouse, hai un elenco di ECID che devono essere filtrati dai dati storici. Copia e incolla questi ECID in un file .csv vuoto con solo due colonne, ECID e flag bot.

* **ECID**: assicurati che questa intestazione di colonna corrisponda al nome assegnato al nuovo ID dichiarato sopra.
* **Flag bot**: aggiungi “Flag bot” come dimensione dello schema dell’attributo del cliente.

Usa questo file .csv come file di importazione dell’attributo cliente, quindi abbona le suite di rapporti all’attributo cliente come descritto in questo [post di blog](https://theblog.adobe.com/link-digital-behavior-customers).

![](assets/bot-csv-4.png)

### Passaggio 5: crea un segmento che sfrutta il nuovo attributo cliente

Una volta elaborato e integrato il set di dati in Analysis Workspace, crea un altro segmento che sfrutta la nuova dimensione dell’attributo del cliente “Bot Flag” e un contenitore [!UICONTROL Exclude]:

![](assets/bot-filter-seg2.png)

### Passaggio 6: utilizza questo segmento come filtro della suite di rapporti virtuale

Infine, crea una [Suite di rapporti virtuale](/help/components/vrs/vrs-about.md) che utilizza questo segmento per filtrare i bot identificati:

![](assets/bot-vrs.png)

Questa suite di rapporti virtuale appena segmentata darà luogo a un set di dati più pulito, con i bot identificati rimossi.

### Passaggio 7: ripeti regolarmente i passaggi 2, 3 e 4

Imposta almeno un promemoria mensile per identificare e filtrare i nuovi bot, probabilmente prima di un’analisi pianificata regolarmente.
