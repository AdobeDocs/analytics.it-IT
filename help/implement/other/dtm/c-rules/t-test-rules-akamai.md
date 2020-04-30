---
description: Eseguite il test delle regole non pubblicate dalla console se utilizzate l'hosting di Akamai.
keywords: Dynamic Tag Management;rule;switcher plug-in;akamai;test akamai;unpublished rules;test unpublished rules;debug rule
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: Verificare le regole non pubblicate per hosting Akamai
uuid: 979e3d74-8d96-47d0-b581-cf5371248434
translation-type: tm+mt
source-git-commit: 3fe3442eae1bdd8b90acffc9c25d184714613c16

---


# Verificare le regole non pubblicate per hosting Akamai

Eseguite il test delle regole non pubblicate dalla console se utilizzate l&#39;hosting di Akamai.

Il plug-in Switcher è spesso il modo più semplice per eseguire il test. Per ulteriori informazioni, consulta Plug-in [](https://docs.adobe.com/content/help/en/dtm/using/resources/plugins/search-discovery-plugins.html) di ricerca nella Documentazione prodotto Gestione tag dinamica.

Nei passaggi seguenti viene illustrato come eseguire il test senza utilizzare il plug-in Switcher:

1. Accedete alla console Web sul sito e digitate `localStorage.setItem('sdsat_stagingLibrary', true)`.
1. Premere **[!UICONTROL Enter]**.
1. Digitare `_satellite.setDebug(true)`, quindi premere **[!UICONTROL Enter]**.
1. Aggiorna la pagina.

   Questa azione carica la libreria di staging e imposta il debugger, in modo da visualizzare i dettagli di tutte le regole disponibili (pubblicate/non pubblicate) in esecuzione sulla pagina.
1. Al termine, eseguire `localStorage.setItem('sdsat_stagingLibrary', false)`, quindi premere **[!UICONTROL Enter]**.

   Risultato passaggio
