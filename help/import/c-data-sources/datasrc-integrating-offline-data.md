---
description: Origini dati offre due modi aggiuntivi per integrare gli eventi che si verificano offline nei dati online.
subtopic: Data sources
title: Integrazione transazione e cliente
topic-fix: Developer and implementation
feature: Data Sources
exl-id: d4e4388b-6449-4fef-a94d-01b3a52c2190
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 69%

---

# Integrazione transazione e cliente

Origini dati offre due modi aggiuntivi per integrare gli eventi che si verificano offline nei dati online.

* [Abilitare la registrazione dell’ID transazione](/help/import/c-data-sources/datasrc-integrating-offline-data.md#section_30D6D47AEC0F4A36B87EBFE4C858F20C)
* [Integrazione transazione](/help/import/c-data-sources/datasrc-integrating-offline-data.md#section_B3F281CEFF9B47E9A07F9851D61D415D)
* [Integrazione cliente](/help/import/c-data-sources/datasrc-integrating-offline-data.md#section_9F4AAD710D2543BDA834090A98115FBF)

Queste integrazioni associano i dati offline a una transazione online specifica o a un visitatore online.

## Abilitare la registrazione dell’ID transazione {#section_30D6D47AEC0F4A36B87EBFE4C858F20C}

L&#39;ID transazione può essere abilitato/disabilitato dalla UI senza coinvolgere ClientCare:

Vai a **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > Seleziona suite di rapporti > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL General Account Settings]**.

<!-- 

<p>When contacting Customer Care, be prepared to provide the following information: </p> 
<ul id="ul_C425C7A074484650AFCCF0425E8E3F47"> 
 <li id="li_7640C0C4DF0C49749A3C37E5461DC22F">Report Suite ID of the data source for which you need transaction ID recording enabled. <p>In Data Sources, the report suite ID is the first part of the login appended by a random number that identifies the specific data source that was set up. For example, <code> RSID-drmossdev5 Login-drmossdev5_0001343430</code>. </p> </li> 
 <li id="li_4FB0E3EC7BE94A2DBEE9063365A71C9C">The Transaction ID expiration window (described in <a href="/help/import/c-data-sources/datasrc-tid-visitor-profile.md"  > Transaction ID and Visitor Profiles</a>). By default this is 90 days, but it can be extended to up to 2 years. </li> 
</ul>

 -->

Per verificare se la registrazione ID transazione è abilitata, passare a **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Data sources]**.

![](assets/transaction-ID-recording-active.png)

Il [!UICONTROL Manage] Questa scheda mostra lo stato della Registrazione ID transazione.

## Integrazione cliente {#section_9F4AAD710D2543BDA834090A98115FBF}

Gli ID cliente vengono utilizzati per specificare l&#39;attività offline di un cliente e collegarla all&#39;attività online. Devono essere utilizzati quando:

* Un ID cliente è inserito nella variabile *`visitorID`*. 
* Non esiste un punto designato in cui l&#39;attività del cliente passa offline, ad esempio un invio lead o acquisto.

Per configurare questo tipo di origine dati, consulta [ID visitatore](/help/import/c-data-sources/c-datasrc-types/datasrc-visitorid.md)

## Integrazione transazione {#section_B3F281CEFF9B47E9A07F9851D61D415D}

Gli ID transazione vengono utilizzati per registrare lo stato di un visitatore in un punto nel tempo. Devono essere utilizzati quando esiste un punto nel tempo in cui i clienti generalmente passano da un&#39;esperienza online a offline, ad esempio:

* Invio di un lead a un venditore per contattare il cliente.
* Acquisto online, che potrebbe essere successivamente restituito in negozio.
* Acquisto di un prodotto per cui successivamente potrebbe verificarsi una chiamata di assistenza.

Il cliente è spesso anonimo quando passa da online a offline.

Gli eventi ID transazione non sono inclusi nelle metriche di partecipazione alla visita (quelle visualizzate nei rapporti di marketing). Questo perché i dati ID transazione non sono associati a una visita (perché l’evento offline di solito non fa parte dell’evento online), ma sono associati al visitatore.

Consulta [ID transazione](/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md).
