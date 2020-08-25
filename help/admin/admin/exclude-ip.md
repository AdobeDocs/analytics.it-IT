---
title: Escludi per indirizzo IP
description: Impedisci la visualizzazione nei report dei dati generati da alcuni indirizzi IP.
translation-type: tm+mt
source-git-commit: 47b14bde1bb1217bcb172c6d4f01d68f917d44db
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 7%

---


# Escludi per indirizzo IP

Puoi escludere dai rapporti i dati da indirizzi IP specifici, ad esempio attività interne sul sito Web, test del sito e utilizzo dei dipendenti. Escludendo i dati si migliora la precisione dei report escludendo i dati degli indirizzi IP. Inoltre, puoi rimuovere i dati dal rifiuto del servizio o da altri eventi dannosi che possono distorcere i dati del rapporto. È possibile configurare l&#39;esclusione o utilizzando il firewall.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Exclude by IP]**

>[!NOTE]
>
>Gli hit esclusi dall&#39;indirizzo IP vengono fatturati come chiamate [](https://docs.adobe.com/content/help/it-IT/analytics/technotes/terms.html)server.

Potete utilizzare gli indicatori di carattere jolly (*) per escludere un intervallo di indirizzi. Ad esempio, `[!DNL 0.0.*.0]` escluderebbe tutti gli indirizzi IP tra `[!DNL 0.0.0.0]` e `[!DNL 0.0.255.0]`. Potete escludere fino a 50 indirizzi IP diversi.

>[!TIP]
>
>Non è necessario escludere gli indirizzi IP privati. Solo gli indirizzi IP esterni raggiungono  server di raccolta dati di Adobe. Gli indirizzi privati includono `10.*.*.*`, `192.168.*.*`, `172.[16-31].*.*`e `169.254.*.*`.

## Impatto dell&#39;offuscamento IP {#section_51B7529FFF16449CA016FDC51D87E2CA}

Se l&#39;offuscamento IP è abilitato, l&#39;esclusione IP avviene prima che l&#39;indirizzo IP sia oscurato, in modo che i clienti non debbano cambiare nulla quando attivano l&#39;offuscamento IP.

Se l&#39;ultimo ottetto viene rimosso, questo viene fatto prima del filtro IP. Di conseguenza, l&#39;ultimo ottetto viene sostituito con 0 e le regole di esclusione IP devono essere aggiornate in modo che corrispondano agli indirizzi IP con uno zero alla fine. La corrispondenza * deve corrispondere a 0.
