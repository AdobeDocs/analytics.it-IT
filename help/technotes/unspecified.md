---
description: Diversi rapporti in Adobe Analytics possono essere indicati da Non specificato, Altro o Sconosciuto, a seconda del rapporto specifico visualizzato. In genere, questo elemento di riga significa che la variabile non è stata definita o in altro modo non disponibile.
seo-description: Diversi rapporti in Adobe Analytics possono essere indicati da Non specificato, Altro o Sconosciuto, a seconda del rapporto specifico visualizzato. In genere, questo elemento di riga significa che la variabile non è stata definita o in altro modo non disponibile.
seo-title: Non specificato, Altro ed Sconosciuto nei rapporti
solution: Analytics
title: Non specificato, Altro ed Sconosciuto nei rapporti
translation-type: tm+mt
source-git-commit: 9170eaee2b816280e48901100ac7aaf3b56ec8c5

---


# “Unspecified” (Non specificato), “Other” (Altro) e “Unknown” (Sconosciuto) nei rapporti

Vari rapporti in Adobe Analytics possono essere indicati da “Unspecified”, “Other” e “Unknown”, a seconda del report specifico visualizzato. In genere, questo elemento di riga significa che la variabile non è stata definita o in altro modo non disponibile. Di seguito viene fornito un elenco completo di come ogni rapporto può avere uno di questi elementi.

## “Unspecified” nel reporting

“Unspecified” è un elemento di riga piuttosto comune nei report.

* **Un evento viene attivato senza una variabile di conversione:** Ad esempio, un utente accede al sito ed effettua un acquisto senza alcun valore evar 1. Se visualizzi ordini con la dimensione evar 1, non esiste alcun valore a cui attribuire l'ordine. Pertanto, viene automaticamente attribuito a “Unspecified”.
* **Dati non classificati nei rapporti classificazione:** Quando si visualizzano i dati di classificazione, qualsiasi valore associato a quella particolare classificazione restituisce “Unspecified”. Per risolvere questo problema, classificare il valore della variabile principale.
* **Rapporti di suddivisione in cui è stata attivata una sola variabile:** Quando applicate una suddivisione a una variabile, ogni istanza di tale variabile deve essere conteggiata. Se la seconda variabile non è stata visualizzata o se è persistente da un hit precedente, il valore della dimensione è "Unspecified".
* **Hit non mobili nei rapporti mobili:** Tutti gli hit non mobili nei rapporti mobili sono elencati come "Non specificato" (“Non mobile” in Reports and Analytics).

## “Other” nel reporting

Anche se leggermente raro nel rapporto, in diverse circostanze possono verificarsi “Other”:

* **Le pagine vengono attivate al di fuori dei filtri URL interni:** Questo valore è utile per proteggere contro la frode dati, ad esempio se un'altra organizzazione gestisce il codice sorgente e la implementa sul suo sito. Per correggere questo problema, assicurati che tutti gli URL in cui il codice è implementato corrispondano ai filtri URL interni nelle impostazioni della suite di rapporti.
* **Visitatori che utilizzano un browser in modo frequente:** Nel rapporto Tipi browser, l'opzione “Other” viene visualizzata come suddivisione se i visitatori utilizzano un browser che non è un tipo di browser molto diffuso. Ci sono molte organizzazioni che producono browser. Tutti i browser che più grandi non hanno creato vengono ridotti in “Other” per evitare confusione.

## “Unknown” nel reporting

L'opzione “Unknown” può verificarsi in diverse circostanze:

* **Hit non del browser durante la visualizzazione dei rapporti Tecnologia:** Se una libreria appmeasurement non è in grado di determinare se una funzione è supportata, nei rapporti viene visualizzato “Unknown”.
* **Uso dei segmenti in cui i componenti non sono accessibili:** Assicuratevi che le variabili utilizzate in un segmento siano abilitate e che gli utenti possano accedervi. Se un utente non ha accesso a un componente segmento o se una variabile è disabilitata, viene visualizzato “Unknown”.

## Filtrare questi valori nel rapporto {#section_5536E2B419D445D39C932E8F12C0070C}

Nella maggior parte dei casi, è sicuro ignorare questi elementi. Il filtro di ricerca può essere usato per rimuoverli, se necessario.

Alcune variabili di dati di back-end utilizzano il valore `::unspecified::` nei report, ma non nell'interfaccia. Se un filtro di ricerca non esclude i dati, provate a usare questo valore (compresi i due punti).
