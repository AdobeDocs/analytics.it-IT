---
title: Rimozione bot in Adobe Analytics
seo-title: Rimozione bot in Adobe Analytics
description: 3 modalità per rimuovere i bot in Adobe Analytics
seo-description: 3 modalità per rimuovere i bot in Adobe Analytics
translation-type: tm+mt
source-git-commit: 53b1559c7596fae7bc36bb7337967a71d9fc22e2

---


# Rimozione bot in Adobe Analytics

In Adobe Analytics, avete diverse opzioni per rimuovere il traffico bot dai rapporti:

## Usa regole bot

Sono supportati sia i metodi di filtro bot standard che quelli personalizzati in !![UICONTROL Analytics > Admin > Report Suites > Edit Settings > General > Bot Rules]:

| Tipo di regola | Descrizione |
|--- |--- |
| Regole bot IAB standard | Selecting 'Enable IAB Bot Filtering Rules' uses the [IAB's](https://www.iab.com/) (International Advertising Bureau's) International Spiders &amp; Bots List to remove bot traffic. La maggior parte dei clienti seleziona questa opzione come minimo. |
| Regole bot personalizzate | Puoi definire e aggiungere regole bot personalizzate basate su agenti utente, indirizzi IP o intervalli IP. |

Per maggiori informazioni, consultate [Panoramica delle regole bot](/help/admin/admin/bot-removal/bot-rules.md).

## Utilizzare il `hitGovernor` plug-in di implementazione

Utilizza il [plug-in di implementazione s. hitdeck](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/plugins/hitgovernor.html), che rimuove i visitatori che si comportano come bot inviando decine o centinaia di hit al minuto.

## Utilizzo di una combinazione di strumenti Adobe

Inoltre, poiché i bot avanzano rapidamente, Adobe offre numerose altre funzionalità avanzate che, se combinate in modo corretto e periodico, possono contribuire a rimuovere la rimozione di questi nemici della qualità dei dati. Queste funzioni sono: Servizio Experience Cloud ID, Segmentazione, Data Warehouse, Attributi del cliente e Suite di rapporti virtuali. Ecco una panoramica su come sfruttare questi strumenti.

### Passaggio 1: Passa l'Experience Cloud ID dei visitatori in un nuovo ID dichiarato

Per iniziare, devi creare un nuovo ID dichiarato nel servizio core [Persone](https://docs.adobe.com/content/help/en/core-services/interface/audiences/audience-library.html). Dovrai passare l'Experience Cloud ID del visitatore in questo nuovo ID dichiarato, che può essere eseguito in modo rapido e semplice con [Adobe Experience Platform Launch](https://docs.adobe.com/content/help/en/launch/using/implement/solutions/idservice-save.html). Usiamo il nome «ECID» per l'ID dichiarato.

![](assets/bot-cust-attr-setup.png)

Ecco come questo ID può essere acquisito tramite Elemento dati. Assicurati di compilare correttamente la tua organizzazione di Experience Cloud nell'elemento dati.

```return Visitor.getInstance("REPLACE_WITH_YOUR_ECORG_ID@AdobeOrg").getExperienceCloudVisitorID();```

Una volta configurato questo elemento dati, segui [queste istruzioni](https://docs.adobe.com/content/help/en/launch/using/implement/solutions/idservice-save.html) per passare gli ID dichiarati nello strumento ECID in Launch.

### Passaggio 2: Usare la segmentazione per identificare i bot

Ora che il ECID del visitatore è passato in un ID dichiarato, puoi utilizzare [la segmentazione in Analysis Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/t-freeform-project-segment.html) per identificare i visitatori che si comportano come bot. I bot sono spesso definiti dal relativo comportamento: visite di accesso singolo, agenti utente insoliti, informazioni sconosciute su dispositivo/browser, nessun referente, nuovi visitatori, pagine di destinazione insolite, ecc. Utilizza le funzionalità di approfondimento e segmentazione di Workspace per identificare i bot che hanno generato filtri IAB evasi e le regole bot della suite di rapporti. Ad esempio, ecco una schermata di un segmento che potresti usare:

![](assets/bot-filter-seg1.png)

### Passaggio 3: Esportare tutti i file ECID dal segmento tramite Data Warehouse

Ora che hai identificato i bot utilizzando i segmenti, il passaggio successivo consiste nell'sfruttare Data Warehouse per estrarre tutti gli ID di Experience Cloud associati a questo segmento. Ecco come impostare la richiesta [Data Warehouse](https://docs.adobe.com/content/help/en/analytics/export/data-warehouse/data-warehouse.html) :

![](assets/bot-dwh-3.png)

Ricorda di utilizzare l'ID visitatore Experience Cloud come dimensione e applicare il segmento Bots.

### Passaggio 4: Reindirizzare questo elenco ad Adobe come attributo cliente

Una volta raggiunto il rapporto Data Warehouse, avrai un elenco di ECID che devono essere filtrati dai dati storici. Copiate e incollate questi ECID in un file. CSV vuoto con sole due colonne, ECID e Flag Bot.

* **ECID**: Assicurati che l'intestazione di colonna corrisponda al nome assegnato al nuovo ID dichiarato sopra.
* **Flag bot**: Aggiungi questa dimensione come dimensione schema attributo cliente.

Usa questo file. CSV come file di importazione attributo del cliente, quindi sottoscrivi le suite di rapporti all'attributo del cliente come descritto in questo [post di blog](https://theblog.adobe.com/link-digital-behavior-customers).

![](assets/bot-csv-4.png)

### Passaggio 5: Crea un segmento che sfrutta il nuovo attributo cliente

Una volta che il set di dati è stato elaborato ed integrato in Analysis Workspace, crea un altro segmento che sfrutta la nuova dimensione attributo "Flag Bot" e un !![UICONTROL Exclude] contenitore:

![](assets/bot-filter-seg2.png)

### Passaggio 6: Usa questo segmento come filtro Suite di rapporti virtuale

Infine, devi creare una [suite di rapporti virtuale](/help/components/vrs/vrs-about.md) che sfrutta questo segmento per filtrare i bot identificati:

![](assets/bot-vrs.png)

Questa suite di rapporti virtuale appena segmentata darà luogo a un insieme di dati significativamente più pulito, con i bots identificati completamente rimossi.

### Passaggio 7: Ripetete i passaggi 2, 3 e 4 regolarmente

Impostare almeno un promemoria mensile per identificare e filtrare nuovi bot, possibilmente prima di un'analisi pianificata regolarmente.
