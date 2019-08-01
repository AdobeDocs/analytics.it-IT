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
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Update your DFA Query-String Parameter{#update-your-dfa-query-string-parameter}

Se avete già tracciato le campagne pubblicitarie con Adobe Analytics prima dell'integrazione DFA, è possibile che tutte le campagne (e-mail, ricerca o banner) utilizzino lo stesso parametro della stringa query per identificare l'ID della campagna di provenienza sulla pagina di destinazione.

Per capire quando richiedere la visualizzazione-through e i dati di click-through dai dati DFA per le campagne di annunci DFA, i Connettori dati devono identificare quando un visitatore ha fatto clic su un annuncio banner della campagna DFA. Per farlo, devi aggiungere un parametro di stringa query differenziata all'URL della pagina di destinazione della campagna di destinazione DFA, in modo che i Connettori dati possano distinguere tra le pagine della campagna annunci DFA e altre pagine della campagna pubblicitaria che potresti avere sul sito Web. The `dfa_overrideParam` in the JavaScript plug-in (see [Update Your Web Site's Data Collection Code](../../../dfa-data-connector-analytics/dfa-integration/dfa-web-site-updates/dfa-update-data-collection-code.md#concept-8c108723ea0b4cc9a8c5cdc2d05894e3)) used for DFA.

>[!CAUTION]
>
>Sebbene la variabile Campaign possa essere utilizzata per altre campagne, non utilizzarla per le campagne DFA. Se imposti la variabile Campaign su una pagina di destinazione della campagna DFA, Adobe non può collegare impression e clic ai click-through della campagna DFA. Una volta per visita, i server di raccolta Adobe controllano i server DFA per un clic o una visualizzazione precedente. Because of this, include the DFA plug-in code (see [Update Your Web Site's Data Collection Code](../../../dfa-data-connector-analytics/dfa-integration/dfa-web-site-updates/dfa-update-data-collection-code.md#concept-8c108723ea0b4cc9a8c5cdc2d05894e3)) only on common landing pages to avoid unnecessary redirects that can slow page-load times, particularly for users with slower Internet connections.

