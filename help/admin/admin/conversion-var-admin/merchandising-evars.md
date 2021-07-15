---
title: eVar per merchandising e metodi di ricerca dei prodotti
description: Approfondisci i concetti alla base degli eVar di merchandising e le modalità di elaborazione e allocazione dei dati.
source-git-commit: e7bfb56b63a9134728360c91f3c835da1952fa5a
workflow-type: tm+mt
source-wordcount: '549'
ht-degree: 0%

---

# eVar per merchandising e metodi di ricerca dei prodotti

Questo documento spiega i concetti alla base degli eVar di merchandising, che elaborano e allocano i dati in modo diverso rispetto agli eVar standard. Inoltre, spiega come le eVar per merchandising si relazionano ai metodi di ricerca dei prodotti.

Mentre la maggior parte dei siti web per la vendita al dettaglio ha molti modi per trovare i prodotti, l&#39;Adobe considera i seguenti metodi fondamentali per la ricerca dei prodotti che ogni cliente al dettaglio dovrebbe monitorare in Adobe Analytics:

* Parole chiave di ricerca interne
* Codici di tracciamento delle campagne interne
* Categorie di merchandising/Sfoglia
* Collegamenti cross-selling

Ai fini del presente documento, mappamo alcuni eVar alle soluzioni come segue:

* eVar 2: Parole chiave di ricerca interne
* eVar 3: Codici di tracciamento delle campagne interne
* eVar 4: Categorie di merchandising/Sfoglia
* eVar 5: Collegamenti cross-selling

Possiamo utilizzare un eVar aggiuntivo per misurare le prestazioni di tutti i metodi di ricerca dei prodotti in relazione tra loro. Oltre ai metodi di ricerca sopra descritti, l’eVar includerà altri metodi di ricerca, come i collegamenti alle pagine di dettaglio dei prodotti da siti web esterni, nel suo confronto.

* eVar 1: Metodi di ricerca dei prodotti

Non devi configurare nessuna di queste variabili come eVar standard, ma piuttosto configurarle come eVar per merchandising.  L’utilizzo delle eVar per merchandising consente di allocare qualsiasi attività di successo ai valori acquisiti dalle eVar a un livello *per prodotto* invece di un livello *per visita/per ordine*. Chiarirò la differenza tra la distribuzione per prodotto e per ordine nel resto del documento.

Per dimostrare come impostare queste variabili, inizierò con un esempio in cui un visitatore decide che utilizzerà i &quot;sandali&quot; di ricerca per parola chiave interna per trovare un prodotto sul sito.  Nella pagina dei risultati della ricerca per parola chiave, devi acquisire dati in almeno due eVar:

* `eVar2` sarà uguale alla parola chiave utilizzata nella ricerca (&quot;sandali&quot;)
* `eVar1` sarà uguale al metodo di ricerca del prodotto utilizzato (&quot;ricerca di parole chiave interna&quot;).

Quando imposti queste due variabili uguali a questi valori specifici, sai che il visitatore sta utilizzando il termine di ricerca per parola chiave interno di &quot;sandali&quot; per trovare un prodotto.
Allo stesso tempo, sai che il visitatore non utilizza gli altri metodi di ricerca dei prodotti per trovare prodotti (ad esempio, il visitatore non sta navigando tra le categorie di prodotti nello stesso momento in cui esegue una ricerca per parola chiave). Per garantire una corretta allocazione per prodotto, questi metodi non utilizzati non devono essere considerati idonei per la ricerca di un prodotto trovato tramite una ricerca di parole chiave interna.  Quindi, devi inserire la logica nel codice (ad esempio AppMeasurement, AEP Web SDK, ecc.) che imposterà automaticamente le eVar associate a questi altri metodi di ricerca uguali al valore &quot;metodo di non ricerca&quot;.

Ad esempio, quando un utente cerca prodotti utilizzando la parola chiave &quot;sandali&quot;, la logica del codice Analytics deve impostare le variabili uguali alle seguenti nella pagina dei risultati interni della ricerca per parola chiave:

* eVar2=&quot;sandali&quot;: la parola chiave &quot;sandali&quot; è stata utilizzata nella ricerca interna di parole chiave
* eVar1=&quot;ricerca di parole chiave interna&quot;: è stato utilizzato il metodo di ricerca &quot;internal keyword search&quot;
* eVar3=&quot;campagna non interna&quot;: non è stata utilizzata una campagna interna per accedere alla pagina dei risultati della ricerca
* eVar4=&quot;non-browse&quot;: non è stato possibile accedere a una categoria Sfoglia nella pagina dei risultati della ricerca
* eVar5=&quot;non-cross-selling&quot;: non è stato fatto clic su un collegamento di cross-selling nella pagina dei risultati della ricerca

