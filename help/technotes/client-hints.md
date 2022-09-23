---
title: Suggerimenti client
description: Scopri in che modo i suggerimenti client sostituiranno gradualmente l’Agente utente come origine delle informazioni sul dispositivo.
source-git-commit: 788ab49fec9117e0ef2a736f609a627b913b9f8c
workflow-type: tm+mt
source-wordcount: '904'
ht-degree: 4%

---


# Panoramica dei suggerimenti client e domande frequenti

I suggerimenti client sono singole informazioni sul dispositivo di un utente. Sono forniti da browser Chromium come Google Chrome e Microsoft Edge. Per questi browser, i suggerimenti client sostituiranno gradualmente l&#39;Agente utente come origine delle informazioni sul dispositivo. Adobe Analytics aggiornerà il processo di ricerca dei dispositivi in modo che utilizzi suggerimenti client oltre a User Agent per determinare le informazioni sul dispositivo.

Google divide i suggerimenti client User Agent in due categorie: note entropiche basse e ad alta entropia.

* I suggerimenti entropici bassi contengono informazioni più generiche sui dispositivi. Questi suggerimenti vengono forniti automaticamente dai browser Chromium.

* I suggerimenti ad alta entropia hanno informazioni più dettagliate. Questi suggerimenti sono disponibili solo su richiesta. È possibile configurare sia AppMeasurement che l&#39;SDK web per richiedere hint ad alta entropia. Per impostazione predefinita, entrambe le librerie lo fanno **not** richiedi suggerimenti entropici elevati.

>[!NOTE]
>
>A partire da ottobre 2022, le nuove versioni dei browser Chromium inizieranno a &#39;congelare&#39; la versione del sistema operativo rappresentata nella stringa User Agent. Ciò significa che, nel tempo, le informazioni sulla versione operativa rappresentate nell&#39;Agente utente diventeranno meno precise. La versione del sistema operativo è un hint ad alta entropia, quindi per mantenere la precisione della versione del sistema operativo nel reporting è necessario configurare la libreria di raccolta per raccogliere questi suggerimenti ad alta entropia. Nel corso del tempo, le altre informazioni relative al dispositivo dell&#39;agente utente verranno congelate, richiedendo suggerimenti client per mantenere l&#39;accuratezza del reporting del dispositivo.

## Domande frequenti

+++**Come si abilita la raccolta di suggerimenti client?**

I suggerimenti entropici bassi vengono forniti automaticamente dal browser e inclusi nel processo di Adobe per le informazioni sul dispositivo. È possibile configurare le versioni più recenti di AppMeasurement (avvio di TBD) e SDK web (avvio di TBD) per raccogliere suggerimenti ad alta entropia. Per entrambe le librerie, la raccolta di suggerimenti ad alta entropia è **disattivato per impostazione predefinita**. Vedi qui per i dettagli su come implementare questo.

+++

+++**Posso scegliere quali suggerimenti ad alta entropia colleziono?**

Non in questo momento. È possibile scegliere di raccogliere tutti i suggerimenti entropici elevati o nessuno.

+++

+++**Ci saranno modifiche al reporting dei dispositivi in Analytics?**

I campi del dispositivo disponibili per la generazione dei rapporti non verranno modificati. I dati acquisiti per tali campi possono variare a seconda del campo e della modalità di configurazione della raccolta per i suggerimenti client.

+++

+++**Quali campi di reporting di Analytics sono derivati dall’agente utente?**

* [Browser](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html?lang=en)
* [Tipo di browser](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html?lang=en)
* [Sistema operativo](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=en)
* [Tipi di sistemi operativi](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-system-types.html?lang=en)
* [Tipo di dispositivo mobile e dispositivo mobile](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html?lang=en)?
* Feed dati (gli utenti devono effettuare l’aggiornamento per acquisire questi campi. Inoltre, esiste una dipendenza in cui non è possibile esporre l’ID mobile insieme alle informazioni sul dispositivo.)
* Connettore origine Analytics (non pronto)

+++

+++**Quali campi di reporting di Analytics sono derivati dai valori memorizzati nei suggerimenti ad alta entropia?**

