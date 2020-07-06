---
description: I filtri consentono di restringere il rapporto per includere o escludere elementi di riga che corrispondono a un filtro.
title: Filtraggio dati dei rapporti
topic: Reports and analytics
uuid: b6dcaaf7-61f0-4793-870d-e1d156575d5a
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 4%

---


# Filtra dati rapporto {#concept_09DC5B986A644738B12204DAC76A90E1}

I filtri consentono di restringere il rapporto per includere o escludere elementi di riga che corrispondono a un filtro.

## Filtro semplice {#section_5C4DE873F8D5484BB77F38A4AEB57B4A}

![](assets/filter.png)

Il filtro semplice viene visualizzato nella maggior parte dei rapporti per individuare rapidamente elementi di riga specifici. I filtri semplici non utilizzano caratteri speciali, pertanto `-, ", ', +` e altri caratteri speciali corrispondono al valore letterale nel rapporto. È possibile trovare righe contenenti più termini utilizzando uno spazio.

Ad esempio:

```
help search
```

Corrisponde alle pagine seguenti:

```
help:Search
help:Paid Search Detection
help:Configure paid search detection
help:Search Keywords Report
help:Internal Search Term
```

## Filtri avanzati {#section_E016626C084640E8A066B2FDA5B932BF}

I filtri avanzati consentono di controllare l&#39;ambito della ricerca utilizzando una raccolta di filtri. È possibile scegliere se applicare tutti i filtri o altri filtri.

![](assets/advanced_filter.png)

**Contiene**

Corrisponde se il termine è trovato in un punto qualsiasi dell&#39;elemento della riga. Funziona come il filtro semplice.

>[!NOTE]
>
>Gli spazi non possono essere utilizzati nei filtri, perché gli spazi sono delimitatori nelle ricerche

**Non contiene**

Corrisponde se il termine non viene trovato in alcun punto dell&#39;elemento della riga. Potete filtrare &quot;unspecified&quot;, &quot;none&quot;, &quot;keyword non disponibile&quot; e altri valori [](https://docs.adobe.com/content/help/en/analytics/technotes/unspecified.html) speciali dai rapporti utilizzando &quot;non contiene&quot;.

Non contiene: `none`

Per un filtro più preciso, potete usare un filtro Avanzate (Caratteri speciali):

* Avanzate (carattere speciale): `-^none$`
* Avanzate (carattere speciale): `-"keyword unavailable"`

Ad esempio, l&#39;elemento di riga seguente viene filtrato in base ai criteri &quot;Non contiene&quot;, ma non in base ai criteri &quot;Avanzate (Carattere speciale)&quot;:

```
help:Rename the None classification key
```

**Contiene Uno**

Corrisponde se nell&#39;elemento della riga sono presenti termini, separati da spazi. Il filtro seguente mostra tutte le pagine che contengono &quot;mens&quot; o &quot;sale&quot;:

Contiene Uno Dei Seguenti Elementi: `mens sale`

Corrisponde alle pagine seguenti:

```
Womens
Mens
Mens:Desk & TravelJewelry & Accessories:Accessories:Hats:Mens
Sale & Values
```

**È uguale a**

Corrisponde se l&#39;intero elemento della riga, compresi gli spazi e altri caratteri, corrisponde alla frase specificata.

È uguale a: `mens:desk & travel`

`Mens:Desk & Travel`

**Inizia con**

Corrisponde se l&#39;elemento di riga, compresi gli spazi e altri caratteri, inizia con la frase specificata.

Inizia con: `mens`

Corrisponde alle pagine seguenti:

```
Mens
Mens:Desk & Travel
Mens:Apparel
Mens Perfume Spray
Mens Hemp/Bamboo Flip Flops
```

**Termina con**

Corrisponde se l&#39;elemento di riga, compresi gli spazi e altri caratteri, termina con la frase specificata.

Termina con: `jean`

