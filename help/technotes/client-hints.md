---
title: Hint client
description: Scopri in che modo gli hint client sostituiranno gradualmente l’agente utente come origine delle informazioni sul dispositivo.
source-git-commit: f2f1e64a62796b58c24e6ff652db93b21f750669
workflow-type: ht
source-wordcount: '855'
ht-degree: 100%

---


# Panoramica degli hint client e domande frequenti

Gli hint client sono singole informazioni relative al dispositivo di un utente. Sono forniti dai browser basati su Chromium, come ad esempio Google Chrome e Microsoft Edge. Per questi browser, gli hint client sostituiranno gradualmente l’agente utente come origine delle informazioni sul dispositivo. Adobe Analytics aggiornerà il processo di ricerca di informazioni sui dispositivi in modo da utilizzare, oltre all’agente utente, anche gli hint client per determinare le informazioni sul dispositivo.

Google divide gli hint client dall’agente utente in due categorie: hint a bassa entropia e ad alta entropia.

* Gli **hint a bassa entropia** contengono informazioni più generiche sui dispositivi. Vengono forniti automaticamente dai browser basati su Chromium.

* Gli hint ad **alta entropia** contengono informazioni più dettagliate. Questi sono disponibili solo su richiesta. Le librerie AppMeasurement e Web SDK [possono essere configurate](/help/implement/vars/config-vars/collecthighentropyuseragenthints.md) per richiedere hint ad alta entropia. Per impostazione predefinita, entrambe le librerie **non** richiedono hint ad alta entropia.

>[!NOTE]
>
>A partire dal mese di ottobre 2022, le nuove versioni dei browser basati su Chromium inizieranno a “congelare“ la versione del sistema operativo rappresentata nella stringa dell’agente utente. Quando un utente aggiornerà il suo dispositivo, il sistema operativo nella stringa dell’agente utente non verrà modificato. Così, nel corso del tempo le informazioni sulla versione del sistema operativo provenienti dalla stringa dell’agente utente diventeranno sempre meno precise. La versione del sistema operativo è un hint ad alta entropia; per essere certi di includere nei rapporti informazioni accurate sulla versione del sistema operativo è quindi necessario configurare la libreria di raccolta per raccogliere tali hint. Nel corso del tempo, le altre informazioni relative al dispositivo dell’agente utente verranno congelate, e sarà quindi necessario ricorrere agli hint client affinché sia possibile raccogliere nei rapporti informazioni accurate sui dispositivi.

## Domande frequenti

+++**Dove posso trovare ulteriori informazioni sugli hint client?**

