---
title: Risoluzione dei problemi dei feed dati
description: Scopri come determinare e risolvere i problemi con i feed di dati.
keywords: processo;risoluzione dei problemi;errore;ftp;chdir;connect;login;put
exl-id: c082bc95-cdae-448b-86b5-695660fb2352
source-git-commit: b81ffba2f1e021888dd1c4b016c9b451448f47bb
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 0%

---

# Risoluzione dei problemi dei feed dati

Determinare i motivi potenziali per cui un processo potrebbe non essere elaborato o consegnato.

## Risoluzione dei problemi di un feed di dati esistente

Se disponi di un feed di dati che funziona correttamente ogni ora o giorno ma di recente non riesce, controlla ciascuno dei seguenti elementi:

* Utilizza la [Strumento Stato Adobe](https://status.adobe.com/en/experience_cloud) per determinare se sono presenti finestre di manutenzione pianificate o problemi di disponibilità. Se al momento si verifica un problema noto, Adobe elabora automaticamente i feed di dati pianificati una volta ripristinato il servizio.
* Assicurati che ci sia abbastanza spazio disponibile sul sito FTP. Se lo spazio su disco del sito FTP è esaurito, elimina alcuni file dal server per lasciare spazio a nuovi file.
* Se non ci sono problemi noti e il sito FTP ha abbastanza spazio su disco, puoi inviare nuovamente il feed di dati.

   1. Accedi ad Adobe Analytics e passa a **[!UICONTROL Admin]** > **[!UICONTROL Data feeds]**.
   2. Individua i feed di dati desiderati, quindi fai clic sulla casella di controllo accanto a ciascuno dei feed di dati da ripetere.
   3. Fai clic su **[!UICONTROL Rerun]**.

   ![Ripristino](assets/rerun.png)

Se non ricevi ancora i file di feed dati dopo averli eseguiti nuovamente, contatta l’Assistenza clienti.

## Risoluzione dei problemi relativi al nuovo feed di dati

Se un nuovo feed di dati genera un errore, risolvi il problema caricando manualmente un file di test sul sito FTP. Nella maggior parte dei casi, è possibile determinare il punto di errore utilizzando questi passaggi.

1. Accedi al tuo sito FTP utilizzando File Explorer (Windows) o Finder (Mac). Assicurati di utilizzare il protocollo FTP (`ftp://`) e che consente [Indirizzi IP di Adobe](/help/technotes/ip-addresses.md) attraverso il firewall dell’organizzazione. Se non riesci a raggiungere il sito FTP, collabora con il proprietario del sito FTP per determinare la destinazione corretta.

   ![Esplora file](assets/file_explorer.png)

2. Viene visualizzata una finestra a comparsa in cui viene richiesto il nome utente e la password. Immetti le credenziali di autenticazione. Se le credenziali vengono accettate, la finestra mostra il contenuto corrente sul sito FTP. Se le credenziali non vengono accettate, collabora con il proprietario FTP per assicurarti che il nome utente e la password siano corretti. Se utilizzi SFTP, assicurati di seguire ogni passaggio nel [Guida a SFTP](../ftp-and-sftp/c-sftp/ftp-sftp.md). Nota che Adobe non supporta tutti i casi di utilizzo SFTP.
3. Carica un file sul sito FTP trascinandolo nella finestra autenticata. Qualsiasi immagine o documento di testo è adeguato. Se ricevi un errore durante il tentativo di inserire un file sul sito FTP, collabora con il proprietario FTP per verificare che lo spazio su disco sia sufficiente e che il nome utente disponga delle autorizzazioni di scrittura per il sito FTP.
4. Dopo aver confermato che il file è sul sito FTP, puoi eliminare il file caricato nel passaggio precedente.

Se tutti i passaggi precedenti funzionano e ottieni comunque un errore FTP, contatta l&#39;Assistenza clienti.
