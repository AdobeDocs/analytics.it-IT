---
title: Rimozione bot in Adobe Analytics
seo-title: Rimozione bot in Adobe Analytics
description: 3 modalità per rimuovere i bot in Adobe Analytics
seo-description: 3 modalità per rimuovere i bot in Adobe Analytics
translation-type: tm+mt
source-git-commit: 0e882f4908dababaf96cf225c62f7ab3bb35860e

---


# Rimozione bot in Adobe Analytics

In Adobe Analytics, avete diverse opzioni per rimuovere il traffico bot dai rapporti:

1. Il metodo di filtro bot predefinito in Adobe Analytics consiste [nel creare regole](/help/admin/admin/bot-removal/bot-rules.md) bot basate sull'elenco bot IAB. Questo elenco viene aggiornato mensilmente e ne effettua la compilazione da numerose fonti, inclusi i DN e le principali proprietà Internet. Comprende migliaia di bot noti, inclusi tutti i preferiti: Google, Bing, Mozilla, ecc. Questo elenco illustra la stragrande maggioranza dei casi di utilizzo e le esigenze per la filtrazione dei bot.

1. Utilizza il [plug-in di implementazione s. hitdeck](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/plugins/hitgovernor.html), che rimuove i visitatori che si comportano come bot inviando decine o centinaia di hit al minuto.

1. Inoltre, poiché i bot avanzano rapidamente, Adobe offre numerose altre funzionalità avanzate che, se combinate in modo corretto e periodico, possono contribuire a rimuovere la rimozione di questi nemici della qualità dei dati. Queste funzioni sono: Servizio Experience Cloud ID, Segmentazione, Data Warehouse, Attributi del cliente e Suite di rapporti virtuali. Ecco una panoramica su come sfruttare i seguenti strumenti:

## Passaggio 1: Passa l'Experience Cloud ID dei visitatori in un nuovo ID dichiarato

Per iniziare, devi creare un nuovo ID dichiarato nel servizio di base [Audience](https://docs.adobe.com/content/help/en/core-services/interface/audiences/audience-library.html). Dovrai passare l'Experience Cloud ID del visitatore in questo nuovo ID dichiarato, che può essere eseguito in modo rapido e semplice con [Adobe Experience Platform Launch](https://docs.adobe.com/content/help/en/launch/using/implement/solutions/idservice-save.html). Usiamo il nome «ECID» per l'ID dichiarato.

screenshot here

Ecco come questo ID può essere acquisito tramite Elemento dati. Accertatevi di compilare correttamente l'ID Adobe ecorg nell'elemento dati.

```return Visitor.getInstance("REPLACE_WITH_YOUR_ECORG_ID@AdobeOrg").getExperienceCloudVisitorID();```

Una volta configurato questo elemento dati, segui [queste istruzioni](https://docs.adobe.com/content/help/en/launch/using/implement/solutions/idservice-save.html) per passare gli ID dichiarati nello strumento ECID in Launch.

## Passaggio 2: Usare la segmentazione per identificare i bot

Ora che il ECID del visitatore è passato in un ID dichiarato, è ora di utilizzare la segmentazione in Analysis Workspace per identificare i visitatori che si comportano come bot. I bot sono spesso definiti dal relativo comportamento: visite di accesso singolo, agenti utente insoliti, informazioni sconosciute su dispositivo/browser, nessun referente, nuovi visitatori, pagine di destinazione insolite, ecc. Utilizza le potenzialità delle drilldown e della segmentazione di Workspace per identificare i bot che hanno generato filtri IAB evasi e le regole bot della suite di rapporti. Ad esempio, ecco una schermata di un segmento che potresti usare:

![](assets/bot-filter-seg1.png)

## Passaggio 3: Esportare tutti i file ECID dal segmento tramite Data Warehouse

Ora che hai identificato i bot utilizzando i segmenti, il passaggio successivo consiste nell'sfruttare Data Warehouse per estrarre tutti gli ID di Experience Cloud associati a questo segmento. Per configurare il rapporto [Data Warehouse](https://docs.adobe.com/content/help/en/analytics/export/data-warehouse/data-warehouse.html) :

![](assets/bot-dwh-3.png)

Ricorda di utilizzare l'ID visitatore Experience Cloud come dimensione e applicare il segmento Bots.

## Passaggio 4: Reindirizzare questo elenco ad Adobe come attributo cliente

Una volta raggiunto il rapporto Data Warehouse, avrai un elenco di ECID che devono essere filtrati dai dati storici. Copiate e incollate questi ECID in un file. CSV vuoto con sole due colonne, ECID e Flag Bot:

![](assets/bot-csv-4.png)

Assicurati che la prima intestazione di colonna corrisponda al nome assegnato al nuovo ID dichiarato sopra. Usa questo file. CSV come file di importazione attributo del cliente, quindi sottoscrivi le suite di rapporti all'attributo del cliente come descritto in questo [post di blog](https://theblog.adobe.com/link-digital-behavior-customers).

## Passaggio 5: Crea un segmento che sfrutta il nuovo attributo cliente

Una volta che il set di dati è stato elaborato ed integrato in Analysis Workspace, crea un altro segmento che sfrutta la nuova dimensione attributo «Flag bot»:

![](assets/bot-filter-seg2.png)

## Passaggio 6: Usa questo segmento come filtro Suite di rapporti virtuale

Infine, devi creare una suite di rapporti virtuale che sfrutta questo segmento per filtrare i bot identificati:

![](assets/bot-vrs.png)

Questa suite di rapporti virtuale appena segmentata darà luogo a un set di dati significativamente più pulito con i bot identificati completamente rimossi.

## Passaggio 7: Ripetete i passaggi 2, 3 e 4 regolarmente

Impostare almeno un promemoria mensile per identificare e filtrare nuovi bot, possibilmente prima di un'analisi pianificata regolarmente.

