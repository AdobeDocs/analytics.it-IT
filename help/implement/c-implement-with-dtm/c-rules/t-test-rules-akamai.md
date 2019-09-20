---
description: Eseguite il test delle regole non pubblicate dalla console se utilizzate l'hosting di Akamai.
keywords: Dynamic Tag Management;rule;switcher plugin;akamai;test akamai;unpublished rules;test unpublished rules;debug rule
seo-description: Eseguite il test delle regole non pubblicate dalla console se utilizzate l'hosting di Akamai.
seo-title: Verificare le regole non pubblicate per hosting Akamai
solution: Experience Cloud,Analytics,Target,Gestione tag dinamica
title: Verificare le regole non pubblicate per hosting Akamai
uuid: 979e3d74-8d96-47d0-b581-cf5371248434
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Verificare le regole non pubblicate per hosting Akamai

Eseguite il test delle regole non pubblicate dalla console se utilizzate l'hosting di Akamai.

Il plugin dello switcher è spesso il modo più semplice per eseguire il test. Per ulteriori informazioni, consulta [Ricerca plug-in](https://marketing.adobe.com/resources/help/en_US/dtm/search_discovery_plugins.html) nella Documentazione prodotto Gestione tag dinamica.

I passaggi seguenti mostrano come eseguire il test senza utilizzare il plug-in Switcher:

1. Accedete alla console Web sul sito e digitate `localStorage.setItem('sdsat_stagingLibrary', true)`.
1. Premere **[!UICONTROL Enter]**.
1. Digitare `_satellite.setDebug(true)`, quindi premere **[!UICONTROL Enter]**.
1. Aggiorna la pagina.

   Questa azione carica la libreria di staging e imposta il debugger, in modo da visualizzare i dettagli di tutte le regole disponibili (pubblicate/non pubblicate) in esecuzione sulla pagina.
1. Al termine, eseguire `localStorage.setItem('sdsat_stagingLibrary', false)`, quindi premere **[!UICONTROL Enter]**.

   Risultato passaggio