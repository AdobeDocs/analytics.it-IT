---
title: Escludi per indirizzo IP
description: Impedisci la visualizzazione nei rapporti dei dati generati da alcuni indirizzi IP.
exl-id: 315a3000-f043-434b-a677-d111aeed7971
feature: Admin Tools
role: Admin
source-git-commit: 4b4febd839682d88164b2f505245441d18ef2543
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 12%

---

# Escludi per indirizzo IP

Puoi escludere dai rapporti i dati provenienti da indirizzi IP specifici, ad esempio attività interne al sito web, test del sito e utilizzo dei dipendenti. L’esclusione dei dati migliora la precisione dei rapporti, escludendo i dati dell’indirizzo IP. Inoltre, puoi rimuovere i dati da denial of service o altri eventi dannosi che possono distorcere i dati dei rapporti.

Per escludere i dati per indirizzo IP, puoi configurare le esclusioni come descritto di seguito oppure [configurare il firewall](/help/technotes/ip-addresses.md).

## Configurare le esclusioni per indirizzo IP

>[!NOTE]
>
>Quando configuri le esclusioni per indirizzo IP, considera quanto segue:
>
>* Gli hit esclusi dall&#39;indirizzo IP vengono fatturati come [chiamate al server](/help/technotes/terms.md).
>* Non è necessario escludere gli indirizzi IP privati. Solo gli indirizzi IP esterni raggiungono i server di raccolta dati di Adobe. Gli indirizzi privati includono `10.*.*.*`, `192.168.*.*`, `172.[16-31].*.*` e `169.254.*.*`.
>* È possibile utilizzare gli indicatori dei caratteri jolly (&#42;) per escludere un intervallo di indirizzi. Ad esempio, `[!DNL 0.0.*.0]` escluderebbe tutti gli indirizzi IP compresi tra `[!DNL 0.0.0.0]` e `[!DNL 0.0.255.0]`. Puoi escludere fino a 50 indirizzi IP diversi.
>* I dati provenienti da un indirizzo IP escluso vengono esclusi per qualsiasi nuovo hit introdotto nel sistema entro 5 minuti dall’impostazione dell’esclusione.
>* I dati per gli hit acquisiti prima del momento in cui sono state apportate le modifiche all’indirizzo IP non sono interessati. L’esclusione degli IP si applica solo ai dati che progrediscono.
>* Gli hit esclusi sono ancora visibili in [Feed dati](/help/export/analytics-data-feed/data-feed-overview.md) (contrassegnati come `exclude_hit = 4`).

Per configurare le esclusioni per indirizzo IP:

1. In Adobe Analytics, selezionare **[!UICONTROL Admin]** > **[!UICONTROL All admin]**.

1. Nella pagina Amministrazione, selezionare **[!UICONTROL Exclude by IP]**.

## Impatto dell’utilizzo dell’offuscamento dell’IP con esclusione dell’IP

L&#39;impatto dell&#39;utilizzo di [offuscamento IP](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md) insieme all&#39;esclusione IP dipende dall&#39;impostazione di offuscamento IP di ogni suite di rapporti:

* **Offuscamento IP (ultimo ottetto)**: IP parzialmente offuscato PRIMA dell&#39;esecuzione dell&#39;esclusione IP. Assicurarsi che le regole di esclusione IP prevedano sempre un `0` come ultimo ottetto (i caratteri jolly sono validi in quanto includono `0`).
* **Offuscamento IP (rimozione IP)**: l&#39;IP è completamente offuscato DOPO l&#39;esecuzione dell&#39;esclusione IP. Non è necessaria alcuna configurazione della regola di esclusione IP.
