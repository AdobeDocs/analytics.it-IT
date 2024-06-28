---
product: analytics
audience: end-user
user-guide-title: Guida all’esportazione di Analytics
breadcrumb-title: Guida all’esportazione
user-guide-description: Scopri come utilizzare i feed di dati per esportare dati non elaborati, e Data Warehouse per recuperare un output di dati sotto forma di foglio di calcolo. Scopri come utilizzare FTP e SFTP per trasferire i file.
source-git-commit: f68cf0de5e7689d8245572b060a3d81c3bf85072
workflow-type: ht
source-wordcount: '284'
ht-degree: 100%

---


# Guida all’esportazione di Adobe Analytics {#export}

+ [Guida all’esportazione di Analytics](home.md)
+ [Note sulla versione di Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=it)
+ Feed dati di Analytics {#analytics-data-feed}
   + [Panoramica sui feed dati](analytics-data-feed/data-feed-overview.md)
   + [Creare o modificare un feed dati](analytics-data-feed/create-feed.md)
   + [Gestire i feed dati](analytics-data-feed/df-manage-feeds.md)
   + [Gestire i lavori sui feed dati](analytics-data-feed/df-manage-jobs.md)
   + Contenuti feed dati {#data-feed-contents}
      + [Panoramica sui contenuti dei feed dati](analytics-data-feed/c-df-contents/datafeeds-contents.md)
      + [Calcolare metriche](analytics-data-feed/c-df-contents/datafeeds-calculate.md)
      + [Riferimento colonna dati](analytics-data-feed/c-df-contents/datafeeds-reference.md)
      + [Ricerca eventi pagina](analytics-data-feed/c-df-contents/datafeeds-page-event.md)
      + [Ricerche dinamiche](analytics-data-feed/c-df-contents/dynamic-lookups.md)
      + [Ricerca eVar merchandising](analytics-data-feed/c-df-contents/merchandising-evar-lookup.md)
      + [Caratteri speciali](analytics-data-feed/c-df-contents/datafeeds-spec-chars.md)
      + [Occorrenza in arrivo](analytics-data-feed/c-df-contents/late-arriving-hits.md)
   + [Domande frequenti sui feed dati](analytics-data-feed/df-faq.md)
   + [Best practice per il feed dati](analytics-data-feed/data-feeds-best-practices.md)
   + [Risoluzione dei problemi dei feed dati](analytics-data-feed/troubleshooting.md)
+ Data Warehouse {#data-warehouse}
   + [Panoramica di Data Warehouse](data-warehouse/data-warehouse.md)
   + [Aggiungere un gruppo utenti di Data Warehouse](data-warehouse/t-dw-group.md)
   + Creare una richiesta di Data Warehouse {#dw-create-request}
      + [Creare una richiesta di Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md)
      + [Impostazioni generali](/help/export/data-warehouse/create-request/dw-general-settings.md)
      + [Generare il rapporto](/help/export/data-warehouse/create-request/dw-request-build-report.md)
      + [Destinazione del rapporto](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)
      + [Opzioni per il rapporto](/help/export/data-warehouse/create-request/dw-request-report-options.md)
      + [Opzioni di pianificazione](/help/export/data-warehouse/create-request/dw-request-scheduling.md)
      + [E-mail di notifica](/help/export/data-warehouse/create-request/dw-request-email.md)
   + [Tempi di consegna delle richieste](data-warehouse/delivery-time.md)
   + [File di dati Tableau](data-warehouse/t-tableau.md)
   + [Ordina per metrica](data-warehouse/sorting-by-metric.md)
   + [Gestire le richieste di Data Warehouse](data-warehouse/data-warehouse-requests-manage.md)
   + [Componenti supportati in Data Warehouse](data-warehouse/component-support.md)
   + [Domande frequenti su Data Warehouse](data-warehouse/faq.md)
   + [Data Warehouse Best Practices (Procedure consigliate per l’archivio dati)](data-warehouse/data-warehouse-bp.md)
+ FTP e SFTP {#ftp-and-sftp}
   + [Utilizzare FTP e SFTP con Adobe Experience Cloud](ftp-and-sftp/ftp-overview.md)
   + Configurazione di account FTP ospitati da Adobe {#set-up-ftp-accounts}
      + [Configurare account FTP: panoramica](ftp-and-sftp/c-set-up-ftp-accounts/ftp-accounts.md)
      + [Classificazioni](ftp-and-sftp/c-set-up-ftp-accounts/ftp-saint.md)
      + [Origini dati](ftp-and-sftp/c-set-up-ftp-accounts/ftp-datasources.md)
      + [Feed dati](ftp-and-sftp/c-set-up-ftp-accounts/ftp-datafeeds.md)
      + [Report consegnati di Data Warehouse](ftp-and-sftp/c-set-up-ftp-accounts/ftp-dw-reports.md)
      + [Report consegnati del Report Builder](ftp-and-sftp/c-set-up-ftp-accounts/ftp-arb-reports.md)
      + [Engagement ai servizi tecnici con FTP](ftp-and-sftp/c-set-up-ftp-accounts/ftp-eng-services.md)
   + [Conservazione dei dati e limitazioni dell&#39;FTP](ftp-and-sftp/ftp-limits.md)
   + [Eliminazione dei dati e degli account FTP](ftp-and-sftp/ftp-delete.md)
   + [Ripristino dei dati e degli account FTP eliminati](ftp-and-sftp/ftp-restore.md)
   + [Aggiornamento dei server Adobe FTP](ftp-and-sftp/ftp-upgrade.md)
   + [Utilizzo della modalità FTP passiva](ftp-and-sftp/ftp-passive.md)
   + [Tempistiche di elaborazione FTP](ftp-and-sftp/ftp-processing.md)
   + Secure File Transfer Protocol (protocollo di trasferimento file sicuro) {#secure-file-transfer-protocol}
      + [Aggiornamento dei servizi SFTP - Domande frequenti](ftp-and-sftp/c-sftp/sftp-upgrade.md)
      + [Secure File Transfer Protocol (protocollo di trasferimento file sicuro): panoramica](ftp-and-sftp/c-sftp/ftp-sftp.md)
      + [Connessione a un account Adobe FTP con SFTP](ftp-and-sftp/c-sftp/ftp-sftp-connect.md)
      + [Invio di dati Adobe a un account FTP esterno tramite SFTP](ftp-and-sftp/c-sftp/ftp-sftp-transfer.md)
      + [Invio di richieste di Data Warehouse a server SFTP](ftp-and-sftp/c-sftp/ftp-sftp-dw.md)
      + [Connessione ad Adobe tramite SFTP senza password](ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)
+ [Download di Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?lang=it)
+ [API Adobe Analytics](https://www.adobe.io/apis/experiencecloud/analytics/docs.html)
+ [Report Builder](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/home.html?lang=it)
