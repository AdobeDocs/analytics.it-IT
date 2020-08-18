---
description: Il Generatore di segmenti consente di confrontare e vincolare i valori utilizzando gli operatori selezionati.
title: Operatori di confronto per i segmenti
topic: Segments
uuid: 02ad814c-2c7c-4833-9bb2-4113dcf9475d
translation-type: tm+mt
source-git-commit: e758c070f402113b6d8a9069437b53633974a3e9
workflow-type: tm+mt
source-wordcount: '1021'
ht-degree: 16%

---


# Operatori di confronto per i segmenti

Il Generatore di segmenti consente di confrontare e vincolare i valori utilizzando gli operatori selezionati.

Esistono tre categorie di operatori: Standard, Data Warehouse e conteggio distinto.

L&#39;unico carattere jolly supportato è l&#39;asterisco: *. Se è necessario cercare *, è possibile fuggire con una barra rovesciata.

**Esempio**: Supponiamo che tu abbia un nome di pagina chiamato &quot;My cool product&quot;. La regola del segmento &quot;Il nome della pagina corrisponde a My*product&quot; corrisponderà al nome della pagina indicato sopra. Tuttavia, la regola &quot;Il nome della pagina corrisponde a My\\*product&quot; corrisponde solo al nome della pagina &quot;My*Product&quot;.

