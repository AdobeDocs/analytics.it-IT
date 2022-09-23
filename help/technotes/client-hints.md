---
title: Suggerimenti client
description: Scopri in che modo i suggerimenti client sostituiranno gradualmente User-Agent come origine delle informazioni sul dispositivo.
source-git-commit: 72ef2d5e34220f1703714fac40a9dae4e76c1ab1
workflow-type: tm+mt
source-wordcount: '833'
ht-degree: 5%

---


# Panoramica dei suggerimenti client e domande frequenti

I suggerimenti client sono singole informazioni sul dispositivo di un utente. Sono forniti da browser Chromium come Google Chrome e Microsoft Edge. Per questi browser, i suggerimenti client sostituiranno gradualmente User-Agent come origine delle informazioni sul dispositivo. Adobe Analytics aggiornerà il processo di ricerca dei dispositivi in modo che utilizzi suggerimenti client oltre a User-Agent per determinare le informazioni sul dispositivo.

Google divide i suggerimenti client User-Agent in due categorie: note entropiche basse e ad alta entropia.

* **Suggerimenti per bassa entropia** contiene informazioni più generiche sui dispositivi. Questi suggerimenti vengono forniti automaticamente dai browser Chromium.

* **Alta entropia** i suggerimenti contengono informazioni più dettagliate. Questi suggerimenti sono disponibili solo su richiesta. SDK per AppMeasurement e web [può essere configurato](/help/implement/vars/config-vars/collecthighentropyuseragenthints.md) per richiedere suggerimenti ad alta entropia. Per impostazione predefinita, entrambe le librerie lo fanno **not** richiedi suggerimenti entropici elevati.

>[!NOTE]
>
>A partire da ottobre 2022, le nuove versioni dei browser Chromium inizieranno a &#39;congelare&#39; la versione del sistema operativo rappresentata nella stringa User-Agent. Quando gli utenti aggiornano i propri dispositivi, il sistema operativo nell&#39;agente utente non verrà modificato. Così, nel tempo le informazioni sulla versione operativa come rappresentate nell&#39;User-Agent diventeranno meno precise. La versione del sistema operativo è un hint ad alta entropia, quindi per mantenere la precisione della versione del sistema operativo nel reporting è necessario configurare la libreria di raccolta per raccogliere questi suggerimenti ad alta entropia. Nel corso del tempo, le altre informazioni relative al dispositivo dell&#39;utente-agente verranno congelate, richiedendo suggerimenti client per mantenere l&#39;accuratezza del reporting del dispositivo.

## Domande frequenti

+++**Dove posso saperne di più sui suggerimenti dei clienti?**

