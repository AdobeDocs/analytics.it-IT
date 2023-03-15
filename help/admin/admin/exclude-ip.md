---
title: Escludi per indirizzo IP
description: Impedisci la visualizzazione nei rapporti dei dati generati da alcuni indirizzi IP.
exl-id: 315a3000-f043-434b-a677-d111aeed7971
feature: Admin Tools
source-git-commit: 2c0aef13bdb88b0a7aa9f100c72c21f66a14c8dd
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 21%

---

# Escludi per indirizzo IP

Puoi escludere dai rapporti i dati di indirizzi IP specifici, ad esempio attività interne al sito web, test del sito e utilizzo dei dipendenti. L’esclusione dei dati migliora la precisione dei rapporti escludendo i dati dell’indirizzo IP. Inoltre, puoi rimuovere i dati da denial of service o altri eventi dannosi che possono distorcere i dati dei rapporti. Puoi configurare l’esclusione o utilizzando il firewall.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Exclude by IP]**

>[!NOTE]
>
>Gli hit esclusi dall’indirizzo IP vengono fatturati come [chiamate server](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html).

È possibile utilizzare indicatori jolly (&#42;) per escludere un intervallo di indirizzi. Ad esempio: `[!DNL 0.0.*.0]` escluderebbe tutti gli indirizzi IP compresi tra `[!DNL 0.0.0.0]` e `[!DNL 0.0.255.0]`. Puoi escludere fino a 50 indirizzi IP diversi.

>[!TIP]
>
>Non è necessario escludere gli indirizzi IP privati. Solo gli indirizzi IP esterni raggiungono i server di raccolta dati di Adobe. Gli indirizzi privati includono `10.*.*.*`, `192.168.*.*`, `172.[16-31].*.*`, e `169.254.*.*`.

## Impatto dell’offuscamento dell’IP {#section_51B7529FFF16449CA016FDC51D87E2CA}

Se l’offuscamento dell’IP è abilitato, l’esclusione di tale IP si verifica prima che l’indirizzo IP sia offuscato, pertanto i clienti non devono apportare alcuna modifica quando abilitano l’offuscamento dell’IP.

Se l’ultimo ottetto viene rimosso, questa operazione viene eseguita prima del filtro dell’IP. Di conseguenza, l’ultimo ottetto viene sostituito da 0 e le regole di esclusione IP devono essere aggiornate in modo che corrispondano agli indirizzi IP con uno zero alla fine. Corrispondenza &#42; deve corrispondere a 0.
