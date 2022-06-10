---
title: Note sulla versione più recente di Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 76190c666b8506e4b3acc1c80e08e60ca1736759
workflow-type: tm+mt
source-wordcount: '984'
ht-degree: 49%

---

# Note sulla versione corrente di Adobe Analytics (giugno 2022)

>[!NOTE]
>
>Questa pagina contiene informazioni precedenti al rilascio ed è soggetta a modifiche.

**Ultimo aggiornamento**: 10 giugno 2022


## Risorse correlate

* [Note sulle versioni precedenti 2022](/help/release-notes/2022.md)
* [Note sulla versione di Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=it)
* [Note sulla versione di Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it) 
* Scopri gli ultimi aggiornamenti sulle versioni dei [prodotti Adobe Experience Cloud](https://business.adobe.com/it/products/adobe-experience-cloud-products.html)

## Nuove funzioni di Adobe Analytics

| Funzione | Descrizione | [Data definita](releases.md) |
| ----------- | ---------- | ------- |
| Nuova interfaccia utente per la visualizzazione del flusso | Offre funzionalità aggiuntive alla visualizzazione Flusso per renderla più potente e in grado di funzionare. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/flow/create-flow.html?lang=en) | 15 giugno 2022 |
| Condivisione di annotazioni nelle scorecard per dispositivi mobili | Puoi visualizzare le annotazioni create in Workspace, nelle scorecard per dispositivi mobili. Questo ti consente di condividere sfumature di dati contestuali e informazioni sull’organizzazione e le campagne direttamente all’interno dei progetti delle scorecard per dispositivi mobili, visualizzabili nell’app mobile delle dashboard di Analytics. Ulteriori informazioni (da seguire) | 15 giugno 2022 |
| Supporto per la versione con sintassi di prodotto di Merchandising Variables with Edge Collection | Ora puoi impostare le variabili di merchandising utilizzando l’equivalente della sintassi di prodotto impostando i campi XDM pertinenti. Ulteriori informazioni sulla sintassi del prodotto per le variabili merchandising [qui](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/merchandising-evars.html?lang=it). Vedi le mappature per la sintassi del prodotto [qui](https://experienceleague.corp.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=en#aep-edge). | 15 giugno 2022 |
| Popolare dimensioni e metriche del ciclo di vita tramite Experience Edge | I dati del ciclo di vita mobile inviati tramite Experience Edge ora verranno visualizzati nei rapporti di Analytics. Consulta la documentazione per i dettagli sui campi XDM da mappare ai rapporti sul ciclo di vita mobile esistenti. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) | 27 maggio 2022 |
| Nuova esperienza di classificazione - Fase 1 | Questa versione graduale di una nuova esperienza utente per set di classificazioni migliora in modo significativo la visibilità nei dati di classificazione di proprietà del cliente. GA è stimato agli inizi del 2023. | I test limitati iniziano il 15 giugno 2022 |

{style=&quot;table-layout:auto&quot;}

### Correzioni in Adobe Analytics

AN-251686; AN-283542; AN-286572; AN-286945; AN-286784; AN-286944; AN-287012; AN-287319; AN-287333; AN-287348; AN-287429; AN-288238; AN-288281; AN-288660; AN-288769; AN-288798; AN-288871; AN-288872; AN-288941; AN-288951; AN-288952; AN-288956; AN-289062; AN-289340; AN-289346; AN-289488; AN-289562; AN-289580; AN-289861; AN-289892;

### Avvisi importanti per gli amministratori di Adobe Analytics

