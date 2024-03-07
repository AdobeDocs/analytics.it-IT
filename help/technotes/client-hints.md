---
title: Hint client
description: Scopri in che modo gli hint client sostituiranno gradualmente l’agente utente come origine delle informazioni sul dispositivo.
exl-id: e0a74daa-12a2-4999-9920-2636b061dcc8
feature: Data Configuration and Collection
role: Admin
source-git-commit: 43c39b99cbae3e714b7f017dec14dd02fa350790
workflow-type: tm+mt
source-wordcount: '1184'
ht-degree: 60%

---

# Panoramica degli hint client e domande frequenti

Gli hint client sono singole informazioni relative al dispositivo di un utente. Sono forniti dai browser basati su Chromium, come ad esempio Google Chrome e Microsoft Edge. Per questi browser, gli hint client sostituiranno gradualmente l’agente utente come origine delle informazioni sul dispositivo. Adobe Analytics aggiornerà il processo di ricerca di informazioni sui dispositivi in modo da utilizzare, oltre all’agente utente, anche gli hint client per determinare le informazioni sul dispositivo.

## Hint client a bassa entropia e ad alta entropia

Google divide gli hint client dall’agente utente in due categorie: hint a bassa entropia e ad alta entropia.

* Gli **hint a bassa entropia** contengono informazioni più generiche sui dispositivi. Vengono forniti automaticamente dai browser basati su Chromium.

* Gli hint ad **alta entropia** contengono informazioni più dettagliate. Questi sono disponibili solo su richiesta. Le librerie AppMeasurement e Web SDK possono essere configurate per richiedere hint ad alta entropia. Per impostazione predefinita, entrambe le librerie **non** richiedono hint ad alta entropia.

A partire da ottobre 2022, le nuove versioni dei browser basati su Chromium hanno iniziato a &quot;congelare&quot; la versione del sistema operativo rappresentata nella stringa dell’agente utente. La versione del sistema operativo è un hint ad alta entropia; per essere certi di includere nei rapporti informazioni accurate sulla versione del sistema operativo è quindi necessario configurare la libreria di raccolta per raccogliere tali hint. Nel corso del tempo, le altre informazioni relative al dispositivo dell’agente utente verranno congelate, e sarà quindi necessario ricorrere agli hint client affinché sia possibile raccogliere nei rapporti informazioni accurate sui dispositivi.

Gli hint client verranno incorporati nel processo di ricerca del dispositivo di Analytics a partire dal 27 febbraio 2023 e fino al 2 marzo 2023. AppMeasurement e Web SDK supportano attualmente la raccolta di dati hint, ma non verranno utilizzati nella ricerca del dispositivo fino a metà febbraio. Come indicato di seguito, la versione del sistema operativo è stata congelata a partire da ottobre, ma a causa di un rollout graduale e del fatto che molti agenti utente forniscono già una versione del sistema operativo congelata (vedi altro [qui](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html)), prevediamo che questo interesserà &lt;3% dei visitatori di Chrome.

>[!NOTE]
>
> A partire da gennaio 2023, alcune versioni dei sistemi operativi Mac e Windows non sono rappresentate correttamente nell’agente utente, ma sono correttamente rappresentate negli hint client ad alta entropia. Consulta [Sistema operativo](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html) per ulteriori informazioni.

Adobe Audience Manager richiede la raccolta di hint ad alta entropia per preservare la piena funzionalità. Se sta usando [inoltro lato server a Adobe Audience Manager](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html?lang=it) allora potrebbe essere utile abilitare la raccolta di hint ad alta entropia.

## Domande frequenti

+++**Dove posso trovare ulteriori informazioni sugli hint client?**

