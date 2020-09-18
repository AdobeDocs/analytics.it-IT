---
description: Domande frequenti su come impostare, configurare e utilizzare le funzionalità in  Activity Map.
title: Domande frequenti su Activity Map
topic: Activity map
uuid: e4f6d4e2-55d1-4e32-bf70-a334178af370
translation-type: tm+mt
source-git-commit: ec93137d0b5334e312fe0ec42953457243117d4a
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 1%

---


# Domande frequenti su Activity Map

Domande frequenti su come impostare, configurare e utilizzare le funzionalità in  Activity Map.

## Tutti i clienti Analytics hanno accesso alla pagina Abilitazione ActivityMap di Strumenti di amministrazione?

Le organizzazioni con un contratto per  Adobe Analytics Standard, Premium e Ultimate hanno accesso a  Activity Map.

##  Activity Map fornisce dati sulle &quot;visualizzazioni&quot;?

No,  Adobe non tiene traccia dei collegamenti visualizzati.

## Quali browser e versioni sono supportate  Activity Map?

 Activity Map supporta la versione più recente della maggior parte dei browser moderni.

##  Activity Map incrementa le chiamate al server?

 Activity Map non invia le chiamate al server da solo. Al contrario,  variabili di dati contestuali Activity Map vengono incluse con le chiamate di visualizzazione della pagina di Analytics sulla pagina successiva.

## Perché mancano alcune sovrapposizioni di elementi classificati?**

Alcuni collegamenti con classifica, come i collegamenti di sottomenu, sono nascosti dalla pagina. Di conseguenza, le sovrapposizioni di collegamento corrispondenti non vengono visualizzate. La classificazione viene calcolata per tutti i collegamenti sulla pagina, compresi i collegamenti nascosti.

## Come viene determinata la classificazione dei collegamenti nel rapporto Tutti i collegamenti?**

* **In modalità** Sfumatura e bolla: La classificazione è determinata dalla colonna della metrica. Per i collegamenti con lo stesso valore di metrica, il livello è ulteriormente basato sull&#39;ordine alfabetico ID collegamento.
* **In modalità** Gainer &amp; Loser: La classificazione è determinata principalmente dalla colonna % guadagno. Per i collegamenti con lo stesso guadagno, il rango è ulteriormente basato sull&#39;ordine alfabetico ID collegamento.

##  Activity Map funziona con pagine che utilizzano più suite di rapporti?

Per impostazione predefinita,  Activity Map utilizza la suite di rapporti associata al primo tag inviato dalla pagina. Puoi selezionare una suite di rapporti con tag diversa tramite **[!UICONTROL Activity Map Settings]** > **[!UICONTROL Others]** scheda.

## Quanto tempo  Activity Map analizza  Adobe Analytics sulla pagina?

La mappa dell&#39;attività cerca la presenza di  Adobe Analytics per un massimo di 20 secondi dopo un evento di completamento della pagina.

## In che modo  Activity Map gestisce il contenuto dinamico?

 Activity Map verifica ogni 2 secondi se sono state apportate modifiche allo stato della pagina Web, ad esempio:

* Contenuto HTML che è diventato visibile
* Contenuto HTML nascosto
* Nuovo contenuto HTML inserito

Se il contenuto è nascosto o visualizzato, l&#39;applicazione modifica automaticamente lo stato dei collegamenti interessati (e quindi le sovrapposizioni) da nascosto a mostrato o da mostrato a nascosto. Se viene inserito nuovo contenuto, l&#39;applicazione recupera i collegamenti associati, estrae i dati di analisi per tali collegamenti e aggiunge sovrapposizioni per tali collegamenti.

## Su quale metrica si basa il rapporto Flusso di pagina?

Tutti i dati visualizzati si basano sulle visualizzazioni della pagina.

## Posso esportare  variabili di dati contestuali Activity Map tramite feed di dati?

Le variabili dei dati contestuali della mappa dell&#39;attività non sono disponibili nei feed di dati.

## I segmenti funzionano in modalità Live?

No, i segmenti non funzionano in modalità Live. La funzionalità è equivalente a quella dei report in tempo reale in Reporting e analisi, che non supportano la segmentazione.

##  Activity Map è compatibile con le suite di rapporti virtuali?

Sì. Tuttavia, a causa di limitazioni delle suite di rapporti virtuali,  modalità Live Activity Map non è compatibile con le suite di rapporti virtuali.
