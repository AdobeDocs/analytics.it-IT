---
title: Escludi per indirizzo IP
description: Impedisci la visualizzazione nei rapporti dei dati generati da alcuni indirizzi IP.
exl-id: 315a3000-f043-434b-a677-d111aeed7971
feature: Admin Tools
role: Admin
source-git-commit: d642bf8703d7c4c1545bfd9763c70ed8b1237eac
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 26%

---

# Escludi per indirizzo IP

Puoi escludere dai rapporti i dati provenienti da indirizzi IP specifici, ad esempio attività interne al sito web, test del sito e utilizzo dei dipendenti. L’esclusione dei dati migliora la precisione dei rapporti, escludendo i dati dell’indirizzo IP. Inoltre, puoi rimuovere i dati da denial of service o altri eventi dannosi che possono distorcere i dati dei rapporti.

Per escludere i dati per indirizzo IP, puoi configurare le esclusioni come descritto di seguito oppure [configurare il firewall](/help/technotes/ip-addresses.md).

## Configurare le esclusioni per indirizzo IP

>[!NOTE]
>
>Quando configuri le esclusioni per indirizzo IP, considera quanto segue:
>
>* Gli hit esclusi dall&#39;indirizzo IP vengono fatturati come [chiamate al server](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html?lang=it).
>* Non è necessario escludere gli indirizzi IP privati. Solo gli indirizzi IP esterni raggiungono i server di raccolta dati di Adobe. Gli indirizzi privati includono `10.*.*.*`, `192.168.*.*`, `172.[16-31].*.*` e `169.254.*.*`.
>* È possibile utilizzare gli indicatori dei caratteri jolly (&#42;) per escludere un intervallo di indirizzi. Ad esempio, `[!DNL 0.0.*.0]` escluderebbe tutti gli indirizzi IP compresi tra `[!DNL 0.0.0.0]` e `[!DNL 0.0.255.0]`. Puoi escludere fino a 50 indirizzi IP diversi.
* I dati provenienti da un indirizzo IP escluso vengono esclusi per qualsiasi nuovo hit introdotto nel sistema entro 5 minuti dall’impostazione dell’esclusione.
* I dati per gli hit acquisiti prima del momento in cui sono state apportate le modifiche all’indirizzo IP non sono interessati.
>

Per configurare le esclusioni per indirizzo IP:

1. In Adobe Analytics, selezionare **[!UICONTROL Admin]** > **[!UICONTROL All admin]**.

1. Nella pagina Amministrazione, selezionare **[!UICONTROL Exclude by IP]**.




## Impatto dell’offuscamento dell’IP {#section_51B7529FFF16449CA016FDC51D87E2CA}

Se l’offuscamento dell’IP è abilitato, l’esclusione di tale IP si verifica prima che l’indirizzo IP sia offuscato, pertanto i clienti non devono apportare alcuna modifica quando abilitano l’offuscamento dell’IP.

Se l’ultimo ottetto viene rimosso, questa operazione viene eseguita prima del filtro dell’IP. Di conseguenza, l’ultimo ottetto viene sostituito da 0 e le regole di esclusione IP devono essere aggiornate in modo che corrispondano agli indirizzi IP con uno zero alla fine. La corrispondenza &#42; deve corrispondere a 0.
