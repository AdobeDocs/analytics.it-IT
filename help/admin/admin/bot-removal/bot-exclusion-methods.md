---
title: Confronto dei diversi metodi di esclusione dei bot
description: Consente di confrontare diversi metodi per escludere i bot.
exl-id: c54ba98a-b396-479e-bfe8-dc6211b26f61
feature: Bot Removal
source-git-commit: f6199620033af9c8e304bd0f537d4e0b052ed64d
workflow-type: ht
source-wordcount: '325'
ht-degree: 100%

---

# Confronto dei diversi metodi di esclusione dei bot

La tabella seguente mostra diversi metodi per escludere i bot e come si sovrappongono tra loro.

| Metodo | Regole bot | Escludi per indirizzo IP | Attributi cliente | Segmentazione | Punteggio di terze parti + Segmentazione | Elimina le chiamate server per i bot in fase di esecuzione | Regola VISTA del database personalizzato |
| --- | --- | --- | --- | --- | --- | --- | --- |
| **Descrizione del metodo di esclusione dei dati** | Escludi in base all’agente utente, all’indirizzo IP o all’intervallo di indirizzi IP | Indirizzo IP | Un flag negli attributi del cliente che identifica ECID come bot | Criteri in un segmento di Analytics che identifica i bot noti in base al comportamento dei bot | Una terza parte, come [Perimeter X](https://www.perimeterx.com) o [Akamai Bot Manager](https://www.akamai.com/it/products/bot-manager) assegna a ogni pagina un punteggio sulla probabilità che si tratti di un bot. Il punteggio viene inviato in Analytics e i segmenti possono essere utilizzati per filtrare i dati in base al punteggio. | La logica lato client impedisce l’esecuzione della chiamata al server Analytics per i bot. | Una regola VISTA sposterà il traffico dai bot che soddisfano determinati criteri a una suite di rapporti separata. |
| **I nomi dei bot sono disponibili per la generazione di rapporti?** | Sì | No | No | No | No | No | Sì |
| **È in grado di vedere quali pagine vengono visitate dai bot?** | Sì | No | No | No | Sì | No | Sì |
| **Riduce i costi di chiamata al server per i bot?** | Sì | Sì | Sì | Sì | Sì | No | Sì |
| **Dati dei bot disponibili nei feed di dati?** | No | No | Sì | Sì | Sì | No | Sì |
| **È in grado di eseguire rapporti sul traffico da bot come se si trattasse di chiamate server effettive?** | No | No | Sì | Sì | Sì | No | No |
| **È possibile rimuovere retroattivamente i dati da un set di dati?** | No | No | Sì, una volta implementati gli ID dichiarati | Sì | Sì, una volta implementati i punteggi | No | No |
| **I criteri sono soggetti ai limiti Uniques?** | No | No | No | Sì | No | No | No |
| **È soggetto a costi aggiuntivi?** | No | No | È possibile, a seconda dello SKU di Analytics | No | Sì | No | Sì - costo per implementare e mantenere una regola VISTA |
