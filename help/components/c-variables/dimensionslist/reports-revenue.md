---
description: Misura l'ammontare del reddito generato attraverso tutti i prodotti in un periodo di tempo specifico.
solution: Analytics
title: Ricavi
topic: Reports
uuid: e5b72798-f5c7-440d-a62d-376bfd115ac8
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Ricavi

Misura l'ammontare del reddito generato attraverso tutti i prodotti in un periodo di tempo specifico.

Utilizzate Revenue (Entrate) per visualizzare il successo e la tendenza generali del sito. Potete anche utilizzarlo per periodi singoli in cui il sito ha avuto un successo particolare, per trovare la fonte e utilizzarlo per campagne future.

## Proprietà generali del report {#section_97FC92DFB07D45A79F40B452F9AEE57B}

* Affinché il rapporto possa raccogliere correttamente i dati, è necessario soddisfare alcuni requisiti. Nella stessa richiesta immagine deve verificarsi quanto segue:

   * Un [!UICONTROL purchase] evento deve essere attivato nella `s.events` variabile.

   * La `products` variabile deve essere definita con un numero nel campo relativo al prezzo.
   * Ad esempio, questo passa $ 35,99 al report sulle entrate:

      ```js
       s.products="Mens;Shoes;1;35.99"
      ```

      ```js
       s.events="purchase"
      ```

* Se nella [!UICONTROL s.products] variabile è presente più di un prodotto, tutti i conteggi per il rapporto sulle entrate. Ad esempio, [!DNL s.products="Mens;Socks;1;4.50,Womens;Socks;1;4.50"] passerebbe $9 in ricavi a reporting.

   >[!NOTE]
   >
   >Le entrate non vengono moltiplicate se la quantità viene aumentata in un singolo prodotto. Ad esempio, [!DNL s.products="Womens;Socks;5;4.50"] non passa $22,50 nel reporting, ma passa $4,50. Assicurarsi che l'implementazione superi le entrate totali per la quantità indicata ( [!DNL s.products="Womens;Socks;5;22.50"]).

* [!UICONTROL Revenue] arrotonda l'importo totale per un periodo di tempo al valore della valuta più vicino. Non arrotonda ogni singolo prodotto o hit.
* Dal momento che Analytics arrotonda ogni giorno alla valuta intera più vicina, il confronto tra la somma di ogni giorno e il totale mensile è di un importo molto ridotto. Questo perché il totale mensile non è la somma di ogni giorno arrotondato, è la somma assoluta arrotondata alla valuta intera più vicina.
* È possibile creare un rapporto che non arrotonda le entrate alla valuta intera più vicina utilizzando una metrica [](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/)calcolata.
* A meno che non venga utilizzata la `purchaseID` variabile, gli utenti che aggiornano la pagina possono incrementare le entrate man mano che invia più volte tali dati ad Adobe.
* Le suddivisioni orari si basano sul fuso orario della suite di rapporti.
* Questo rapporto non contiene elementi di riga. Può essere visualizzato solo in formato con tendenze.
* È possibile applicare la granularità di ora, giorno, settimana, mese, trimestre e anno. Tali granularità sono disponibili a seconda dell'intervallo di date del rapporto.
* Questo rapporto può essere suddiviso per i seguenti rapporti (a seconda delle impostazioni dell'organizzazione e della suite di rapporti):

   * [!UICONTROL Time Spent per Visit] rapporto.
   * [!UICONTROL Pages and Site Sections] rapporto.
   * [!UICONTROL Videos] rapporto.
   * [!UICONTROL Page Depth and Entry Pages] rapporto.
   * La maggior parte [!UICONTROL Traffic Sources]dei rapporti, inclusi [!UICONTROL Search Keywords], [!UICONTROL Search Engines]e [!UICONTROL Referring Domains] i rapporti.

   * [!UICONTROL Tracking Code] report e tutti i report associati alle classificazioni.
   * [!UICONTROL Products variable] report e tutti i report associati alle classificazioni. Anche [!UICONTROL Categories] i rapporti.

   * Quasi tutti [!UICONTROL Visitor Profile] i rapporti, esclusi [!UICONTROL GeoSegmentation] quelli.

   * Tutti i rapporti [!UICONTROL Custom Conversion] delle variabili con le sottorerelazioni di base.

* Le suddivisioni non sono disponibili per ora.

## Proprietà specifiche del prodotto {#section_ED87FFD020634453AABE86B0248BE69B}

* Per accedere a questo rapporto, vai su **[!UICONTROL Conversion]** &gt; **[!UICONTROL Purchases]** &gt; **[!UICONTROL Revenue]**.

* [!UICONTROL Traffic Sources] le suddivisioni sono disponibili in [!UICONTROL Finding Methods].

* Per accedere a questo rapporto, vai su **[!UICONTROL Site Metrics]** &gt; **[!UICONTROL Purchases]** &gt; **[!UICONTROL Revenue]**.

* Oltre a tutte le suddivisioni elencate in precedenza, [!UICONTROL First and Last Touch Marketing Channel] sono disponibili anche le suddivisioni.

* Per accedere a questo rapporto, vai a **[!UICONTROL Site Metrics]** &gt; **[!UICONTROL Purchases]** &gt; **[!UICONTROL Revenue]**.

* Oltre alle suddivisioni precedentemente citate, è possibile utilizzare [!UICONTROL List]le variabili e le [!UICONTROL Video] variabili correnti.

* Questo rapporto può utilizzare segmenti.

* È possibile suddividere ogni elemento di questo rapporto per tutti gli altri rapporti e variabili, consentendo di visualizzare le suddivisioni per ogni granularità desiderata.
* Puoi utilizzare tutte [!UICONTROL conversion] e [!UICONTROL traffic] le metriche insieme a [!UICONTROL Revenue]. Puoi utilizzare un'allocazione diversa per tutte [!UICONTROL conversion] le metriche.

* Questo report può utilizzare più segmenti altamente avanzati.

Se il rapporto non è disponibile nel percorso specificato, rivolgiti all'amministratore. Potrebbero aver modificato il nome predefinito o la struttura del menu per soddisfare meglio le esigenze specifiche della tua organizzazione.
