---
description: La variabile pageName deve essere compilata con un identificatore di pagina intuitivo e di facile lettura.
keywords: Implementazione di Analytics
seo-description: La variabile pageName deve essere compilata con un identificatore di pagina intuitivo e di facile lettura.
seo-title: Strategie di denominazione delle pagine
solution: Analytics
title: Strategie di denominazione delle pagine
topic: Sviluppatore e implementazione
uuid: a829d0c7-6ebf-459a-b403-5e9c05161e5c
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Strategie di denominazione delle pagine

La variabile pageName deve essere compilata con un identificatore di pagina intuitivo e di facile lettura.

È possibile determinare il modo migliore per compilare la *`pageName`* variabile osservando la struttura del sito Web. I metodi elencati di seguito delineano vari metodi per compilare la *`pageName`* variabile.

Sebbene la *`pageName`* variabile sia fondamentale per identificare il comportamento degli utenti, Adobe consiglia di utilizzare più variabili per indicare le informazioni sulla pagina. Le migliori strategie di denominazione delle pagine utilizzano una variabile diversa per ogni livello di gerarchia all’interno del sito, come illustrato di seguito:

* La *`channel`* variabile può essere utilizzata per indicare la sezione del sito.
* La *`pageName`* variabile può essere utilizzata per mostrare il tipo di contenuto.
* Per il contenuto dettagliato è possibile utilizzare una [!UICONTROL custom insight] variabile (prop1).

I livelli di dettaglio variano a seconda delle proprietà, come illustrato di seguito:

| Variabile | Livello di dettaglio | Esempio  |
|---|---|---|
| Canale | Sezione Generale | Elettronica |
| Prop1 | Sezione | Sport: Sport locali |
| PageName | Descrizione contenuto generale | Prestiti : Home Ipoteca : Confronto tra velocità |
| Prop2 | Descrizione dettagliata del contenuto | Elettronica : PC portatile: Specifiche dettagliate: Thinkpad T20 IBM |

Maggiore è il livello del sito, più variabili devono essere utilizzate per identificare il contenuto della pagina. Le aziende hanno anche valore nel consentire la sovrapposizione tra le variabili. Ad esempio, una variabile più dettagliata può contenere informazioni non solo sul prodotto visualizzato, ma anche sulla sezione del sito e sulla sottosezione. Ciò è particolarmente utile quando un prodotto o un articolo viene visualizzato in più sezioni del sito.

Le seguenti strategie di denominazione delle pagine descrivono come compilare la *`pageName`* variabile. Sebbene sia tentata di scegliere la strategia di denominazione delle pagine più facile da implementare, la strategia di denominazione delle pagine determina in larga misura l’usabilità di tutti [!UICONTROL Path] e [!UICONTROL Page] i rapporti. Utilizzate il buon senso per decidere come assegnare un nome alle pagine.

## Nome univoco per ogni pagina {#section_24704CA39E2F4C00ACEAFF39CA0A921B}

Il metodo più valido per denominare le pagine consiste nel fornire a ciascuna pagina un identificatore univoco facilmente comprensibile per tutti [!DNL Analytics] gli utenti dell’organizzazione. Alcuni esempi di nomi di pagina sono Home Page, Electronics Department Home e Sports: Sport Locali : Liceo.

La maggior parte [!DNL Analytics] degli utenti ritiene che i nomi gerarchici delle pagine siano utili sia per identificare dove si trova la pagina sul sito, sia per identificare la sua funzione. Nella tabella seguente sono riportati alcuni nomi di pagina di esempio per vari settori:

| Conversione | Media | Finanza |
|---|---|---|
| Home page | Home page | Home page |
| Elettronica | Tecnologia | Home Crediti |
| Elettronica : PC notebook | Tecnologia: Nuovi gadget | Home Crediti : Confronta tasso |
| Elettronica : PC notebook: Pagina prodotto | Tecnologia: Nuovi gadget: Pagina articolo | Home Crediti : Confronto tariffe: 10 anni fisso |

## Percorso file (non URL completo) {#section_37FDCDA00DA84B3D9B8AB4290555FF34}

Per alcuni siti, il percorso del file è chiaro e di facile lettura. Ogni utente aziendale può leggere un URL e determinare la pagina a cui fa riferimento il percorso del file. Se questo è il caso del sito, potete utilizzare una variabile lato server per compilare il percorso del file nella *`pageName`* variabile, come illustrato di seguito:

```js
s.pageName="<%= file_path %>"
```

Adobe non consiglia di lasciare *`pageName`* vuoto tale campo (con conseguente utilizzo dell’URL completo della pagina) anche se potrebbe essere tentata. I seguenti effetti collaterali sono causati dal fatto che la *`pageName`* variabile rimane vuota e che viene utilizzata *`pageURL`* come identificatore di pagina.

* Il dominio e il percorso di una pagina potrebbero non essere sempre identici. Ad esempio, i seguenti quattro URL restituiscono una singola pagina:

   * `https://www.mysite.com/index.jsp`
   * `https://www.mysite.com`
   * `https://mysite.com/index.jsp`
   * `https://mysite.com/`
   Se *`pageName`* viene lasciato vuoto, ciascuno di questi nomi di pagina occuperebbe una voce separata nei rapporti.

* Alcune pagine (come i moduli) vengono pubblicate da sole, eliminando in tal modo qualsiasi distinzione tra il modulo originale e l'output risultante.
* Quando la pagina viene tradotta in un’altra lingua dai motori di ricerca o da altri strumenti online, l’URL della pagina è l’URL del motore di ricerca (non l’URL del sito).

## HTML (document.title) {#section_B99B8F66B0E2410FA7BFE44E6851EB3F}

Se avete dedicato del tempo a rendere i titoli HTML leggibili e intuitivi, potete usare lo stesso titolo del valore della *`pageName`* variabile. Adobe consiglia di utilizzare una variabile lato server per compilare il file *`pageName`* anziché utilizzare JavaScript [!DNL document.title]. Alcuni browser interpretano il titolo HTML in modo diverso rispetto ad altri, il che potrebbe causare la [!DNL Analytics] ricezione di nomi di pagina diversi da browser diversi.

L’utilizzo del titolo HTML si consiglia di copiare i titoli esistenti per ciascuna pagina in una variabile o in un elemento di gestione del contenuto separato. Quando si decide di apportare modifiche al titolo HTML per l’ottimizzazione del motore di ricerca o per altri scopi, i nomi delle [!DNL Analytics] pagine non vengono modificati. Se il nome di una pagina cambia in [!DNL Analytics], diventa una nuova pagina e non è connessa al nome della pagina precedente, indipendentemente dall'URL associato.
