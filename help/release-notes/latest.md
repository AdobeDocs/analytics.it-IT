---
title: Note sulla versione più recente di Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 62bc0da1de9303cb3a15731eac4f25ac294ddd4b
workflow-type: tm+mt
source-wordcount: '982'
ht-degree: 36%

---

# Note sulla versione corrente di Adobe Analytics (aprile 2022)

**Ultimo aggiornamento**: 19 aprile 2022

* Per le note sulla versione di marzo 2022, consulta [qui](/help/release-notes/2022.md).

* Per le note sulla versione di Customer Journey Analytics, consulta [qui](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=it).

* Per le note sulla versione di Media Analytics, vai [qui](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=en).

* Scopri gli ultimi aggiornamenti sulle versioni dei [prodotti Adobe Experience Cloud](https://business.adobe.com/it/products/adobe-experience-cloud-products.html). Ottieni la documentazione, i tutorial e i corsi di supporto autonomo più recenti su Experience League.


| Funzione | Descrizione | [Data definita](releases.md) |
| ----------- | ---------- | ------- |
| Aggiornamenti delle pagine di destinazione di Adobe Analytics | Aggiornamenti alla pagina di destinazione congiunta Workspace/Reports &amp; Analytics che migliora l’usabilità e la facilità di navigazione. [Ulteriori informazioni](/help/analyze/landing.md) | 20 aprile 2022 |
| [!UICONTROL Next item] o [!UICONTROL Previous item] Pannello Workspace | La [!UICONTROL Next or Previous item] consente di esplorare gli elementi che seguono o precedono un elemento dimensionale scelto. Ad esempio, utilizzalo se desideri visualizzare le pagine successive o precedenti in una pagina di prodotto specifica, in un canale di marketing o persino in un tipo di dispositivo. Questo pannello va oltre il reporting precedente/successivo legacy, perché consente di esaminare qualsiasi dimensione e non richiede alcuna nuova implementazione per ottenere informazioni approfondite. [Ulteriori informazioni](/help/analyze/analysis-workspace/c-panels/next-previous.md) | 20 aprile 2022 |
| [!UICONTROL Page Summary] Pannello Workspace | La [!UICONTROL Page Summary] fornisce un’analisi approfondita per una pagina a scelta. Fornisce gli stessi dettagli di Reports &amp; Analytics legacy [!UICONTROL Page Summary] report, più molto altro. [Ulteriori informazioni](/help/analyze/analysis-workspace/c-panels/page-summary.md) | 20 aprile 2022 |

{style=&quot;table-layout:auto&quot;}

## Correzioni in Adobe Analytics

* È stato risolto un problema in Feed dati a causa del quale le date di inizio e fine venivano modificate automaticamente dopo il salvataggio del Feed dati durante la creazione dall’interfaccia utente Feed dati. Le date si stavano aggiornando di un giorno. (AN-281262)

* È stato risolto un problema che impediva il rinnovo dei progetti pianificati tramite collegamento e-mail. (AN-283622)

### Ulteriori correzioni in Adobe Analytics

AN-274486; AN-279258; AN-279995; AN-280918; AN-281423; AN-282084; AN-282435; AN-283508; AN-283517; AN-283706; AN-283762; AN-283921; AN-284195; AN-284663; AN-284573; AN-284721; AN-284790; AN-284867; AN-284870; AN-284872; AN-284884; AN-284914; AN-284930; AN-284933; AN-284967; AN-284970; AN-285187; AN-285328; AN-285337; AN-285375; AN-285447; AN-285724; AN-285753; AN-285761;

## Avvisi importanti per gli amministratori di Adobe Analytics

| Avviso | Data di aggiunta o aggiornamento | Descrizione |
| ----------- | ---------- | ---------- |
| **Adesione a Cross-Device Analytics (CDA)** | 13 aprile 2022 | Efficace **1 maggio 2022**, qualsiasi nuova attuazione [CDA](/help/components/cda/overview.md) sarà limitato a un massimo di tre ID suite di rapporti (RSID) per cliente. |
| **Modifica del modo in cui Adobe Analytics gestisce i dati A4T raccolti tramite Experience Edge** | 31 marzo 2022 | Il 7 marzo 2022 è stato modificato il modo in cui vengono gestite alcune chiamate provenienti da Experience Edge che includono contenuti Target destinati al reporting di Analytics for Target (A4T). A partire dal 7 marzo, tutti gli hit con contenuti di reporting A4T sono stati modificati in modo da non essere trattati come eventi di visualizzazione pagina o di collegamento. Avvio **31 marzo 2022**, abbiamo modificato la nostra logica per renderla più selettiva in modo che gli eventi standard Visualizzazione pagina e Clic non vengano modificati. In futuro, gli unici eventi che verranno modificati saranno le chiamate di sola personalizzazione che hanno solo contenuto A4T. |
| **Aggiornamento dei metodi di crittografia del browser supportati per alcuni clienti** | 28 marzo 2022 | Adobe offre due livelli di sicurezza cifratura per soddisfare le diverse esigenze dei clienti in materia di sicurezza nella raccolta dati di prime parti. On **23 giugno 2022** verrà rimosso il supporto di alcuni algoritmi di crittografia HTTPS, noti come cifratori, per i clienti con il loro livello di sicurezza impostato su &quot;Elevato&quot;. Ciò significa che alcuni sistemi operativi meno recenti non saranno più in grado di inviare dati ad Analytics in quanto non supportano metodi di crittografia moderni. I clienti che utilizzano le impostazioni di protezione crittografata standard non saranno interessati. Tutti i clienti che utilizzano attualmente l’impostazione &quot;Alta&quot; sono già stati contattati direttamente. Un elenco dettagliato delle crittografie interessate da questa modifica è disponibile qui. |
| **Sospensione dei rapporti pianificati meno recenti** | 12 aprile 2022 | Efficace **20 aprile 2022**, Adobe intende mettere in pausa tutti i rapporti pianificati con una data di creazione maggiore di due anni (creati prima del 31 gennaio 2020). Nessun rapporto o dato verrà eliminato. Verranno messi in pausa solo i rapporti identificati come più vecchi di due anni e non verranno inviati ulteriori rapporti pianificati. Ulteriori informazioni |
| **Aggiornamenti per l’area geografica ISO 2022** | 11 marzo 2021 | Adobe eseguirà gli aggiornamenti di 2022 per l’area ISO su **10 giugno 2022**. Ci si aspetta di vedere piccoli aggiornamenti delle informazioni geografiche dopo questa versione. |
| **Sospensione delle attività di Report Builder pianificate precedenti** | 12 aprile 2022 | Efficace **20 aprile 2022**, Adobe intende mettere in pausa tutte le attività di Report Builder pianificate create più di due anni fa. In particolare, questa pausa si applica alle attività create prima del 31 gennaio 2020. Non verranno eliminate attività, cartelle di lavoro o dati. Tuttavia, le attività identificate come più vecchie di due anni verranno messe in pausa e non verranno inviate altre attività pianificate. Ulteriori informazioni |
| **Scadenza dell’estensione per inserire nell’elenco Consentiti EOL le integrazioni legacy di Analytics OAuth/JWT** | 14 gennaio 2022 | Il **25 maggio 2022** scadrà l’estensione per l’elenco Consentiti di [API di Analytics 1.3, API SOAP 1.4 e del servizio obsoleto Legacy OAuth/JWT di Analytics](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md). Questo offriva ai clienti che utilizzano le credenziali OAuth/JWT legacy di [!DNL Adobe Analytics] ulteriore tempo per migrare le integrazioni client alle [credenziali Adobe IMS](https://developer.adobe.com/console). Questa scadenza riguarda (ma non è limitata a) i clienti [!DNL Adobe Analytics Livestream] e [!DNL Adobe Campaign] che non hanno completato le migrazioni IMS richieste. I clienti che attualmente utilizzano versioni precedenti delle credenziali OAuth/JWT [!DNL Analytics] tramite l’estensione per inserire nell’elenco Consentiti e che non completano la migrazione alle credenziali IMS entro il 25 maggio 2022 perderanno l’accesso ai servizi Adobe. I clienti di Livestream possono fare riferimento a queste [istruzioni](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) durante la migrazione delle applicazioni client alle credenziali IMS. I clienti [!DNL Campaign] possono contattare il proprio account team Adobe per informazioni sull’aggiornamento alla versione più recente di [!DNL Campaign]. |
| **Fine del ciclo di vita per[!DNL Reports & Analytics]** | 4 gennaio 2022 | A partire dal **31 dicembre 2023**, Adobe intende terminare [!DNL Reports & Analytics] e i relativi rapporti e funzioni. I rapporti, le visualizzazioni e la tecnologia su cui si basa [!DNL Reports & Analytics] non soddisfano più gli standard tecnologici di Adobe. La maggior parte delle funzioni di [!DNL Reports & Analytics] sono disponibili in [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=it). A partire dal rilascio di Analysis Workspace nel 2015, le funzionalità e le caratteristiche di [!DNL Reports & Analytics] sono state trasferite ad Analysis Workspace ed è stata raggiunta una soglia di parità dei flussi di lavoro. [Questo avviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) spiega il processo di fine del ciclo di vita. |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement {#appm}

Per gli ultimi aggiornamenti sulle versioni di AppMeasurement (versione 2.22.4), fai riferimento alle [note sulla versione di AppMeasurement per JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=it).

>[!MORELIKETHIS]
>[[!DNL Customer Journey Analytics] note sulla versione](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=en)
