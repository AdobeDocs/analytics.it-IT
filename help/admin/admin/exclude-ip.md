---
description: Puoi escludere dai rapporti i dati da indirizzi IP specifici, ad esempio attività interne sul sito Web, test del sito e utilizzo dei dipendenti. Escludendo i dati si migliora la precisione dei report escludendo i dati degli indirizzi IP. Inoltre, puoi rimuovere i dati dal rifiuto del servizio o da altri eventi dannosi che possono distorcere i dati del rapporto. È possibile configurare l'esclusione o utilizzando il firewall.
title: Escludi per indirizzo IP
topic: Admin tools
uuid: 1ed6105f-e7c5-4c4f-b8f4-e5f66d0824bb
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 4%

---


# Escludi per indirizzo IP

Puoi escludere dai rapporti i dati da indirizzi IP specifici, ad esempio attività interne sul sito Web, test del sito e utilizzo dei dipendenti. Escludendo i dati si migliora la precisione dei report escludendo i dati degli indirizzi IP. Inoltre, puoi rimuovere i dati dal rifiuto del servizio o da altri eventi dannosi che possono distorcere i dati del rapporto. È possibile configurare l&#39;esclusione o utilizzando il firewall.

**[!UICONTROL Analytics]** (Workspace) > **[!UICONTROL Admin]** (Progetto) > **[!UICONTROL Exclude by IP]** (Annulla/Ripeti)

>[!NOTE]
>
>Gli hit esclusi dall&#39;indirizzo IP vengono fatturati come chiamate [](https://docs.adobe.com/content/help/it-IT/analytics/technotes/terms.translate.html)server.

## Escludi per cookie {#section_FB5A20AB5E514DA6BC596CC67F6A3A4C}

Consente di escludere il computer dal tracciamento dell&#39;account. Se si sceglie di escludere il computer, tutti i dati generati dal computer non vengono conteggiati.

Questa funzione consente a voi e ai vostri colleghi di visitare il sito senza distorcere i dati del traffico. È possibile utilizzare questa funzione se non si dispone di un indirizzo IP statico (ad esempio, se si dispone di una connessione Internet remota tramite un provider di servizi) e si desidera escluderlo dai dati dell&#39;account.

| Elemento | Descrizione |
|--- |--- |
| [!UICONTROL Add CNAME] | Genera un collegamento di rinuncia che puoi utilizzare per escludere il dominio. Per assistenza, contattate gli Utenti supportati della società. <br>Il traffico può essere escluso dalla generazione di rapporti nelle suite di rapporti visitando la pagina di rifiuto della società e scegliendo di escludere il browser dalla misurazione. <br>Se l’implementazione utilizza cookie di terze parti, la pagina di rinuncia è [disponibile qui](https://democorp.112.2o7.net/optout.html?locale=en_US&amp;popup=true). |

>[!NOTE]
>
>L&#39;esclusione per computer funziona solo se:
>
> * Si accede al sito Web dalla stessa stazione di lavoro.
> * I cookie sono attivati nel browser in uso.
> * I cookie non vengono eliminati. Se i cookie vengono eliminati, devi escluderti di nuovo.


## Exclude by IP Address {#section_609FB6461529409D840111A32FEF5C3D}

Un indirizzo IP è un indirizzo Internet. A tutti gli utenti di Internet vengono assegnati indirizzi IP numerici (generalmente attraverso provider di servizi Internet) che fungono da identificatori elettronici.

Le visualizzazioni di pagina vengono conteggiate e i visitatori di pagina univoci vengono identificati tramite indirizzi IP. Escludendo gli indirizzi IP dal conteggio, potete impedire ad Adobe di monitorare i visitatori frequenti. Questa funzione consente a voi e ai vostri colleghi di visitare il sito senza distorcere i dati del traffico. È possibile escludere fino a 50 indirizzi IP diversi.

È possibile utilizzare gli indicatori di carattere jolly (*) per escludere un intervallo di indirizzi. Ad esempio, `[!DNL 0.0.*.0]` escluderebbe tutti gli indirizzi IP tra `[!DNL 0.0.0.0]` e `[!DNL 0.0.255.0]`. Potete escludere fino a 50 indirizzi IP diversi.

## Escludi per firewall {#section_3E7BFB71ADD941D39F923DB9557AD9CD}

È inoltre possibile bloccare la raccolta di dati da indirizzi IP specifici tramite un firewall.

Consultate gli indirizzi [IP utilizzati nell&#39;articolo  Experience Cloud](https://helpx.adobe.com/it/analytics/kb/adobe-ip-addresses.html) .

## Impatto dell&#39;offuscamento IP {#section_51B7529FFF16449CA016FDC51D87E2CA}

Se l&#39;offuscamento IP è abilitato, l&#39;esclusione IP avviene prima che l&#39;indirizzo IP sia oscurato, in modo che i clienti non debbano cambiare nulla quando attivano l&#39;offuscamento IP.

Se l&#39;ultimo ottetto viene rimosso, questo viene fatto prima del filtro IP. Di conseguenza, l&#39;ultimo ottetto viene sostituito con 0 e le regole di esclusione IP devono essere aggiornate in modo che corrispondano agli indirizzi IP con uno zero alla fine. La corrispondenza * deve corrispondere a 0.
