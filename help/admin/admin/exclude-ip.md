---
title: Escludi per indirizzo IP
description: Impedisci la visualizzazione nei rapporti dei dati generati da determinati indirizzi IP.
exl-id: 315a3000-f043-434b-a677-d111aeed7971
source-git-commit: d198e8ef0ec8415a4a555d3c385823baad6104fe
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 7%

---

# Escludi per indirizzo IP

Puoi escludere dai rapporti i dati da indirizzi IP specifici, ad esempio attività interne del sito web, test del sito e utilizzo dei dipendenti. L’esclusione dei dati migliora l’accuratezza del rapporto escludendo i dati relativi agli indirizzi IP. Inoltre, puoi rimuovere i dati dal rifiuto del servizio o da altri eventi dannosi che possono distorcere i dati del rapporto. È possibile configurare l’esclusione o utilizzando il firewall.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Exclude by IP]**

>[!NOTE]
>
>Gli hit esclusi dall’indirizzo IP vengono fatturati come [chiamate server](https://docs.adobe.com/content/help/it-IT/analytics/technotes/terms.html).

Puoi utilizzare gli indicatori jolly (*) per escludere un intervallo di indirizzi. Ad esempio, `[!DNL 0.0.*.0]` escluderebbe tutti gli indirizzi IP compresi tra `[!DNL 0.0.0.0]` e `[!DNL 0.0.255.0]`. Puoi escludere fino a 50 indirizzi IP diversi.

>[!TIP]
>
>Non è necessario escludere gli indirizzi IP privati. Solo gli indirizzi IP esterni raggiungono i server di raccolta dati di Adobe. Gli indirizzi privati includono `10.*.*.*`, `192.168.*.*`, `172.[16-31].*.*` e `169.254.*.*`.

## Impatto dell&#39;offuscamento dell&#39;IP {#section_51B7529FFF16449CA016FDC51D87E2CA}

Se l’offuscamento dell’IP è abilitato, l’esclusione IP si verifica prima che l’indirizzo IP sia offuscato, pertanto i clienti non devono apportare alcuna modifica quando abilitano l’offuscamento dell’IP.

Se l’ultimo ottetto viene rimosso, questo viene fatto prima del filtro IP. Di conseguenza, l’ultimo ottetto viene sostituito da 0 e le regole di esclusione IP devono essere aggiornate in modo che corrispondano a zero agli indirizzi IP alla fine. La corrispondenza * deve corrispondere a 0.
