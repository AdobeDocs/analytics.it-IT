---
description: Le tabelle riportate di seguito presentano il rapporto sulla mappatura variabile, sui rapporti e sulle variabili utilizzate.
keywords: Implementazione di Analytics
seo-description: Le tabelle riportate di seguito presentano il rapporto sulla mappatura variabile, sui rapporti e sulle variabili utilizzate.
seo-title: Rapporto sulla mappatura variabile
solution: Analytics
title: Rapporto sulla mappatura variabile
topic: Sviluppatore e implementazione
uuid: 4707660 c -4 be 5-425 c-a 690-7 bc 6 df 4 cc 0 fa
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Rapporto sulla mappatura variabile

Le tabelle riportate di seguito presentano il rapporto sulla mappatura variabile, sui rapporti e sulle variabili utilizzate.

**Rapporti conversione** Nella tabella seguente sono elencate le variabili di conversione utilizzate per comporre ciascun rapporto:

| Acquisti |
|---|
| Conversioni e medie | s. events, s. products, s. purchaseid | Set s. events to purchase, product detail, order number |
| Ricavi | s. events, s. products, s. purchaseid | Set s. events to purchase, product detail, order number |
| Ordini | s. events, s. products, s. purchaseid | Set s. events to purchase, product detail, order number |
| Unità | s. events, s. products, s. purchaseid | Set s. events to purchase, product detail, order number |

| Carrello acquisti |
|---|
| Conversioni e medie | s. events, s. products, s. purchaseid |  |
| Carrello | s. events | Imposta s. events su scoen |
| Visualizzazioni carrello | s. events | Impostate s. events su scview |
| Aggiunte carrello | s. events | Impostare s. events su cetd |
| Rimozioni carrello | s. events | Impostate s. events su scremove |
| Pagamenti | s. events | Imposta s. events su sccheckout |

| Eventi personalizzati |
|---|
| Evento personalizzato 1 | s. events | Compilazione con event 1 - event 100 |
| … | … | Compilazione con event 1 - event 100 |
| Evento personalizzato 100 | s. events | Compilazione con event 1 - event 100 |

| Variabile   |
|---|
| Conversioni e medie | s. events, s. products, s. purchaseid |  |
| Variabile   | s. products, s. events | Può variare a seconda delle metriche di colonna corrette |
| Cross-sell | s. products, s. events, s. purchaseid | Può variare a seconda delle metriche di colonna corrette |
| Categorie | s. products | Può variare a seconda delle metriche di colonna corrette |

| Campagne |
|---|
| Conversioni e medie | s. products, s. events, s. campaign |  |
| Codice di tracciamento | s.campaign |  |
| Elementi creativi | N/D | Defined in [!DNL Analytics] |
| Campagne | N/D | Defined in [!DNL Analytics] |

| Fedeltà cliente |
|---|
| Fedeltà cliente | s. products, s. events, s. purchaseid | Variabili impostate nella conferma ordine (Ringraziamenti!) page |

| Ciclo di vendita |
|---|
| Giorni prima del primo acquisto | s. products, s. events, s. purchaseid | Variabili impostate nella conferma ordine (Ringraziamenti!) page |
| Giorni dall'ultimo acquisto | s. products, s. events, s. purchaseid | Variabili impostate nella conferma ordine (Ringraziamenti!) page |
| Numero visita | s. products, s. events, s. purchaseid | Variabili impostate nella conferma ordine (Ringraziamenti!) page |
| Clienti univoci giornalieri | s. products, s. events, s. purchaseid | Variabili impostate nella conferma ordine (Ringraziamenti!) page |
| Clienti univoci mensili | s. products, s. events, s. purchaseid | Variabili impostate nella conferma ordine (Ringraziamenti!) page |
| Clienti annuali univoci | s. products, s. events, s. purchaseid | Variabili impostate nella conferma ordine (Ringraziamenti!) page |

| Metodi di ricerca |
|---|
| Domini di riferimento | N/D | Imposta automaticamente dal file. JS |
| Domini di riferimento originali | N/D | Imposta automaticamente dal file. JS |
| Motori di ricerca | N/D | Imposta automaticamente dal file. JS |
| Ricerca parole chiave | N/D | Imposta automaticamente dal file. JS |

