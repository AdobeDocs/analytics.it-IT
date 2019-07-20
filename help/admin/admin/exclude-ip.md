---
description: Dai rapporti potete escludere dati da indirizzi IP specifici, ad esempio attività interne al sito Web, test di siti e uso dei dipendenti. L'esclusione di dati migliora la precisione dei report escludendo i dati dell'indirizzo IP. Inoltre, è possibile rimuovere dati da negazione di servizio o altri eventi dannosi in grado di inclinare i dati del rapporto. Potete configurare l'esclusione o utilizzare il firewall.
seo-description: Dai rapporti potete escludere dati da indirizzi IP specifici, ad esempio attività interne al sito Web, test di siti e uso dei dipendenti. L'esclusione di dati migliora la precisione dei report escludendo i dati dell'indirizzo IP. Inoltre, è possibile rimuovere dati da negazione di servizio o altri eventi dannosi in grado di inclinare i dati del rapporto. Potete configurare l'esclusione o utilizzare il firewall.
seo-title: Escludi per indirizzo IP
solution: Analytics
title: Escludi per indirizzo IP
topic: Strumenti di amministrazione
uuid: 1 ed 6105 f-e 7 c 5-4 c 4 f-b 8 f 4-e 5 f 66 d 0824 bb
translation-type: tm+mt
source-git-commit: 26ea8e41b9a45c87c339d4d4d56c914fbc44bae8

---


# Escludi per indirizzo IP

Dai rapporti potete escludere dati da indirizzi IP specifici, ad esempio attività interne al sito Web, test di siti e uso dei dipendenti. L'esclusione di dati migliora la precisione dei report escludendo i dati dell'indirizzo IP. Inoltre, è possibile rimuovere dati da negazione di servizio o altri eventi dannosi in grado di inclinare i dati del rapporto. Potete configurare l'esclusione o utilizzare il firewall.

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Exclude by IP]**

>[!NOTE]
>
>Hits marked as *bots* are billed as [server calls](https://marketing.adobe.com/resources/help/en_US/reference/primary_server_calls.html).

## Exclude By Cookie {#section_FB5A20AB5E514DA6BC596CC67F6A3A4C}

Consente di escludere questo computer dal tracciamento dell'account. Se scegliete di escludere il computer, tutti i dati generati dal computer non vengono conteggiati.

Questa funzione consente a voi e ai vostri colleghi di visitare il sito senza distorcere i dati sul traffico. Potrebbe essere utile utilizzare questa funzione se non si dispone di un indirizzo IP statico (ad esempio, se si dispone di una connessione Internet tramite connessione remota tramite un provider di servizi) e si desidera escludersi dai dati dell'account.

| Elemento | Descrizione |
|--- |--- |
| [!UICONTROL Add CNAME] | Genera un collegamento di rinuncia che puoi utilizzare per escludere il dominio. Per assistenza, contattate gli utenti supportati della vostra azienda. <br>Per escludere il traffico nelle suite di rapporti, visita la pagina di rinuncia della tua società e scegli di escludere dalla misurazione il browser. <br>Se la vostra implementazione utilizza cookie di terze parti, la vostra pagina di rinuncia è [disponibile](https://democorp.112.2o7.net/optout.html?locale=en_US&popup=true)qui. |

>[!NOTE]
>
>L'esclusione per computer funziona solo se:
>
>* Potete accedere al sito Web dalla stessa stazione di lavoro.
>* I cookie sono abilitati nel browser in uso.
>* I cookie non vengono eliminati. Se i cookie vengono eliminati, è necessario escluderli.


## Exclude by IP Address {#section_609FB6461529409D840111A32FEF5C3D}

Un indirizzo IP è un indirizzo Internet. A tutti gli utenti Internet vengono assegnati indirizzi IP numerici (solitamente attraverso provider di servizi Internet) che agiscono in modo efficace da identificatori elettronici.

Le visualizzazioni di pagina sono conteggiate e i visitatori univoci della pagina vengono identificati tramite indirizzi IP. Escludendo gli indirizzi IP da conteggio, potete impedire ad Adobe di tenere traccia di visitatori frequenti. Questa funzione consente a voi e ai vostri colleghi di visitare il sito senza distorcere i dati sul traffico. Potete escludere fino a 50 indirizzi IP diversi.

Potete utilizzare indicatori jolly (*) per escludere un intervallo di indirizzi. For example, `[!DNL 0.0.*.0]` would exclude all IP addresses between `[!DNL 0.0.0.0]` and `[!DNL 0.0.255.0]`. Potete escludere fino a 50 indirizzi IP diversi.

## Exclude by Firewall {#section_3E7BFB71ADD941D39F923DB9557AD9CD}

Potete anche bloccare la raccolta di dati da indirizzi IP specifici tramite un firewall.

See the [IP Addresses Used in the Experience Cloud](https://marketing.adobe.com/resources/help/en_US/home/index.html#kb-adobe-ip-addresses) article.

## Impact of IP Obfuscation {#section_51B7529FFF16449CA016FDC51D87E2CA}

Se l'offuscamento IP è abilitato, l'esclusione IP avviene prima che l'indirizzo IP non venga oscurato, in modo che i clienti non debbano modificare nulla quando abilitano l'offuscamento IP.

Se l'ultimo ottetto viene rimosso, viene eseguito prima del filtro IP. Pertanto, l'ultimo ottetto viene sostituito con un 0 e le regole di esclusione IP devono essere aggiornate per corrispondere agli indirizzi IP con uno zero alla fine. Corrispondenza * deve corrispondere a 0.
