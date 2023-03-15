---
description: Il tracciamento determina il modo in cui i dati del motore di ricerca vengono tracciati dall’implementazione di Adobe Analytics. Questo passaggio è necessario per integrare correttamente i dati di Adobe Analytics con i dati del motore di ricerca.
title: Modalità manuale di tracciamento e modalità automatica
feature: Advertising Analytics
exl-id: 3e2ed26f-dfb2-43ea-8eb6-e332cd10fb29
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: tm+mt
source-wordcount: '606'
ht-degree: 0%

---

# Tracciamento: modalità manuale e modalità automatica

Il tracciamento determina il modo in cui i dati del motore di ricerca vengono tracciati dall’implementazione di Adobe Analytics. Questo passaggio è necessario per integrare correttamente i dati di Adobe Analytics con i dati del motore di ricerca.

Ecco una panoramica video su come implementare il modello di tracciamento di Advertising Analytics:

>[!VIDEO](https://video.tv.adobe.com/v/23120/?quality=12)

Sono supportate due modalità di tracciamento: modalità automatica e modalità manuale.

## Tracciamento in modalità automatica {#concept_C4C6107838C947CFBB7F4E0CB94264F0}

In modalità automatica, puoi lasciare che sia il motore di Advertising Cloud a decidere come gestire i dati del motore di ricerca. Questo è l’approccio più semplice, ma potrebbe non risultare nel miglior set di dati integrato.

Di conseguenza, è necessario selezionare una casella di controllo di conferma quando si seleziona Modalità automatica, prima di poter salvare l&#39;impostazione dell&#39;account.

Per configurare un account del motore di ricerca in &quot;Modalità automatica&quot;, è necessario effettuare le seguenti operazioni:

* Il `s_kwcid` Il parametro e il valore verranno aggiunti ai modelli di tracciamento dell’account o agli URL della pagina di destinazione nell’account aggiunto. Verrà inserito alla fine dell’URL. Potrebbe essere necessaria un&#39;azione aggiuntiva da parte tua se il server web richiede una determinata coppia chiave=valore alla fine dell&#39;URL OPPURE un aggiornamento per supportare qualsiasi nuova coppia chiave=valore nell&#39;URL. **È tua responsabilità verificare che i parametri URL aggiunti persistano correttamente nella pagina di destinazione finale.**
* Inoltre, è possibile inserire parole chiave nell’URL di destinazione come parte del `s_kwcid` valore. Se contengono caratteri o simboli speciali, verificare che il server Web in uso supporti tali caratteri. Esempio: un carattere speciale comune è &quot;+&quot;, che viene utilizzato nelle parole chiave &quot;Broad Match Modified&quot;.

>[!IMPORTANT]
>
>Ulteriori informazioni sull&#39;aggiunta o meno del `s_kwcid` parametro per il [Informativa sulla sicurezza dei contenuti](https://experienceleague.adobe.com/docs/id-service/using/reference/csp.html).

## Tracciamento modalità manuale {#concept_87B28BA9E7F84BA5972F69E6F3482A33}

In modalità manuale, devi specificare in che modo i dati del motore di ricerca devono essere trattati dal processo di integrazione dei dati di Advertising Analytics.

### Aggiungi tracciamento manuale all’account Google {#section_41C1EB1AEB034544A5BC291F53C05C67}

La stringa da aggiungere al tuo account Google è mostrata di seguito. Devi aggiungere la stringa a tutti i modelli di tracciamento utilizzati nel tuo account.

>[!IMPORTANT]
>
>Il `<Advertising Analytics ID>` valore (in **grassetto** di seguito) è generico e **deve essere sostituito con la stringa del tuo ID account specifico**. Puoi ottenere la stringa dell’ID account specifico dalla schermata di configurazione dell’account nella sezione &quot;Tracking&quot; (Tracciamento).

**Stringa di tracciamento per le campagne:**

```
s_kwcid=AL! 
<b><Advertising Analytics ID></b>!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

![](assets/Google.png)

Esempi di codici di tracciamento in vari formati di modelli di tracciamento:

**`{lpurl}`**

```
{lpurl}?s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!network}!{product_partition_id}!{keyword}
```

**`{lpurl}`con parametro URL aggiuntivo**

```
{lpurl}?campaign=PPC&s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!network}!{product_partition_id}!{keyword}
```

**Terze parti (doppio clic)`{unescapedlpurl}`**

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={unescapedlpurl}?s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

**Terze parti (doppio clic)`{lpurl}`**

Se l’URL attraversa un reindirizzamento e non utilizza un valore &quot;unescape edlpurl&quot;, devi codificare la stringa un numero di volte sufficiente affinché persista attraverso il reindirizzamento all’URL della pagina di destinazione finale.

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={lpurl}?s_kwcid%3DAL!9999!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

### Aggiungi tracciamento manuale all&#39;account Bing {#section_094F8ACA493C4D65B1F54A695558EBF2}

La stringa da aggiungere al tuo account Bing è mostrata di seguito. Devi aggiungere la stringa a tutti i suffissi URL finali utilizzati in tutto l’account.

>[!IMPORTANT]
>
>Il `<Advertising Analytics ID>` valore (in **grassetto** di seguito) è generico e **deve essere sostituito con la stringa del tuo ID account specifico**. Puoi ottenere la stringa dell’ID account specifico dalla schermata di configurazione dell’account nella sezione &quot;Tracking&quot; (Tracciamento).

**Stringa di tracciamento per le campagne:**

```
s_kwcid=AL!<Advertising Analytics ID>!10!{AdId}!{OrderItemId} 
```

![](assets/Bing.png)

Esempi di codici di tracciamento in vari formati di suffisso URL finale:

**{lpurl}**

```
{lpurl}?s_kwcid=AL!9999!10!{AdId}!{OrderItemId}
```

**`{lpurl}`con parametro URL aggiuntivo**

```
{lpurl}?campaign=PPC&
s_kwcid=AL!9999!10!{AdId}!{OrderItemId}
```

**Terze parti (doppio clic)`{unescapedlpurl}`**

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={unescapedlpurl}?s_kwcid=AL!9999!10!{AdId}!{OrderItemId}
```

**Terze parti (doppio clic)`{lpurl}`**

Se l’URL attraversa un reindirizzamento e non utilizza un valore &quot;unescape edlpurl&quot;, devi codificare la stringa un numero di volte sufficiente affinché persista attraverso il reindirizzamento all’URL della pagina di destinazione finale.

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={lpurl}?s_kwcid%3DAL!9999!10!{AdId}!{OrderItemId}
```