A partire da settembre 2022, la data di pubblicazione di Google per il blocco dei suggerimenti utente-agente indica che la versione del sistema operativo cesserà di essere aggiornata a partire da ottobre 2022. Senza indicazioni entropiche elevate, la precisione della versione del sistema operativo, inclusa nella dimensione &quot;Sistema operativo&quot; di Analytics, si degraderà gradualmente.

Consulta la sezione [timeline pubblicata da Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html) per vedere i tempi di congelamento dell&#39;agente utente.

+++

+++**Quali browser sono interessati dai suggerimenti dei clienti?**

I suggerimenti client si applicano solo ai browser Chromium come Google Chrome e Microsoft Edge. Non vi sono modifiche ai dati provenienti da altri browser o app mobili.

+++

+++**In che modo Adobe utilizzerà i suggerimenti client per derivare le informazioni sul dispositivo?**

Ad Adobe viene utilizzato un Atlante dei dispositivi di terze parti che utilizzerà sia i suggerimenti client che l&#39;agente utente per derivare le informazioni sul dispositivo.

+++

+++**I suggerimenti client saranno disponibili nei feed dati?**

Sì. Consulta la documentazione (da seguire).

+++

+++**I suggerimenti client saranno disponibili nei dati inviati ad AEP e CJA tramite il connettore sorgente Adobe?**

Prevediamo di includere i suggerimenti dei clienti nei dati tramite Adobe Source Connector nella prima metà del 2023.

+++

+++**Come vengono rappresentati i suggerimenti client in XDM?**

Consulta la sezione [documentazione dello schema](https://github.com/adobe/xdm/blob/master/components/datatypes/browserdetails.schema.json#L121) in Adobe Experience Platform.

+++

+++**Dove posso saperne di più sui suggerimenti dei clienti?**

Questo [Post di blog Google](https://web.dev/user-agent-client-hints/) è un buon punto di riferimento e di partenza.

+++

+++**Quali sono i vari campi di suggerimenti? Quali influiscono sul reporting dei dispositivi?**

La tabella seguente descrive i suggerimenti dei clienti a partire da settembre 2022.

| Suggerimento (intestazione) | Suggerimento | Entropia alta o bassa | Esempio | Campi di reporting di Analytics |
| --- | --- | --- | --- | --- |
| Sec-CH-UA | Browser e versione significativa | Bassa | Google Chrome 84 | [Browser](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html?lang=en) e [Tipo di browser](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html?lang=en) |
| Sec-CH-UA-Mobile | Dispositivo mobile (true o false) | Bassa | TRUE | [Tipo di dispositivo mobile e dispositivo mobile](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html?lang=en)? |
| Piattaforma Sec-CH-UA | Sistema operativo/piattaforma | Bassa | Android | [Sistema operativo](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=en) |
| Sec-CH-UA-Arch | Architettura del sito | Alta | &quot;braccio&quot; | Nessuno? |
| Sec-CH-UA-Bitness | Sec-CH-UA-Bitness | Alta |  | Nessuno? |
| Sec-CH-UA-Versione completa | Versione completa del browser | Alta | &quot;84.0.4143.2&quot; | Nessuno? |
| Sec-CH-UA-Elenco completo delle versioni | ?? | Alta | ?? | Nessuno? |
| Modello Sec-CH-UA | Modello del dispositivo | Alta | &quot;Pixel 3&quot; | Nessuno? |
| Sec-CH-UA-Platform-Version | Versione sistema operativo/piattaforma | Alta | &quot;10&quot; | [Sistema operativo](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=en) |

+++

+++**Come posso acquisire i suggerimenti ad alta entropia?**

È possibile configurare suggerimenti entropici elevati

* Per AppMeasurement direttamente [collegamento alla voce flag nella guida all’implementazione]
* Nell’estensione Tags Analytics
* Nell’SDK per web.

+++

+++**Quali dati vengono rimossi dall’agente utente e quando?**

Consulta la sezione [timeline pubblicata da Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html). Questo può essere soggetto a cambiamenti.

+++