| Profilo visitatore |
|---|
| Domini di livello principale | N/D | Imposta automaticamente dal file. JS |
| Lingue | N/D | Imposta automaticamente dal file. JS |
| Fusi orari | N/D | Imposta automaticamente dal file. JS |
| Gli stati   | s. state | Variabile impostata nella sezione Conferma ordine (Ringraziamento!) page |
| CAP | s.zip | Variabile impostata nella sezione Conferma ordine (Ringraziamento!) page |
| Domains (Domini) | N/D | Imposta automaticamente dal file. JS |

| Tecnologia |
|---|
| Browser | N/D | Imposta automaticamente dal file. JS |
| Sistemi operativi | N/D | Imposta automaticamente dal file. JS |
| Risoluzioni monitor | N/D | Imposta automaticamente dal file. JS |

| Percorso sito |
|---|
| Valore pagina | s. pagename, s. products, s. events, s. purchaseid |  |
| Pagine di immissione | s. pagename |  |
| Pagine di immissione originali | s. pagename |  |
| Pagine per visita | N/D | Calculated by business rules in [!DNL Analytics] |
| Tempo trascorso sul sito | N/D | Calculated by business rules in [!DNL Analytics] |
| Sezione sito | [!UICONTROL s.channel] | Same as [!UICONTROL Channel] report in [!UICONTROL Traffic] reports section |

| Variabili cliente |
|---|
| Evar personalizzato 1 | [!UICONTROL s.eVar] 1 |  |
| Evar personalizzato 2 | [!UICONTROL s.eVar] 2 |  |
| Evar personalizzato 3 | [!UICONTROL s.eVar] 3 |  |
| … |  |  |
| Evar personalizzato 75 | [!UICONTROL s.eVar] 75 |  |

## Traffic Reports {#section_76A74C3D7B60461D9ADE0E5E183DD777}

The following table lists the [!UICONTROL traffic] variables that are used to populate each report:

| Metriche calcolate |
|---|
| N/D | N/D | N/D |

| Traffico del sito |
|---|
| Visualizzazioni pagina | N/D | Calculated by business rules in [!DNL Analytics] |
| Visitatori unici orari | N/D | Calculated by business rules in [!DNL Analytics] |
| Visitatori giornalieri univoci | N/D | Calculated by business rules in [!DNL Analytics] |
| Visitatori unici mensili | N/D | Calculated by business rules in [!DNL Analytics] |
| Visitatori annuali univoci | N/D | Calculated by business rules in [!DNL Analytics] |
| Visite | N/D | Calculated by business rules in [!DNL Analytics] |
| Download dei file | N/D | Tracciamento automatico dal file. JS (dipende dalle impostazioni della variabile JS) |

| Metodi di ricerca |
|---|
| Domini di riferimento | N/D | Imposta automaticamente dal file. JS |
| Referenti | N/D | Imposta automaticamente dal file. JS |
| Motori di ricerca | N/D | Imposta automaticamente dal file. JS |
| Ricerca parole chiave | N/D | Imposta automaticamente dal file. JS |
| Restituisci frequenza | N/D | Calculated by business rules in [!DNL Analytics] |
| Visite giornaliere di ritorno | N/D | Calculated by business rules in [!DNL Analytics] |
| Visite di ritorno | N/D | Calculated by business rules in [!DNL Analytics] |
| Numeri visita | N/D | Calculated by business rules in [!DNL Analytics] |

| Profilo visitatore |
|---|
| Domains (Domini) | N/D | Imposta automaticamente dal file. JS |
| Domini di livello principale | N/D | Imposta automaticamente dal file. JS |
| Lingue | N/D | Imposta automaticamente dal file. JS |
| Fusi orari | N/D | Imposta automaticamente dal file. JS |
| Dettagli visitatore | N/D | Imposta automaticamente dal file. JS |
| Ultimi 100 visitatori | N/D | Calculated by business rules in [!DNL Analytics] |
| Home page utente | N/D | Imposta automaticamente dal file. JS |
| Visitatori principali | N/D | In base all'indirizzo IP del visitatore |
| Pagine visualizzate da Visitatori chiave | N/D | In base all'indirizzo IP del visitatore |

| Segmentazione geografica |
|---|
| Paesi | N/D | In base all'indirizzo IP del visitatore |
| Stati Stati Uniti | N/D | In base all'indirizzo IP del visitatore |
| DMA | N/D | In base all'indirizzo IP del visitatore |
| Città internazionali | N/D | In base all'indirizzo IP del visitatore |
| Città USA | N/D | In base all'indirizzo IP del visitatore |