Questo [articolo di blog di Google](https://web.dev/user-agent-client-hints/) è un ottimo punto di partenza e riferimento.

+++

+++**Come si abilita la raccolta di hint client?**

Gli hint a bassa entropia vengono forniti automaticamente dal browser e inclusi per derivare le informazioni sul dispositivo e sul browser. Le versioni più recenti di Web SDK (a partire dalla versione 2.12.0) e AppMeasurement (a partire dalla versione 2.23.0) possono essere configurate per raccogliere hint ad alta entropia tramite le rispettive estensioni di tag oppure direttamente tramite un’opzione di configurazione. Consultare le istruzioni per [SDK per web](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html#enabling-high-entropy-client-hints) e [AppMeasurement](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/collecthighentropyuseragenthints.html).

Per entrambe le librerie, la raccolta di hint ad alta entropia è **disattivata per impostazione predefinita**.

Per i dati inviati tramite API, ad esempio tramite [API di inserimento dati](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/data-insertion-api/index.md) o [API di inserimento dati in blocco](https://experienceleague.adobe.com/docs/analytics/import/bulk-data-insert.html), gli hint devono essere inclusi esplicitamente nel payload. Per informazioni dettagliate, consulta la relativa documentazione.

+++

+++**Posso scegliere quali hint ad alta entropia raccogliere?**

Al momento non è possibile. È possibile scegliere di raccogliere tutti gli hint ad alta entropia oppure nessuno.

FullVersionList non viene attualmente raccolto perché la versione principale del browser viene acquisita come hint a bassa entropia.

+++

+++**Quali sono i diversi valori degli hint client?**

La tabella seguente descrive gli hint client da ottobre 2022.

| Hint | Descrizione | Alta o bassa entropia | Esempio |
| --- | --- | --- | --- | 
| Sec-CH-UA | Browser e versione rilevante | Bassa | `"Google Chrome 84"` |
| Sec-CH-UA-Mobile | Dispositivo mobile (true o false) | Bassa | `true` |
| Sec-CH-UA-Platform | Sistema operativo/piattaforma | Bassa | `"Android"` |
| architettura | Architettura del sito | Alta | `"arm"` |
| amarezza | Abilità dell&#39;architettura | Alta | `"64"` |
| fullVersionList | Elenco dei marchi e versione | Alta | `"Not A;Brand";v="99", "Chromium";v="98", "Google Chrome";v="98"` |
| modello | Modello dispositivo | Alta | `"Pixel 3"` |
| platformVersion | Versione del sistema operativo/piattaforma | Alta | `"10"` |

* Gli hint a bassa entropia vengono raccolti tramite l’intestazione della richiesta.
* Gli hint ad alta entropia vengono raccolti tramite JavaScript e trasmessi attraverso i valori dei parametri delle stringhe di query. I parametri della stringa di query utilizzano `h.` come prefisso nella richiesta di immagine. FullVersionList non viene attualmente raccolto perché la versione principale del browser viene acquisita come hint a bassa entropia.

Gli hint ad alta entropia vengono raccolti tramite chiamata JavaScript e trasmessi tramite il parametro di query

+++

+++**Ci saranno modifiche al reporting sui dispositivi in Analytics?**

I campi relativi al dispositivo disponibili per il reporting non subiranno modifiche. I dati acquisiti per questi campi possono variare a seconda del campo e della modalità di configurazione della raccolta di hint client.

+++

+++**Quali campi di reporting di Analytics sono derivati dall’agente utente?**

Questi campi sono derivati direttamente dall’agente utente, ma l’agente utente può essere utilizzato per aiutare a derivare i valori per altri campi relativi al dispositivo, a seconda dei relativi dettagli.

* [Browser](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html)
* [Tipo di browser](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html)
* [Sistema operativo](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html)
* [Tipi di sistemi operativi](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-system-types.html)
* [Tipo di dispositivo mobile e dispositivo mobile](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html)

+++

+++**Quali parti dell’agente utente saranno “congelate” e quando?**

Consulta la [timeline pubblicata da Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html). Tale timeline potrebbe essere soggetta a modifiche.

+++

+++**In che modo Analytics dipende dall’agente utente?**

Le informazioni sul dispositivo nel reporting sono derivate dall’agente utente. Abbiamo aggiornato i nostri processi per utilizzare sia l’agente utente che gli hint client, se disponibili.

ID di fallback ([s_fid](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/analytics-ids.html?lang=it)) deriva dall&#39;agente utente e dall&#39;indirizzo IP. Questo ID viene utilizzato solo se non è possibile impostare un cookie in modo che non sia ampiamente utilizzato

+++

+++**Quali campi di reporting di Analytics sono derivati dai valori memorizzati negli hint ad alta entropia?**

Tali campi subiranno modifiche nel tempo, man mano che Google “congelerà” più parti dell&#39;agente utente. Il primo campo che verrà interessato direttamente è “Sistema operativo” che include la versione del sistema operativo in base alla timeline pubblicata di Google per il “congelamento” degli hint dell’agente utente e la versione del sistema operativo verrà congelata a partire dalla fine di ottobre 2022 con la versione 107 di Chromium. A quel punto la versione del sistema operativo nell&#39;agente utente in alcuni casi sarà imprecisa.

Consulta la [timeline pubblicata da Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html) per informazioni sulla tempistica del congelamento di altre parti dell’agente utente.

+++

+++**In che modo Adobe utilizzerà gli hint client per derivare informazioni sul dispositivo?**

Adobe utilizza una terza parte, Device Atlas, che utilizzerà sia gli hint client che l’agente utente per derivare informazioni sul dispositivo.

+++

+++**Quali browser sono interessati dagli hint client?**

Gli hint client sono applicabili solo ai browser basati su Chromium, come Google Chrome e Microsoft Edge. Non vi sono cambiamenti per quanto riguarda i dati provenienti da altri browser o app per dispositivi mobili.

+++

+++**Gli hint client sono supportati su connessioni non sicure?**

No. Gli hint client possono essere raccolti solo tramite una connessione HTTP protetta, ad esempio HTTPS.

+++

+++**Come si includono i dati degli hint client quando si utilizza l’invio tramite API?**

Consulta la documentazione per includerli tramite l’[API di inserimento dati in blocco](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/file-format/).

+++

+++**Gli hint client saranno disponibili nei dati inviati a Adobe Experience Platform e Customer Journey Analytics tramite il connettore di origine di Adobe?**

Adobe prevede di includere gli hint client nei dati tramite il connettore di origine di Adobe nella prima metà del 2023.

+++

+++**Come vengono rappresentati gli hint client in XDM?**

Consulta la [documentazione sugllo schema](https://github.com/adobe/xdm/blob/master/components/datatypes/browserdetails.schema.json#L121) in Adobe Experience Platform.

+++

+++**L’inoltro lato server a Adobe Audience Manager supporterà gli hint client?**

Sì. Gli hint client verranno inclusi nei dati inoltrati a Adobe Audience Manager. Tieni presente che Adobe Audience Manager richiede la raccolta di hint ad alta entropia per preservare la piena funzionalità. Se sta usando [inoltro lato server a Adobe Audience Manager](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html?lang=it) allora potrebbe essere utile abilitare la raccolta di hint ad alta entropia.

+++
