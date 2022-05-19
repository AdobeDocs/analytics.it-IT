---
title: Note sulla versione più recente di Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: b9bf373d7d62d7b6df405629cdf304246b80649f
workflow-type: tm+mt
source-wordcount: '905'
ht-degree: 82%

---

# Note sulla versione corrente di Adobe Analytics (maggio 2022)

**Ultimo aggiornamento**: 17 maggio 2022

## Risorse correlate

* [Note sulle versioni precedenti 2022](/help/release-notes/2022.md)
* [Note sulla versione di Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=it)
* [Note sulla versione di Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it) 
* Scopri gli ultimi aggiornamenti sulle versioni dei [prodotti Adobe Experience Cloud](https://business.adobe.com/it/products/adobe-experience-cloud-products.html)

## Nuove funzioni di Adobe Analytics

| Funzione | Descrizione | [Data definita](releases.md) |
| ----------- | ---------- | ------- |
| Popolare dimensioni e metriche del ciclo di vita tramite Experience Edge | I dati del ciclo di vita mobile inviati tramite Experience Edge verranno ora visualizzati nei rapporti di Analytics. Consulta la documentazione per i dettagli su quali dati del ciclo di vita vengono raccolti tramite Experience Edge e come corrispondono ai rapporti esistenti sul ciclo di vita. [Ulteriori informazioni - disponibile a breve] | 27 maggio 2022 |

{style=&quot;table-layout:auto&quot;}

### Correzioni in Adobe Analytics

(Correzioni per più clienti)

N/D

### Ulteriori correzioni in Adobe Analytics

(Correzioni per i singoli clienti)

AN-274429; AN-279640; AN-280918; AN-280945; AN-282884; AN-283565; AN-284785; AN-284814; AN-284854; AN-284989; AN-285244; AN-285253; AN-285432; AN-285528; AN-285535; AN-285710; AN-286255; AN-286340; AN-286434; AN-286454; AN-286630; AN-286716; AN-286854; AN-286911

### Avvisi importanti per gli amministratori di Adobe Analytics

| Avviso | Data di aggiunta o aggiornamento | Descrizione |
| ----------- | ---------- | ---------- |
| **Aggiornamento SFTP** | 9 maggio 2022 | In precedenza, avevamo comunicato che Adobe avrebbe aggiornato i servizi SFTP (Secure File Transfer Protocol) nel maggio 2022 per fornire una maggiore sicurezza per il trasferimento di file. Abbiamo posticipato questo aggiornamento all&#39;estate del 2022. Quando avviene questa modifica, alcune configurazioni client SFTP non saranno più supportate. Questo influisce solo sui dati inviati o recuperati da Adobe Analytics tramite SFTP. Il protocollo FTP non è interessato. Per evitare interruzioni del servizio, assicurati che i client SFTP (codice, strumenti, servizi) siano in linea con le modifiche descritte [qui](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=it). |
| **Adesione a Cross-Device Analytics (CDA)** | 13 aprile 2022 | Efficace **1 maggio 2022**, qualsiasi nuova implementazione di [CDA](/help/components/cda/overview.md) sono limitati a un massimo di tre ID suite di rapporti (RSID) per cliente. |
| **Modifica del modo in cui Adobe Analytics gestisce i dati A4T raccolti tramite Experience Edge** | 31 marzo 2022 | Il 7 marzo 2022 è stato modificato il modo in cui vengono gestite alcune chiamate provenienti da Experience Edge che includono contenuti Target destinati al reporting di Analytics for Target (A4T). A partire dal 7 marzo, tutti gli hit con contenuti di reporting A4T sono stati modificati in modo da non essere trattati come eventi di Visualizzazione pagina o Collegamento. A partire dal **31 marzo 2022**, la logica è più selettiva in modo che gli eventi di Visualizzazione pagina e Clic standard non vengano modificati. In futuro, gli unici eventi che verranno modificati saranno le chiamate di sola personalizzazione che presentano esclusivamente contenuti A4T. |
| **Aggiornamento dei metodi di crittografia del browser supportati per alcuni clienti** | 28 marzo 2022 | Adobe offre due livelli di protezione crittografata per soddisfare le diverse esigenze dei clienti in materia di sicurezza nella raccolta dati di prime parti. Il **23 giugno 2022** verrà rimosso il supporto di alcuni algoritmi di crittografia HTTPS, o crittografie, per i clienti con livello di sicurezza impostato su “Elevato”. Di conseguenza, alcuni sistemi operativi meno recenti non saranno più in grado di inviare dati ad Analytics, in quanto non supportano metodi di crittografia moderni. I clienti che utilizzano le impostazioni predefinite di sicurezza con crittografia “Standard” non saranno interessati. Tutti i clienti che utilizzano attualmente l’impostazione “Elevato” sono già stati contattati direttamente. Un elenco dettagliato delle crittografie interessate da questo cambiamento è disponibile qui. |
| **Sospensione dei rapporti pianificati meno recenti** | 12 aprile 2022 | A decorrere dal **20 aprile 2022**, Adobe intende sospendere tutti i rapporti pianificati con una data di creazione superiore ai due anni (creati prima del 31 gennaio 2020). Non verranno eliminati rapporti o dati. Verranno sospesi solo i rapporti identificati come più vecchi di due anni e non verranno inviati ulteriori rapporti pianificati. Ulteriori informazioni |
| **Aggiornamenti per area geografica ISO 2022** | 11 marzo 2021 | Il **10 giugno 2022**, Adobe eseguirà gli aggiornamenti per area geografica ISO 2022. Con questa versione, sono previsti aggiornamenti minori relativi alle informazioni geografiche. |
| **Sospensione delle precedenti attività di Report Builder pianificate** | 12 aprile 2022 | A decorrere dal **20 aprile 2022**, Adobe intende sospendere tutte le attività di Report Builder pianificate create più di due anni fa. In particolare, questa sospensione si applica alle attività create prima del 31 gennaio 2020. Non vengono eliminate attività, cartelle di lavoro o dati. Tuttavia, le attività identificate come più vecchie di due anni verranno sospese e non verranno inviate altre attività pianificate. Ulteriori informazioni |
| **Scadenza dell’estensione per l’elenco Consentiti relativa alla fine del ciclo di vita di integrazioni legacy Analytics OAuth/JWT** | 14 gennaio 2022 | Il **25 maggio 2022**, scadrà l’estensione per l’elenco Consentiti relativa alla [fine del ciclo di vita delle API Analytics 1.3, delle API SOAP 1.4 e del servizio Legacy OAuth/JWT di Analytics](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md). Questo offriva ai clienti che utilizzano le credenziali OAuth/JWT legacy di [!DNL Adobe Analytics] ulteriore tempo per migrare le integrazioni client alle [credenziali Adobe IMS](https://developer.adobe.com/console). Questa scadenza riguarda (ma non è limitata a) i clienti [!DNL Adobe Analytics Livestream] e [!DNL Adobe Campaign] che non hanno completato le migrazioni IMS richieste. I clienti che attualmente utilizzano credenziali legacy OAuth/JWT per [!DNL Analytics] tramite l’estensione per l’elenco Consentiti e che non completano la migrazione alle credenziali IMS entro il 25 maggio 2022 non potranno più accedere ai servizi Adobe. I clienti di Livestream possono fare riferimento a queste [istruzioni](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) durante la migrazione delle applicazioni client alle credenziali IMS. I clienti [!DNL Campaign] possono contattare il proprio account team Adobe per informazioni sull’aggiornamento alla versione più recente di [!DNL Campaign]. |
| **Fine del ciclo di vita per [!DNL Reports & Analytics]** | 4 gennaio 2022 | A partire dal **31 dicembre 2023**, Adobe intende terminare [!DNL Reports & Analytics] e i relativi rapporti e funzioni. I rapporti, le visualizzazioni e la tecnologia su cui si basa [!DNL Reports & Analytics] non soddisfano più gli standard tecnologici di Adobe. La maggior parte delle funzioni di [!DNL Reports & Analytics] sono disponibili in [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=it). A partire dal rilascio di Analysis Workspace nel 2015, le funzionalità e le caratteristiche di [!DNL Reports & Analytics] sono state trasferite ad Analysis Workspace ed è stata raggiunta una soglia di parità dei flussi di lavoro. [Questo avviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) spiega il processo di fine del ciclo di vita. |

{style=&quot;table-layout:auto&quot;}

### AppMeasurement

Per gli ultimi aggiornamenti sulle versioni di AppMeasurement (versione 2.22.4), fai riferimento alle [note sulla versione di AppMeasurement per JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=it).

