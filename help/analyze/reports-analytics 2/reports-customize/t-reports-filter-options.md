---
description: I filtri consentono di restringere il rapporto includendo o escludendo elementi di riga che corrispondono a un filtro.
title: Filtraggio dei dati dei rapporti
uuid: b6dcaaf7-61f0-4793-870d-e1d156575d5a
feature: Reports & Analytics Basics
role: User, Admin
exl-id: 232c6f69-40bf-487a-8621-d1d7d633681f
source-git-commit: a2e69b5f39de3c964381bb5dd5ecd4d9714e9249
workflow-type: tm+mt
source-wordcount: '627'
ht-degree: 97%

---

# Filtrare i dati dei rapporti {#concept_09DC5B986A644738B12204DAC76A90E1}

{{ra-eol}}

I filtri consentono di restringere il rapporto includendo o escludendo elementi di riga che corrispondono a un filtro.

## Filtro semplice {#section_5C4DE873F8D5484BB77F38A4AEB57B4A}

![](/help/admin/admin/assets/filter.png)

Il filtro semplice viene visualizzato nella maggior parte dei rapporti per consentire di trovare rapidamente elementi di riga specifici. I filtri semplici non utilizzano caratteri speciali, pertanto `-, ", ', +` e altri caratteri speciali corrispondono al valore letterale nel rapporto. È possibile trovare elementi di riga contenenti più termini utilizzando uno spazio.

Esempio:

```
help search
```

Corrisponde alle seguenti pagine:

```
help:Search
help:Paid Search Detection
help:Configure paid search detection
help:Search Keywords Report
help:Internal Search Term
```

## Filtri avanzati {#section_E016626C084640E8A066B2FDA5B932BF}

I filtri avanzati consentono di controllare l’ambito della ricerca utilizzando una raccolta di filtri. Puoi scegliere se applicare tutti i filtri o qualsiasi filtro.

![](assets/advanced_filter.png)

**Contiene**

Restituisce un risultato se il termine si trova in un punto qualsiasi della riga. Funziona allo stesso modo del filtro semplice.

>[!NOTE]
>
>Gli spazi non possono essere utilizzati nei filtri, perché sono delimitatori nelle ricerche

**Non contiene**

