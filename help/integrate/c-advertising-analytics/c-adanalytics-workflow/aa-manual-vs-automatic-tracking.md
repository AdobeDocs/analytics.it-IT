---
description: Il tracciamento determina il modo in cui i dati del motore di ricerca vengono tracciati dall’implementazione Adobe Analytics . Si tratta di un passaggio necessario per migliorare correttamente i dati Adobe Analytics  con i dati del motore di ricerca.
title: Modalità manuale di tracciamento e modalità automatica
translation-type: tm+mt
source-git-commit: 69db61bdfd9375df4d090add7d8ed08135d1f087
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 1%

---


# Tracciamento: modalità manuale e modalità automatica

Il tracciamento determina il modo in cui i dati del motore di ricerca vengono tracciati dall’implementazione Adobe Analytics . Si tratta di un passaggio necessario per migliorare correttamente i dati Adobe Analytics  con i dati del motore di ricerca.

Sono supportate due modalità di tracciamento: Modalità automatica e Modalità manuale.

## Tracciamento modalità automatica {#concept_C4C6107838C947CFBB7F4E0CB94264F0}

In modalità Auto, è possibile consentire al  Advertising Cloud Engine di decidere come gestire i dati del motore di ricerca. Questo è l&#39;approccio più semplice, ma potrebbe non generare il miglior set di dati integrato.

Di conseguenza, è necessario selezionare una casella di controllo di riconoscimento quando si seleziona la modalità Auto, prima di poter salvare l&#39;impostazione dell&#39;account.

Per configurare un account del motore di ricerca in modalità automatica, è necessario effettuare le seguenti operazioni:

* Il `s_kwcid` parametro e il valore verranno aggiunti ai modelli di tracciamento dell’account o agli URL delle pagine di destinazione nell’account che si sta aggiungendo. Questo verrà inserito alla fine dell’URL. Potrebbe essere necessaria un&#39;azione aggiuntiva da parte dell&#39;utente se il server Web richiede una coppia chiave=valore alla fine dell&#39;URL OPPURE un aggiornamento per supportare qualsiasi nuova coppia chiave=valore nell&#39;URL. **È responsabilità dell’utente assicurarsi che i parametri URL aggiunti continuino correttamente sulla pagina di destinazione finale.**
* Inoltre, le parole chiave possono essere inserite nell’URL di destinazione come parte del `s_kwcid` valore. Se contengono caratteri o simboli speciali, verificare che il server Web sia in grado di supportare tali caratteri. Esempio: Un carattere speciale comune è &quot;+&quot;, utilizzato nelle parole chiave &quot;Corrispondenza estesa modificata&quot;.

>[!IMPORTANT]
>
>Ulteriori informazioni sull&#39;aggiunta del `s_kwcid` parametro all&#39;informativa sulla sicurezza dei [contenuti](https://docs.adobe.com/content/help/en/id-service/using/reference/csp.html).

## Tracciamento modalità manuale {#concept_87B28BA9E7F84BA5972F69E6F3482A33}

In modalità Manuale, è necessario specificare come i dati del motore di ricerca devono essere gestiti dal processo di integrazione dei dati Advertising Analytics .

### Aggiungi tracciamento manuale all&#39;account Google {#section_41C1EB1AEB034544A5BC291F53C05C67}

La stringa che deve essere aggiunta al tuo account Google è mostrata di seguito. Devi aggiungere la stringa a tutti i modelli di tracciamento utilizzati nell’account.

>[!IMPORTANT]
>
>Il `<Advertising Analytics ID>` valore (in **grassetto** di seguito) è generico e **deve essere sostituito con la stringa** ID account specifica. Puoi ottenere la stringa ID account specifica dalla schermata di configurazione dell&#39;account nella sezione &quot;Tracciamento&quot;.

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

**`{lpurl}`con parametri URL aggiuntivi **

```
{lpurl}?campaign=PPC&s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!network}!{product_partition_id}!{keyword}
```

**3rd-party (DoubleClick)`{unescapedlpurl}`**

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={unescapedlpurl}?s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

**3rd-party (DoubleClick)`{lpurl}`**

Se l’URL attraversa un reindirizzamento e non utilizza un valore &quot;unescape edlpurl&quot;, è necessario codificare la stringa abbastanza volte in modo che continui a persistere attraverso il reindirizzamento all’URL finale della pagina di destinazione.

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={lpurl}?s_kwcid%3DAL!9999!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

### Aggiungi tracciamento manuale al conto Bing {#section_094F8ACA493C4D65B1F54A695558EBF2}

La stringa che deve essere aggiunta al tuo account Bing è mostrata di seguito. Dovete aggiungere la stringa a tutti i suffissi URL finali utilizzati nell’account.

>[!IMPORTANT]
>
>Il `<Advertising Analytics ID>` valore (in **grassetto** di seguito) è generico e **deve essere sostituito con la stringa** ID account specifica. Puoi ottenere la stringa ID account specifica dalla schermata di configurazione dell&#39;account nella sezione &quot;Tracciamento&quot;.

**Stringa di tracciamento per le campagne:**

```
s_kwcid=AL!<Advertising Analytics ID>!10!{AdId}!{OrderItemId} 
```

![](assets/Bing.png)

Esempi di codici di tracciamento in vari formati di suffisso URL finali:

**{lpurl}**

```
{lpurl}?s_kwcid=AL!9999!10!{AdId}!{OrderItemId}
```

**`{lpurl}`con parametri URL aggiuntivi **

```
{lpurl}?campaign=PPC&
s_kwcid=AL!9999!10!{AdId}!{OrderItemId}
```

**3rd-party (DoubleClick)`{unescapedlpurl}`**

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={unescapedlpurl}?s_kwcid=AL!9999!10!{AdId}!{OrderItemId}
```

**3rd-party (DoubleClick)`{lpurl}`**

Se l’URL attraversa un reindirizzamento e non utilizza un valore &quot;unescape edlpurl&quot;, è necessario codificare la stringa abbastanza volte in modo che continui a persistere attraverso il reindirizzamento all’URL finale della pagina di destinazione.

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={lpurl}?s_kwcid%3DAL!9999!10!{AdId}!{OrderItemId}
```
