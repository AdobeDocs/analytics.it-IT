---
description: Il tracciamento determina il modo in cui i dati dei motori di ricerca vengono tracciati dall’implementazione Adobe Analytics. Questo è un passaggio necessario per integrare correttamente i dati di Adobe Analytics con i dati del motore di ricerca.
title: Modalità manuale di tracciamento e modalità automatica
exl-id: 3e2ed26f-dfb2-43ea-8eb6-e332cd10fb29
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 1%

---

# Tracciamento: modalità manuale e modalità automatica

Il tracciamento determina il modo in cui i dati dei motori di ricerca vengono tracciati dall’implementazione Adobe Analytics. Questo è un passaggio necessario per integrare correttamente i dati di Adobe Analytics con i dati del motore di ricerca.

Sono supportate due modalità di tracciamento: Modalità automatica e modalità manuale.

## Tracciamento automatico della modalità {#concept_C4C6107838C947CFBB7F4E0CB94264F0}

In modalità automatica, puoi consentire al motore di ricerca Advertising Cloud di decidere come gestire i dati del motore di ricerca. Questo è l’approccio più semplice, ma potrebbe non tradursi in un set di dati integrato migliore.

Di conseguenza, è necessario selezionare una casella di controllo di conferma quando si seleziona Modalità automatica, prima di salvare l&#39;impostazione dell&#39;account.

Tieni presente che per configurare un account del motore di ricerca in &quot;Modalità automatica&quot;, sei responsabile di eseguire le azioni seguenti:

* Il parametro e il valore `s_kwcid` verranno aggiunti ai modelli di tracciamento dell’account o agli URL della pagina di destinazione nell’account che si sta aggiungendo. Questo verrà inserito alla fine dell’URL. Può essere necessaria un&#39;azione aggiuntiva da parte dell&#39;utente se il server web richiede una determinata coppia chiave=valore alla fine dell&#39;URL OPPURE un aggiornamento per supportare una nuova coppia chiave=valore nell&#39;URL. **È tua responsabilità assicurarsi che i parametri dell’URL aggiunto persistano correttamente nella pagina di destinazione finale.**
* Inoltre, le parole chiave possono essere inserite nell’URL di destinazione come parte del valore `s_kwcid` . Se contengono caratteri o simboli speciali, confermare che il server web possa supportare questi caratteri. Esempio: Un carattere speciale comune è &quot;+&quot;, utilizzato nelle parole chiave &quot;Broad Match Modified&quot;.

>[!IMPORTANT]
>
>Ulteriori informazioni sull&#39;aggiunta del parametro `s_kwcid` al [Criterio di sicurezza dei contenuti](https://experienceleague.adobe.com/docs/id-service/using/reference/csp.html).

## Tracciamento manuale della modalità {#concept_87B28BA9E7F84BA5972F69E6F3482A33}

In modalità Manuale, è necessario specificare come i dati del motore di ricerca devono essere trattati dal processo di integrazione dei dati di Advertising Analytics.

### Aggiungi tracciamento manuale all’account Google {#section_41C1EB1AEB034544A5BC291F53C05C67}

La stringa che deve essere aggiunta al tuo account Google è mostrata di seguito. Devi aggiungere la stringa a tutti i modelli di tracciamento utilizzati nell’account.

>[!IMPORTANT]
>
>Il valore `<Advertising Analytics ID>` (in **bold** sotto) è generico e **deve essere sostituito con la stringa ID account specifica**. Puoi ottenere la stringa ID account specifica dalla schermata di configurazione dell’account nella sezione &quot;Tracking&quot; (Tracciamento).

**Stringa di tracciamento per campagne:**

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

**di terze parti (DoubleClick)`{unescapedlpurl}`**

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={unescapedlpurl}?s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

**di terze parti (DoubleClick)`{lpurl}`**

Se l’URL passa attraverso un reindirizzamento e non utilizza un valore &quot;unescapelpurl&quot;, devi codificare la stringa abbastanza volte in modo che continui a persistere attraverso il reindirizzamento all’URL della pagina di destinazione finale.

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={lpurl}?s_kwcid%3DAL!9999!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

### Aggiungi tracciamento manuale all&#39;account Bing {#section_094F8ACA493C4D65B1F54A695558EBF2}

La stringa che deve essere aggiunta al tuo account Bing è mostrata di seguito. Devi aggiungere la stringa a tutti i suffissi URL finali utilizzati in tutto l’account.

>[!IMPORTANT]
>
>Il valore `<Advertising Analytics ID>` (in **bold** sotto) è generico e **deve essere sostituito con la stringa ID account specifica**. Puoi ottenere la stringa ID account specifica dalla schermata di configurazione dell’account nella sezione &quot;Tracking&quot; (Tracciamento).

**Stringa di tracciamento per campagne:**

```
s_kwcid=AL!<Advertising Analytics ID>!10!{AdId}!{OrderItemId} 
```

![](assets/Bing.png)

Esempi di codici di tracciamento in vari formati di suffisso URL finali:

**{lpurl}**

```
{lpurl}?s_kwcid=AL!9999!10!{AdId}!{OrderItemId}
```

**`{lpurl}`con parametro URL aggiuntivo**

```
{lpurl}?campaign=PPC&
s_kwcid=AL!9999!10!{AdId}!{OrderItemId}
```

**di terze parti (DoubleClick)`{unescapedlpurl}`**

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={unescapedlpurl}?s_kwcid=AL!9999!10!{AdId}!{OrderItemId}
```

**di terze parti (DoubleClick)`{lpurl}`**

Se l’URL passa attraverso un reindirizzamento e non utilizza un valore &quot;unescapelpurl&quot;, devi codificare la stringa abbastanza volte in modo che continui a persistere attraverso il reindirizzamento all’URL della pagina di destinazione finale.

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={lpurl}?s_kwcid%3DAL!9999!10!{AdId}!{OrderItemId}
```
