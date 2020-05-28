---
description: Il rapporto Panoramica canale di marketing è progettato per fornire informazioni di alto livello sui metodi più efficaci per i clienti che arrivano sul sito. Utilizzate questo rapporto per allocare metriche di successo e ricavi a vari canali. Puoi anche visualizzare le campagne o le parole chiave specifiche all'interno di ciascun canale che hanno maggior successo. Contiene una propria interfaccia univoca e intuitiva, che consente di visualizzare contemporaneamente sia la prima che l’ultima metrica touch.
title: Panoramica sul canale di marketing
topic: Reports
uuid: e4542014-2098-4f4a-ac0d-97587182d6cc
translation-type: tm+mt
source-git-commit: ad991b8fcc309d1f3aae01d472683927a447ab4d
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 1%

---


# Panoramica sul canale di marketing

Il rapporto Panoramica canale di marketing è progettato per fornire informazioni di alto livello sui metodi più efficaci per i clienti che arrivano sul sito. Utilizzate questo rapporto per allocare metriche di successo e ricavi a vari canali. Puoi anche visualizzare le campagne o le parole chiave specifiche all&#39;interno di ciascun canale che hanno maggior successo. Contiene una propria interfaccia univoca e intuitiva, che consente di visualizzare contemporaneamente sia la prima che l’ultima metrica touch.

## Proprietà generali {#section_87F54048CE5445F7A6C795C7787C530A}

* Questo rapporto dipende esclusivamente dalle regole di [elaborazione](/help/components/c-marketing-channels/c-rules.md)del canale di marketing. La modifica di queste regole modifica il modo in cui vengono calcolati i dati in questo rapporto.
* L&#39;ordine delle regole di elaborazione è fondamentale per il funzionamento di Marketing Channels. Ogni hit verifica prima i criteri nella parte superiore delle regole di elaborazione, quindi filtra verso il basso.
* Questo rapporto è composto da due suddivisioni: i canali stessi e i relativi dettagli di canale. Facendo clic sul pulsante &quot;+&quot; accanto a ciascun canale, vengono visualizzati i relativi dettagli.
* È possibile aggiungere solo quattro metriche a ciascuna colonna. Tuttavia, il numero di colonne utilizzabili non è limitato.
* Una piccola linea di tendenza è visibile alla fine dell’ultima colonna. Questa linea di tendenza può scorrere tra le metriche attive.
* Oltre ai vari canali raccolti con metodi standard, è possibile utilizzare origini dati offline.
* [È possibile utilizzare le classificazioni](/help/components/c-classifications2/c-classifications.md) , per rinominare e consolidare gli elementi di riga.
* Le metriche seguenti possono essere utilizzate in questo rapporto (a seconda delle impostazioni dell&#39;organizzazione e della suite di rapporti):

   * **ClickThrough**: il numero di volte che la *`s.campaign`* variabile viene definita.
   * [Nuovi impegni](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-new-engagements.html): il numero di visitatori che hanno ricevuto un nuovo Primo canale di contatto.
   * Tutte le metriche standard di eCommerce: Entrate, Ordini, Unità, Carrelli, Visualizzazioni Carrello, Checkout, Aggiunte Carrello, Rimozioni Carrello.
   * Tutti gli eventi personalizzati: Eventi 1-80 ed Eventi 81-100 se nel codice H22 o versioni successive.
   * **Visite** e **visitatori**: richiede Visite e Visitatori di Commerce, che dipendono dall&#39;organizzazione e dalla suite di rapporti. Per ulteriori informazioni, contattate l&#39;Account Manager.
   * **Bilancio** e **costi**: metriche specifiche per Marketing Channels (Canali di marketing). See [Costs and Budgets](https://docs.adobe.com/content/help/en/analytics/components/marketing-channels/analyze-mc.html).

## Proprietà specifiche del prodotto {#section_0C78D294D00942FD9A26D37CB5D645AE}

**Versioni 14 e 15**

È possibile accedere a questo rapporto scegliendo **[!UICONTROL Marketing Channels]** > **[!UICONTROL Channel Overview Report]** (a condizione che il menu non sia personalizzato).

La segmentazione non è disponibile in questo rapporto. Utilizzate invece i [!UICONTROL First- or Last-Touch Channel] rapporti o [!UICONTROL First- or Last-Touch Details] .

**Ad Hoc Analysis**

Anche se non [!UICONTROL Marketing Channel Overview Report] è disponibile, i report Marketing Channel sono accessibili con metriche con allocazione diversa. Questo consente di ricreare in modo efficace un rapporto molto simile.

Questo rapporto può sfruttare più segmenti avanzati.
