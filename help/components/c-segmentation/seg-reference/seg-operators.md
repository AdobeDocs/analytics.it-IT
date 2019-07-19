---
description: Il Generatore di segmenti consente di confrontare e bloccare i valori utilizzando operatori selezionati.
seo-description: Il Generatore di segmenti consente di confrontare e bloccare i valori utilizzando operatori selezionati.
seo-title: Operatori di confronto per segmenti
solution: Analytics
title: Operatori di confronto per segmenti
topic: Segmenti
uuid: 02 ad 814 c -2 c 7 c -4833-9 bb 2-4113 dcf 9475 d
translation-type: tm+mt
source-git-commit: c36bc5a74e89fda3e23113851f850fd6c98b8c40

---


# Operatori di confronto per segmenti

Il Generatore di segmenti consente di confrontare e bloccare i valori utilizzando operatori selezionati.

Esistono tre categorie di operatori: Standard, Data Warehouse e Count Count.

L'unico carattere jolly supportato è l'asterisco: *. Se hai bisogno di cercare *, puoi uscirne con una barra rovesciata.

**Esempio**: Supponiamo di avere un nome di pagina denominato «my cool product». La regola del segmento "Nome pagina corrisponde my * product" corrisponderà al nome della pagina precedente. Tuttavia, la regola "Nome pagina corrisponde al nome My\\ *" corrisponde solo al nome della pagina "My * Product".

