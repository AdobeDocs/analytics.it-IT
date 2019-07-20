---
description: La variabile pagename deve essere compilata con un identificatore pagina intuitivo e intuitivo.
keywords: Implementazione di Analytics
seo-description: La variabile pagename deve essere compilata con un identificatore pagina intuitivo e intuitivo.
seo-title: Strategie di denominazione delle pagine
solution: Analytics
title: Strategie di denominazione delle pagine
topic: Sviluppatore e implementazione
uuid: a 829 d 0 c 7-6 ebf -459 a-b 403-5 e 9 c 05161 e 5 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Strategie di denominazione delle pagine

La variabile pagename deve essere compilata con un identificatore pagina intuitivo e intuitivo.

You can determine the best way of populating the *`pageName`* variable by looking at the structure of your website. The methods listed below outline various ways of populating the *`pageName`* variable.

While the *`pageName`* variable is central to identifying user behavior, Adobe recommends using multiple variables to indicate page information. Le strategie di denominazione delle pagine ottimali utilizzano una variabile diversa per ogni livello di gerarchia all'interno del sito, come illustrato di seguito:

* The *`channel`* variable can be used to indicate the site section.
* The *`pageName`* variable can be used to show content type.
* A [!UICONTROL custom insight] variable (prop1) can be used for detailed content.

I livelli di dettaglio variano a seconda della proprietà, come illustrato di seguito:

| Variabile | Livello di dettaglio | Esempio  |
|---|---|---|
| Canale | Sezione generale | Electronics |
| Prop1 | Sezione secondaria | Sport: Sport locali |
| Pagename | Descrizione generale del contenuto | Prestiti: Mutuo abitazione: Confronto delle rate |
| Prop2 | Descrizione dettagliata del contenuto | Electronics: Notebook PC: Specifiche dettagliate: IBM Thinkpad T 20 |

Più disponete del sito, più variabili devono essere utilizzate per identificare il contenuto della pagina. Le aziende trovano anche il valore per la sovrapposizione tra variabili. Ad esempio, una variabile più dettagliata potrebbe contenere informazioni non solo sul prodotto visualizzato, ma anche sulla sezione e nella sezione del sito. Questo è particolarmente utile quando un prodotto o un articolo viene visualizzato in più sezioni del sito.

The following page naming strategies describe how to populate the *`pageName`* variable. While it is tempting to choose the page naming strategy that is easiest to implement, the page naming strategy largely determines the usability of all [!UICONTROL Path] and [!UICONTROL Page] reports. Utilizzate un buon giudizio per decidere in che modo le pagine vengono denominate.

## Unique Name for Each Page {#section_24704CA39E2F4C00ACEAFF39CA0A921B}

The most valuable method of naming pages is to give each page a unique identifier that is easily understood by all [!DNL Analytics] users in your organization. Esempi di nomi di pagina includono Home Page, Electronics Department Home e Sport: Sport locali: High School.

Most [!DNL Analytics] users find that hierarchical page names are useful in both identifying where the page is found on the site and its purpose. Nella tabella seguente sono riportati alcuni nomi di pagina di esempio per i vari settori:

| Conversione   | Media | Finanza |
|---|---|---|
| Home page | Home page | Home page |
| Electronics | Tecnologia | Prestiti domiciliari |
| Electronics: Notebook | Tecnologia: Nuovi Gadget | Prestiti home: Confronto rate |
| Electronics: Notebook: Pagina prodotto | Tecnologia: Nuovi Gadget: Pagina articolo | Prestiti home: Confronto frequenza: 10 anno fisso |

## File Path (Not the Full URL) {#section_37FDCDA00DA84B3D9B8AB4290555FF34}

Per alcuni siti, il percorso del file è chiaro e leggibile. Qualsiasi utente aziendale può leggere un URL e determinare la pagina a cui fa riferimento il percorso del file. If this is the case for your site, you can use a server-side variable to populate the path to the file into the *`pageName`* variable, as shown below:

```js
s.pageName="<%= file_path %>"
```

Adobe does not recommend leaving the *`pageName`* blank, (which results in using the full URL of the page) even though you may be tempted to do so. The following side-effects are caused by leaving the *`pageName`* variable blank and using the *`pageURL`* as the page identifier.

* Il dominio e il percorso di una pagina potrebbero non essere sempre visualizzati in modo identico. Ad esempio, i quattro URL seguenti restituiscono una singola pagina:

   * `https://www.mysite.com/index.jsp`
   * `https://www.mysite.com`
   * `https://mysite.com/index.jsp`
   * `https://mysite.com/`
   If the *`pageName`* is left blank, each of these page names would occupy a separate entry in reports.

* Alcune pagine (come i moduli) vengono pubblicate su se stessi, eliminando così qualsiasi distinzione tra il modulo originale e l'output risultante.
* Quando la pagina viene convertita in un'altra lingua dai motori di ricerca o altri strumenti online, l'URL della pagina è l'URL del motore di ricerca (non l'URL del sito).

## HTML (document.title) {#section_B99B8F66B0E2410FA7BFE44E6851EB3F}

If you have invested time into making your HTML titles readable and intuitive, you might consider using the same title as the value in the *`pageName`* variable. Adobe recommends using a server-side variable to populate the *`pageName`* rather than using JavaScript's [!DNL document.title]. Some browsers interpret the HTML title differently than others, which may cause [!DNL Analytics] to receive different page names from different browsers.

La procedura ottimale per utilizzare il titolo HTML è copiare i titoli esistenti di ciascuna pagina in una variabile distinta o in un elemento di gestione dei contenuti. When you decide to make changes to the HTML title for search engine optimization or other purposes, the [!DNL Analytics] page names are not affected. If a page name changes in [!DNL Analytics], it becomes a new page and is not connected with the old page name, regardless of the associated URL.