Questo [articolo di blog di Google](https://web.dev/user-agent-client-hints/) è un ottimo punto di partenza e riferimento.

+++

+++**Come si abilita la raccolta di hint client?**

Gli hint a bassa entropia vengono forniti automaticamente dal browser e inclusi nel processo di Adobe per derivare le informazioni sul dispositivo e sul browser. Puoi configurare le versioni più recenti di AppMeasurement (a partire dalla versione 2.23.0) e Web SDK (a partire dalla versione 2.12.0) per raccogliere hint ad alta entropia. Per entrambe le librerie, la raccolta di hint ad alta entropia è **disattivata per impostazione predefinita**.

+++

+++**Come posso acquisire hint ad alta entropia?**

Gli hint ad alta entropia possono essere configurati con le librerie Web SDK e AppMeasurement tramite le rispettive estensioni tag oppure direttamente con il flag collectHighEntropyUserAgentHints.

+++

+++**Posso scegliere quali hint ad alta entropia raccogliere?**

Al momento non è possibile. È possibile scegliere di raccogliere tutti gli hint ad alta entropia oppure nessuno.

+++

+++**Ci saranno modifiche al reporting sui dispositivi in Analytics?**

I campi relativi al dispositivo disponibili per il reporting non subiranno modifiche. I dati acquisiti per questi campi possono variare a seconda del campo e della modalità di configurazione della raccolta di hint client.

+++

+++**Quali campi di reporting di Analytics sono derivati dall’agente utente?**

* [Browser](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html?lang=it)
* [Tipo di browser](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html?lang=it)
* [Sistema operativo](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=it)
* [Tipi di sistemi operativi](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-system-types.html?lang=it)
* [Tipo di dispositivo mobile e dispositivo mobile](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html?lang=it)
* [Feed dati](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=it)

+++

+++**Quali campi di reporting di Analytics sono derivati dai valori memorizzati negli hint ad alta entropia?**

In base alle informazioni disponibili a settembre 2022, la timeline pubblicata da Google relativa al “congelamento“ degli hint dall’agente utente indica che la versione del sistema operativo cesserà di essere aggiornata a partire dal mese di ottobre 2022. Quando un utente aggiornerà il suo dispositivo, la versione del sistema operativo nella stringa dell’agente utente non verrà modificata. Senza gli hint ad alta entropia, le informazioni sulla versione del sistema operativo, incluse nella dimensione “Sistema operativo“ di Analytics, diventeranno gradualmente meno accurate.

Consulta la [timeline pubblicata da Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html) per informazioni sulla tempistica del congelamento di altre parti dell’agente utente.

+++

+++**In che modo Adobe utilizzerà gli hint client per derivare informazioni sul dispositivo?**

Adobe utilizza un componente di terze parti, Device Atlas, che utilizzerà sia gli hint client che l’agente utente per derivare informazioni sul dispositivo.

+++

+++**Quali browser sono interessati dagli hint client?**

Gli hint client sono applicabili solo ai browser basati su Chromium, come Google Chrome e Microsoft Edge. Non vi sono cambiamenti per quanto riguarda i dati provenienti da altri browser o app per dispositivi mobili.

+++

+++**Gli hint client sono supportati su connessioni non sicure?

No. Gli hint client possono essere raccolti solo tramite una connessione HTTP protetta, ad esempio HTTPS.

+++

+++**Gli hint client saranno disponibili nei dati inviati ad AEP e CJA tramite il connettore di origine di Adobe?**

Adobe prevede di includere gli hint client nei dati tramite il connettore di origine di Adobe nella prima metà del 2023.

+++

+++**Come vengono rappresentati gli hint client in XDM?**

Consulta la [documentazione sugllo schema](https://github.com/adobe/xdm/blob/master/components/datatypes/browserdetails.schema.json#L121) in Adobe Experience Platform.

+++

+++**Quali sono i vari campi degli hint? Quali influiscono sui dati di reporting relativi ai dispositivi?**

La tabella seguente descrive gli hint client disponibili da settembre 2022.

| Hint | Descrizione | Alta o bassa entropia | Esempio |
| --- | --- | --- | --- | 
| Sec-CH-UA | Browser e versione rilevante | Bassa | &quot;Google Chrome 84&quot; |
| Sec-CH-UA-Mobile | Dispositivo mobile (true o false) | Bassa | TRUE |
| Sec-CH-UA-Platform | Sistema operativo/piattaforma | Bassa | &quot;Android&quot; |
| Sec-CH-UA-Arch | Architettura del sito | Alta | &quot;arm&quot; |
| Sec-CH-UA-Bitness | Numero di bit dell’architettura | Alta | &quot;64&quot; |
| Sec-CH-UA-Full-Version | Versione completa del browser | Alta | &quot;84.0.4143.2&quot; |
| Sec-CH-UA-Full-Version-List | Elenco dei marchi e versione | Alta | &quot;Not A;Brand&quot;;v=&quot;99&quot;, &quot;Chromium&quot;;v=&quot;98&quot;, &quot;Google Chrome&quot;;v=&quot;98&quot; |
| Sec-CH-UA-Model | Modello dispositivo | Alta | &quot;Pixel 3&quot; |
| Sec-CH-UA-Platform-Version | Versione del sistema operativo/piattaforma | Alta | &quot;10&quot; |

+++



+++**Quali parti dell’agente utente saranno “congelate“ e quando?**

Consulta la [timeline pubblicata da Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html). Tale timeline potrebbe essere soggetta a modifiche.

+++
