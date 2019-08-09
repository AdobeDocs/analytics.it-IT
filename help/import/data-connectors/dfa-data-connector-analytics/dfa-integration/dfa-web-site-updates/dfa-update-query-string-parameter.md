---
description: nulle
keywords: DFA
seo-description: nulle
seo-title: Aggiorna il parametro della stringa query DFA
solution: Analytics
title: Aggiorna il parametro della stringa query DFA
topic: Connettori dati
uuid: adf 585 ac -84 ff -44 c 1-a 48 d-b 072726 c 8494
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Aggiorna il parametro della stringa query DFA{#update-your-dfa-query-string-parameter}

Se avete già tracciato le campagne pubblicitarie con Adobe Analytics prima dell'integrazione DFA, è possibile che tutte le campagne (e-mail, ricerca o banner) utilizzino lo stesso parametro della stringa query per identificare l'ID della campagna di provenienza sulla pagina di destinazione.

Per capire quando richiedere la visualizzazione-through e i dati di click-through dai dati DFA per le campagne di annunci DFA, i Connettori dati devono identificare quando un visitatore ha fatto clic su un annuncio banner della campagna DFA. Per farlo, devi aggiungere un parametro di stringa query differenziata all'URL della pagina di destinazione della campagna di destinazione DFA, in modo che i Connettori dati possano distinguere tra le pagine della campagna annunci DFA e altre pagine della campagna pubblicitaria che potresti avere sul sito Web. Nel `dfa_overrideParam` plug-in javascript (consultate [Aggiornare il codice di raccolta dati del sito Web](../../../dfa-data-connector-analytics/dfa-integration/dfa-web-site-updates/dfa-update-data-collection-code.md#concept-8c108723ea0b4cc9a8c5cdc2d05894e3)) utilizzato per DFA.

>[!CAUTION]
>
>Sebbene la variabile Campaign possa essere utilizzata per altre campagne, non utilizzarla per le campagne DFA. Se imposti la variabile Campaign su una pagina di destinazione della campagna DFA, Adobe non può collegare impression e clic ai click-through della campagna DFA. Una volta per visita, i server di raccolta Adobe controllano i server DFA per un clic o una visualizzazione precedente. In tal caso, includete il codice del plug-in DFA (consultate [Aggiornamento del codice di raccolta dati del sito Web](../../../dfa-data-connector-analytics/dfa-integration/dfa-web-site-updates/dfa-update-data-collection-code.md#concept-8c108723ea0b4cc9a8c5cdc2d05894e3)) solo sulle pagine di destinazione comuni per evitare reindirizzamenti inutili che possono rallentare i tempi di caricamento delle pagine, in particolare per gli utenti con connessioni Internet lente.

