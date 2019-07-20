---
description: Misura il modo in cui vari codici di tracciamento pubblicitari influiscono su eventi di conversione diversi sul sito. Questo rapporto può essere utilizzato per misurare quali campagne specifiche funzionano meglio per eventi di successo diversi, o per vedere in che modo le campagne contribuiscono o si limitano alle iniziative del sito, ad esempio quelle generate dai ricavi.
seo-description: Misura il modo in cui vari codici di tracciamento pubblicitari influiscono su eventi di conversione diversi sul sito. Questo rapporto può essere utilizzato per misurare quali campagne specifiche funzionano meglio per eventi di successo diversi, o per vedere in che modo le campagne contribuiscono o si limitano alle iniziative del sito, ad esempio quelle generate dai ricavi.
seo-title: Codici di tracciamento
solution: Analytics
title: Codici di tracciamento
topic: Rapporti
uuid: c 893 d 592-10 fd -4 b 40-84 b 3-8 c 8949 a 67 b 25
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Codici di tracciamento

Misura il modo in cui vari codici di tracciamento pubblicitari influiscono su eventi di conversione diversi sul sito. Questo rapporto può essere utilizzato per misurare quali campagne specifiche funzionano meglio per eventi di successo diversi, o per vedere in che modo le campagne contribuiscono o si limitano alle iniziative del sito, ad esempio quelle generate dai ricavi.

**Proprietà generali**

* This report references data directly from the [s.campaign](/help/implement/js-implementation/c-variables/page-variables.md) variable implemented on your website.
* The variable this report is based on is a [conversion variable](/help/admin/admin/conversion-var-admin/conversion-var-admin.md). Ciò significa che può persistere oltre la visualizzazione della pagina e associarsi alle metriche entro la scadenza specificata.
* La metrica predefinita del report è Revenue (Entrate). You can change this default value in the [!UICONTROL Report Suite Manager] in [!UICONTROL Admin Tools]. ( **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Individual Report Settings]** &gt; **[!UICONTROL Default Metrics]**.)

* Questo rapporto può essere visualizzato sia nei formati con tendenze che in quelli classificati.
* Questo rapporto può utilizzare un filtro di ricerca per individuare elementi di righe specifiche.
* The [!UICONTROL Campaigns] and [!UICONTROL Creative Elements] reports are classifications based on this report, and are automatically created with each report suite.

* In questo rapporto possono essere utilizzate classificazioni SAINT, che consentono di rinominare e consolidare gli elementi della riga.
* Puoi suddividere questo rapporto in base ai report seguenti (a seconda delle impostazioni dell'organizzazione e della suite di rapporti):

   * Tempo trascorso per visita
   * Rapporti sulle pagine e sezioni Siti con tutte le classificazioni correlate
   * Profondità pagina, Pagine di partecipazione e pagine di immissione originali
   * Maggior parte dei rapporti sulle origini traffico
   * Numero visita e fedeltà cliente
   * Molti rapporti Profilo visitatore e tecnologia, eccetto Geosegmentazione
   * Tutte le variabili di conversione personalizzate

* In questo rapporto possono essere utilizzate le metriche seguenti (a seconda delle impostazioni dell'organizzazione e della suite di rapporti):

   * Click-throughs: the number of times the *`s.campaign`* variable is defined
   * Tutte le metriche standard ecommerce: Ricavi, Ordini, Unità, Carrelli, Visualizzazioni carrello, Pagamenti, Aggiunte carrello, Rimozioni carrello.
   * Tutti gli eventi personalizzati: Eventi 1-80 e Eventi 81-100 se sul codice H 22 o superiore
   * Visite e visitatori: dipende dalla società e dalla suite di rapporti. Per ulteriori informazioni, contattate l'Account Manager.

**Proprietà reporting e analisi**

* Click **[!UICONTROL Conversion]** &gt; **[!UICONTROL Campaigns]** &gt; **[!UICONTROL Tracking Code]** to locate this report, unless the menu is customized.

* This report can also be broken down by all [List Variables](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=list_var).
* Visualizzazioni di pagina, Visite ed Visitatori univoci sono disponibili come metriche.
* Questo rapporto può utilizzare i segmenti.

** Proprietà analisi ad hoc**

* Oltre alle variabili di conversione predefinite, puoi suddividere il rapporto Codice di tracciamento in base a tutti gli altri rapporti nell'interfaccia di reporting.
* Oltre a ecommerce e agli eventi personalizzati, puoi utilizzare tutte le metriche di conversione e traffico, nonché utilizzare allocazione diversa per tutte le metriche di conversione.
* Questo rapporto può utilizzare segmenti avanzati.

