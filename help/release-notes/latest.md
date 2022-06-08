---
title: Note sulla versione più recente di Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 9a16f3942505028624e5c07568342a9acac898d7
workflow-type: tm+mt
source-wordcount: '821'
ht-degree: 63%

---

# Note sulla versione corrente di Adobe Analytics (maggio 2022)

**Ultimo aggiornamento**: 8 giugno 2022

## Risorse correlate

* [Note sulle versioni precedenti 2022](/help/release-notes/2022.md)
* [Note sulla versione di Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=it)
* [Note sulla versione di Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it) 
* Scopri gli ultimi aggiornamenti sulle versioni dei [prodotti Adobe Experience Cloud](https://business.adobe.com/it/products/adobe-experience-cloud-products.html)

## Nuove funzioni di Adobe Analytics

| Funzione | Descrizione | [Data definita](releases.md) |
| ----------- | ---------- | ------- |
| Popolare dimensioni e metriche del ciclo di vita tramite Experience Edge | I dati del ciclo di vita mobile inviati tramite Experience Edge ora verranno visualizzati nei rapporti di Analytics. Consulta la documentazione per i dettagli su quali dati del ciclo di vita vengono raccolti tramite Experience Edge e qual è la corrispondenza con i rapporti sul ciclo di vita già esistenti. [Ulteriori informazioni disponibili a breve] | 27 maggio 2022 |

{style=&quot;table-layout:auto&quot;}

### Correzioni in Adobe Analytics

Correzioni per più clienti

N/D

### Ulteriori correzioni in Adobe Analytics

Correzioni per singoli clienti

AN-274429; AN-279640; AN-280918; AN-280945; AN-282884; AN-283565; AN-284785; AN-284814; AN-284854; AN-284989; AN-285244; AN-285253; AN-285432; AN-285528; AN-285535; AN-285710; AN-286255; AN-286340; AN-286434; AN-286454; AN-286630; AN-286716; AN-286854; AN-286911

### Avvisi importanti per gli amministratori di Adobe Analytics

| Avviso | Data di aggiunta o aggiornamento | Descrizione |
| ----------- | ---------- | ---------- |
| Sospensione dei rapporti pianificati in Reporting e analisi | 8 giugno 2022 | Il 21 aprile 2022 è stata annunciata la rimozione di diverse funzioni specifiche dei rapporti pianificati in preparazione dell’annuncio in precedenza [fine del ciclo di vita di Reports &amp; Analytics](https://express.adobe.com/page/6WnF8JK6IRDhf/). Queste funzionalità includevano la possibilità di pianificare nuovi rapporti e nuovi estratti di dati.<p>In risposta alle richieste dei clienti che richiedono un’estensione e per facilitare la transizione da Reports and Analytics, abbiamo deciso di estendere l’accesso a queste funzioni fino a **31 gennaio 2023**. Si prega di notare che le scadenze per i rapporti e gli estratti dei dati continueranno a essere limitate a nove mesi; la consegna del report e dell&#39;estrazione dei dati verrà sospesa alla fine di questo periodo, a meno che la pianificazione non venga riattivata. <p>Per ribadire, queste funzioni verranno rese obsolete il 31 gennaio 2023, prima del quale sarà necessario migrare i rapporti pianificati in uno degli altri meccanismi disponibili in Adobe Analytics. Per ulteriori domande o supporto, contatta l’Assistenza clienti di Adobe. |
| Sospensione delle attività pianificate nel Report Builder | 8 giugno 2022 | Il 21 aprile 2022 sono state implementate modifiche alle attività pianificate in Report Builder nell’ambito delle attività di ottimizzazione delle prestazioni e della consegna. Tali modifiche includevano la rimozione della possibilità di avere consegne pianificate &quot;end after x events&quot; (termine dopo gli eventi x). In risposta a diverse richieste dei clienti che richiedono più tempo per esplorare e implementare alternative, abbiamo deciso di ripristinare questa opzione in modo limitato fino a **31 gennaio 2023**.<p>Sarà possibile continuare a pianificare le attività al Report Builder orario e farle terminare dopo un massimo di 99 occorrenze. Si prega di notare che lo smantellamento si applica solo alle attività orarie; la &quot;fine dopo x occorrenze&quot; rimarrà non disponibile per tutti gli altri intervalli di consegna (giornalieri, settimanali, mensili e annuali). Tieni presente che questa opzione diventerà obsoleta il 31 gennaio 2023. Per ulteriori domande o supporto, contatta l’Assistenza clienti di Adobe. |
| **Aggiornamento SFTP** | 9 maggio 2022 | In precedenza, avevamo comunicato che Adobe avrebbe aggiornato i servizi SFTP (Secure File Transfer Protocol) nel maggio 2022 per garantire una maggiore sicurezza nel trasferimento di file. L&#39;aggiornamento è stato posticipato al **estate del 2022**. Quando questa modifica verrà implementata, alcune configurazioni client SFTP non saranno più supportate. Questo influisce solo sui dati inviati o recuperati da Adobe Analytics tramite SFTP. Il protocollo FTP non è interessato. Per evitare interruzioni del servizio, assicurati che i client SFTP (codice, strumenti, servizi) siano in linea con le modifiche descritte [qui](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=it). |
| **Aggiornamento dei metodi di crittografia del browser supportati per alcuni clienti** | 28 marzo 2022 | Adobe offre due livelli di protezione crittografata per soddisfare le diverse esigenze dei clienti in materia di sicurezza nella raccolta dati di prime parti. Il **23 giugno 2022** verrà rimosso il supporto di alcuni algoritmi di crittografia HTTPS, o crittografie, per i clienti con livello di sicurezza impostato su “Elevato”. Di conseguenza, alcuni sistemi operativi meno recenti non saranno più in grado di inviare dati ad Analytics, in quanto non supportano metodi di crittografia moderni. I clienti che utilizzano le impostazioni predefinite di sicurezza con crittografia “Standard” non saranno interessati. Tutti i clienti che utilizzano attualmente l’impostazione “Elevato” sono già stati contattati direttamente. Un elenco dettagliato delle crittografie interessate da questo cambiamento è disponibile qui. |
| **Aggiornamenti per area geografica ISO 2022** | 11 marzo 2021 | Il **10 giugno 2022**, Adobe eseguirà gli aggiornamenti per area geografica ISO 2022. Con questa versione, sono previsti aggiornamenti minori relativi alle informazioni geografiche. |
| **Fine del ciclo di vita per [!DNL Reports & Analytics]** | 4 gennaio 2022 | A partire dal **31 dicembre 2023**, Adobe intende terminare [!DNL Reports & Analytics] e i relativi rapporti e funzioni. I rapporti, le visualizzazioni e la tecnologia su cui si basa [!DNL Reports & Analytics] non soddisfano più gli standard tecnologici di Adobe. La maggior parte delle funzioni di [!DNL Reports & Analytics] sono disponibili in [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=it). A partire dal rilascio di Analysis Workspace nel 2015, le funzionalità e le caratteristiche di [!DNL Reports & Analytics] sono state trasferite ad Analysis Workspace ed è stata raggiunta una soglia di parità dei flussi di lavoro. [Questo avviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) spiega il processo di fine del ciclo di vita. |

{style=&quot;table-layout:auto&quot;}

### AppMeasurement

Per gli ultimi aggiornamenti sulle versioni di AppMeasurement (versione 2.22.4), fai riferimento alle [note sulla versione di AppMeasurement per JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=it).

