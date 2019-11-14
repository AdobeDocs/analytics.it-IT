---
description: Diversi report in Adobe Analytics possono mostrare Non specificato, Altro o Sconosciuto, a seconda del rapporto specifico visualizzato. In genere, questo elemento di riga indica che la variabile non era definita o altrimenti non disponibile.
solution: Analytics
title: Non specificato, Altro e Sconosciuto nel reporting
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# "Non specificato", "Altro" e "Sconosciuto" nei rapporti

Diversi report in Adobe Analytics possono mostrare "Non specificato", "Altro" o "Sconosciuto", a seconda del rapporto specifico visualizzato. In genere, questo elemento di riga indica che la variabile non era definita o altrimenti non disponibile. Di seguito viene fornito un elenco completo di come ogni rapporto può contenere una di queste voci.

## "Non specificato" nel reporting

"Non specificato" è un elemento di riga piuttosto comune nei report.

* **** Un evento viene attivato senza una variabile di conversione: Ad esempio, un utente accede al sito e effettua un acquisto senza alcun valore eVar1. Se visualizzate gli ordini utilizzando la dimensione eVar1, non è presente alcun valore a cui attribuire l'ordine. Pertanto, viene automaticamente attribuito a "Non specificato".
* **** Dati non classificati nei rapporti sulla classificazione: Quando si visualizzano i dati di classificazione, qualsiasi valore a cui non siano associati dati a quella particolare classificazione restituisce "Non specificato". Per risolvere questo problema, classificare il valore della variabile padre.
* **** Report di suddivisione in cui è stata attivata una sola variabile: Quando si applica una suddivisione a una variabile, ogni istanza di tale variabile deve essere contabilizzata. Se la seconda variabile non è stata visualizzata o se è persistente da un hit precedente, il valore della dimensione è "Non specificato".
* **** hit non mobili nei rapporti sui dispositivi mobili: Gli hit non mobili nei rapporti sui dispositivi mobili sono elencati come "Non specificato" ("Non mobile" in Reporting e analisi).

## "Altro" nella segnalazione

Anche se alquanto raro nel reportage, "Altro" può verificarsi in diverse circostanze:

* **** Le pagine vengono attivate al di fuori dei filtri URL interni: Questo valore è attivo per proteggere contro le frodi ai dati, ad esempio se un'altra organizzazione ruba il codice sorgente e lo implementa sul proprio sito. Per correggere questo problema, accertatevi che tutti gli URL per i quali il codice è implementato corrispondano ai filtri URL interni nelle impostazioni della suite di rapporti.
* **** Visitatori che utilizzano un browser di uso raro: Nel rapporto Tipi browser, se i visitatori utilizzano un browser che non è un tipo di browser popolare, viene visualizzato "Altro" come suddivisione. Ci sono molte organizzazioni che producono browser. Tutti i browser che le organizzazioni più grandi non hanno creato vengono inseriti in "Altro" per evitare confusione nei report.

## "Sconosciuto" nel report

"Unknown" può verificarsi in diverse circostanze:

* **** Non riscontri browser quando si visualizzano i report Tecnologia: Se una libreria AppMeasurement non è in grado di determinare se una funzione è supportata, nei rapporti viene visualizzato "Sconosciuto".
* **** Utilizzo di segmenti in cui i componenti non sono accessibili: Assicurati che le variabili utilizzate in un segmento siano abilitate e che gli utenti possano accedervi. Se un utente non ha accesso a un componente segmento o se una variabile è disabilitata, viene visualizzato "Sconosciuto".

## Filtrare questi valori nei rapporti {#section_5536E2B419D445D39C932E8F12C0070C}

Nella maggior parte dei casi, è sicuro ignorare questi elementi. Il filtro di ricerca può essere usato per rimuoverli, se necessario.

Alcune variabili di dati di back-end utilizzano il valore `::unspecified::` nel reporting, anche se non viene visualizzato nell'interfaccia. Se un filtro di ricerca non riesce ad escludere i dati, provate a utilizzare questo valore (inclusi i due punti).
