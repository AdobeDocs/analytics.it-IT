---
title: Confronto dei diversi metodi di esclusione bot
description: Consente di confrontare diversi metodi per escludere i bot.
translation-type: tm+mt
source-git-commit: 76ee4a8db49765590e7cca864d6d4b152d7ba112
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 18%

---


# Confronto dei diversi metodi di esclusione bot

Nella tabella seguente sono riportati diversi metodi per escludere i bot e per impilarli uno contro l&#39;altro.

| Metodo | Regole bot | Escludi per indirizzo IP | Attributi cliente | Segmentazione | punteggio di 3 terze parti + segmentazione | Elimina &#x200B; chiamate server per i bot in fase di esecuzione | Regola VISTA DB personalizzata |
| --- | --- | --- | --- | --- | --- | --- | --- |
| **Descrizione del metodo di esclusione dei dati** | &#x200B; Escludi in base all&#39;agente utente, all&#39;indirizzo IP o all&#39;intervallo di indirizzi IP | Indirizzo IP | &#x200B; Un flag negli attributi del cliente che identifica ECID come bot | Criteri &#x200B; in un segmento di Analytics che identifica i bot noti in base al comportamento dei bot | &#x200B; Una terza parte, ad esempio [Perimetro X](https://www.perimeterx.com) o [Akamai Bot Manager](https://www.akamai.com/us/en/products/security/bot-manager.jsp) , assegna a ogni pagina una valutazione sulla probabilità che si tratti di un bot. Il punteggio viene inviato in Analytics e i segmenti possono essere utilizzati per filtrare i dati in base alla valutazione. | &#x200B; logica lato client impedisce l&#39;esecuzione della chiamata al server di Analytics per i bot. | &#x200B; Una regola VISTA sposterà il traffico dai bot che soddisfano determinati criteri a una suite di rapporti separata. |
| **&#x200B; nomi dei bot sono disponibili per il reporting?** | Sì | No | No | No | No | No | Sì |
| **&#x200B; in grado di vedere quali pagine vengono visitate dai bot?** | Sì | No | No | No | Sì | No | Sì |
| &#x200B;**Incurs Server call cost for bot?** | Sì | Sì | Sì | Sì | Sì | No | Sì |
| **Dati bot disponibili nei feed di dati?** | No | No | Sì | Sì | Sì | No | Sì |
| **È possibile &#x200B; il traffico bot come se si trattasse di chiamate server effettive?** | No | No | Sì | Sì | Sì | Sì | No |
| **È possibile rimuovere retroattivamente i dati da un set di dati?** | No | No | &#x200B; Sì, una volta implementati gli ID dichiarati | Sì | Sì, una volta implementati i punteggi | No | No |
| **È soggetto ai limiti di Uniques nei criteri?** | No | No | No | Sì | No | No | No |
| **È &#x200B; soggetto a costi aggiuntivi?** | No | No | &#x200B; possibile, a seconda dello SKU di Analytics | No | Sì | No | &#x200B; Sì - costo per implementare e mantenere una regola VISTA |
