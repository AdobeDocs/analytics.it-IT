---
description: Fornisce un'analisi completa, accurata e dettagliata dell'attività del cliente. Metriche come la gestione delle campagne, il ciclo di vendita, l'abbandono del cliente e la conversione del cliente consentono di misurare le transazioni di e-commerce, le fonti di vendita, l'efficacia della pubblicità, la fedeltà dei clienti e altro ancora.
seo-description: Fornisce un'analisi completa, accurata e dettagliata dell'attività del cliente. Metriche come la gestione delle campagne, il ciclo di vendita, l'abbandono del cliente e la conversione del cliente consentono di misurare le transazioni di e-commerce, le fonti di vendita, l'efficacia della pubblicità, la fedeltà dei clienti e altro ancora.
seo-title: Conversione
solution: Analytics
title: Conversione
topic: Rapporti
uuid: 457d3033-6562-4fba-8c2e-0e7a9be44bfd
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Conversione

Fornisce un'analisi completa, accurata e dettagliata dell'attività del cliente. Metriche come la gestione delle campagne, il ciclo di vendita, l'abbandono del cliente e la conversione del cliente consentono di misurare le transazioni di e-commerce, le fonti di vendita, l'efficacia della pubblicità, la fedeltà dei clienti e altro ancora.

Ad esempio, se desideri visualizzare il tipo di campagne interne sulla pagina principale che potrebbero dare luogo ad acquisti, devi prima acquisire i codici di tracciamento interni e impostare la persistenza su un periodo di una visita per le campagne *`s.eVar`* che acquisiscono le campagne interne. Quando un evento di successo viene completato (come l'acquisto), il credito per tale successo viene dato a qualsiasi variabile di conversione persistente sul visitatore, ad esempio ID campagna interna. L'esecuzione [!UICONTROL Internal Campaign Report]consente di vedere quale campagna ha generato la conversione più onsite.

Alcuni report out-of-the-box contengono sia le metriche Traffic (Traffico) che Conversion (Conversione) (come i [!UICONTROL Search Engine] report). Tuttavia, [!UICONTROL Traffic] e [!UICONTROL Conversion] i rapporti sono specifici della tua organizzazione e vengono visualizzati nei **[!UICONTROL Traffic]** menu e nei **[!UICONTROL Conversion]** menu.

**Proprietà report**

* [!UICONTROL Custom Conversion] i report sono basati su eVar (variabili di conversione).
* Le variabili di conversione possono persistere oltre la visualizzazione della pagina ed essere associate alle metriche entro la scadenza specificata.
* Le metriche predefinite dei report sono entrate. Per modificare le metriche predefinite, vedi [Selezione delle metriche](https://marketing.adobe.com/resources/help/en_US/sc/user/t_metrics_set_default.html)di report predefinite.
* Visualizzate questi rapporti sia in formato con tendenze che classifica.
* Puoi utilizzare Classificazioni in questi rapporti per rinominare e consolidare gli elementi di riga.
* Se sono abilitate le sottorelazioni di base, questi rapporti possono essere suddivisi per:

   * Campagne e prodotti, con tutte le classificazioni correlate
   * Fedeltà cliente
   * Tutte le eVar correlate a tutte le sottoscrizioni

* Sono disponibili altri rapporti con cui suddividere le sottorelazioni complete quando queste sono abilitate:

   * Tempo trascorso per ciascuna visita
   * Pagine e sezioni del sito, con tutte le classificazioni correlate
   * Pagine di entrata
   * Quasi tutti i rapporti Sorgenti di traffico
   * Numero visita
   * Molti rapporti sul profilo dei visitatori e sulla tecnologia
   * Tutte le altre eVar
   * Canali di marketing - Primo e ultimo tocco

* I seguenti eventi possono essere utilizzati come metriche:

   * Istanze, il numero di volte in cui è stata definita l'eVar
   * Tutte le metriche eCommerce standard: Entrate, Ordini, Unità, Carrelli, Visualizzazioni Carrello, Checkout, Aggiunte Carrello, Rimozioni Carrello.
   * Tutti gli eventi personalizzati: Eventi 1-80 ed Eventi 81-100 se con codice H22 o superiore
   * Visite e visitatori: Disponibile a seconda dell'organizzazione e della suite di rapporti. Contatta il tuo Account Manager per ulteriori informazioni

* La posizione di ciascun [!UICONTROL Custom Conversion] report varia a seconda del valore assegnato numerico dell'eVar. In genere, possono essere trovati nella [!UICONTROL Custom Conversion] cartella (a condizione che il menu non sia personalizzato).

