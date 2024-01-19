---
description: Domande frequenti sull’organizzazione, la configurazione e l’implementazione delle funzioni in Activity Map.
title: Domande frequenti su Activity Map
uuid: e4f6d4e2-55d1-4e32-bf70-a334178af370
feature: Activity Map
role: User, Admin
exl-id: 6b2767cb-6c2c-4bf3-b9a9-a23418624650
source-git-commit: 93099d36a65ca2bf16fbd6342f01bfecdc8c798e
workflow-type: tm+mt
source-wordcount: '662'
ht-degree: 98%

---

# Domande frequenti su Activity Map

Domande frequenti sull’organizzazione, la configurazione e l’implementazione delle funzioni in Activity Map.

+++Tutti i clienti di Analytics hanno accesso alla pagina Abilitazione ActivityMap degli Strumenti di amministrazione?
Le organizzazioni con un contratto per Adobe Analytics Standard, Premium e Ultimate possono accedere ad Activity Map.
+++

+++In che modo Activity Map supporta le applicazioni a pagina singola (SPA)?
Ogni pochi secondi, Activity Map esegue la scansione della pagina web alla ricerca di modifiche alla pagina. ActivityMap trova nuovi contenuti nella pagina senza dover caricare una nuova pagina, ma questo nuovo contenuto è sempre attribuito al primo pageName trovato al caricamento della pagina.

* Activity Map controlla se la visibilità dei collegamenti di cui è a conoscenza è cambiata. Se viene rilevata una modifica nella visibilità, la colonna Link On Page della tabella Links On Page presente per quel collegamento si aggiorna con [!UICONTROL Displayed] o [!UICONTROL Hidden].

* Quando l’interazione dell’utente crea un nuovo contenuto, tutti i nuovi elementi trovati da AppMeasurement come collegamento verranno aggiunti alla tabella [!UICONTROL Links On Page]. Activity Map invia una nuova richiesta di dati che include questi nuovi collegamenti. I nuovi collegamenti dovrebbero essere visualizzati nella sezione [!UICONTROL Links On Page] quando la richiesta di dati viene gestita dall’interfaccia utente.
+++

+++Activity Map fornisce dati sulle “visualizzazioni”?
No, Adobe non tiene traccia dei collegamenti visualizzati.
+++

+++Quali browser e versioni sono supportate da Activity Map?
Activity Map supporta la versione più recente della maggior parte dei browser moderni.
+++

+++Activity Map aumenta le chiamate server?
Activity Map non invia chiamate server da sola. Invece, le variabili di dati di contesto di Activity Map sono incluse nelle chiamate di visualizzazione della pagina di Analytics nella pagina successiva.
+++

+++Perché mancano alcune sovrapposizioni di elementi classificati?
Alcuni collegamenti classificati, come i collegamenti dei sottomenu, sono nascosti dalla pagina. Di conseguenza, le sovrapposizioni di collegamento corrispondenti non vengono visualizzate. La classificazione viene calcolata per tutti i collegamenti sulla pagina, compresi quelli nascosti.
+++

+++Come viene determinata la classificazione dei collegamenti nel rapporto Tutti i collegamenti?**
* **In modalità Sfumatura e bolla**: la classificazione è determinata dalla colonna della metrica. Per i collegamenti con lo stesso valore di metrica, la classificazione si basa ulteriormente sull’ordine alfabetico degli ID collegamento.
* **In modalità Gainer &amp; Loser**: la classificazione è determinata principalmente dalla colonna Guadagno %. Per i collegamenti con lo stesso guadagno, la classificazione è ulteriormente basato sull’ordine alfabetico dell’ID collegamento.
+++

+++Come funziona Activity Map con pagine che utilizzano più suite di rapporti?
Per impostazione predefinita, Activity Map utilizza la suite di rapporti associata al primo tag inviato dalla pagina. Puoi selezionare una suite di rapporti con tag diversa tramite la scheda **[!UICONTROL Activity Map Settings]** > **[!UICONTROL Others]**.
+++

+++Per quanto tempo Activity Map esegue la scansione di Adobe Analytics sulla pagina?
Activity Map cerca la presenza di Adobe Analytics per un massimo di 20 secondi dopo un evento di completamento della pagina.
+++

+++In che modo Activity Map gestisce il contenuto dinamico?
Activity Map controlla ogni 2 secondi per verificare se sono state rilevate modifiche allo stato della pagina web, ad esempio:

* Contenuto HTML diventato visibile
* Contenuto HTML nascosto
* Nuovo contenuto HTML inserito

Se il contenuto è nascosto o visualizzato, lo stato dei collegamenti interessati (e quindi le sovrapposizioni) viene modificato automaticamente da nascosto a mostrato o da mostrato a nascosto. Se viene inserito un nuovo contenuto, l’applicazione recupera i collegamenti associati, estrae i dati analitici relativi e aggiunge sovrapposizioni per tali collegamenti.
+++

+++Su quale metrica si basa il rapporto Flusso di pagina?
Tutti i dati visualizzati si basano sulle visualizzazioni di pagina.
+++

+++Posso esportare le variabili di dati di contesto Activity Map tramite feed di dati?
Sì. Le [Colonne dati](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) che Activity Map utilizza sono `clickmaplink`, `clickmaplinkbyregion`, `clickmappage`e `clickmapregion`.
+++

+++I segmenti funzionano in modalità Live?
No, i segmenti non funzionano in modalità Live.
+++

+++Activity Map è compatibile con le suite di rapporti virtuali?
Sì. Tuttavia, a causa delle limitazioni della suite di rapporti virtuali, la modalità Live Activity Map non è compatibile con le suite di rapporti virtuali.
+++

+++Come posso disabilitare Activity Map?
Sono disponibili tre opzioni:

* Elimina la funzione `AppMeasurement_Module_ActivityMap` dal file JS
* Aggiungi un codice personalizzato che riscrive la funzione precedente con un corpo vuoto, ad esempio:

  ```js
  function AppMeasurement_Module_ActivityMap() {}
  ```

* Configurare AppMeasurement impostando `s.trackClickMap` e `s.trackInlineStats` a `false`
+++
