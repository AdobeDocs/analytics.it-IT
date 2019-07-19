---
description: I filtri consentono di restringere il rapporto per includere o escludere elementi di riga che corrispondono a un filtro.
seo-description: I filtri consentono di restringere il rapporto per includere o escludere elementi di riga che corrispondono a un filtro.
seo-title: Filtrare i dati dei rapporti
solution: Analytics
title: Filtrare i dati dei rapporti
topic: Reports & Analytics
uuid: b 6 dcaaf 7-61 f 0-4793-870 d-e 1 d 156575 d 5 a
translation-type: tm+mt
source-git-commit: bf67baa33bc21e71c911d5108ee6044adf634fce

---


# Filter Report Data {#concept_09DC5B986A644738B12204DAC76A90E1}

I filtri consentono di restringere il rapporto per includere o escludere elementi di riga che corrispondono a un filtro.

## Simple Filter {#section_5C4DE873F8D5484BB77F38A4AEB57B4A}

![](assets/filter.png)

Il filtro semplice viene visualizzato sulla maggior parte dei rapporti per trovare rapidamente elementi specifici della linea. Simple filters do not use any special characters, so `-, ", ', +` and other special characters match the literal value in the report. È possibile trovare elementi linea contenenti termini multipli utilizzando uno spazio.

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

## Advanced Filters {#section_E016626C084640E8A066B2FDA5B932BF}

I filtri avanzati consentono di controllare l'ambito della ricerca utilizzando una raccolta di filtri. È possibile selezionare tutti i filtri o tutti i filtri.

![](assets/advanced_filter.png)

**Contiene**

Corrisponde se il termine viene trovato ovunque nell'elemento della riga. Funziona come il filtro semplice.

>[!NOTE]
>
>Gli spazi non possono essere utilizzati nei filtri perché gli spazi sono delimitati da ricerche nelle ricerche

**Non contiene**

Corrisponde se il termine non è trovato nell'elemento della riga. You can filter "unspecified", "none", "keyword unavailable" and other [special values](https://marketing.adobe.com/resources/help/en_US/reference/none-unspecified-unknown-other.html) from reports using "does not contain".

Non contiene: `none`

Per un filtro più preciso, potete usare un filtro Avanzato (Caratteri speciali):

* Advanced (Special Character): `-^none$`
* Advanced (Special Character): `-"keyword unavailable"`

Ad esempio, la seguente voce di riga viene filtrata dai criteri "Does Not contain" (Non contiene), ma non viene filtrata dai criteri "Advanced (Special Character)":

```
help:Rename the None classification key
```

**Contiene uno di**

Corrisponde se sono presenti termini, separati da spazi, nell'elemento della riga. Il filtro seguente mostra tutte le pagine contenenti «menu» o «vendita»:

Contains One Of: `mens sale`

Corrisponde alle pagine seguenti:

```
Womens
Mens
Mens:Desk & TravelJewelry & Accessories:Accessories:Hats:Mens
Sale & Values
```

**È uguale a**

Corrisponde se l'intero elemento della riga, incluso spazi e altri caratteri, corrisponde alla frase specificata.

È uguale a: `mens:desk & travel`

`Mens:Desk & Travel`

**Inizia con**

Corrisponde se l'elemento della riga, incluso spazi e altri caratteri, inizia con la frase specificata.

Starts With: `mens`

Corrisponde alle pagine seguenti:

```
Mens
Mens:Desk & Travel
Mens:Apparel
Mens Perfume Spray
Mens Hemp/Bamboo Flip Flops
```

**Termina con**

Corrisponde se l'elemento della riga, incluso spazi e altri caratteri, termina con la frase specificata.

Ends With: `jean`

Corrisponde alle pagine seguenti:

```
Bell Bottom Jean
Velvet Dream Skinny Leg Jean
Dark Slimmer Jean
Bling Belt High Waist Jean
Ocean Blue Jean
```

## Advanced (Special Character) {#section_83DA3B6C23EB4C119DB6D74062DB501D}

Avanzata consente di eseguire caratteri jolly e altre ricerche complesse.

| Avanzato (carattere speciale) | Descrizione |
|--- |--- |
| `" "` | Corrispondenza esatta. |
| `*` | Carattere jolly, corrispondenza greedy. <br>`r*p` Ad esempio, corrisponde a "Registrazione registrazione". |
| `^` | Inizia con. <br>Non includete uno spazio tra il carattere speciale e la frase di ricerca. |
| `$` | Termina con. <br>Non includete uno spazio tra il carattere speciale e la frase di ricerca. |
| `-` | Not. <br>Non includete uno spazio tra il carattere speciale e la frase di ricerca. |
| `|` | Or<br>Note:  you must include a space on each side of the pipe character, `" | "`. |

## Create report-specific filters {#task_DEBB0632411D4CA8AA0B3BA267A5B35F}

Procedura che descrive come creare filtri per i rapporti.

<!-- 

t_reports_filter_specific.xml

 -->

Alcuni rapporti contengono un filtro specifico per tale rapporto. For example, a [!UICONTROL Purchase Conversion Funnel Report] lets you filter by web pages. A [!UICONTROL Geosegmentation Report] lets you filter by geographical region. Altri rapporti sono dotati di altri filtri specifici per tali rapporti.

Quando accedete a tali filtri, potete visualizzare le metriche di rapporti per gli elementi specificati nell'elenco.

**Per creare filtri specifici per i rapporti**

1. Generate a report, such as a [!UICONTROL Purchase Report] ( **[!UICONTROL Site Metrics]** &gt; **[!UICONTROL Purchases]** &gt; **[!UICONTROL Purchase Conversion Funnel]**).
1. In the report header, click the **[!UICONTROL Filter]** link.
1. On the [!UICONTROL Filter Selector] page, click **[!UICONTROL Apply a Filter]**, then select a filter type.
1. To search for an item, type a character string in the **[!UICONTROL Search]** field.
1. Fai clic su **[!UICONTROL OK]**.

## Add a correlation filter {#task_065042E384DA4BF3864C58AF2B88D6E2}

Procedura che descrive come aggiungere un filtro di correlazione.

<!-- 

t_reports_correlation_filter.xml

 -->

Alcuni rapporti consentono di aggiungere filtri di correlazione personalizzati. For example, if you are viewing the [!UICONTROL Pages Report] for a report suite that has Site Sections correlated with a Women's page, you can create a filter rule that generates a report showing the most popular pages when Site Sections = Women.

Puoi filtrare i dati mostrati in un rapporto di correlazione utilizzando qualsiasi correlazione disponibile. Nell'esempio seguente viene illustrato come aggiungere un filtro di correlazione motore di ricerca.

**Per aggiungere un filtro di correlazione**

1. Eseguite un report che supporta le correlazioni. (See [Running a Breakdown Report](../../../analyze/reports-analytics/reports-customize/breakdowns.md#task_F685624830E64C829C8BE6435A107F69).)
1. In the report header, click the **[!UICONTROL Correlation Filter]** link.
1. Under [!UICONTROL Filter Rule Creator], select a category to correlate with an item.
1. Fai clic su **[!UICONTROL OK.]**