Questo [Post di blog Google](https://web.dev/user-agent-client-hints/) è un buon punto di riferimento e di partenza.

+++

+++**Come si abilita la raccolta di suggerimenti client?**

I suggerimenti entropici bassi vengono forniti automaticamente dal browser e inclusi nel processo di Adobe per la derivazione delle informazioni sul dispositivo e sul browser. Puoi configurare le versioni più recenti di AppMeasurement (a partire dalla versione 2.23.0) e SDK web (a partire dalla versione 2.12.0) per raccogliere suggerimenti ad alta entropia. Per entrambe le librerie, la raccolta di suggerimenti ad alta entropia è **disattivato per impostazione predefinita**.

+++

+++**Come posso acquisire i suggerimenti ad alta entropia?**

I suggerimenti ad alta entropia possono essere configurati con le librerie SDK web e AppMeasurement tramite le rispettive estensioni Tags o direttamente con il flag collectHighEntropyUserAgentHint.

+++

+++**Posso scegliere quali suggerimenti ad alta entropia colleziono?**

Non in questo momento. È possibile scegliere di raccogliere tutti i suggerimenti entropici elevati o nessuno.

+++

+++**Ci saranno modifiche al reporting dei dispositivi in Analytics?**

I campi del dispositivo disponibili per la generazione dei rapporti non verranno modificati. I dati acquisiti per questi campi possono variare a seconda del campo e della modalità di configurazione della raccolta per i suggerimenti client.

+++

+++**Quali campi di reporting di Analytics sono derivati dall’utente-agente?**

* [Browser](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html?lang=en)
* [Tipo di browser](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html?lang=en)
* [Sistema operativo](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=en)
* [Tipi di sistemi operativi](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-system-types.html?lang=en)
* [Tipo di dispositivo mobile e dispositivo mobile](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html?lang=en)
* [Feed dati](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=it)

+++

+++**Quali campi di reporting di Analytics sono derivati dai valori memorizzati nei suggerimenti ad alta entropia?**

A partire da settembre 2022, la cronologia pubblicata da Google per il &quot;congelamento&quot; dei suggerimenti utente-agente indica che la versione del sistema operativo cesserà di essere aggiornata a partire da ottobre 2022. Quando gli utenti aggiornano il proprio sistema operativo, la versione del sistema operativo nell&#39;agente utente non viene aggiornata. Senza indicazioni entropiche elevate, la precisione della versione del sistema operativo, inclusa nella dimensione &quot;Sistema operativo&quot; di Analytics, si degraderà gradualmente.

Fai riferimento a [timeline pubblicata da Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html) per vedere la tempistica del congelamento di altre parti dell&#39;Utente-Agente.

+++

+++**In che modo Adobe utilizzerà i suggerimenti client per derivare le informazioni sul dispositivo?**

Ad Adobe viene utilizzato un componente di terze parti, Device Atlas, che utilizzerà sia i suggerimenti client che l&#39;agente utente per derivare le informazioni sul dispositivo.

+++

+++**Quali browser sono interessati dai suggerimenti dei clienti?**

I suggerimenti client si applicano solo ai browser Chromium come Google Chrome e Microsoft Edge. Non vi sono modifiche ai dati provenienti da altri browser o app mobili.

+++

+++**I suggerimenti client saranno disponibili nei dati inviati ad AEP e CJA tramite il connettore sorgente Adobe?**

Prevediamo di includere i suggerimenti dei clienti nei dati tramite Adobe Source Connector nella prima metà del 2023.

+++

+++**Come vengono rappresentati i suggerimenti client in XDM?**

Consulta la sezione [documentazione dello schema](https://github.com/adobe/xdm/blob/master/components/datatypes/browserdetails.schema.json#L121) in Adobe Experience Platform.

+++

+++**Quali sono i vari campi di suggerimenti? Quali influiscono sul reporting dei dispositivi?**

La tabella seguente descrive i suggerimenti dei clienti a partire da settembre 2022.

| Suggerimento | Descrizione | Entropia alta o bassa | Esempio |
| --- | --- | --- | --- | 
| Sec-CH-UA | Browser e versione significativa | Bassa | &quot;Google Chrome 84&quot; |
| Sec-CH-UA-Mobile | Dispositivo mobile (true o false) | Bassa | TRUE |
| Piattaforma Sec-CH-UA | Sistema operativo/piattaforma | Bassa | &quot;Android&quot; |
| Sec-CH-UA-Arch | Architettura del sito | Alta | &quot;braccio&quot; |
| Sec-CH-UA-Bitness | Punte dell&#39;architettura | Alta | &quot;64&quot; |
| Sec-CH-UA-Versione completa | Versione completa del browser | Alta | &quot;84.0.4143.2&quot; |
| Sec-CH-UA-Elenco completo delle versioni | Elenco dei marchi con la loro versione | Alta | &quot;Not A;Brand&quot;;v=&quot;99&quot;, &quot;Chromium&quot;;v=&quot;98&quot;, &quot;Google Chrome&quot;;v=&quot;98&quot; |
| Modello Sec-CH-UA | Modello del dispositivo | Alta | &quot;Pixel 3&quot; |
| Sec-CH-UA-Platform-Version | Versione sistema operativo/piattaforma | Alta | &quot;10&quot; |

+++



+++**Quali parti dell&#39;Utente-Agente vengono &quot;congelate&quot; e quando?**

Consulta la sezione [timeline pubblicata da Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html). Questo può essere soggetto a cambiamenti.

+++
