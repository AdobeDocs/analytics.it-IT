---
description: Il Generatore di segmenti consente di confrontare e vincolare i valori utilizzando gli operatori selezionati.
title: Operatori di confronto per i segmenti
feature: Segmentazione
uuid: 02ad814c-2c7c-4833-9bb2-4113dcf9475d
exl-id: 1ec1ff05-03a9-4151-8fcb-a72ebbce87dd
translation-type: tm+mt
source-git-commit: af3e4fc64085e94ec5616b8b6851a823e4954b36
workflow-type: tm+mt
source-wordcount: '1041'
ht-degree: 99%

---

# Operatori di confronto per i segmenti

Il Generatore di segmenti consente di confrontare e vincolare i valori utilizzando gli operatori selezionati. Esistono tre categorie di operatori: Standard, Data Warehouse e Conteggio valori univoci.

L’unico carattere jolly supportato è l’asterisco: *. Se desideri cercare *, puoi utilizzare la barra rovesciata come carattere di escape.

**Esempio**: supponiamo che tu abbia un nome pagina “My cool product”. La regola del segmento “Il nome pagina corrisponde a My*product” corrisponderà al nome pagina indicato sopra. Tuttavia, la regola “Il nome pagina corrisponde a My\\*product” corrisponde solo al nome pagina “My*Product”.

## Operatori standard

| Operatore | L’evento di dimensione, segmento o metrica selezionato... |
|--- |--- |
| è uguale a | Restituisce elementi che corrispondono esattamente a un valore numerico o stringa. Nota: se utilizzi caratteri jolly, usa l’operatore “corrisponde a”. |
| non è uguale a | Restituisce tutti gli elementi che non contengono la corrispondenza esatta del valore inserito.  Nota: se utilizzi caratteri jolly, usa l’operatore “non corrisponde a”. |
| è uguale a uno qualsiasi di | Restituisce elementi che corrispondono esattamente a qualsiasi valore nel campo di input (fino a 500 elementi). Ad esempio, l’inserimento di “Risultati ricerca, Home page” con questo operatore corrisponde a “Risultati ricerca” e “Home page”, che verranno conteggiati come 2 elementi. Il campo di input per questo operatore è delimitato da virgole. |
| non è uguale a nessuno di | Identifica gli elementi che corrispondono esattamente a qualsiasi valore nel campo di input (fino a 500 elementi) e restituisce solo gli elementi senza questi valori. Ad esempio, l’inserimento di “Risultati ricerca, Home page” con questo operatore identifica “Risultati ricerca” e “Home page” e li esclude dagli elementi restituiti. In questo esempio vengono conteggiati 2 elementi. Il campo di input per questo operatore è delimitato da virgole. |
| contiene | Restituisce elementi paragonabili alle sottostringhe dei valori inseriti. Ad esempio, se la regola per “Pagina” contiene “Cerca”, corrisponderà a qualsiasi pagina contenente la sottostringa “Cerca”, incluse “Risultati ricerca”, “Cerca” e “Ricerca in corso”. |
| non contiene | Restituisce l’inverso della regola “contiene”. Nello specifico, tutti gli elementi che corrispondono al valore inserito verranno esclusi dai valori inseriti. Ad esempio, se la regola per “Pagina” non contiene “Cerca”, non corrisponderà a nessuna pagina contenente la sottostringa “Cerca”, incluse “Risultati ricerca”, “Cerca” e “Ricerca in corso”. Questi valori verranno esclusi dai risultati. |
| contiene tutti | Restituisce gli elementi confrontati con le sottostringhe, compresi più valori uniti tra loro. Ad esempio, l’inserimento di “Risultati ricerca” con questo operatore corrisponderebbe a “Risultati ricerca” e “Risultati della ricerca”, ma non a “Ricerca” o “Risultati” in modo indipendente. Corrisponderebbe a Ricerca E Risultati trovati insieme. Il campo di input per questo operatore è delimitato da spazi (100 parole). |
| non contiene tutti | Identifica gli elementi confrontati con le sottostringhe, inclusi più valori uniti tra loro, e restituisce solo gli elementi senza questi valori. Ad esempio, l’inserimento di “Risultati ricerca” con questo operatore identificherebbe “Risultati ricerca” e “Risultati della ricerca” (ma non “Ricerca” o “Risultati” in modo indipendente) ed escluderebbe questi elementi. Il campo di input per questo operatore è delimitato da spazi (100 parole). |
| contiene alcuni | Restituisce gli elementi confrontati con le sottostringhe, compresi più valori uniti o identificati in modo indipendente. Ad esempio, l’inserimento di “Risultati ricerca” con questo operatore corrisponderebbe a “Risultati ricerca”, “Risultati della ricerca”, “Ricerca” e “Risultati”. Corrisponderebbe a “Ricerca” O “Risultati” trovati insieme o in modo indipendente. Il campo di input per questo operatore è delimitato da spazi (100 parole). |
| non contiene nessuno | Identifica gli elementi in base alle sottostringhe e restituisce valori che non contengono tali sottostringhe. Può avere più valori uniti o valori identificati in modo indipendente. Ad esempio, l’inserimento di “Risultati ricerca” corrisponderebbe a “Risultati ricerca”, “Risultati della ricerca”, “Ricerca” e “Risultati” dove “Ricerca” o “Risultati” si trovano insieme o in modo indipendente. Gli elementi che contengono tali sottostringhe vengono poi esclusi. Il campo di input per questo operatore è delimitato da spazi (100 parole). |
| inizia con | Restituisce elementi che iniziano con il carattere o le stringhe del valore inserito. |
| non inizia con | Restituisce tutti gli elementi che non iniziano con i caratteri o le stringhe dei valori inseriti. Si tratta dell’inverso dell’operatore “inizia con”. |
| termina con | Restituisce elementi che terminano con il carattere o le stringhe del valore inserito. |
| non termina con | Restituisce tutti gli elementi che non terminano con i caratteri o le stringhe del valore inserito. Si tratta dell’inverso dell’operatore “termina con”. |
| corrisponde | Restituisce elementi che contengono una corrispondenza esatta in base a un dato valore numerico o stringa. Nota: utilizza questo operatore per le funzioni dei caratteri jolly (globbing). |
| non corrisponde | Restituisce tutti gli elementi che non contengono la corrispondenza esatta del valore inserito. Nota: utilizza questo operatore per le funzioni dei caratteri jolly (globbing). |
| esiste | Restituisce il numero di elementi esistenti. Ad esempio, se valuti la dimensione Pagine non trovate utilizzando l’operatore “esiste”, viene restituito il numero di pagine di errore esistenti. |
| non esiste | Restituisce tutti gli elementi che non esistono. Ad esempio, se valuti la dimensione Pagine non trovate utilizzando l’operatore “non esiste”, viene restituito il numero di pagine in cui non esisteva questa pagina di errore. |

