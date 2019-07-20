---
description: Misura la quantità di entrate generate da tutti i tuoi prodotti in un periodo di tempo specifico.
seo-description: Misura la quantità di entrate generate da tutti i tuoi prodotti in un periodo di tempo specifico.
seo-title: Ricavi
solution: Analytics
title: Ricavi
topic: Rapporti
uuid: e 5 b 72798-f 5 c 7-440 d-a 62 d -376 bfd 115 ac 8
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Ricavi

Misura la quantità di entrate generate da tutti i tuoi prodotti in un periodo di tempo specifico.

Utilizzate Entrate per visualizzare il successo e la tendenza generali del sito. Potete anche utilizzarlo per periodi di out out in cui il sito ha avuto esito positivo, trovare l'origine e usarlo per campagne future.

## General Properties of Report {#section_97FC92DFB07D45A79F40B452F9AEE57B}

* Per raccogliere correttamente i dati, sono necessari requisiti che devono essere soddisfatti. Devono essere presenti le seguenti richieste di immagine:

   * A [!UICONTROL purchase] event must fire in the `s.events` variable.

   * The `products` variable must be defined with a number in the price field.
   * Ad esempio, questo valore passa $ 35.99 nel rapporto sulle entrate:

      ```js
       s.products="Mens;Shoes;1;35.99"
      ```

      ```js
       s.events="purchase"
      ```

* When more than one product is present in the [!UICONTROL s.products] variable, all count towards the revenue report. For example, [!DNL s.products="Mens;Socks;1;4.50,Womens;Socks;1;4.50"] would pass $9 in revenue to reporting.

   >[!NOTE]
   >
   >Le entrate non vengono moltiplicate se la quantità viene aumentata in un singolo prodotto. For example, [!DNL s.products="Womens;Socks;5;4.50"] does not pass $22.50 into reporting, it passes $4.50. Make sure your implementation passes the total revenue for the quantity listed ( [!DNL s.products="Womens;Socks;5;22.50"]).

* [!UICONTROL Revenue] arrotonda l'importo totale per un periodo di tempo al valore della valuta più vicino. Non arrotonda ogni singolo prodotto o hit.
* Dato che Analytics arrotonda ogni giorno alla valuta intera più vicina, il confronto tra la somma di ogni giorno al totale mensile e quello mensile è disattivato. poiché il totale mensile non è la somma di ogni giorno arrotondato, si tratta della somma assoluta arrotondato alla valuta intera più vicina.
* You can create a report that does not round revenue to the nearest whole currency by using a [calculated metric](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/).
* Unless using the `purchaseID` variable, users refreshing the page may inflate revenue as it sends this data to Adobe multiple times.
* Le suddivisioni orarie si basano sul fuso orario della suite di rapporti.
* Questo rapporto non contiene elementi della riga. Può essere visualizzato solo nel formato con tendenze.
* È possibile applicare un mese, un giorno, una settimana, un mese, un trimestre e un anno. Queste granularità sono disponibili a seconda dell'intervallo di date del rapporto.
* Questo rapporto può essere suddiviso dai report seguenti (a seconda delle impostazioni dell'organizzazione e della suite di rapporti):

   * [!UICONTROL Time Spent per Visit] rapporto.
   * [!UICONTROL Pages and Site Sections] rapporto.
   * [!UICONTROL Videos] rapporto.
   * [!UICONTROL Page Depth and Entry Pages] rapporto.
   * Most [!UICONTROL Traffic Sources]reports, including [!UICONTROL Search Keywords], [!UICONTROL Search Engines], and [!UICONTROL Referring Domains] reports.

   * [!UICONTROL Tracking Code] e tutti i rapporti classificazioni associati.
   * [!UICONTROL Products variable] e tutti i rapporti classificazioni associati. [!UICONTROL Categories] Report.

   * Almost all [!UICONTROL Visitor Profile] reports, excluding [!UICONTROL GeoSegmentation] reports.

   * All [!UICONTROL Custom Conversion] variables reports with basic subrelations.

* Le suddivisioni non sono disponibili per ora.

## Product-Specific Properties {#section_ED87FFD020634453AABE86B0248BE69B}

* This report can be accessed by going to **[!UICONTROL Conversion]** &gt; **[!UICONTROL Purchases]** &gt; **[!UICONTROL Revenue]**.

* [!UICONTROL Traffic Sources] sono disponibili suddivisioni sotto [!UICONTROL Finding Methods].

* This report can be accessed by going to **[!UICONTROL Site Metrics]** &gt; **[!UICONTROL Purchases]** &gt; **[!UICONTROL Revenue]**.

* In addition to all previously listed breakdowns, [!UICONTROL First and Last Touch Marketing Channel] breakdowns are available.

* This report can also be accessed by going to **[!UICONTROL Site Metrics]** &gt; **[!UICONTROL Purchases]** &gt; **[!UICONTROL Revenue]**.

* In addition to the previously mentioned breakdowns, [!UICONTROL List]variables and the current [!UICONTROL Video] variables can be used.

* Questo rapporto può utilizzare segmenti.

* Puoi suddividere ogni elemento del rapporto in base a tutti gli altri report e variabili, per visualizzare le suddivisioni in base a qualsiasi granularità desiderata.
* You can use all [!UICONTROL conversion] and [!UICONTROL traffic] metrics alongside [!UICONTROL Revenue]. You can use different allocation for all [!UICONTROL conversion] metrics.

* Questo rapporto può utilizzare più segmenti altamente avanzati.

Se il rapporto non è disponibile nel percorso specificato, rivolgetevi all'amministratore. Possono aver modificato il nome predefinito o la struttura del menu per soddisfare meglio le esigenze specifiche della tua organizzazione.
