---
title: Integrazione DFA - Informazioni sulla fine del ciclo di vita
description: Perché l’Adobe termina il ciclo di vita del DFA Data Connector e quali alternative esistono?
translation-type: tm+mt
source-git-commit: 6669f678c1327b6af4a5b67c8033a9b7d8c9dbcf
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 1%

---


# Integrazione DFA - Informazioni sulla fine del ciclo di vita

Adobe ha recentemente annunciato [i suoi piani per la fine del ciclo di vita Data Connector](https://experienceleague.adobe.com/docs/analytics/import/dataconnectors/data-connectors-eol.html), un set di strumenti legacy per l&#39;integrazione di dati di terze parti (ad esempio ESP, VOC, ecc.) con Adobe Analytics.

## Perché i Data Connectors stanno terminando il ciclo di vita?

La piattaforma supportata per l&#39;integrazione dei partner è [Adobe Exchange](https://exchange.adobe.com/experiencecloud), progettata per facilitare l&#39;integrazione delle applicazioni di esperienza digitale di Adobe, l&#39;integrazione di CXM di terze parti e per supportare in futuro i vari requisiti di dati dei clienti e dei partner. Molti partner che avevano creato le loro integrazioni utilizzando i Data Connectors hanno già migrato tali integrazioni in Adobe Exchange, con più partner che intendono farlo.

## Perché l’integrazione DFA sta terminando?

In [gennaio 2020, Google ha annunciato](https://blog.chromium.org/2020/01/building-more-private-web-path-towards.html) che ritirerà gradualmente i cookie di terze parti in Chrome entro il 2022. Questo segue gli standard di settore impostati da Apple e Mozilla rispettivamente per i loro browser Safari e Firefox. L’integrazione del DFAE si basa fortemente sui cookie di terze parti e diventerà quindi inefficace e obsoleta con la rimozione dei cookie di terze parti nei tre principali browser Internet. Google [ha rafforzato questa posizione nel marzo 2021](https://blog.google/products/ads-commerce/a-more-privacy-first-web) annunciando che non rilasceranno soluzioni alternative.

Sfortunatamente, Google, che possiede l’integrazione DFA, è improbabile che lo replichi sulla piattaforma Adobe Exchange. Pertanto, stiamo procedendo partendo dal presupposto che, una volta che i Data Connectors andranno offline, l’integrazione esistente cesserà di funzionare e non avrà una sostituzione produttiva.

Un fattore importante e aggiuntivo è la capacità di &quot;view-through&quot; dell’integrazione DFA. Consente ad Adobe Analytics di tenere traccia dei casi in cui un utente ha visto un annuncio visualizzato, non ha fatto clic, ma ha successivamente visitato il sito web. Le &quot;View-through&quot; si basano su cookie di terze parti, che continueranno a essere gradualmente eliminate nel corso del 2021. Si tratta di una questione di mercato, non solo di un problema Adobe. Per il momento non esistono alternative per la replica di questi dati.

## Quali alternative esistono per lei?

Per i clienti interessati a integrare i dati degli annunci display (senza &quot;view-through&quot;) in Adobe Analytics, al momento sono disponibili le seguenti opzioni:

* I clienti Adobe Advertising Cloud DSP possono utilizzare [un&#39;integrazione di prodotto con Adobe Analytics](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/integrations/ad-cloud/introduction-to-the-analytics-for-advertising-cloud-dsp-integration.html?lang=en#integrations) per impostare i dati degli annunci display da Google ad Adobe Analytics. Questa integrazione è la nostra migliore alternativa e sarebbe il nostro consiglio per i clienti. Ad Cloud DSP consente ai clienti di fornire esperienze collegate tra tutti i canali pubblicitari, inclusi ricerca a pagamento, visualizzazione, video e altri. Puoi trovare ulteriori informazioni [qui](https://experienceleague.adobe.com/docs/advertising-cloud/dsp/introduction/dsp-about.html?lang=en#introduction). Tuttavia, l’DSP Ad Cloud sarà influenzata anche dalla perdita di cookie di terze parti.
* Adobe Experience Platform e [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=en), che forniscono funzionalità relative all&#39;integrazione di annunci display con altre origini dati. I clienti possono scaricare i dati di visualizzazione dal proprio provider di ricerca a pagamento e caricare tali dati in Experience Platform. Quindi inseriscono i dati direttamente in CJA per analizzarli insieme agli altri set di dati.
* Adobe Consulting (Engineering Architects) può creare una soluzione personalizzata per acquisire le metriche degli annunci display in Adobe Analytics. Questa soluzione è ancora in fase di sviluppo e tutti i clienti interessati a partecipare alla versione beta sono i benvenuti a partecipare. Maggiori dettagli sulle caratteristiche, la disponibilità e i costi saranno forniti non appena saranno disponibili.
* Puoi gestire la tua integrazione con gli annunci display, utilizzando la funzionalità Origini dati e le classificazioni in Adobe Analytics. Importa manualmente i dati di ricerca e visualizzazione a pagamento utilizzando Origini dati e Classificazioni [come descritto qui](https://experienceleague.adobe.com/docs/analytics/import/use-cases/paid-search-metrics.html?lang=en#use-cases). (Nota: questo documento si riferisce alla ricerca a pagamento, ma il caso d&#39;uso e il concetto sono gli stessi e possono essere applicati alla visualizzazione).

Per ulteriori domande o supporto, contatta l’ [Adobe Customer Care](https://helpx.adobe.com/it/contact/enterprise-support.ec.html).