---
title: Confronto dei diversi metodi di esclusione dei bot
description: Consente di confrontare diversi metodi per escludere i bot.
exl-id: c54ba98a-b396-479e-bfe8-dc6211b26f61
role: Admin
feature: Bot Removal
source-git-commit: 75c1585f88d9d3adcf66632c52cecf2a97fa2632
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 45%

---

# Confronto dei diversi metodi di esclusione dei bot

La tabella seguente mostra i diversi metodi di esclusione dei bot e il modo in cui si confrontano tra loro.

| Metodo | Regole bot | Escludi per indirizzo IP | Attributi cliente | Segmentazione | Punteggio di terze parti + Segmentazione | Elimina le chiamate server per i bot in fase di esecuzione | Regola VISTA del database personalizzato |
| --- | --- | --- | --- | --- | --- | --- | --- |
| **Descrizione del metodo di esclusione dei dati** | Escludi in base all’agente utente, all’indirizzo IP o all’intervallo di indirizzi IP | Indirizzo IP | Un flag negli attributi del cliente che identifica ECID come bot | Criteri in un segmento di Analytics che identifica i bot noti in base al comportamento dei bot | Una terza parte, come [Perimeter X](https://www.perimeterx.com) o [Akamai Bot Manager](https://www.akamai.com/it/products/bot-manager) assegna a ogni pagina un punteggio sulla probabilità che si tratti di un bot. Il punteggio viene inviato in Analytics e i segmenti possono essere utilizzati per filtrare i dati in base al punteggio. | La logica lato client impedisce l’esecuzione della chiamata al server Analytics per i bot. | Una regola VISTA sposterà il traffico dai bot che soddisfano determinati criteri a una suite di rapporti separata. |
| **I nomi dei bot sono disponibili per il reporting?** | Sì | No | No | No | No | No | Sì |
| **Impossibile vedere quali pagine vengono visitate dai bot?** | Sì | No | No | No | Sì | No | Sì |
| **Riduce i costi delle chiamate al server per i bot?** | Sì | Sì | Sì | Sì | Sì | No | Sì |
| **Dati dei bot disponibili nei feed di dati?** | No | No | Sì | No | Sì | No | Sì |
| **È possibile creare rapporti sul traffico da bot come se si trattasse di chiamate server effettive?** | No | No | Sì | Sì | Sì | No | No |
| **È possibile rimuovere retroattivamente i dati da un set di dati?** | No | No | Sì, una volta implementati gli ID dichiarati | Sì | Sì, una volta implementati i punteggi | No | No |
| **I criteri sono soggetti ai limiti Uniques?** | No | No | No | Sì | No | No | No |
| **È soggetto a costi aggiuntivi?** | No | No | È possibile, a seconda dello SKU di Analytics | No | Sì | No | Sì - costo per implementare e mantenere una regola VISTA |
