---
description: Nelle tabelle riportate di seguito viene visualizzato il rapporto sulla mappatura delle variabili, oppure i rapporti e le variabili in essi utilizzate.
keywords: Analytics Implementation
solution: Analytics
title: Rapporto sulla mappatura variabile
topic: Developer and implementation
uuid: 4707660c-4be5-425c-a690-7bc6df4cc0fa
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Rapporto sulla mappatura variabile

Nelle tabelle riportate di seguito viene visualizzato il rapporto sulla mappatura delle variabili, oppure i rapporti e le variabili in essi utilizzate.

**Report** conversione Nella tabella seguente sono elencate le variabili di conversione utilizzate per compilare ciascun rapporto:

| Acquisti |
|---|
| Conversioni e medie | s.events, s.products, s.purchaseID | Imposta s.events su acquisto, dettaglio prodotto, numero ordine |
| Ricavi | s.events, s.products, s.purchaseID | Imposta s.events su acquisto, dettaglio prodotto, numero ordine |
| Ordini | s.events, s.products, s.purchaseID | Imposta s.events su acquisto, dettaglio prodotto, numero ordine |
| Unità | s.events, s.products, s.purchaseID | Imposta s.events su acquisto, dettaglio prodotto, numero ordine |

| Carrello |
|---|
| Conversioni e medie | s.events, s.products, s.purchaseID |  |
| Carrello | s.events | Imposta s.events su scOpen |
| Visualizzazioni carrello | s.events | Imposta s.events su scView |
| Aggiunte carrello | s.events | Imposta s.events su scAdd |
| Rimozioni carrello | s.events | Imposta s.events su scRemove |
| Pagamenti | s.events | Imposta s.events su scCheckout |

| Eventi personalizzati |
|---|
| Evento personalizzato 1 | s.events | Compilazione con event1 - event100 |
| … | … | Compilazione con event1 - event100 |
| Evento personalizzato 100 | s.events | Compilazione con event1 - event100 |

| Prodotti |
|---|
| Conversioni e medie | s.events, s.products, s.purchaseID |  |
| Prodotti | s.products, s.events | Può variare a seconda delle metriche delle colonne corrette |
| Vendita incrociata | s.products, s.events, s.purchaseID | Può variare a seconda delle metriche delle colonne corrette |
| Categorie | s.products | Può variare a seconda delle metriche delle colonne corrette |

| Campagne |
|---|
| Conversioni e medie | s.products, s.events, s.campaign |  |
| Codice di tracciamento | s.campaign |  |
| Elementi creativi | N/D | Definito in [!DNL Analytics] |
| Campagne | N/D | Definito in [!DNL Analytics] |

| Fedeltà cliente |
|---|
| Fedeltà cliente | s.products, s.events, s.purchaseID | Variabili impostate sulla conferma dell'ordine (grazie!) page |

| Ciclo di vendita |
|---|
| Giorni precedenti al primo acquisto | s.products, s.events, s.purchaseID | Variabili impostate sulla conferma dell'ordine (grazie!) page |
| Giorni dall'ultimo acquisto | s.products, s.events, s.purchaseID | Variabili impostate sulla conferma dell'ordine (grazie!) page |
| Numero visita | s.products, s.events, s.purchaseID | Variabili impostate sulla conferma dell'ordine (grazie!) page |
| Clienti univoci giornalieri | s.products, s.events, s.purchaseID | Variabili impostate sulla conferma dell'ordine (grazie!) page |
| Clienti univoci mensili | s.products, s.events, s.purchaseID | Variabili impostate sulla conferma dell'ordine (grazie!) page |
| Clienti univoci annuali | s.products, s.events, s.purchaseID | Variabili impostate sulla conferma dell'ordine (grazie!) page |

| Metodi di ricerca |
|---|
| Domini di riferimento | N/D | Imposta automaticamente dal file .JS |
| Domini di riferimento originali | N/D | Imposta automaticamente dal file .JS |
| Motori di ricerca | N/D | Imposta automaticamente dal file .JS |
| Parole chiave di ricerca | N/D | Imposta automaticamente dal file .JS |

| Profilo visitatore |
|---|
| Domini di livello principali | N/D | Imposta automaticamente dal file .JS |
| Lingue | N/D | Imposta automaticamente dal file .JS |
| Fusi orari | N/D | Imposta automaticamente dal file .JS |
| Gli stati   | s.state | Variabile impostata sulla conferma dell'ordine (grazie!) page |
| Codici CAP | s.zip | Variabile impostata sulla conferma dell'ordine (grazie!) page |
| Domains (Domini) | N/D | Imposta automaticamente dal file .JS |

