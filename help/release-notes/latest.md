---
title: Note sulla versione più recente di Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 1e8aa373bcb2714c6b2c7605e1ea7c7c462b89e7
workflow-type: tm+mt
source-wordcount: '1152'
ht-degree: 40%

---

# Note sulla versione corrente di Adobe Analytics (marzo 2022)

**Ultimo aggiornamento: 12 aprile 2022**

* Per le note sulla versione di febbraio 2022, consulta [qui](/help/release-notes/2022.md).
* Per le note sulla versione di Customer Journey Analytics, consulta [qui](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=it)
* Per le note sulla versione di Media Analytics, vai [qui](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=en)
* Scopri gli ultimi aggiornamenti sulle versioni dei [prodotti Adobe Experience Cloud](https://business.adobe.com/it/products/adobe-experience-cloud-products.html). Ottieni la documentazione, i tutorial e i corsi di supporto autonomo più recenti su Experience League.

## Nuove funzioni di Adobe Analytics {#aa-features}

| Funzione | Descrizione | [Data definita](releases.md) |
| ----------- | ---------- | ------- |
| Annotazioni in Workspace | Le annotazioni in Workspace consentono di comunicare in modo efficace sfumature di dati e informazioni contestuali all’organizzazione. [Ulteriori informazioni](/help/analyze/analysis-workspace/components/annotations/overview.md) | Il rollout graduale inizia il 23 marzo 2022. Disponibilità generale: 11 aprile 2022 |
| Aggiornamenti delle pagine di destinazione di Adobe Analytics | Aggiornamenti alla pagina di destinazione congiunta Workspace/Reports &amp; Analytics che migliora l’usabilità e la facilità di navigazione. [Ulteriori informazioni](/help/analyze/landing.md) | 20 aprile 2022 |
| [!UICONTROL Next item] o [!UICONTROL Previous item] Pannello Workspace | La [!UICONTROL Next or Previous item] consente di esplorare gli elementi che seguono o precedono un elemento dimensionale scelto. Ad esempio, utilizzalo se desideri visualizzare le pagine successive o precedenti in una pagina di prodotto specifica, in un canale di marketing o persino in un tipo di dispositivo. Questo pannello va oltre il reporting precedente/successivo legacy, perché consente di esaminare qualsiasi dimensione e non richiede alcuna nuova implementazione per ottenere informazioni approfondite. | 20 aprile 2022 |
| [!UICONTROL Page Summary] Pannello Workspace | La [!UICONTROL Page Summary] fornisce un’analisi approfondita per una pagina a scelta. Fornisce gli stessi dettagli di Reports &amp; Analytics legacy [!UICONTROL Page Summary] report, più molto altro. | 20 aprile 2022 |

{style=&quot;table-layout:auto&quot;}

## Correzioni in Adobe Analytics

* È stato risolto un problema che causava un errore durante il tentativo di accesso ad Activity Map. (AN-267177)
* È stato risolto un problema relativo ai trasferimenti di risorse utente non riusciti. (AN-279813)
* Sono stati risolti i problemi relativi al pannello Area di lavoro A4T . (AN-281594; AN-282418)
* È stato risolto un problema che impediva ad alcuni utenti di accedere ad Adobe Analytics. (AN-282776)
* Sono stati risolti dei problemi a causa dei quali alcune suite di rapporti appena create non raccoglievano dati. (AN-283114, AN-283311)
* Sono stati risolti i problemi relativi alle e-mail dei feed di dati inviate in modo errato. (AN-280255; AN-282051)

### Ulteriori correzioni in Adobe Analytics

AN-256929; AN-270937; AN-272158; AN-275130; AN-277830; AN-278635; AN-279066; AN-279683; AN-279899; AN-280504; AN-280617; AN-280663; AN-281423; AN-281523; AN-281608; AN-281671; AN-281963; AN-282027; AN-282218; AN-282593; AN-282605; AN-282632; AN-282654; AN-282694; AN-282744; AN-282756; AN-282804; AN-282838; AN-282862; AN-282903; AN-282937; AN-282892; AN-283315; AN-283338; AN-283388; AN-283417; AN-283474; AN-283511; AN-283691, AN-283895; AN-283943; AN-283957; AN-284030; AN-284100; AN-284142; AN-284162

## Avvisi importanti per gli amministratori di Adobe Analytics

| Avviso | Data di aggiunta o aggiornamento | Descrizione |
| ----------- | ---------- | ---------- |
| Modifica del modo in cui Analytics gestisce i dati A4T raccolti tramite Experience Edge | 31 marzo 2022 | On **7 marzo 2022**, abbiamo modificato il modo in cui gestiamo alcune chiamate provenienti da Experience Edge che includono il contenuto Target destinato al reporting di Analytics for Target (A4T). A partire dal 7 marzo, tutti gli hit con contenuti di reporting A4T sono stati modificati in modo da non essere trattati come eventi di visualizzazione pagina o di collegamento. **A partire dal 31 marzo 2022**, abbiamo modificato la nostra logica per renderla più selettiva in modo che gli eventi standard Visualizzazione pagina e Clic non vengano modificati. In futuro, gli unici eventi che verranno modificati saranno le chiamate di sola personalizzazione che hanno solo contenuto A4T. |
| Aggiornamento dei metodi di crittografia del browser supportati per alcuni clienti | 28 marzo 2022 | Adobe offre due livelli di sicurezza cifratura per soddisfare le diverse esigenze dei clienti in materia di sicurezza nella raccolta dati di prime parti. On **23 giugno 2022** verrà rimosso il supporto di alcuni algoritmi di crittografia HTTPS, noti come cifratori, per i clienti con il loro livello di sicurezza impostato su &quot;Elevato&quot;. Ciò significa che alcuni sistemi operativi meno recenti non saranno più in grado di inviare dati ad Analytics in quanto non supportano metodi di crittografia moderni. I clienti che utilizzano le impostazioni di protezione crittografata standard non saranno interessati. Tutti i clienti che utilizzano attualmente l’impostazione &quot;Alta&quot; sono già stati contattati direttamente. È possibile trovare un elenco dettagliato delle crittografie interessate da questa modifica [qui](/help/technotes/rdc/encryption-algos.md). |
| Sospensione dei rapporti pianificati meno recenti | 12 aprile 2022 | Efficace **21 aprile 2022**, Adobe intende mettere in pausa tutti i rapporti pianificati con una data di creazione maggiore di due anni (creati prima del 31 gennaio 2020). Nessun rapporto o dato verrà eliminato. Verranno messi in pausa solo i rapporti identificati come più vecchi di due anni e non verranno inviati ulteriori rapporti pianificati. Per qualsiasi rapporto con una data di creazione inferiore a due anni senza data di scadenza (o con una data di scadenza superiore a due anni) verrà applicata una data di scadenza predefinita di 9 mesi. [Ulteriori informazioni](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| Aggiornamenti per l’area geografica ISO 2022 | 11 marzo 2021 | Adobe eseguirà gli aggiornamenti di 2022 per l’area ISO su **10 giugno 2022**. Ci si aspetta di vedere piccoli aggiornamenti delle informazioni geografiche dopo questa versione. |
| Sospensione delle attività di Report Builder pianificate precedenti | 12 aprile 2022 | **Attive dal 21 aprile 2022**, Adobe intende mettere in pausa tutte le attività di Report Builder pianificate create più di due anni fa. In particolare, questa pausa si applica alle attività create prima del 31 gennaio 2020. Non verranno eliminate attività, cartelle di lavoro o dati. Tuttavia, le attività identificate come più vecchie di due anni verranno messe in pausa e non verranno inviate altre attività pianificate. [Ulteriori informazioni](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| Scadenza dell’estensione per inserire nell’elenco Consentiti EOL le integrazioni legacy di Analytics OAuth/JWT | 14 gennaio 2022 | Il **25 maggio 2022** scadrà l’estensione per l’elenco Consentiti di [API di Analytics 1.3, API SOAP 1.4 e del servizio obsoleto Legacy OAuth/JWT di Analytics](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md). Questo offriva ai clienti che utilizzano le credenziali OAuth/JWT legacy di [!DNL Adobe Analytics] ulteriore tempo per migrare le integrazioni client alle [credenziali Adobe IMS](https://developer.adobe.com/console). Questa scadenza riguarda (ma non è limitata a) i clienti [!DNL Adobe Analytics Livestream] e [!DNL Adobe Campaign] che non hanno completato le migrazioni IMS richieste. I clienti che attualmente utilizzano versioni precedenti delle credenziali OAuth/JWT [!DNL Analytics] tramite l’estensione per inserire nell’elenco Consentiti e che non completano la migrazione alle credenziali IMS entro il 25 maggio 2022 perderanno l’accesso ai servizi Adobe. I clienti di Livestream possono fare riferimento a queste [istruzioni](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) durante la migrazione delle applicazioni client alle credenziali IMS. I clienti [!DNL Campaign] possono contattare il proprio account team Adobe per informazioni sull’aggiornamento alla versione più recente di [!DNL Campaign]. |
| Aggiornamento dei servizi SFTP (Secure File Transfer Protocol) | 3 marzo 2022 | Il **15 maggio 2022**, in [!DNL Adobe Analytics] verranno aggiornati i servizi SFTP (Secure File Transfer Protocol) per migliorare ulteriormente la sicurezza dei trasferimenti di file. Con questa modifica, alcune configurazioni client SFTP non saranno più supportate. Stiamo anche aggiungendo alcune opzioni di connessione che saranno disponibili entro il **1° marzo 2022**. Questo influisce solo sui dati inviati o recuperati da Adobe Analytics tramite SFTP. Il protocollo FTP non è interessato. Per evitare interruzioni del servizio, assicurati che i client SFTP (codice, strumenti, servizi) siano in linea con le modifiche descritte [qui](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=it). |
| Fine del ciclo di vita per [!DNL Reports & Analytics] | 4 gennaio 2022 | A partire dal **31 dicembre 2023**, Adobe intende terminare [!DNL Reports & Analytics] e i relativi rapporti e funzioni. I rapporti, le visualizzazioni e la tecnologia su cui si basa [!DNL Reports & Analytics] non soddisfano più gli standard tecnologici di Adobe. La maggior parte delle funzioni di [!DNL Reports & Analytics] sono disponibili in [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=it). A partire dal rilascio di Analysis Workspace nel 2015, le funzionalità e le caratteristiche di [!DNL Reports & Analytics] sono state trasferite ad Analysis Workspace ed è stata raggiunta una soglia di parità dei flussi di lavoro. [Questo avviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) spiega il processo di fine del ciclo di vita. |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement {#appm}

Per gli ultimi aggiornamenti sulle versioni di AppMeasurement (versione 2.22.4), fai riferimento alle [note sulla versione di AppMeasurement per JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=it).

>[!MORELIKETHIS]
>[[!DNL Customer Journey Analytics] note sulla versione](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=en)
