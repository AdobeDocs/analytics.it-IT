---
title: Risoluzione dei problemi dei feed dati
description: Scopri i motivi per cui un processo di feed dati potrebbe non riuscire a elaborare o consegnare i dati. Risolvere i potenziali problemi relativi ai feed di dati.
feature: Data Feeds
exl-id: c082bc95-cdae-448b-86b5-695660fb2352
TQID: https://experienceleague.adobe.com/JkayhoeQk24AwoDkz25lvZBzq-xNcFjW6l-cN-TwuKk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 467
ht-degree: 0%

---

# Risoluzione dei problemi dei feed dati

Determinare i possibili motivi per cui un processo potrebbe non riuscire a elaborare o consegnare.

## Risolvere i problemi relativi a un feed dati esistente

Se un feed di dati funziona correttamente su base oraria o giornaliera ma di recente ha esito negativo, verifica quanto segue:

* Utilizza lo strumento [Adobe Status](https://status.adobe.com/en/experience_cloud) per determinare se sono presenti finestre di manutenzione pianificate o problemi di disponibilità. Se al momento è presente un problema noto, Adobe elabora automaticamente i feed di dati pianificati dopo il ripristino del servizio.
* Assicurati che ci sia abbastanza spazio disponibile sul sito FTP. Se lo spazio su disco del sito FTP è insufficiente, eliminare alcuni file dal server per liberare spazio per i nuovi file.
* Se non sono presenti problemi noti e il sito FTP dispone di spazio su disco sufficiente, puoi inviare nuovamente il feed di dati.

   1. Accedi ad Adobe Analytics e passa a **[!UICONTROL Admin]** > **[!UICONTROL Data feeds]**.
   2. Individua i feed di dati desiderati, quindi fai clic sulla casella di controllo accanto a ciascuno di essi che desideri rieseguire.
   3. Fai clic su **[!UICONTROL Rerun]**.

  ![Riesecuzione](assets/rerun.png)

Se ancora non ricevi i file dei feed dati dopo averli rieseguiti, contatta l’Assistenza clienti.

## Risolvere i problemi relativi a un nuovo feed dati

Se un nuovo feed di dati genera un errore, risolvi il problema caricando manualmente un file di test sul sito FTP. Nella maggior parte dei casi, è possibile determinare il punto di errore utilizzando questi passaggi.

1. Accedi al tuo sito FTP utilizzando Esplora file (Windows) o Finder (Mac). Assicurarsi di utilizzare il protocollo FTP (`ftp://`) e di consentire [indirizzi IP di Adobe](/help/technotes/ip-addresses.md) tramite il firewall dell&#39;organizzazione. Se non riesci a raggiungere il sito FTP, rivolgiti al proprietario del sito FTP per determinare la destinazione corretta.

   ![Esplora file](assets/file_explorer.png)

2. Viene visualizzata una finestra a comparsa che richiede un nome utente e una password. Immetti le credenziali di autenticazione. Se le credenziali vengono accettate, la finestra mostra il contenuto corrente sul sito FTP. Se le credenziali non vengono accettate, rivolgiti al proprietario FTP per assicurarti che il nome utente e la password siano corretti. Se utilizzi SFTP, assicurati di seguire ogni passaggio nella [guida SFTP](../ftp-and-sftp/c-sftp/ftp-sftp.md). Tieni presente che Adobe non supporta tutti i casi di utilizzo SFTP.
3. Carica un file sul sito FTP trascinandolo nella finestra autenticata. Qualsiasi immagine o documento di testo è adeguato. Se ricevi un errore durante il tentativo di inserire un file nel sito FTP, rivolgiti al proprietario FTP per verificare che lo spazio su disco sia sufficiente e che il nome utente disponga delle autorizzazioni di scrittura per il sito FTP.
4. Dopo aver confermato che il file si trova sul sito FTP, puoi eliminare il file caricato nel passaggio precedente.

Se tutti i passaggi precedenti funzionano e ricevi comunque un errore FTP, contatta l’Assistenza clienti.