| Operatore | L’evento di dimensione, segmento o metrica selezionato... |
|--- |--- |
| **Standard** |  |
| è uguale a | Restituisce elementi che corrispondono esattamente a un valore numerico o stringa. Nota:  Se si utilizzano caratteri jolly, utilizzare l&#39;operatore &quot;matches&quot;. |
| è diverso da | Restituisce tutti gli elementi che non contengono la corrispondenza esatta del valore immesso.  Nota:  Se si utilizzano caratteri jolly, utilizzare l&#39;operatore &quot;non corrisponde&quot;. |
| è uguale a uno qualsiasi di | Restituisce elementi che corrispondono esattamente a qualsiasi valore nel campo di input (fino a 500 elementi). Ad esempio, se immettete &quot;Risultati ricerca, Homepage&quot; con questo operatore, i risultati della ricerca corrisponderanno a &quot;Risultati ricerca&quot; e &quot;Homepage&quot; e verranno conteggiati come 2 elementi. Il campo di input per questo operatore è delimitato da virgole. |
| è diverso da uno qualsiasi di | Identifica gli elementi che corrispondono esattamente a qualsiasi valore nel campo di input (fino a 500 elementi), quindi restituisce solo gli elementi senza questi valori. Ad esempio, immettendo &quot;Risultati ricerca, Homepage&quot; con questo operatore si identificano &quot;Risultati ricerca&quot; e &quot;Homepage&quot;, quindi si escludono dagli elementi restituiti. Questo esempio viene conteggiato come 2 elementi. Il campo di input per questo operatore è delimitato da virgole. |
| contiene | Restituisce elementi che si confrontano con le sottostringhe dei valori immessi. Ad esempio, se la regola per &quot;Pagina&quot; contiene &quot;Cerca&quot;, corrisponderà a qualsiasi pagina contenente la sottostringa &quot;Cerca&quot;, inclusi &quot;Risultati ricerca&quot;, &quot;Ricerca&quot; e &quot;Ricerca&quot;. |
| non contiene | Restituisce l&#39;inverso della regola &quot;contains&quot;. Nello specifico, tutti gli elementi che corrispondono al valore immesso verranno esclusi dai valori inseriti. Ad esempio, se la regola per &quot;Pagina&quot; non contiene &quot;Cerca&quot;, non corrisponderà ad alcuna pagina contenente la sottostringa &quot;Cerca&quot;, inclusi &quot;Risultati ricerca&quot;, &quot;Ricerca&quot; e &quot;Ricerca&quot;. Questi valori verranno esclusi dai risultati. |
| contiene tutti i | Restituisce gli elementi confrontati con le sottostringhe, compresi più valori uniti tra loro. Ad esempio, l&#39;immissione di &quot;Risultati ricerca&quot; con questo operatore corrisponderebbe a &quot;Risultati ricerca&quot; e &quot;Risultati ricerca&quot;, ma non a &quot;Ricerca&quot; o &quot;Risultati&quot; in modo indipendente. Corrisponderebbe ai risultati di ricerca e ricerca trovati insieme. Il campo di input per questo operatore è delimitato da uno spazio (100 parole). |
| non contiene tutti i | Identifica gli elementi confrontati con le sottostringhe, inclusi più valori uniti tra loro, e restituisce solo gli elementi senza questi valori. Ad esempio, l&#39;immissione di &quot;Risultati ricerca&quot; con questo operatore identificherebbe &quot;Risultati ricerca&quot; e &quot;Risultati ricerca&quot; (ma non &quot;Ricerca&quot; o &quot;Risultati&quot; in modo indipendente) ed escluderebbe quindi tali elementi. Il campo di input per questo operatore è delimitato da uno spazio (100 parole). |
| contiene | Restituisce gli elementi confrontati con le sottostringhe, compresi più valori uniti o identificati in modo indipendente. Ad esempio, l&#39;immissione di &quot;Risultati ricerca&quot; con questo operatore corrisponderebbe a &quot;Risultati ricerca&quot;, &quot;Risultati ricerca&quot;, &quot;Ricerca&quot; e &quot;Risultati&quot;. Corrisponde a &quot;Search&quot; (Ricerca) O &quot;Results&quot; (Risultati) trovati insieme o in modo indipendente. Il campo di input per questo operatore è delimitato da uno spazio (100 parole). |
| non contiene | Identifica gli elementi in base alle sottostringhe e restituisce valori che non contengono tali sottostringhe. Può avere più valori o valori uniti identificati in modo indipendente. Ad esempio, l&#39;immissione di &quot;Risultati ricerca&quot; corrisponderebbe a &quot;Risultati ricerca&quot;, &quot;Risultati ricerca&quot;, &quot;Ricerca&quot; e &quot;Risultati&quot; in cui &quot;Ricerca&quot; o &quot;Risultati&quot; vengono trovati insieme o in modo indipendente. Vengono quindi esclusi gli elementi che contengono tali sottostringhe. Il campo di input per questo operatore è delimitato da uno spazio (100 parole). |
| inizia con | Restituisce elementi che iniziano con il carattere o le stringhe del valore immesso. |
| non inizia con | Restituisce tutti gli elementi che non iniziano con i caratteri o le stringhe dei valori immessi. Questo è l&#39;inverso dell&#39;operatore &quot;inizia con&quot;. |
| termina con | Restituisce gli elementi che terminano con il carattere o le stringhe del valore immesso. |
| non termina con | Restituisce tutti gli elementi che non terminano con i caratteri o le stringhe del valore immesso. Questo è l&#39;inverso dell&#39;operatore &quot;ends with&quot;. |
| matches | Restituisce elementi che corrispondono esattamente in base a un valore numerico o a una stringa specificato. Nota:  Utilizzare questo operatore quando si utilizzano le funzioni carattere jolly (globbing). |
| non corrisponde | Restituisce tutti gli elementi che non contengono la corrispondenza esatta del valore immesso. Nota:  Utilizzare questo operatore quando si utilizzano le funzioni carattere jolly (globbing). |
| exists | Restituisce il numero di elementi esistenti. Ad esempio, se si valuta la dimensione Pagine non trovate utilizzando l&#39;operatore &quot;esiste&quot;, viene restituito il numero di pagine di errore esistenti. |
| non esiste | Restituisce tutti gli elementi che non esistono. Ad esempio, se si valuta la dimensione Pagine non trovate utilizzando l&#39;operatore &quot; non esiste&quot;, viene restituito il numero di pagine in cui non esisteva questa pagina di errore. |
| **Data Warehouse** |  |
| è minore di | Restituisce elementi il cui conteggio numerico è inferiore al valore immesso. |
| è minore o uguale a | Restituisce elementi il cui conteggio numerico è minore o uguale al valore immesso. |
| è maggiore di | Restituisce elementi il cui conteggio numerico è maggiore del valore immesso. |
| è maggiore o uguale a | Restituisce elementi il cui conteggio numerico è maggiore di o uguale al valore immesso. |
| **Conteggio distinto** | Potete segmentare su un numero distinto di elementi all&#39;interno di una dimensione. Esempio: “Visitatori che hanno visualizzato più di 5 prodotti distinti” o “Visite in cui sono state visualizzate più di 5 pagine distinte”.  |
| è uguale a | Restituisce elementi dimensione il cui conteggio univoco è uguale al valore immesso. |
| è diverso da | Restituisce elementi dimensione il cui conteggio univoco non è uguale al valore immesso. |
| è maggiore di | Restituisce elementi dimensione il cui conteggio univoco è maggiore del valore immesso. |
| è minore di | Restituisce elementi dimensione il cui conteggio univoco è inferiore al valore immesso. |
| è maggiore o uguale a | Restituisce elementi dimensione il cui conteggio univoco è maggiore o uguale al valore immesso. |
| è minore o uguale a | Restituisce elementi dimensione il cui conteggio univoco è minore o uguale al valore immesso. |

