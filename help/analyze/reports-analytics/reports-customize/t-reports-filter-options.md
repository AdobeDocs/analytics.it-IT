---
description: I filtri ti consentono di restringere il rapporto per includere o escludere elementi di riga che corrispondono a un filtro.
title: Filtraggio dati dei rapporti
uuid: b6dcaaf7-61f0-4793-870d-e1d156575d5a
feature: Nozioni di base su Reports & Analytics
role: User, Admin
exl-id: 232c6f69-40bf-487a-8621-d1d7d633681f
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '647'
ht-degree: 4%

---

# Filtrare i dati dei rapporti {#concept_09DC5B986A644738B12204DAC76A90E1}

I filtri ti consentono di restringere il rapporto per includere o escludere elementi di riga che corrispondono a un filtro.

## Filtro semplice {#section_5C4DE873F8D5484BB77F38A4AEB57B4A}

![](assets/filter.png)

Il filtro semplice viene visualizzato nella maggior parte dei rapporti per consentire di trovare rapidamente elementi di riga specifici. I filtri semplici non utilizzano caratteri speciali, pertanto `-, ", ', +` e altri caratteri speciali corrispondono al valore letterale nel rapporto. È possibile trovare elementi riga contenenti più termini utilizzando uno spazio.

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

I filtri avanzati consentono di controllare l’ambito della ricerca utilizzando una raccolta di filtri. Puoi scegliere se abbinare tutti i filtri o altri filtri.

![](assets/advanced_filter.png)

**Contiene**

Corrisponde se il termine si trova in un punto qualsiasi della riga. Funziona allo stesso modo del filtro semplice.

>[!NOTE]
>
>Gli spazi non possono essere utilizzati nei filtri, perché gli spazi sono delimitatori nelle ricerche

**Non contiene**

Corrisponde se il termine non viene trovato in un punto qualsiasi della riga. Puoi filtrare &quot;non specificato&quot;, &quot;nessuno&quot;, &quot;parola chiave non disponibile&quot; e altri [valori speciali](https://experienceleague.adobe.com/docs/analytics/technotes/unspecified.html) dai rapporti che utilizzano &quot;non contiene&quot;.

Non contiene: `none`

Per un filtro più preciso, puoi utilizzare un filtro Avanzate (Caratteri speciali):

* Avanzate (carattere speciale): `-^none$`
* Avanzate (carattere speciale): `-"keyword unavailable"`

Ad esempio, la seguente riga viene filtrata dai criteri &quot;Non contiene&quot;, ma non viene filtrata dai criteri &quot;Avanzate (Carattere speciale)&quot;:

```
help:Rename the None classification key
```

**Contiene Uno Dei**

Corrisponde se i termini, separati da spazi, si trovano nella voce di riga. Il filtro seguente mostra tutte le pagine che contengono &quot;mens&quot; o &quot;sale&quot;:

Contiene Uno Di: `mens sale`

Corrisponde alle pagine seguenti:

```
Womens
Mens
Mens:Desk & TravelJewelry & Accessories:Accessories:Hats:Mens
Sale & Values
```

**È uguale a**

Corrisponde se l’intero elemento della riga, compresi gli spazi e altri caratteri, corrisponde alla frase specificata.

È uguale a: `mens:desk & travel`

`Mens:Desk & Travel`

**Inizia con**

Corrisponde se l’elemento, compresi gli spazi e altri caratteri, inizia con la frase specificata.

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

Corrisponde se la riga, compresi gli spazi e altri caratteri, termina con la frase specificata.

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

Avanzate ti consente di eseguire caratteri jolly e altre ricerche complesse.

| Avanzate (carattere speciale) | Descrizione |
|--- |--- |
| `" "` | Corrispondenza esatta frase. |
| `*` | Cartoncino selvaggio, acidità abbinamento. <br>Ad esempio,  `r*p`  corrisponde a &quot;Registrazione registrazione&quot;. |
| `^` | Inizia con. <br>Non includere uno spazio tra il carattere speciale e la frase di ricerca. |
| `$` | Termina con. <br>Non includere uno spazio tra il carattere speciale e la frase di ricerca. |
| `-` | No. <br>Non includere uno spazio tra il carattere speciale e la frase di ricerca. |
| `|` | Oppure<br>Nota:  è necessario includere uno spazio su ciascun lato del carattere della barra verticale, `" | "`. |

## Creare filtri specifici per i rapporti {#task_DEBB0632411D4CA8AA0B3BA267A5B35F}

Passaggi che descrivono come creare filtri per i rapporti.

<!-- 

t_reports_filter_specific.xml

 -->

Alcuni rapporti contengono un filtro specifico per quel rapporto. Ad esempio, un [!UICONTROL Purchase Conversion Funnel Report] consente di filtrare per pagine web. Un [!UICONTROL Geosegmentation Report] consente di filtrare per area geografica. Altri filtri sono disponibili per i rapporti specifici.

Quando accedi a questi filtri, puoi visualizzare le metriche dei rapporti per gli elementi specificati nell’elenco.

**Creazione di filtri specifici per i rapporti**

1. Genera un rapporto, ad esempio un [!UICONTROL Purchase Report] ( **[!UICONTROL Site Metrics]** > **[!UICONTROL Purchases]** > **[!UICONTROL Purchase Conversion Funnel]**).
1. Nell’intestazione del rapporto, fai clic sul collegamento **[!UICONTROL Filter]** .
1. Nella pagina [!UICONTROL Filter Selector] , fai clic su **[!UICONTROL Apply a Filter]**, quindi seleziona un tipo di filtro.
1. Per cercare un elemento, digitare una stringa di caratteri nel campo **[!UICONTROL Search]**.
1. Fai clic su **[!UICONTROL OK]**.

## Aggiungere un filtro di correlazione {#task_065042E384DA4BF3864C58AF2B88D6E2}

Passaggi che descrivono come aggiungere un filtro di correlazione.

<!-- 

t_reports_correlation_filter.xml

 -->

Alcuni rapporti consentono di aggiungere filtri di correlazione personalizzati. Ad esempio, se visualizzi la sezione [!UICONTROL Pages Report] per una suite di rapporti con sezioni del sito correlate a una pagina Donne, puoi creare una regola di filtro che genera un rapporto che mostra le pagine più popolari quando Sezioni del sito = Donne.

Puoi filtrare i dati visualizzati in un rapporto di correlazione utilizzando qualsiasi correlazione disponibile. L’esempio seguente mostra come aggiungere un filtro di correlazione del motore di ricerca.

**Per aggiungere un filtro di correlazione**

1. Esegui un rapporto che supporta le correlazioni. (Consultare [Esecuzione di un rapporto di suddivisione](/help/analyze/reports-analytics/reports-customize/breakdowns.md#task_F685624830E64C829C8BE6435A107F69).)
1. Nell’intestazione del rapporto, fai clic sul collegamento **[!UICONTROL Correlation Filter]** .
1. In [!UICONTROL Filter Rule Creator], seleziona una categoria da correlare a un elemento.
1. Fai clic su **[!UICONTROL OK.]**
