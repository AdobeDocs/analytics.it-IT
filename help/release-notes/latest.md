---
title: Note sulla versione più recente di Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: c29515da8c74ad3332aa9797db9de505af7fe3aa
workflow-type: tm+mt
source-wordcount: '1056'
ht-degree: 60%

---

# Note sulla versione corrente di Adobe Analytics (aprile 2022)

**Ultimo aggiornamento**: 28 aprile 2022

## Risorse correlate

* [Note sulla versione precedente per il 2022](/help/release-notes/2022.md)
* [Note sulla versione di Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Note sulla versione di Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* Ultimi aggiornamenti sulla versione di [Prodotti Adobe Experience Cloud](https://business.adobe.com/it/products/adobe-experience-cloud-products.html)

## Nuove funzioni di Adobe Analytics

| Funzione | Descrizione | [Data definita](releases.md) |
| ----------- | ---------- | ------- |
| Aggiornamenti pagina di destinazione di Adobe Analytics | Aggiornamenti alla pagina di destinazione congiunta Workspace/Reports &amp; Analytics che migliora l’usabilità e la facilità di navigazione. [Ulteriori informazioni](/help/analyze/landing.md) | 20 aprile 2022 |
| Pannello Workspace [!UICONTROL Next item] o [!UICONTROL Previous item]  | Il panello [!UICONTROL Next or Previous item] consente di esplorare gli elementi che seguono o precedono un elemento dimensionale scelto. Ad esempio, utilizzalo se desideri visualizzare le pagine successive o precedenti in una pagina di prodotto specifica, in un canale di marketing o persino in un tipo di dispositivo. Questo pannello va oltre il reporting legacy precedente/successivo, perché consente di esaminare qualsiasi dimensione e non richiede alcuna nuova implementazione per ottenere informazioni approfondite. [Ulteriori informazioni](/help/analyze/analysis-workspace/c-panels/next-previous.md) | 20 aprile 2022 |
| Pannello Workspace [!UICONTROL Page Summary]  | Il pannello [!UICONTROL Page Summary] fornisce un’analisi approfondita per una pagina a scelta. Fornisce gli stessi dettagli del report legacy Reports &amp; Analytics [!UICONTROL Page Summary] e molto altro. [Ulteriori informazioni](/help/analyze/analysis-workspace/c-panels/page-summary.md) | 20 aprile 2022 |
| Obbligo di `x-proxy-global-company-id` intestazione per le chiamate API 2.0 | Le API di Adobe Analytics 2.0 non richiedono più il `x-proxy-global-company-id` , poiché queste informazioni fanno parte dell’URL dell’endpoint. Puoi comunque includere questa intestazione, ma non ricevi più un errore se manca. | 20 aprile 2022 |

{style=&quot;table-layout:auto&quot;}

## Correzioni in Adobe Analytics

* È stato risolto un problema nel Feed dati a causa del quale le date di inizio e di fine venivano modificate automaticamente dopo il salvataggio del Feed dati durante la creazione dalla relativa interfaccia utente. Le date si stavano aggiornando di un giorno. (AN-281262)
* È stato risolto un problema che impediva il rinnovo dei progetti pianificati tramite collegamento e-mail. (AN-283622)
* È stato risolto un problema che impediva la corretta identificazione delle versioni recenti di Apple Safari e Microsoft Edge nella tabella di ricerca del tipo di browser di Adobe. Simile a quando [le versioni del browser vengono aggiornate](/help/components/dimensions/browser.md), aggiornamenti alle tabelle di ricerca del tipo di browser solo i dati corretti che avanzano. Le tabelle di ricerca per la versione del browser sono state aggiornate il 20 aprile e le tabelle di ricerca per il tipo di browser sono state aggiornate il 28 aprile. (AN-284872; AN-285753; (AN-286257)

### Ulteriori correzioni in Adobe Analytics

AN-274486; AN-279258; AN-279995; AN-280918; AN-281423; AN-282084; AN-282435; AN-283508; AN-283517; AN-283706; AN-283762; AN-283921; AN-284195; AN-284663; AN-284573; AN-284721; AN-284790; AN-284867; AN-284870; AN-284872; AN-284884; AN-284914; AN-284930; AN-284933; AN-284967; AN-284970; AN-285187; AN-285328; AN-285337; AN-285375; AN-285447; AN-285724; AN-285753; AN-285761

## Avvisi importanti per gli amministratori di Adobe Analytics

| Avviso | Data di aggiunta o aggiornamento | Descrizione |
| ----------- | ---------- | ---------- |
| **Adesione a Cross-Device Analytics (CDA)** | 13 aprile 2022 | Efficace **1 maggio 2022**, qualsiasi nuova attuazione [CDA](/help/components/cda/overview.md) sono limitati a un massimo di tre ID suite di rapporti (RSID) per cliente. |
| **Modifica del modo in cui Adobe Analytics gestisce i dati A4T raccolti tramite Experience Edge** | 31 marzo 2022 | Il 7 marzo 2022 Analytics ha modificato il modo in cui gestisce alcune chiamate provenienti da Experience Edge che includono il contenuto Target destinato al reporting di Analytics for Target (A4T). A partire dal 7 marzo, tutti gli hit con contenuti di reporting A4T vengono modificati in modo da non essere trattati come eventi di visualizzazione pagina o di collegamento. Avvio **31 marzo 2022**, la logica è più selettiva in modo che gli eventi Visualizzazione pagina e Clic standard non vengano modificati. In futuro, gli unici eventi modificati sono le chiamate di sola personalizzazione che hanno solo contenuto A4T. |
| **Aggiornamento dei metodi di crittografia del browser supportati per alcuni clienti** | 28 marzo 2022 | Adobe offre due livelli di protezione crittografata per soddisfare le diverse esigenze dei clienti in materia di sicurezza nella raccolta dati di prime parti. On **23 giugno 2022** Il supporto viene rimosso per alcuni algoritmi di crittografia HTTPS, noti come cifratori, per i clienti il cui livello di sicurezza è impostato su &quot;Elevato&quot;. Ciò significa che alcuni sistemi operativi meno recenti non sono più in grado di inviare dati ad Analytics in quanto non supportano metodi di crittografia moderni. I clienti che utilizzano le impostazioni di protezione crittografata standard non sono interessati. Tutti i clienti che utilizzano attualmente l’impostazione “Elevato” sono già stati contattati direttamente. Un elenco dettagliato delle crittografie interessate da questa modifica è disponibile qui. |
| **Sospensione dei rapporti pianificati meno recenti** | 12 aprile 2022 | A decorrere dal **20 aprile 2022**, Adobe intende sospendere tutti i rapporti pianificati con una data di creazione superiore ai due anni (creati prima del 31 gennaio 2020). Nessun rapporto o dato viene eliminato. Vengono messi in pausa solo i rapporti identificati come più vecchi di due anni e non vengono inviati ulteriori rapporti pianificati. Ulteriori informazioni |
| **Aggiornamenti per area geografica ISO 2022** | 11 marzo 2021 | Adobe prevede di eseguire gli aggiornamenti dell&#39;area ISO 2022 su **10 giugno 2022**. Con questa versione, sono previsti aggiornamenti delle informazioni geografiche minori. |
| **Sospensione delle precedenti attività di Report Builder pianificate** | 12 aprile 2022 | A decorrere dal **20 aprile 2022**, Adobe intende sospendere tutte le attività di Report Builder pianificate create più di due anni fa. In particolare, questa sospensione si applica alle attività create prima del 31 gennaio 2020. Non vengono eliminate attività, cartelle di lavoro o dati. Tuttavia, le attività identificate come più vecchie di due anni vengono messe in pausa e non vengono inviate altre attività pianificate. Ulteriori informazioni |
| **Scadenza dell’estensione per inserire nell’elenco Consentiti EOL le integrazioni legacy di Analytics OAuth/JWT** | 14 gennaio 2022 | On **25 maggio 2022**, [API di Analytics 1.3, API SOAP 1.4 e EOL legacy di Analytics OAuth/JWT di Analytics](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md) inserire nell&#39;elenco Consentiti scadenza dell’estensione del . Questo offriva ai clienti che utilizzano le credenziali OAuth/JWT legacy di [!DNL Adobe Analytics] ulteriore tempo per migrare le integrazioni client alle [credenziali Adobe IMS](https://developer.adobe.com/console). Questa scadenza riguarda (ma non è limitata a) i clienti [!DNL Adobe Analytics Livestream] e [!DNL Adobe Campaign] che non hanno completato le migrazioni IMS richieste. Clienti che attualmente utilizzano versioni precedenti [!DNL Analytics] Le credenziali OAuth/JWT tramite l’estensione inserire nell&#39;elenco Consentiti e che non completano la migrazione alle credenziali IMS entro il 25 maggio 2022 perdono l’accesso ai servizi Adobe. I clienti di Livestream possono fare riferimento a queste [istruzioni](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) durante la migrazione delle applicazioni client alle credenziali IMS. I clienti [!DNL Campaign] possono contattare il proprio account team Adobe per informazioni sull’aggiornamento alla versione più recente di [!DNL Campaign]. |
| **Fine del ciclo di vita per[!DNL Reports & Analytics]** | 4 gennaio 2022 | A partire dal **31 dicembre 2023**, Adobe intende terminare [!DNL Reports & Analytics] e i relativi rapporti e funzioni. I rapporti, le visualizzazioni e la tecnologia su cui si basa [!DNL Reports & Analytics] non soddisfano più gli standard tecnologici di Adobe. La maggior parte delle funzioni di [!DNL Reports & Analytics] sono disponibili in [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=it). A partire dal rilascio di Analysis Workspace nel 2015, le funzionalità e le caratteristiche di [!DNL Reports & Analytics] sono state trasferite ad Analysis Workspace ed è stata raggiunta una soglia di parità dei flussi di lavoro. [Questo avviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) spiega il processo di fine del ciclo di vita. |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement {#appm}

Per gli ultimi aggiornamenti sulle versioni di AppMeasurement (versione 2.22.4), fai riferimento alle [note sulla versione di AppMeasurement per JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=it).

>[!MORELIKETHIS]
>[[!DNL Customer Journey Analytics] note sulla versione](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=en)
