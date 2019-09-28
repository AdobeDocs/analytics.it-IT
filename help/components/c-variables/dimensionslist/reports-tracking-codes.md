---
description: Misura il modo in cui vari codici di monitoraggio pubblicitario influiscono sui diversi eventi di conversione sul sito. Questo rapporto può essere utilizzato per misurare le prestazioni di campagne specifiche per diversi eventi di successo o per vedere in che modo le campagne aiutano o ostacolano le iniziative del sito, ad esempio quali campagne generano il maggior numero di entrate.
seo-description: Misura il modo in cui vari codici di monitoraggio pubblicitario influiscono sui diversi eventi di conversione sul sito. Questo rapporto può essere utilizzato per misurare le prestazioni di campagne specifiche per diversi eventi di successo o per vedere in che modo le campagne aiutano o ostacolano le iniziative del sito, ad esempio quali campagne generano il maggior numero di entrate.
seo-title: Codici di tracciamento
solution: Analytics
title: Codici di tracciamento
topic: Rapporti
uuid: c893d592-10fd-4b40-84b3-8c8949a67b25
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Codici di tracciamento

Misura il modo in cui vari codici di monitoraggio pubblicitario influiscono sui diversi eventi di conversione sul sito. Questo rapporto può essere utilizzato per misurare le prestazioni di campagne specifiche per diversi eventi di successo o per vedere in che modo le campagne aiutano o ostacolano le iniziative del sito, ad esempio quali campagne generano il maggior numero di entrate.

**Proprietà generali**

* Questo rapporto fa riferimento direttamente ai dati della variabile [s.campaign](/help/implement/js-implementation/c-variables/page-variables.md) implementata sul sito Web.
* La variabile su cui si basa il rapporto è una variabile [di](/help/admin/admin/conversion-var-admin/conversion-var-admin.md)conversione. Ciò significa che può persistere oltre la visualizzazione della pagina e associarsi alle metriche entro la scadenza specificata.
* La metrica predefinita del report è Revenue (Entrate). È possibile modificare questo valore predefinito nella [!UICONTROL Report Suite Manager] casella in [!UICONTROL Admin Tools]. ( **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Individual Report Settings]** &gt; **[!UICONTROL Default Metrics]**.)

* Questo rapporto può essere visualizzato sia in formato con tendenze che in formato classifica.
* Questo rapporto può utilizzare un filtro di ricerca per individuare specifici elementi di riga.
* I [!UICONTROL Campaigns] rapporti e [!UICONTROL Creative Elements] le classificazioni si basano su questo rapporto e vengono creati automaticamente con ogni suite di rapporti.

* Le classificazioni SAINT possono essere utilizzate in questo rapporto, consentendo di rinominare e consolidare gli elementi di riga.
* Puoi suddividere il rapporto in base ai seguenti rapporti (in base alle impostazioni dell'organizzazione e della suite di rapporti):

   * Tempo trascorso per ciascuna visita
   * Report Pagine e sezioni del sito, con tutte le classificazioni correlate
   * Profondità pagina, pagine di entrata e pagine di entrata originali
   * Report sulla maggior parte delle origini di traffico
   * Numero visita e fedeltà cliente
   * Molti rapporti sul profilo dei visitatori e sulla tecnologia, esclusa la segmentazione geografica
   * Tutte le variabili di conversione personalizzate

* Le metriche seguenti possono essere utilizzate in questo rapporto (a seconda delle impostazioni dell'organizzazione e della suite di rapporti):

   * Click-through: il numero di volte in cui è definita la *`s.campaign`* variabile
   * Tutte le metriche eCommerce standard: Entrate, Ordini, Unità, Carrelli, Visualizzazioni Carrello, Checkout, Aggiunte Carrello, Rimozioni Carrello.
   * Tutti gli eventi personalizzati: Eventi 1-80 ed Eventi 81-100 se con codice H22 o superiore
   * Visite e visitatori: la disponibilità dipende dall'organizzazione e dalla suite di rapporti. Per ulteriori informazioni, contattate l'Account Manager.

**Proprietà Reporting e analisi**

* Fate clic **[!UICONTROL Conversion]** &gt; **[!UICONTROL Campaigns]** &gt; **[!UICONTROL Tracking Code]** per individuare il rapporto, a meno che il menu non sia personalizzato.

* Questo rapporto può essere suddiviso per tutte le variabili [](https://marketing.adobe.com/resources/help/en_US/sc/implement/list_var.html)elenco.
* Visualizzazioni di pagina, Visite e Visitatori unici sono disponibili come metriche.
* Questo report può utilizzare segmenti.

** Proprietà Analisi ad hoc*

* Oltre alla maggior parte delle variabili di conversione pronte all’uso, puoi suddividere il rapporto Codice di tracciamento per tutti gli altri rapporti all’interno dell’interfaccia di reporting.
* Oltre agli eventi eCommerce e personalizzati, puoi utilizzare tutte le metriche di conversione e traffico, nonché un'allocazione diversa per tutte le metriche di conversione.
* Questo rapporto può utilizzare segmenti avanzati.

