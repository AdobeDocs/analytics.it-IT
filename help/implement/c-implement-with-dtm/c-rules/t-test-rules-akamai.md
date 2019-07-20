---
description: Potete testare le regole non pubblicate dalla console se utilizzate l'hosting di Akamai.
keywords: Gestione tag dinamica; rule; plugin di commutatore; akamai; test akamai; regole non pubblicate; test unpublished rules; regola di debug
seo-description: Potete testare le regole non pubblicate dalla console se utilizzate l'hosting di Akamai.
seo-title: Verificare le regole non pubblicate per hosting Akamai
solution: Marketing Cloud, Analytics, Target, Gestione tag dinamica
title: Verificare le regole non pubblicate per hosting Akamai
uuid: 979 e 3 d 74-8 d 96-47 d 0-b 581-cf 5371248434
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Verificare le regole non pubblicate per hosting Akamai

Potete testare le regole non pubblicate dalla console se utilizzate l'hosting di Akamai.

Il plug-plugin Switcher è spesso il metodo più semplice per eseguire il test. See [Search Discovery Plugins](https://marketing.adobe.com/resources/help/en_US/dtm/search_discovery_plugins.html) in the Dynamic Tag Management Product Documentation for more information.

I passaggi seguenti mostrano come eseguire il test senza utilizzare il plug-plugin Switcher:

1. Access your web console on your site and type `localStorage.setItem('sdsat_stagingLibrary', true)`.
1. Press **[!UICONTROL Enter]**.
1. Type `_satellite.setDebug(true)`, then press **[!UICONTROL Enter]**.
1. Aggiorna la pagina.

   Questa azione carica la libreria di staging e imposta il debugger, per visualizzare i dettagli di tutte le regole disponibili (pubblicate/non pubblicate) che si attivano sulla pagina.
1. When finished, run `localStorage.setItem('sdsat_stagingLibrary', false)`, then press **[!UICONTROL Enter]**.

   Risultato passaggio