---
description: La connessione senza password agli account FTP è possibile solo utilizzando sia una connessione SFTP che un metodo di autenticazione alternativo. Ciò prevede un set di due file (uno che risiederà sull'account FTP e l'altro che risiederà sul tuo computer) denominato "combinazione di chiave pubblica e privata".
keywords: ftp;sftp
title: Connessione ad Adobe tramite SFTP senza password
feature: FTP Export
exl-id: 7ff9511c-50a2-466f-b5af-6bbd59941ce5
source-git-commit: 34ba0e09cd909951a777b0ad3da080958633f97e
workflow-type: tm+mt
source-wordcount: '605'
ht-degree: 72%

---

# Connessione ad Adobe tramite SFTP senza password

La connessione senza password agli account FTP è possibile solo utilizzando sia una connessione SFTP che un metodo di autenticazione alternativo. Ciò prevede un set di due file (uno che risiederà sull&#39;account FTP e l&#39;altro che risiederà sul tuo computer) denominato &quot;combinazione di chiave pubblica e privata&quot;.

La sicurezza è la medesima garantita dall&#39;uso dell&#39;autenticazione tramite password. Si tratta di una forma di autenticazione diversa che non richiede all&#39;utente di immettere ogni volta una password. Quando utilizzati correttamente, questi file consentono l&#39;accesso a un particolare computer, senza dover specificare una password. Questa modalità deve essere configurata computer per computer. Tutte le altre connessioni che non utilizzano questi file chiave devono sempre specificare una password.

Alcuni client richiedono un SFTP (Secure File Transfer Protocol) per la trasmissione di dati sensibili. Una connessione SFTP è più sicura di una normale connessione FTP perché consente la comunicazione di dati crittografati. Per impostazione predefinita, tutti gli account FTP Adobe sono pronti per SFTP. È possibile aprire una connessione SFTP con un nome utente e una password validi utilizzando un client SFTP che si connette alla porta 22 (normali connessioni FTP non protette dalla porta 21).

Quando utilizzi SFTP, in determinate condizioni è possibile utilizzare chiavi private per connettersi all’account senza una password. Questo metodo consente al tuo computer di utilizzare per l&#39;autenticazione i file chiave invece della solita autenticazione tramite password. Ciò significa che solamente il computer su cui si trova la chiave privata può effettuare la connessione senza una password. Tutti gli altri computer/utenti dovranno sempre utilizzare l&#39;autenticazione tramite password (a meno che non siano state configurate chiavi private anche su questi computer).

**Per configurare e utilizzare le chiavi private per l&#39;autenticazione senza password**

1. Account FTP creato (Adobe).

   Un rappresentante Adobe può creare un account FTP, se non esiste già. Contatta il tuo Account Team Adobe o l’Assistenza clienti Adobe per creare un account.
1. Creazione di chiave pubblica/privata (cliente).

   Crea una combinazione di chiave pubblica e privata. La chiave privata è un file riservato al tuo computer/server e su cui è memorizzato. Il file di chiave pubblica deve essere caricato sull&#39;account Adobe. Quando utilizzato in questo modo, puoi effettuare connessioni senza autenticazione tramite password. Il file di chiave pubblica di Adobe corrisponde al file di chiave privata sul tuo computer/server e l&#39;autenticazione avviene in questo modo.

   Per la creazione di questi file rivolgiti al tuo gruppo di assistenza di rete interno e chiedi di creare un set di chiavi adatto al tuo ambiente. Gli strumenti e le applicazioni che possono essere utilizzati per la creazione di questi due file sono molteplici.

   Sotto è riportato un esempio che mostra la creazione di questi tipi di file nell&#39;ambiente shell di Unix. Si tratta solo di un esempio di come è possibile procedere e può essere un utile punto di riferimento per comunicare i requisiti necessari al tuo team o gruppo di rete interno.

   ```
   // Linux/Unix (bash shell)
   
   // First make sure the ".ssh" directory exists
   
   $ mkdir ~/.ssh
   
   $ cd ~/.ssh
   
   // Now actually generate the key pair
   
   // Usually we will want to create an empty passphrase (just hit "Enter" for both password prompts)
   
   $ ssh-keygen -q -t dsa
   
   Enter file in which to save the key (/home/user/.ssh/id_dsa):
   
   Enter passphrase (empty for no passphrase): ...
   
   Enter same passphrase again: ...
   
   // Rename or copy the public key file to "authorized_keys"
   
   // This "authorized_keys" file is the one that we will upload to the Adobe FTP server in step 3
   
   $ cp id_dsa.pub authorized_keys 
   ```

1. Carica la chiave pubblica in un account FTP (cliente).

   Carica e testa la chiave pubblica. Connettersi all&#39;account FTP Adobe e creare una directory [!DNL .ssh], se non esiste già. Caricare il file [!DNL authorized_keys] in questa directory [!DNL .ssh]. Per questo passaggio puoi procedere in modi diversi (da riga di comando, da client FTP grafico, e così via). È richiesta solamente la capacità di creare una directory e di caricare un file.

   Di seguito è riportato un altro esempio che prevede sempre l&#39;utilizzo della shell di UNIX.

   ```
   $ ftp ftp.Adobe.com
   
   OR (depending on hostname provided by Adobe)
   
   $ ftp ftp2.Adobe.com
   
   // Enter username and password for account as prompted
   
   ftp> mkdir .ssh
   
   ftp> cd .ssh
   
   ftp> put authorized_keys
   
   ftp> exit
   
   // Now test the connection by logging in to the server using "sftp" command:
   
   $ sftp username@ftp.omniture.com
   
   OR (depending on hostname provided by Adobe)
   
   $ sftp username@ftp2.omniture.com
   
   // You should immediately receive an sftp prompt without having to enter the password:
   
   sftp>
   ```
