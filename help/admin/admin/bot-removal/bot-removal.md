---
title: Rimozione dei bot in Adobe Analytics
seo-title: Rimozione dei bot in Adobe Analytics
description: 3 modi per rimuovere bot in Adobe Analytics
seo-description: 3 modi per rimuovere bot in Adobe Analytics
translation-type: tm+mt
source-git-commit: ef17712b4a8a4a5c13dde9be9fdf2281eeb40091

---


# Rimozione dei bot in Adobe Analytics

In Adobe Analytics sono disponibili diverse opzioni per rimuovere il traffico bot dai report:

## Usa regole bot

I metodi di filtraggio dei bot standard e personalizzati sono supportati in **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]** &gt; **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL General]** &gt; **[!UICONTROL Bot Rules]**:

| Tipo di regola | Descrizione |
|--- |--- |
| Regole bot IAB standard | La selezione **[!UICONTROL Enable IAB Bot Filtering Rules]** utilizza l' [IAB](https://www.iab.com/) (International Advertising Bureau's) International Spiders &amp; Bots List per rimuovere il traffico bot. La maggior parte dei clienti seleziona questa opzione almeno. |
| Regole bot personalizzate | Potete definire e aggiungere regole bot personalizzate basate su agenti utente, indirizzi IP o intervalli IP. |

Per ulteriori dettagli, consultate Panoramica delle regole [bot](/help/admin/admin/bot-removal/bot-rules.md).

## Utilizzare il plug-in di `hitGovernor` implementazione

Utilizzate il plug-in [di implementazione](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/plugins/hitgovernor.html)s.hitGovernatore, che rimuove i visitatori che si comportano come bot, il che significa che questi visitatori inviano decine o centinaia di hit al minuto.

## Utilizzare una combinazione di Adobe Tools

Inoltre, dal momento che i bot si stanno trasformando rapidamente, Adobe offre diverse altre potenti funzionalità che, se combinate correttamente e su base regolare, possono aiutare a rimuovere questi nemici dalla qualità dei dati. Tali caratteristiche sono: Servizio Experience Cloud ID, segmentazione, data warehouse, attributi cliente e suite di rapporti virtuali. Di seguito viene fornita una panoramica di come utilizzare questi strumenti.

### Passaggio 1: Passa l’Experience Cloud ID dei visitatori in un nuovo ID dichiarato

Per iniziare, create un nuovo ID dichiarato nel servizio [core](https://docs.adobe.com/content/help/en/core-services/interface/audiences/audience-library.html)Persone. Dovrai trasmettere l’Experience Cloud ID del visitatore a questo nuovo ID dichiarato, che può essere fatto in modo rapido e semplice con [Adobe Experience Platform Launch](https://docs.adobe.com/content/help/en/launch/using/implement/solutions/idservice-save.html). Usiamo il nome "ECID" per l’ID dichiarato.

![](assets/bot-cust-attr-setup.png)

Questo è il modo in cui questo ID può essere acquisito tramite Data Element. Assicurati di compilare correttamente l’ID organizzazione Experience Cloud nell’elemento dati.

```return Visitor.getInstance("REPLACE_WITH_YOUR_ECORG_ID@AdobeOrg").getExperienceCloudVisitorID();```

Una volta configurato questo elemento dati, segui [queste istruzioni](https://docs.adobe.com/content/help/en/launch/using/implement/solutions/idservice-save.html) per passare gli ID dichiarati allo strumento ECID in Launch.

### Passaggio 2: Utilizzare la segmentazione per identificare i bot

Ora che l’ECID del visitatore viene passato in un ID dichiarato, puoi utilizzare la [segmentazione in Analysis Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/t-freeform-project-segment.html) per identificare i visitatori che si comportano come bot. I robot sono spesso definiti dal loro comportamento: visite di accesso singolo, agenti utente insoliti, informazioni sconosciute su dispositivo/browser, nessun referente, nuovi visitatori, pagine di destinazione insolite, ecc. Utilizzate le funzionalità di drill-down e segmentazione di Workspace per identificare i bot che hanno evitato il filtro IAB e le regole bot della suite di rapporti. Ad esempio, di seguito è riportata una schermata di un segmento utilizzabile:

![](assets/bot-filter-seg1.png)

### Passaggio 3: Esportare tutti [!DNL Experience Cloud IDs] dal segmento tramite Data Warehouse

Dopo aver identificato i bot utilizzando i segmenti, il passo successivo consiste nell’utilizzare Data Warehouse per estrarre tutti gli Experience Cloud ID associati a questo segmento. Come impostare la richiesta [Data Warehouse](https://docs.adobe.com/content/help/en/analytics/export/data-warehouse/data-warehouse.html) :

![](assets/bot-dwh-3.png)

Ricorda di usare l’ID visitatore di Experience Cloud come dimensione e di applicare il segmento Bots.

### Passaggio 4: Restituisci questo elenco ad Adobe come attributo del cliente

Una volta ricevuto il rapporto Data Warehouse, avrai un elenco di ECID che devono essere filtrati dai dati storici. Copiate e incollate questi ECID in un file .CSV vuoto contenente solo due colonne, ECID e Bot Flag.

* **ECID**: Assicurati che l’intestazione di colonna corrisponda al nome assegnato al nuovo ID dichiarato sopra.
* **Flag** bot: Aggiungete questa dimensione come schema attributo cliente.

Utilizzate questo file .CSV come file di importazione attributo del cliente, quindi iscrivete le suite di rapporti all'attributo del cliente come descritto in questo post [di](https://theblog.adobe.com/link-digital-behavior-customers)blog.

![](assets/bot-csv-4.png)

### Passaggio 5: Crea un segmento che sfrutta il nuovo attributo cliente

Dopo aver elaborato e integrato il set di dati in Analysis Workspace, crea un altro segmento che sfrutta la nuova dimensione attributo cliente "Bot Flag" e un [!UICONTROL Exclude] contenitore:

![](assets/bot-filter-seg2.png)

### Passaggio 6: Utilizza questo segmento come filtro della suite di rapporti virtuale

Infine, è necessario creare una suite [di rapporti](/help/components/vrs/vrs-about.md) virtuale che sfrutta questo segmento per filtrare i bot identificati:

![](assets/bot-vrs.png)

Questa suite di rapporti virtuali di nuova segmentazione darà vita a un set di dati significativamente più pulito, con i bot identificati completamente rimossi.

### Passaggio 7: Ripetere regolarmente i passaggi 2, 3 e 4

Impostate almeno un promemoria mensile per identificare e filtrare i nuovi bot, forse prima dell'analisi pianificata regolarmente.