| Tecnologia |
|---|
| Browser | N/D | Imposta automaticamente dal file .JS |
| Sistemi operativi | N/D | Imposta automaticamente dal file .JS |
| Risoluzioni monitor | N/D | Imposta automaticamente dal file .JS |

| Percorso sito |
|---|
| Valore pagina | s.pageName, s.products, s.events, s.purchaseID |  |
| Pagine di entrata | s.pageName |  |
| Pagine di entrata originali | s.pageName |  |
| Pagine per visita | N/D | Calcolato dalle regole aziendali in [!DNL Analytics] |
| Tempo trascorso sul sito | N/D | Calcolato dalle regole aziendali in [!DNL Analytics] |
| Sezione sito | [!UICONTROL s.channel] | Come [!UICONTROL Channel] rapporto nella sezione [!UICONTROL Traffic] report |

| Variabili cliente |
|---|
| eVar personalizzato 1 | [!UICONTROL s.eVar] 1 |  |
| eVar personalizzato 2 | [!UICONTROL s.eVar] 2 |  |
| eVar personalizzato 3 | [!UICONTROL s.eVar] 3 |  |
| … |  |  |
| eVar personalizzato 75 | [!UICONTROL s.eVar] 75 |  |

## Rapporti sul traffico {#section_76A74C3D7B60461D9ADE0E5E183DD777}

Nella tabella seguente sono elencate le [!UICONTROL traffic] variabili utilizzate per compilare ciascun rapporto:

| Metriche calcolate |
|---|
| N/D | N/D | N/D |

| Traffico del sito |
|---|
| Visualizzazioni pagina | N/D | Calcolato dalle regole aziendali in [!DNL Analytics] |
| Visitatori unici orari | N/D | Calcolato dalle regole aziendali in [!DNL Analytics] |
| Visitatori giornalieri unici | N/D | Calcolato dalle regole aziendali in [!DNL Analytics] |
| Visitatori unici mensili | N/D | Calcolato dalle regole aziendali in [!DNL Analytics] |
| Visitatori unici annuali | N/D | Calcolato dalle regole aziendali in [!DNL Analytics] |
| Visite | N/D | Calcolato dalle regole aziendali in [!DNL Analytics] |
| Download dei file | N/D | Traccia automaticamente dal file .JS (dipende dalle impostazioni delle variabili .JS) |

| Metodi di ricerca |
|---|
| Domini di riferimento | N/D | Imposta automaticamente dal file .JS |
| Riferimenti | N/D | Imposta automaticamente dal file .JS |
| Motori di ricerca | N/D | Imposta automaticamente dal file .JS |
| Parole chiave di ricerca | N/D | Imposta automaticamente dal file .JS |
| Restituisci frequenza | N/D | Calcolato dalle regole aziendali in [!DNL Analytics] |
| Visite giornaliere di ritorno | N/D | Calcolato dalle regole aziendali in [!DNL Analytics] |
| Visite di ritorno | N/D | Calcolato dalle regole aziendali in [!DNL Analytics] |
| Numeri di visita | N/D | Calcolato dalle regole aziendali in [!DNL Analytics] |

| Profilo visitatore |
|---|
| Domains (Domini) | N/D | Imposta automaticamente dal file .JS |
| Domini di livello principali | N/D | Imposta automaticamente dal file .JS |
| Lingue | N/D | Imposta automaticamente dal file .JS |
| Fusi orari | N/D | Imposta automaticamente dal file .JS |
| Dettagli visitatore | N/D | Imposta automaticamente dal file .JS |
| Ultimi 100 visitatori | N/D | Calcolato dalle regole aziendali in [!DNL Analytics] |
| Home page utente | N/D | Imposta automaticamente dal file .JS |
| Visitatori principali | N/D | In base all'indirizzo IP del visitatore |
| Pagine visualizzate dai visitatori principali | N/D | In base all'indirizzo IP del visitatore |

| Segmentazione geografica |
|---|
| Paesi | N/D | In base all'indirizzo IP del visitatore |
| Stati Uniti | N/D | In base all'indirizzo IP del visitatore |
| DMA | N/D | In base all'indirizzo IP del visitatore |
| Città internazionali | N/D | In base all'indirizzo IP del visitatore |
| Città degli Stati Uniti | N/D | In base all'indirizzo IP del visitatore |