## Date Warehouse

| Operatore | L’evento di dimensione, segmento o metrica selezionato... |
| --- | --- |
| è minore di | Restituisce elementi il cui conteggio numerico è inferiore al valore inserito. |
| è minore o uguale a | Restituisce elementi il cui conteggio numerico è minore o uguale al valore inserito. |
| è maggiore di | Restituisce elementi il cui conteggio numerico è maggiore del valore inserito. |
| è maggiore o uguale a | Restituisce elementi il cui conteggio numerico è maggiore di o uguale al valore inserito. |

## Operatori di conteggio distinti

Puoi creare segmenti in base a un numero specifico di elementi all’interno di una dimensione. Esempio: “Visitatori che hanno visualizzato più di 5 prodotti distinti” o “Visite in cui sono state visualizzate più di 5 pagine distinte”.

| Operatore | L’evento di dimensione, segmento o metrica selezionato... |
| --- | --- |
| è uguale a | Restituisce elementi dimensionali il cui conteggio univoco è uguale al valore inserito. |
| non è uguale a | Restituisce elementi dimensionali il cui conteggio univoco non è uguale al valore inserito. |
| è maggiore di | Restituisce elementi dimensionali il cui conteggio univoco è maggiore del valore inserito. |
| è minore di | Restituisce elementi dimensionali il cui conteggio univoco è inferiore al valore inserito. |
| è maggiore o uguale a | Restituisce elementi dimensionali il cui conteggio univoco è maggiore o uguale al valore inserito. |
| è minore o uguale a | Restituisce elementi dimensionali il cui conteggio univoco è minore o uguale al valore inserito. |
