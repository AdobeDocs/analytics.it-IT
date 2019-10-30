---
description: Il Generatore di segmenti consente di confrontare e vincolare i valori utilizzando gli operatori selezionati.
seo-description: Il Generatore di segmenti consente di confrontare e vincolare i valori utilizzando gli operatori selezionati.
seo-title: Operatori di confronto per i segmenti
solution: Analytics
title: Operatori di confronto per i segmenti
topic: Segmenti
uuid: 02ad814c-2c7c-4833-9bb2-4113dcf9475d
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Operatori di confronto per i segmenti

Il Generatore di segmenti consente di confrontare e vincolare i valori utilizzando gli operatori selezionati.

Esistono tre categorie di operatori: Standard, Data Warehouse e Conteggio distinto.

L'unico carattere jolly supportato è l'asterisco: *. Se è necessario cercare *, è possibile fuggire con una barra rovesciata.

**Esempio**: Supponete di avere un nome di pagina chiamato "My cool product". La regola del segmento "Il nome della pagina corrisponde a My*product" corrisponderà al nome della pagina indicato sopra. Tuttavia, la regola "Il nome della pagina corrisponde a My\\*product" corrisponde solo al nome della pagina "My*Product".

| Operatore | L’evento di dimensione, segmento o metrica selezionato... |
|--- |--- |
| **Standard** |  |
| è uguale a | Restituisce elementi che corrispondono esattamente a un valore numerico o a una stringa. Nota:  Se utilizzate caratteri jolly, utilizzate l'operatore "matches". |
| è diverso da | Restituisce tutti gli elementi che non contengono la corrispondenza esatta del valore immesso.  Nota:  Se si utilizzano caratteri jolly, utilizzare l'operatore "non corrisponde". |
| è uguale a uno qualsiasi di | Restituisce elementi che corrispondono esattamente a qualsiasi valore nel campo di input (fino a 500 elementi). Ad esempio, se immettete "Risultati ricerca, Homepage" con questo operatore, i risultati della ricerca corrisponderanno a "Risultati ricerca" e "Homepage" e verranno conteggiati come 2 elementi. Il campo di input per questo operatore è delimitato da virgole. |
| è diverso da uno qualsiasi di | Identifica gli elementi che corrispondono esattamente a qualsiasi valore nel campo di input (fino a 500 elementi), quindi restituisce solo gli elementi senza questi valori. Ad esempio, immettendo "Risultati ricerca, Homepage" con questo operatore si identificano "Risultati ricerca" e "Homepage", quindi si escludono dagli elementi restituiti. Questo esempio viene conteggiato come 2 elementi. Il campo di input per questo operatore è delimitato da virgole. |
| contiene | Restituisce elementi che si confrontano con le sottostringhe dei valori immessi. Ad esempio, se la regola per "Pagina" contiene "Cerca", corrisponderà a qualsiasi pagina contenente la sottostringa "Cerca", inclusi "Risultati ricerca", "Ricerca" e "Ricerca". |
| non contiene | Restituisce l'inverso della regola "contains". Nello specifico, tutti gli elementi che corrispondono al valore immesso verranno esclusi dai valori inseriti. Ad esempio, se la regola per "Pagina" non contiene "Cerca", non corrisponderà ad alcuna pagina contenente la sottostringa "Cerca", inclusi "Risultati ricerca", "Ricerca" e "Ricerca". Questi valori verranno esclusi dai risultati. |
| contiene tutti i | Restituisce gli elementi confrontati con le sottostringhe, compresi più valori uniti tra loro. Ad esempio, l'immissione di "Risultati ricerca" con questo operatore corrisponderebbe a "Risultati ricerca" e "Risultati ricerca", ma non a "Ricerca" o "Risultati" in modo indipendente. Corrisponderebbe ai risultati di ricerca e ricerca trovati insieme. Il campo di input per questo operatore è delimitato da uno spazio (100 parole). |
| non contiene tutti i | Identifica gli elementi confrontati con le sottostringhe, inclusi più valori uniti, e restituisce solo gli elementi senza questi valori. Ad esempio, l'immissione di "Risultati ricerca" con questo operatore identificherebbe "Risultati ricerca" e "Risultati ricerca" (ma non "Ricerca" o "Risultati" in modo indipendente) ed escluderebbe quindi tali elementi. Il campo di input per questo operatore è delimitato da uno spazio (100 parole). |
| contiene | Restituisce gli elementi confrontati con le sottostringhe, compresi più valori uniti o identificati in modo indipendente. Ad esempio, l'immissione di "Risultati ricerca" con questo operatore corrisponde a "Risultati ricerca", "Risultati ricerca", "Ricerca" e "Risultati". Corrisponde a "Search" (Ricerca) O "Results" (Risultati) trovati insieme o in modo indipendente. Il campo di input per questo operatore è delimitato da uno spazio (100 parole). |
| non contiene | Identifica gli elementi in base alle sottostringhe e restituisce valori che non contengono tali sottostringhe. Può avere più valori o valori uniti identificati in modo indipendente. Ad esempio, l'immissione di "Risultati ricerca" corrisponderebbe a "Risultati ricerca", "Risultati ricerca", "Ricerca" e "Risultati" in cui "Ricerca" o "Risultati" vengono trovati insieme o in modo indipendente. Vengono quindi esclusi gli elementi che contengono tali sottostringhe. Il campo di input per questo operatore è delimitato da uno spazio (100 parole). |
| inizia con | Restituisce elementi che iniziano con il carattere o le stringhe del valore immesso. |
| non inizia con | Restituisce tutti gli elementi che non iniziano con i caratteri o le stringhe dei valori immessi. Questo è l'inverso dell'operatore "inizia con". |
| termina con | Restituisce gli elementi che terminano con il carattere o le stringhe del valore immesso. |
| non termina con | Restituisce tutti gli elementi che non terminano con i caratteri o le stringhe del valore immesso. Questo è l'inverso dell'operatore "ends with". |
| matches | Restituisce elementi che corrispondono esattamente in base a un valore numerico o a una stringa specificato. Nota:  Utilizzare questo operatore quando si utilizzano le funzioni carattere jolly (globbing). |
| non corrisponde | Restituisce tutti gli elementi che non contengono la corrispondenza esatta del valore immesso. Nota:  Utilizzare questo operatore quando si utilizzano le funzioni carattere jolly (globbing). |
| exists | Restituisce il numero di elementi esistenti. Ad esempio, se si valuta la dimensione Pagine non trovate utilizzando l'operatore "esiste", viene restituito il numero di pagine di errore esistenti. |
| non esiste | Restituisce tutti gli elementi che non esistono. Ad esempio, se si valuta la dimensione Pagine non trovate utilizzando l'operatore " non esiste", viene restituito il numero di pagine in cui non esiste questa pagina di errore. |
| **Data Warehouse** |  |
| è minore di | Restituisce elementi il cui conteggio numerico è inferiore al valore immesso. |
| è minore o uguale a | Restituisce elementi il cui conteggio numerico è minore o uguale al valore immesso. |
| è maggiore di | Restituisce elementi il cui conteggio numerico è maggiore del valore immesso. |
| è maggiore o uguale a | Restituisce elementi il cui conteggio numerico è maggiore o uguale al valore immesso. |
| **Conteggio distinto** | Potete segmentare su un numero distinto di elementi all'interno di una dimensione. Esempio: “Visitatori che hanno visualizzato più di 5 prodotti distinti” o “Visite in cui sono state visualizzate più di 5 pagine distinte”. |
| è uguale a | Restituisce elementi dimensione il cui conteggio univoco è uguale al valore immesso. |
| è diverso da | Restituisce elementi dimensione il cui conteggio univoco non è uguale al valore immesso. |
| è maggiore di | Restituisce elementi dimensione il cui conteggio univoco è maggiore del valore immesso. |
| è minore di | Restituisce elementi dimensione il cui conteggio univoco è inferiore al valore immesso. |
| è maggiore o uguale a | Restituisce elementi dimensione il cui conteggio univoco è maggiore o uguale al valore immesso. |
| è minore o uguale a | Restituisce elementi dimensione il cui conteggio univoco è minore o uguale al valore immesso. |