| Avviso | Data di aggiunta o aggiornamento | Descrizione |
| ----------- | ---------- | ---------- |
| **Sospensione dei rapporti pianificati in Reporting e analisi** | 8 giugno 2022 | Il 21 aprile 2022 è stata annunciata la rimozione di diverse funzioni specifiche dei rapporti pianificati in preparazione della scadenza del ciclo di vita di Reports &amp; Analytics, precedentemente annunciata. Queste funzionalità includevano la possibilità di pianificare nuovi rapporti e nuovi estratti di dati.<p>In risposta alle richieste dei clienti che richiedono un’estensione e per facilitare la transizione da Reports and Analytics, abbiamo deciso di estendere l’accesso a queste funzioni fino a **31 gennaio 2023**. Si prega di notare che le scadenze per i rapporti e gli estratti dei dati continueranno a essere limitate a nove mesi; la consegna del report e dell&#39;estrazione dei dati verrà sospesa alla fine di questo periodo, a meno che la pianificazione non venga riattivata.<p>Per ribadire questo punto, queste funzioni verranno rese obsolete il 31 gennaio 2023. Prima di questa data, devi migrare i rapporti pianificati in uno degli altri meccanismi disponibili in Adobe Analytics. Per ulteriori domande o supporto, contatta l’Assistenza clienti di Adobe. [Ulteriori informazioni](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **Sospensione delle attività pianificate nel Report Builder** | 8 giugno 2022 | Il 21 aprile 2022 sono state implementate modifiche alle attività pianificate in Report Builder nell’ambito delle attività di ottimizzazione delle prestazioni e della consegna. Tali modifiche includevano la rimozione della possibilità di avere consegne pianificate &quot;end after x events&quot; (termine dopo gli eventi x). In risposta a diverse richieste dei clienti che richiedono più tempo per esplorare e implementare alternative, abbiamo deciso di ripristinare questa opzione in modo limitato fino a **31 gennaio 2023**.<p>È possibile continuare a pianificare le attività al Report Builder orario e farle terminare dopo un massimo di 99 occorrenze. Si prega di notare che lo smantellamento si applica solo alle attività orarie; la &quot;fine dopo x occorrenze&quot; rimarrà non disponibile per tutti gli altri intervalli di consegna (giornalieri, settimanali, mensili e annuali). Tieni presente che questa opzione diventerà obsoleta il 31 gennaio 2023. Per ulteriori domande o supporto, contatta l’Assistenza clienti di Adobe. [Ulteriori informazioni](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| **Aggiornamento SFTP** | 9 maggio 2022 | In precedenza, avevamo comunicato che Adobe avrebbe aggiornato i servizi SFTP (Secure File Transfer Protocol) nel maggio 2022 per garantire una maggiore sicurezza nel trasferimento di file. L&#39;aggiornamento è stato posticipato al **estate del 2022**. Quando questa modifica verrà implementata, alcune configurazioni client SFTP non saranno più supportate. Questo influisce solo sui dati inviati o recuperati da Adobe Analytics tramite SFTP. Il protocollo FTP non è interessato. Per evitare interruzioni del servizio, assicurati che i client SFTP (codice, strumenti, servizi) siano in linea con le modifiche descritte [qui](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=it). |
| **Aggiornamento dei metodi di crittografia del browser supportati per alcuni clienti** | 28 marzo 2022 | Adobe offre due livelli di protezione crittografata per soddisfare le diverse esigenze dei clienti in materia di sicurezza nella raccolta dati di prime parti. Il **23 giugno 2022** verrà rimosso il supporto di alcuni algoritmi di crittografia HTTPS, o crittografie, per i clienti con livello di sicurezza impostato su “Elevato”. Di conseguenza, alcuni sistemi operativi meno recenti non saranno più in grado di inviare dati ad Analytics, in quanto non supportano metodi di crittografia moderni. I clienti che utilizzano le impostazioni predefinite di sicurezza con crittografia “Standard” non saranno interessati. Tutti i clienti che utilizzano attualmente l’impostazione “Elevato” sono già stati contattati direttamente. Elenco dettagliato dei crittografie interessate |
| **Aggiornamenti per area geografica ISO 2022** | 11 marzo 2021 | Adobe ha eseguito gli aggiornamenti dell&#39;area ISO 2022 su **10 giugno 2022**. Con questa versione, sono previsti aggiornamenti minori relativi alle informazioni geografiche. |
| **Fine del ciclo di vita per [!DNL Reports & Analytics]** | 4 gennaio 2022 | A partire dal **31 dicembre 2023**, Adobe intende terminare [!DNL Reports & Analytics] e i relativi rapporti e funzioni. I rapporti, le visualizzazioni e la tecnologia su cui si basa [!DNL Reports & Analytics] non soddisfano più gli standard tecnologici di Adobe. La maggior parte delle funzioni di [!DNL Reports & Analytics] sono disponibili in [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=it). A partire dal rilascio di Analysis Workspace nel 2015, le funzionalità e le caratteristiche di [!DNL Reports & Analytics] sono state trasferite ad Analysis Workspace ed è stata raggiunta una soglia di parità dei flussi di lavoro. [Questo avviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) spiega il processo di fine del ciclo di vita. |

{style=&quot;table-layout:auto&quot;}

### AppMeasurement

Per gli ultimi aggiornamenti sulle versioni di AppMeasurement (versione 2.22.4), fai riferimento alle [note sulla versione di AppMeasurement per JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=it).