| Tecnologia |
|---|
| Tipi di browser | N/D | Imposta automaticamente dal file .JS |
| Browser | N/D | Imposta automaticamente dal file .JS |
| Dispositivi mobili | N/D | Imposta automaticamente dal file .JS |
| Larghezza browser | N/D | Imposta automaticamente dal file .JS |
| Altezza browser | N/D | Imposta automaticamente dal file .JS |
| Sistemi operativi | N/D | Imposta automaticamente dal file .JS |
| Profondità colore del monitor | N/D | Imposta automaticamente dal file .JS |
| Risoluzioni monitor | N/D | Imposta automaticamente dal file .JS |
| Plug-in Netscape | N/D | Imposta automaticamente dal file .JS |
| Java | N/D | Imposta automaticamente dal file .JS |
| JavaScript | N/D | Imposta automaticamente dal file .JS |
| JavaScript versione | N/D | Imposta automaticamente dal file .JS |
| Cookie | N/D | Imposta automaticamente dal file .JS |
| Tipi di connessione | N/D | Imposta automaticamente dal file .JS |
| Segmentazione |

| Segmentazione |
|---|
| Pagine più popolari | s.pageName |  |
| Sezioni più popolari del sito | s.channel |  |
| Server più popolari | s.server |  |

| Custom Insight |
|---|
| Collegamenti personalizzati | s.linkName | Richiede implementazione personalizzata |
| Custom Insight 1 | s.prop1 |  |
| … | … |  |
| Custom Insight 75 | s.prop75 |  |

| Gerarchie |
|---|
| Gerarchia 1 | s.hier1 |  |
| … | … |  |
| Gerarchia 5 | s.hier5 |  |

## Report percorsi {#section_85E0A2396B894659A6BE572819263E95}

Nella tabella seguente sono elencate le variabili di percorso utilizzate per compilare ciascun report all'interno [!DNL Analytics]:

| Pagine |
|---|
| Riepilogo pagina | s.pageName (o altra variabile con percorso) | Dipende anche dalle regole aziendali interne |
| Valore pagina | s.pageName (o altra variabile con percorso) | Dipende anche dalle regole aziendali interne |
| Pagine più popolari | s.pageName (o altra variabile con percorso) | Dipende anche dalle regole aziendali interne |
| Ricariche | s.pageName (o altra variabile con percorso) | Dipende anche dalle regole aziendali interne |
| Clic sulla pagina | s.pageName (o altra variabile con percorso) | Dipende anche dalle regole aziendali interne |
| Tempo trascorso nella pagina | s.pageName (o altra variabile con percorso) | Dipende anche dalle regole aziendali interne |
| Pagine non trovate | s.pageName (o altra variabile con percorso) | Dipende anche dalle regole aziendali interne |

| Entrate e uscite |
|---|
| Pagine di entrata | s.pageName (o altra variabile con percorso) | Dipende anche dalle regole aziendali interne |
| Esci da pagine | s.pageName (o altra variabile con percorso) | Dipende anche dalle regole aziendali interne |
| Esci dai collegamenti | s.pageName (o altra variabile con percorso) | Dipende anche dalle regole aziendali interne |

| Percorsi completi |
|---|
| Percorsi completi | s.pageName (o altra variabile con percorso) | Dipende anche dalle regole aziendali interne |
| Percorsi più lunghi | s.pageName (o altra variabile con percorso) | Dipende anche dalle regole aziendali interne |
| Lunghezza percorso | s.pageName (o altra variabile con percorso) | Dipende anche dalle regole aziendali interne |
| Tempo trascorso per ciascuna visita | s.pageName (o altra variabile con percorso) | Dipende anche dalle regole aziendali interne |
| Visite a pagina singola | s.pageName (o altra variabile con percorso) | Dipende anche dalle regole aziendali interne |

| Analisi avanzata |
|---|
| Pagina precedente | s.pageName (o altra variabile con percorso) | Dipende anche dalle regole aziendali interne |
| Pagina successiva | s.pageName (o altra variabile con percorso) | Dipende anche dalle regole aziendali interne |
| Flusso pagina precedente | s.pageName (o altra variabile con percorso) | Dipende anche dalle regole aziendali interne |
| Flusso pagina successiva | s.pageName (o altra variabile con percorso) | Dipende anche dalle regole aziendali interne |
| PathFinder | s.pageName (o altra variabile con percorso) | Dipende anche dalle regole aziendali interne |
| Abbandono | s.pageName (o altra variabile con percorso) | Dipende anche dalle regole aziendali interne |