Restituisce un risultato se il termine non viene trovato in nessun punto della riga. Utilizzando “non contiene” puoi filtrare i valori “non specificato”, “nessuno”, “parola chiave non disponibile” e altri [valori speciali](https://experienceleague.adobe.com/docs/analytics/technotes/unspecified.html?lang=it) dai rapporti.

Non contiene: `none`

Per un filtro più preciso, puoi utilizzare un filtro Avanzato (caratteri speciali):

* Avanzato (carattere speciale): `-^none$`
* Avanzato (carattere speciale): `-"keyword unavailable"`

Ad esempio, il seguente elemento di riga viene filtrato dal criterio “Non contiene”, ma non viene filtrato dal criterio “Avanzato (carattere speciale)”:

```
help:Rename the None classification key
```

**Contiene uno di**

Restituisce un risultato se i termini, separati da spazi, si trovano nell’elemento di riga. Il seguente filtro mostra tutte le pagine che contengono “mens” o “sale”:

Contiene uno di: `mens sale`

Corrisponde alle seguenti pagine:

```
Womens
Mens
Mens:Desk & TravelJewelry & Accessories:Accessories:Hats:Mens
Sale & Values
```

**È uguale a**

Restituisce un risultato se l’intero elemento di riga, compresi gli spazi e altri caratteri, corrisponde alla frase specificata.

È uguale a: `mens:desk & travel`

`Mens:Desk & Travel`

**Inizia con**

Restituisce un risultato se l’elemento di riga, compresi gli spazi e altri caratteri, inizia con la frase specificata.

Inizia con: `mens`

Corrisponde alle seguenti pagine:

```
Mens
Mens:Desk & Travel
Mens:Apparel
Mens Perfume Spray
Mens Hemp/Bamboo Flip Flops
```

**Termina con**

Restituisce un risultato se l’elemento di riga, compresi gli spazi e altri caratteri, termina con la frase specificata.

Termina con: `jean`

Corrisponde alle seguenti pagine:

```
Bell Bottom Jean
Velvet Dream Skinny Leg Jean
Dark Slimmer Jean
Bling Belt High Waist Jean
Ocean Blue Jean
```

## Avanzato (carattere speciale) {#section_83DA3B6C23EB4C119DB6D74062DB501D}

Avanzato consente di cercare caratteri jolly ed eseguire altre ricerche complesse.

| Avanzato (carattere speciale) | Descrizione |
|--- |--- |
| `" "` | Restituisce un risultato se viene trovata la frase esatta. |
| `*` | Carattere jolly, corrispondenza con algoritmo greedy. <br>Esempio: `r*p` troverà “Registration Signup”. |
| `^` | Inizia con. <br>Non includere uno spazio tra il carattere speciale e la frase di ricerca. |
| `$` | Termina con. <br>Non includere uno spazio tra il carattere speciale e la frase di ricerca. |
| `-` | No. <br>Non includere uno spazio tra il carattere speciale e la frase di ricerca. |
| `|` | Oppure<br>Nota: è necessario includere uno spazio prima e dopo il carattere della barra verticale, `" | "`. |

## Creare filtri specifici per i rapporti {#task_DEBB0632411D4CA8AA0B3BA267A5B35F}

Puoi creare filtri per i rapporti.

<!-- 

t_reports_filter_specific.xml

 -->

Alcuni rapporti contengono un filtro specifico per quel rapporto. Ad esempio, un [!UICONTROL Purchase Conversion Funnel Report] consente di filtrare per pagine web. Un [!UICONTROL Geosegmentation Report] consente di filtrare per area geografica. Ulteriori rapporti hanno altri filtri specifici per tali rapporti.

Quando accedi a questi filtri, puoi visualizzare le metriche dei rapporti per gli elementi specificati nell’elenco.

Per creare filtri specifici per i rapporti:

1. Genera un rapporto, ad esempio un [!UICONTROL Purchase Report] ( **[!UICONTROL Site Metrics]** > **[!UICONTROL Purchases]** > **[!UICONTROL Purchase Conversion Funnel]**).
1. Nell’intestazione del rapporto, fai clic sul pulsante sul collegamento **[!UICONTROL Filter]**.
1. Sulla pagina [!UICONTROL Filter Selector], fai clic su **[!UICONTROL Apply a Filter]**, quindi seleziona un tipo di filtro.
1. Per cercare un elemento, digita una stringa di caratteri nel campo **[!UICONTROL Search]**.
1. Fai clic su **[!UICONTROL OK]**.

## Aggiungere un filtro di correlazione {#task_065042E384DA4BF3864C58AF2B88D6E2}

<!-- 

t_reports_correlation_filter.xml

 -->

Alcuni rapporti consentono di aggiungere filtri di correlazione personalizzati. Ad esempio, se visualizzi il [!UICONTROL Pages Report] per una suite di rapporti con sezioni del sito correlate a una pagina Donne, puoi creare una regola di filtro che genera un rapporto che mostra le pagine più popolari quando Sezioni del sito = Donne.

Puoi filtrare i dati visualizzati in un rapporto di correlazione utilizzando qualsiasi correlazione disponibile. L’esempio seguente mostra come aggiungere un filtro di correlazione per motore di ricerca.

Per aggiungere un filtro di correlazione:

1. Esegui un rapporto che supporta le correlazioni. (Vedi [Esecuzione di un rapporto con raggruppamenti](/help/analyze/reports-analytics/reports-customize/breakdowns.md#task_F685624830E64C829C8BE6435A107F69).)
1. Nell’intestazione del rapporto, fai clic sul collegamento **[!UICONTROL Correlation Filter]**.
1. In [!UICONTROL Filter Rule Creator], seleziona una categoria da correlare a un elemento.
1. Fai clic su **[!UICONTROL OK.]**
