---
description: Domande frequenti sulla configurazione, la configurazione e l’implementazione delle funzioni in Activity Map.
title: Domande frequenti su Activity Map
uuid: e4f6d4e2-55d1-4e32-bf70-a334178af370
feature: Activity Map
role: Business Practices, amministratore
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 1%

---


# Domande frequenti su Activity Map

Domande frequenti sulla configurazione, la configurazione e l’implementazione delle funzioni in Activity Map.

## Tutti i clienti di Analytics hanno accesso alla pagina Abilitazione ActivityMap degli Strumenti di amministrazione?

Le organizzazioni con un contratto per Adobe Analytics Standard, Premium e Ultimate possono accedere ad Activity Map.

## Activity Map fornisce dati sulle &quot;visualizzazioni&quot;?

No, Adobe non tiene traccia dei collegamenti visualizzati.

## Quali browser e versioni supporta Activity Map?

Activity Map supporta la versione più recente della maggior parte dei browser moderni.

## Activity Map incrementa le chiamate server?

Activity Map non invia chiamate server da sola. Invece, le variabili di dati di contesto di Activity Map sono incluse nelle chiamate di visualizzazione della pagina di Analytics nella pagina successiva.

## Perché mancano alcune sovrapposizioni di elementi classificati?**

Alcuni collegamenti con classifica, come i collegamenti dei sottomenu, sono nascosti dalla pagina. Di conseguenza, le sovrapposizioni di collegamento corrispondenti non vengono visualizzate. La classificazione viene calcolata per tutti i collegamenti sulla pagina, compresi quelli nascosti.

## Come viene determinata la classificazione dei collegamenti nel rapporto Tutti i collegamenti?**

* **In modalità** Sfumatura e bolla: La classificazione è determinata dalla colonna della metrica. Per i collegamenti con lo stesso valore di metrica, il rango si basa ulteriormente sull’ordine alfabetico degli ID collegamento.
* **In modalità** Gainer &amp; Loser: La classificazione è determinata principalmente dalla colonna Guadagno %. Per i collegamenti con lo stesso guadagno, il rango è ulteriormente basato sull&#39;ordine alfabetico dell&#39;ID collegamento.

## Come funziona Activity Map con pagine che utilizzano più suite di rapporti?

Per impostazione predefinita, Activity Map utilizza la suite di rapporti associata al primo tag inviato dalla pagina. Puoi selezionare una suite di rapporti con tag diversa tramite la scheda **[!UICONTROL Activity Map Settings]** > **[!UICONTROL Others]** .

## Per quanto tempo Activity Map esegue la scansione di Adobe Analytics sulla pagina?

Activity Map cerca la presenza di Adobe Analytics per un massimo di 20 secondi dopo un evento di completamento della pagina.

## In che modo Activity Map gestisce il contenuto dinamico?

Activity Map controlla ogni 2 secondi per verificare se sono state rilevate modifiche allo stato della pagina web, ad esempio:

* Contenuto HTML diventato visibile
* Contenuto HTML nascosto
* Nuovo contenuto HTML inserito

Se il contenuto è nascosto o visualizzato, lo stato dei collegamenti interessati (e quindi le sovrapposizioni) viene modificato automaticamente da nascosto a mostrato o da mostrato a nascosto. Se viene inserito un nuovo contenuto, l’applicazione recupera i collegamenti associati, estrae i dati analitici relativi e aggiunge sovrapposizioni per tali collegamenti.

## Su quale metrica si basa il rapporto di flusso di pagina?

Tutti i dati visualizzati si basano sulle visualizzazioni di pagina.

## Posso esportare variabili di dati di contesto di Activity Map tramite feed di dati?

Le variabili di dati contestuali di Activity Map non sono disponibili nei feed di dati.

## I segmenti funzionano in modalità Live?

No, i segmenti non funzionano in modalità Live. La funzionalità è equivalente a quella del reporting in tempo reale in Reports &amp; Analytics, che non supporta la segmentazione.

## Activity Map è compatibile con le suite di rapporti virtuali?

Sì. Tuttavia, a causa delle limitazioni della suite di rapporti virtuali, la modalità Live Activity Map non è compatibile con le suite di rapporti virtuali.