| Operatore | L'evento dimensione, segmento o metrica selezionato… |
|--- |--- |
| **Standard** |  |
| è uguale a | Restituisce elementi che corrispondono esattamente a un valore numerico o stringa. Nota: Se utilizzate caratteri jolly, utilizzate l'operatore "matches". |
| è diverso da | Restituisce tutti gli elementi che non contengono la corrispondenza esatta del valore immesso. Nota: Se utilizzate caratteri jolly, utilizzate l'operatore "non corrisponde". |
| è uguale a uno qualsiasi di | Restituisce elementi che corrispondono esattamente a qualsiasi valore nel campo di input (fino a 500 elementi). Ad esempio, l'immissione di "Risultati di ricerca, Pagina principale" con questo operatore corrisponde a "Risultati ricerca" e "Pagina iniziale" e conta su 2 elementi. Il campo di input per questo operatore è delimitato da virgole. |
| è diverso da uno qualsiasi di | Identifica gli elementi che corrispondono esattamente a qualsiasi valore nel campo di input (fino a 500 elementi), quindi restituisce solo gli elementi senza tali valori. Ad esempio, immettendo «Risultati di ricerca, Pagina principale» con questo operatore identificare «Risultati della ricerca» e «Pagina iniziale», quindi escluderli dagli elementi restituiti. Questo esempio viene conteggiato come 2 elementi. Il campo di input per questo operatore è delimitato da virgole. |
| contiene | Restituisce gli elementi che confrontano con le sottostringhe dei valori immessi. Ad esempio, se la regola "Pagina" contiene "Cerca", corrisponde a qualsiasi pagina con la sottostringa "Cerca", compresi i "Risultati della ricerca", "Ricerca" e "Ricerca". |
| non contiene | Restituisce l'inverso della regola «contiene». In modo specifico, tutti gli elementi che corrispondono al valore immesso saranno esclusi dai valori immessi. Ad esempio, se la regola per «Pagina» non contiene «Cerca», non corrisponderà a nessuna pagina con la sottostringa «Cerca», inclusi «Risultati ricerca», «Ricerca» e «Ricerca». Tali valori saranno esclusi dai risultati. |
| contiene tutto | Restituisce elementi confrontati con le sottostringhe, compresi più valori uniti insieme. Ad esempio, l'immissione di «Risultati della ricerca» con questo operatore corrisponde ai «Risultati della ricerca» e ai «Risultati della ricerca», ma non alla casella di ricerca «Cerca» o «Risultati». Corrisponde alla ricerca e ai risultati trovati insieme. Il campo di input per questo operatore è delimitato da spazio (100 parole). |
| non contiene tutto | Identifica gli elementi confrontati con le sottostringhe, compresi più valori uniti insieme, e quindi restituisce solo gli elementi privi di tali valori. Ad esempio, l'immissione di "Risultati della ricerca" con questo operatore identifica i "Risultati della ricerca" e i "Risultati della ricerca" (ma non la ricerca o i risultati in modo indipendente) e quindi escludono questi elementi. Il campo di input per questo operatore è delimitato da spazio (100 parole). |
| contiene qualsiasi | Restituisce elementi confrontati alle sottostringhe, compresi più valori uniti o identificati in modo indipendente. Ad esempio, l'immissione di "Risultati ricerca" con questo operatore corrisponde a "Risultati ricerca", "Risultati della ricerca", "Ricerca" e "Risultati". Corrisponde ai risultati "Cerca" o "Risultati" trovati insieme o in modo indipendente. Il campo di input per questo operatore è delimitato da spazio (100 parole). |
| non contiene alcun | Identifica gli elementi basati su stringhe e quindi restituisce valori che non contengono queste sottostringhe. Può avere più valori o valori uniti in modo indipendente. Ad esempio, immettendo «Risultati ricerca» corrisponderebbero ai «Risultati della ricerca», «Risultati della ricerca», «Cerca» e «Risultati» dove «Cerca» o «Risultati» vengono trovati o in modo indipendente. Quindi, escluderà gli elementi che contengono queste sottostringhe. Il campo di input per questo operatore è delimitato da spazio (100 parole). |
| inizia con | Restituisce gli elementi che iniziano con il carattere o le stringhe del valore immesso. |
| non inizia con | Restituisce tutti gli elementi che non iniziano con i caratteri o le stringhe dei valori immessi. Questo è l'inverso dell'operatore "inizia con". |
| termina con | Restituisce gli elementi che terminano con il carattere o le stringhe del valore immesso. |
| non termina con | Restituisce tutti gli elementi che non si terminano con i caratteri o le stringhe del valore immesso. Questo è l'inverso dell'operatore "termina con". |
| matches | Restituisce elementi che corrispondono esattamente in base a un valore numerico o stringa specificato. Nota: Utilizzate questo operatore quando utilizzate le funzioni jolly (glogging). |
| non corrisponde | Restituisce tutti gli elementi che non contengono la corrispondenza esatta del valore immesso. Nota: Utilizzate questo operatore quando utilizzate le funzioni jolly (glogging). |
| exists | Restituisce il numero di elementi esistenti. Ad esempio, se valutate la dimensione Pagine non trovata utilizzando l'operatore "esiste", viene restituito il numero di pagine di errore esistenti. |
| non esiste | Restituisce tutti gli elementi che non esistono. Ad esempio, se si valuta la dimensione Pagine non trovata utilizzando l'operatore "Non esiste", viene restituito il numero di pagine in cui la pagina di errore non esiste. |
| **Data Warehouse** |  |
| è minore di | Restituisce elementi il cui conteggio numerico è inferiore al valore immesso. |
| è minore o uguale a | Restituisce elementi il cui conteggio numerico è minore o uguale al valore immesso. |
| è maggiore di | Restituisce elementi il cui conteggio numerico è maggiore del valore immesso. |
| è maggiore o uguale a | Restituisce elementi il cui conteggio numerico è maggiore o uguale al valore immesso. |
| **Conteggio distinto** | Puoi segmentare un numero distinto di elementi all'interno di una dimensione. Esempio: “Visitatori che hanno visualizzato più di 5 prodotti distinti” o “Visite in cui sono state visualizzate più di 5 pagine distinte”. |
| è uguale a | Restituisce elementi dimensionali il cui conteggio univoco corrisponde al valore immesso. |
| è diverso da | Restituisce elementi dimensionali il cui conteggio univoco non equivale al valore immesso. |
| è maggiore di | Restituisce elementi dimensionali il cui conteggio univoco è maggiore del valore immesso. |
| è minore di | Restituisce elementi dimensionali il cui conteggio univoco è inferiore al valore immesso. |
| è maggiore o uguale a | Restituisce elementi dimensionali il cui conteggio univoco è maggiore o uguale al valore immesso. |
| è minore o uguale a | Restituisce elementi dimensionali il cui conteggio univoco è minore o uguale al valore immesso. |