Corrisponde alle pagine seguenti:

```
Bell Bottom Jean
Velvet Dream Skinny Leg Jean
Dark Slimmer Jean
Bling Belt High Waist Jean
Ocean Blue Jean
```

## Avanzate (carattere speciale) {#section_83DA3B6C23EB4C119DB6D74062DB501D}

Avanzate consente di eseguire caratteri jolly e altre ricerche complesse.

| Avanzate (carattere speciale) | Descrizione |
|--- |--- |
| `" "` | Corrispondenza esatta. |
| `*` | Carattere jolly, corrispondenza avida. <br>Ad esempio, `r*p` corrisponde a &quot;Registrazione&quot;. |
| `^` | Inizia con. <br>Non includete uno spazio tra il carattere speciale e la frase di ricerca. |
| `$` | Termina con. <br>Non includete uno spazio tra il carattere speciale e la frase di ricerca. |
| `-` | No. <br>Non includete uno spazio tra il carattere speciale e la frase di ricerca. |
| `|` | <br>OrNote:  è necessario includere uno spazio su ogni lato del carattere barra verticale, `" | "`. |

## Creare filtri specifici per i rapporti {#task_DEBB0632411D4CA8AA0B3BA267A5B35F}

Passaggi che descrivono come creare filtri per i rapporti.

<!-- 

t_reports_filter_specific.xml

 -->

Alcuni rapporti contengono un filtro specifico per il rapporto. Ad esempio, un [!UICONTROL Purchase Conversion Funnel Report] consente di filtrare per pagine Web. A [!UICONTROL Geosegmentation Report] consente di filtrare per area geografica. I rapporti aggiuntivi contengono altri filtri specifici per tali rapporti.

Quando accedete a questi filtri, potete visualizzare le metriche dei rapporti per gli elementi specificati nell&#39;elenco.

**Creazione di filtri specifici per i rapporti**

1. Generate un rapporto, ad esempio [!UICONTROL Purchase Report] ( **[!UICONTROL Site Metrics]** > **[!UICONTROL Purchases]** > **[!UICONTROL Purchase Conversion Funnel]**).
1. Nell’intestazione del rapporto, fate clic sul **[!UICONTROL Filter]** collegamento.
1. Sulla [!UICONTROL Filter Selector] pagina, fate clic **[!UICONTROL Apply a Filter]**, quindi selezionate un tipo di filtro.
1. Per cercare un elemento, digitare una stringa di caratteri nel **[!UICONTROL Search]** campo.
1. Fai clic su **[!UICONTROL OK]**.

## Add a correlation filter {#task_065042E384DA4BF3864C58AF2B88D6E2}

Passaggi che descrivono come aggiungere un filtro di correlazione.

<!-- 

t_reports_correlation_filter.xml

 -->

Alcuni rapporti consentono di aggiungere filtri di correlazione personalizzati. Ad esempio, se stai visualizzando il report [!UICONTROL Pages Report] per una suite di rapporti con sezioni del sito correlate a una pagina femminile, puoi creare una regola di filtro che genera un report con le pagine più popolari quando Sezioni del sito = Donne.

Puoi filtrare i dati visualizzati in un rapporto di correlazione utilizzando qualsiasi correlazione disponibile. L’esempio seguente mostra come aggiungere un filtro di correlazione per il motore di ricerca.

**Aggiunta di un filtro di correlazione**

1. Eseguire un report che supporti le correlazioni. (Vedere [Esecuzione di un rapporto](/help/analyze/reports-analytics/reports-customize/breakdowns.md#task_F685624830E64C829C8BE6435A107F69)di suddivisione.)
1. Nell’intestazione del rapporto, fate clic sul **[!UICONTROL Correlation Filter]** collegamento.
1. In [!UICONTROL Filter Rule Creator]selezionare una categoria da correlare a un elemento.
1. Fai clic su **[!UICONTROL OK.]**
