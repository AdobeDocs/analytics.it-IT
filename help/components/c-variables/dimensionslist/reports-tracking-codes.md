---
description: Misura il modo in cui vari codici di monitoraggio pubblicitario influiscono sui diversi eventi di conversione sul sito. Questo rapporto può essere utilizzato per misurare le prestazioni di campagne specifiche per diversi eventi di successo o per vedere in che modo le campagne aiutano o ostacolano le iniziative del sito, ad esempio quali campagne generano il maggior numero di entrate.
title: Codici di tracciamento
topic: Reports
uuid: c893d592-10fd-4b40-84b3-8c8949a67b25
translation-type: tm+mt
source-git-commit: 3fe3442eae1bdd8b90acffc9c25d184714613c16

---


# Codici di tracciamento

Misura il modo in cui vari codici di monitoraggio pubblicitario influiscono sui diversi eventi di conversione sul sito. Questo rapporto può essere utilizzato per misurare le prestazioni di campagne specifiche per diversi eventi di successo o per vedere in che modo le campagne aiutano o ostacolano le iniziative del sito, ad esempio quali campagne generano il maggior numero di entrate.

**Proprietà generali**

* Questo rapporto fa riferimento direttamente ai dati provenienti dalla campagna [s.campaign](/help/implement/vars/page-vars/campaign.md)
* La variabile su cui si basa il rapporto è una variabile [di](/help/admin/admin/conversion-var-admin/conversion-var-admin.md)conversione. Ciò significa che può persistere oltre la visualizzazione della pagina e associarsi alle metriche entro la scadenza specificata.
* La metrica predefinita del report è Revenue (Entrate). È possibile modificare questo valore predefinito nella [!UICONTROL Report Suite Manager] casella in [!UICONTROL Admin Tools]. ( **[!UICONTROL Edit Settings]** > **[!UICONTROL Individual Report Settings]** > **[!UICONTROL Default Metrics]**.)

* Questo rapporto può essere visualizzato sia in formato con tendenze che in formato classifica.
* Questo rapporto può utilizzare un filtro di ricerca per individuare specifici elementi di riga.
* I [!UICONTROL Campaigns] rapporti e [!UICONTROL Creative Elements] le classificazioni si basano su questo rapporto e vengono creati automaticamente con ogni suite di rapporti.

* Le classificazioni SAINT possono essere utilizzate in questo rapporto, consentendo di rinominare e consolidare gli elementi di riga.
* Puoi suddividere il rapporto in base ai seguenti rapporti (in base alle impostazioni dell&#39;organizzazione e della suite di rapporti):

   * Tempo trascorso per ciascuna visita
   * Report Pagine e sezioni del sito, con tutte le classificazioni correlate
   * Profondità pagina, pagine di entrata e pagine di entrata originali
   * Report sulla maggior parte delle origini di traffico
   * Numero visita e fedeltà cliente
   * Molti rapporti sul profilo dei visitatori e sulla tecnologia, esclusa la segmentazione geografica
   * Tutte le variabili di conversione personalizzate

* Le metriche seguenti possono essere utilizzate in questo rapporto (a seconda delle impostazioni dell&#39;organizzazione e della suite di rapporti):

   * Click-through: il numero di volte in cui è definita la *`s.campaign`* variabile
   * Tutte le metriche standard di eCommerce: Entrate, Ordini, Unità, Carrelli, Visualizzazioni Carrello, Checkout, Aggiunte Carrello, Rimozioni Carrello.
   * Tutti gli eventi personalizzati: Eventi 1-80 ed Eventi 81-100 se con codice H22 o superiore
   * Visite e visitatori: la disponibilità dipende dall&#39;organizzazione e dalla suite di rapporti. Per ulteriori informazioni, contattate l&#39;Account Manager.

**Proprietà Reporting e analisi**

* Fate clic **[!UICONTROL Conversion]** > **[!UICONTROL Campaigns]** > **[!UICONTROL Tracking Code]** per individuare il rapporto, a meno che il menu non sia personalizzato.

* Questo rapporto può essere anche suddiviso per tutte le variabili [](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/conversion-variables/list-var-admin.html)elenco.
* Visualizzazioni di pagina, Visite e Visitatori unici sono disponibili come metriche.
* Questo report può utilizzare segmenti.

**Proprietà di analisi ad hoc**

* Oltre alla maggior parte delle variabili di conversione pronte all’uso, puoi suddividere il rapporto Codice di tracciamento per tutti gli altri rapporti all’interno dell’interfaccia di reporting.
* Oltre agli eventi eCommerce e personalizzati, puoi utilizzare tutte le metriche di conversione e traffico, nonché un&#39;allocazione diversa per tutte le metriche di conversione.
* Questo rapporto può utilizzare segmenti avanzati.

