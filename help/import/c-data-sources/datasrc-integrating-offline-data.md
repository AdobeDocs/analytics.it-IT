---
description: Origini dati offre due modi aggiuntivi per integrare gli eventi che si verificano offline nei dati online.
seo-description: Origini dati offre due modi aggiuntivi per integrare gli eventi che si verificano offline nei dati online.
seo-title: Integrazione transazione e cliente
solution: Analytics
subtopic: Origini dati
title: Integrazione transazione e cliente
topic: Sviluppatore e implementazione
uuid: 71 f 73 a 47-3436-4314-a 182-36 de 4 bd 935 ba
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Integrazione transazione e cliente

Origini dati offre due modi aggiuntivi per integrare eventi che si verificano offline nei dati online.

* [Abilita registrazione ID transazione](../../import/c-data-sources/datasrc-integrating-offline-data.md#section_30D6D47AEC0F4A36B87EBFE4C858F20C)
* [Integrazione transazione](../../import/c-data-sources/datasrc-integrating-offline-data.md#section_B3F281CEFF9B47E9A07F9851D61D415D)
* [Integrazione cliente](../../import/c-data-sources/datasrc-integrating-offline-data.md#section_9F4AAD710D2543BDA834090A98115FBF)

Queste integrazioni associano i dati offline a una transazione online specifica o a un visitatore online.

## Abilita registrazione ID transazione {#section_30D6D47AEC0F4A36B87EBFE4C858F20C}

L'ID transazione può essere abilitato/disabilitato dalla UI senza coinvolgere ClientCare:

Go to **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]** &gt; **[!UICONTROL[Select Report Suite]]** &gt; **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL General]** &gt; **[!UICONTROL General Account Settings]**.

<!-- 

<p>When contacting Customer Care, be prepared to provide the following information: </p> 
<ul id="ul_C425C7A074484650AFCCF0425E8E3F47"> 
 <li id="li_7640C0C4DF0C49749A3C37E5461DC22F">Report Suite ID of the data source for which you need transaction ID recording enabled. <p>In Data Sources, the report suite ID is the first part of the login appended by a random number that identifies the specific data source that was set up. For example, <code> RSID-drmossdev5 Login-drmossdev5_0001343430</code>. </p> </li> 
 <li id="li_4FB0E3EC7BE94A2DBEE9063365A71C9C">The Transaction ID expiration window (described in <a href="../../import/c-data-sources/datasrc-tid-visitor-profile.md#concept_0AF92491E8274BF69E66DB36E5F54A0F" format="dita" scope="local"> Transaction ID and Visitor Profiles</a>). By default this is 90 days, but it can be extended to up to 2 years. </li> 
</ul>

 -->

To see if Transaction ID Recording is enabled, navigate to **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Data Sources]**.

![](assets/transaction-ID-recording-active.png)

The [!UICONTROL Manage] tab displays the status of Transaction ID Recording.

## Integrazione cliente {#section_9F4AAD710D2543BDA834090A98115FBF}

Gli ID cliente vengono utilizzati per specificare l'attività offline di un cliente e collegarla all'attività online. Devono essere utilizzati quando:

* Un ID cliente è inserito nella variabile *`visitorID`* variabile.
* Non esiste un punto designato in cui l'attività del cliente passa offline, ad esempio un invio lead o acquisto.

Per configurare questo tipo di origine dati, consulta [Visitor ID](../../import/c-data-sources/c-datasrc-types/datasrc-visitorid.md#concept_1CFAA61D57A84B22A41F7A8E0DFCAAB5)

## Integrazione transazione {#section_B3F281CEFF9B47E9A07F9851D61D415D}

Gli ID transazione vengono utilizzati per registrare lo stato di un visitatore in un punto nel tempo. Devono essere utilizzati quando esiste un punto nel tempo in cui i clienti generalmente passano da un'esperienza online a offline, ad esempio:

* Invio di un lead a un venditore per contattare il cliente.
* Acquisto online, che potrebbe essere successivamente restituito in negozio.
* Acquisto di un prodotto per cui successivamente potrebbe verificarsi una chiamata di assistenza.

Il cliente è spesso anonimo quando passa da online a offline.

Gli eventi ID transazione non sono inclusi nelle metriche Partecipazione visita (mostrate nei rapporti di marketing), ma sono inclusi nelle metriche Partecipazione visitatore (disponibili solo nell'analisi ad hoc).

Questo perché i dati ID transazione non sono associati a una visita (perché l'evento offline generalmente non fa parte dell'evento online), ma sono associati al visitatore.

Consulta  [ID transazione](../../import/c-data-sources/c-datasrc-types/datasrc-transactionid.md#concept_A97302E9EC45468A8F30285FACE8C776).
