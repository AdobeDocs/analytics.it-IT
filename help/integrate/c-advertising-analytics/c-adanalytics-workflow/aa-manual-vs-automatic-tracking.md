---
description: Il tipo di tracciamento determina il modo in cui l’implementazione di Adobe Analytics tiene traccia dei dati del motore di ricerca. Questo tipo di tracciamento è un passaggio necessario per integrare correttamente i dati di Adobe Analytics con i dati del motore di ricerca.
title: Tipo di tracciamento
feature: Advertising Analytics
exl-id: 3e2ed26f-dfb2-43ea-8eb6-e332cd10fb29
source-git-commit: 8b1e25b9633b6db3e49da079f7014e6b7b595474
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 0%

---

# Tipo di tracciamento

Il tipo di tracciamento determina il modo in cui l’implementazione di Adobe Analytics tiene traccia dei dati del motore di ricerca. Questo tipo di tracciamento è un passaggio necessario per integrare correttamente i dati di Adobe Analytics con i dati del motore di ricerca.

<!--

Here is a video overview of how to implement the Advertising Analytics tracking template:

>[!VIDEO](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/integrations/ad-cloud/implementing-tracking-templates-into-search-engines)

-->

Sono supportate due modalità di tracciamento: [!UICONTROL Auto] e [!UICONTROL Manual].

## Tracciamento di [!UICONTROL Auto] {#concept_C4C6107838C947CFBB7F4E0CB94264F0}

Il monitoraggio di [!UICONTROL Auto] consente al motore di Advertising Cloud di decidere come gestire i dati del motore di ricerca. Il tracciamento automatico è l’approccio più semplice, ma potrebbe non risultare nel miglior set di dati integrato.

Di conseguenza, è necessario selezionare una casella di controllo di conferma quando si seleziona **[!UICONTROL Auto]** prima di poter salvare l&#39;impostazione dell&#39;account.

Per configurare un account del motore di ricerca con tipo **[!UICONTROL Auto]**, è necessario eseguire le azioni seguenti:

* Il parametro e il valore `s_kwcid` vengono aggiunti ai modelli di tracciamento dell&#39;account o agli URL della pagina di destinazione nell&#39;account aggiunto. Questo parametro e il valore vengono inseriti alla fine dell’URL. Se il server Web richiede una coppia di `key=value` alla fine dell&#39;URL, potrebbe essere necessaria un&#39;azione aggiuntiva. Oppure un aggiornamento per supportare qualsiasi nuova coppia `key=value` nell&#39;URL. È tua responsabilità verificare che i parametri URL aggiunti persistano correttamente nella pagina di destinazione finale.
* Inoltre, è possibile inserire parole chiave nell&#39;URL di destinazione come parte del valore `s_kwcid`. Se contengono caratteri o simboli speciali, verificare che il server Web in uso supporti tali caratteri. Ad esempio, un carattere speciale comune è `+`, utilizzato nelle parole chiave &quot;Broad Match Modified&quot;.

>[!IMPORTANT]
>
>Ulteriori informazioni sull&#39;aggiunta del parametro `s_kwcid` ai [Criteri sulla sicurezza dei contenuti](https://experienceleague.adobe.com/en/docs/id-service/using/reference/csp).

## Tracciamento manuale {#concept_87B28BA9E7F84BA5972F69E6F3482A33}

Il tracciamento manuale consente di specificare in che modo il processo di integrazione dei dati di Advertising Analytics deve trattare i dati del motore di ricerca.

### Aggiungere il tracciamento manuale all’account Google {#section_41C1EB1AEB034544A5BC291F53C05C67}

La stringa da aggiungere al tuo account Google è mostrata di seguito. Devi aggiungere la stringa a tutti i modelli di tracciamento utilizzati nel tuo account.

>[!IMPORTANT]
>
>Il valore *`<Advertising Analytics ID>`* (in **bold** di seguito) è generico e **deve essere sostituito con la stringa ID account specifica**. Puoi ottenere la stringa dell&#39;ID account specifico dalla schermata dell&#39;account nella sezione [!UICONTROL Tracking].

**Stringa di tracciamento per le campagne:**

```
s_kwcid=AL! 
<b><Advertising Analytics ID></b>!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

![Google](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/assets/google-account.png)

Esempi di codici di tracciamento in vari formati di modelli di tracciamento:

**`{lpurl}`**

```
{lpurl}?s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!network}!{product_partition_id}!{keyword}
```

**`{lpurl}`con parametro URL aggiuntivo**

```
{lpurl}?campaign=PPC&s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!network}!{product_partition_id}!{keyword}
```

**terze parti (DoubleClick)`{unescapedlpurl}`**

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={unescapedlpurl}?s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

**terze parti (DoubleClick)`{lpurl}`**

Per garantire che la stringa persista attraverso il reindirizzamento all’URL della pagina di destinazione finale, devi codificare la stringa a sufficienza:

* se l’URL passa attraverso un reindirizzamento, e
* non utilizza un valore &quot;unescape edlpurl&quot;.


```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={lpurl}?s_kwcid%3DAL!9999!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

### Aggiungere il tracciamento manuale all’account Microsoft Advertising {#section_094F8ACA493C4D65B1F54A695558EBF2}

La stringa da aggiungere al tuo account Microsoft Advertising è mostrata di seguito. Devi aggiungere la stringa a tutti i suffissi URL finali utilizzati in tutto l’account.

>[!IMPORTANT]
>
>Il valore _`<Advertising Analytics ID>`_(in **bold**&#x200B;di seguito) è generico e **deve essere sostituito con la stringa ID account specifica**. Puoi ottenere la stringa del tuo ID account specifico dalla schermata dell’account nella sezione &quot;Tracking&quot; (Tracciamento).

**Stringa di tracciamento per le campagne:**

```
s_kwcid=AL!<Advertising Analytics ID>!10!{AdId}!{OrderItemId} 
```

![Aggiungi parametri del codice di tracciamento](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/assets/bing-account.png)

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

**terze parti (DoubleClick)`{unescapedlpurl}`**

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={unescapedlpurl}?s_kwcid=AL!9999!10!{AdId}!{OrderItemId}
```

**terze parti (DoubleClick)`{lpurl}`**

Per garantire che la stringa persista attraverso il reindirizzamento all’URL della pagina di destinazione finale, devi codificare la stringa a sufficienza:

* se l’URL passa attraverso un reindirizzamento, e
* non utilizza un valore &quot;unescape edlpurl&quot;.

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={lpurl}?s_kwcid%3DAL!9999!10!{AdId}!{OrderItemId}
```