| Tecnologia |
|---|
| Tipi di browser | N/D | Imposta automaticamente dal file. JS |
| Browser | N/D | Imposta automaticamente dal file. JS |
| Dispositivi mobili | N/D | Imposta automaticamente dal file. JS |
| Larghezza browser | N/D | Imposta automaticamente dal file. JS |
| Altezza browser | N/D | Imposta automaticamente dal file. JS |
| Sistemi operativi | N/D | Imposta automaticamente dal file. JS |
| Profondità colore monitor | N/D | Imposta automaticamente dal file. JS |
| Risoluzioni monitor | N/D | Imposta automaticamente dal file. JS |
| Plug-in Netscape | N/D | Imposta automaticamente dal file. JS |
| Java | N/D | Imposta automaticamente dal file. JS |
| JavaScript | N/D | Imposta automaticamente dal file. JS |
| JavaScript versione | N/D | Imposta automaticamente dal file. JS |
| Cookie | N/D | Imposta automaticamente dal file. JS |
| Tipi di connessione | N/D | Imposta automaticamente dal file. JS |
| Segmentazione |

| Segmentazione |
|---|
| Pagine più popolari | s. pagename |  |
| Sezioni più comuni del sito | s. channel |  |
| Più server | s. server |  |

| Custom Insight |
|---|
| Collegamenti personalizzati | s. linkname | Richiede implementazione personalizzata |
| Custom Insight 1 | s.prop1 |  |
| … | … |  |
| Custom Insight 75 | s.prop75 |  |

| Gerarchie |
|---|
| Gerarchia 1 | s.hier1 |  |
| … | … |  |
| Gerarchia 5 | s.hier5 |  |

## Pathing Reports {#section_85E0A2396B894659A6BE572819263E95}

The following table lists the pathing variables that are used to populate each report within [!DNL Analytics]:

| Pagine |
|---|
| Riepilogo pagina | s. pagename (o altra variabile pathed) | Dipende anche dalle regole aziendali interne |
| Valore pagina | s. pagename (o altra variabile pathed) | Dipende anche dalle regole aziendali interne |
| Pagine più popolari | s. pagename (o altra variabile pathed) | Dipende anche dalle regole aziendali interne |
| Ricarica | s. pagename (o altra variabile pathed) | Dipende anche dalle regole aziendali interne |
| Clic su pagina | s. pagename (o altra variabile pathed) | Dipende anche dalle regole aziendali interne |
| Tempo trascorso sulla pagina | s. pagename (o altra variabile pathed) | Dipende anche dalle regole aziendali interne |
| Pagine non trovate | s. pagename (o altra variabile pathed) | Dipende anche dalle regole aziendali interne |

| Entrata ed uscita |
|---|
| Pagine di immissione | s. pagename (o altra variabile pathed) | Dipende anche dalle regole aziendali interne |
| Esci da pagine | s. pagename (o altra variabile pathed) | Dipende anche dalle regole aziendali interne |
| Uscita dai collegamenti | s. pagename (o altra variabile pathed) | Dipende anche dalle regole aziendali interne |

| Complete Paths (Percorsi completi) |
|---|
| Percorsi completi | s. pagename (o altra variabile pathed) | Dipende anche dalle regole aziendali interne |
| Percorsi più lunghi | s. pagename (o altra variabile pathed) | Dipende anche dalle regole aziendali interne |
| Lunghezza percorso | s. pagename (o altra variabile pathed) | Dipende anche dalle regole aziendali interne |
| Tempo trascorso per visita | s. pagename (o altra variabile pathed) | Dipende anche dalle regole aziendali interne |
| Visite a una singola pagina | s. pagename (o altra variabile pathed) | Dipende anche dalle regole aziendali interne |

| Analisi avanzata |
|---|
| Pagina precedente | s. pagename (o altra variabile pathed) | Dipende anche dalle regole aziendali interne |
| Pagina successiva | s. pagename (o altra variabile pathed) | Dipende anche dalle regole aziendali interne |
| Flusso pagina precedente | s. pagename (o altra variabile pathed) | Dipende anche dalle regole aziendali interne |
| Flusso pagina successiva | s. pagename (o altra variabile pathed) | Dipende anche dalle regole aziendali interne |
| Pathfinder | s. pagename (o altra variabile pathed) | Dipende anche dalle regole aziendali interne |
| Abbandono | s. pagename (o altra variabile pathed) | Dipende anche dalle regole aziendali interne |
