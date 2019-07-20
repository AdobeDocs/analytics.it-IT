---
description: La connessione senza password agli account FTP è possibile solo tramite una connessione SFTP e un metodo di autenticazione alternativo. Ciò prevede un set di due file (uno che risiederà sull'account FTP e l'altro che risiederà sul tuo computer) denominato "combinazione di chiave pubblica e privata".
keywords: ftp; sftp
seo-description: La connessione senza password agli account FTP è possibile solo tramite una connessione SFTP e un metodo di autenticazione alternativo. Ciò prevede un set di due file (uno che risiederà sull'account FTP e l'altro che risiederà sul tuo computer) denominato "combinazione di chiave pubblica e privata".
seo-title: Connessione ad Adobe tramite SFTP senza password
solution: Analytics
title: Connessione ad Adobe tramite SFTP senza password
uuid: 88728309-50 d 2-450 b-b 0 e 6-7 dcdf 61 b 5 dbc
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Connessione ad Adobe tramite SFTP senza password

La connessione senza password agli account FTP è possibile solo tramite una connessione SFTP e un metodo di autenticazione alternativo. Ciò prevede un set di due file (uno che risiederà sull'account FTP e l'altro che risiederà sul tuo computer) denominato "combinazione di chiave pubblica e privata".

La sicurezza è la medesima garantita dall'uso dell'autenticazione tramite password. Si tratta di una forma di autenticazione diversa che non richiede all'utente di immettere ogni volta una password. Quando utilizzati correttamente, questi file consentono l'accesso a un particolare computer, senza dover specificare una password. Questa modalità deve essere configurata computer per computer. Tutte le altre connessioni che non utilizzano questi file chiave devono sempre specificare una password.

Un SFTP (Secure File Transfer Protocol, Protocollo di trasferimento file sicuro) è richiesto da alcuni client per la trasmissione di dati sensibili. Una connessione SFTP è più sicura rispetto a una normale connessione FTP, perché consente la comunicazione dati crittografata. Per impostazione predefinita, tutti gli account Adobe FTP sono a pagamento. Una connessione SFTP può essere aperta con un nome utente e una password validi utilizzando un client SFTP che si connetta sulla porta 22 (le normali connessioni FTP non sicure utilizzano la porta 21).

Quando si utilizza SFTP, è possibile, in condizioni specifiche, utilizzare chiavi private per connettersi all'account senza una password. Questo metodo consente al tuo computer di utilizzare per l'autenticazione i file chiave invece della solita autenticazione tramite password. Ciò significa che solamente il computer su cui si trova la chiave privata può effettuare la connessione senza una password. Tutti gli altri computer/utenti dovranno sempre utilizzare l'autenticazione tramite password (a meno che non siano state configurate chiavi private anche su questi computer).

**Per configurare e utilizzare le chiavi private per l'autenticazione senza password**

1. Account FTP creato (Adobe).

   Un rappresentante Adobe può creare un account FTP, se non esiste già. Contatta il tuo Adobe Account Manager o l'Assistenza clienti Adobe per richiedere la creazione di un account.
1. Creazione di chiave pubblica/privata (cliente).

   Crea una combinazione di chiave pubblica e privata. La chiave privata è un file riservato al tuo computer/server e su cui è memorizzato. Il file di chiave pubblica deve essere caricato sull'account Adobe. Quando utilizzato in questo modo, puoi effettuare connessioni senza autenticazione tramite password. Il file di chiave pubblica di Adobe corrisponde al file di chiave privata sul tuo computer/server e l'autenticazione avviene in questo modo.

   Per la creazione di questi file rivolgiti al tuo gruppo di assistenza di rete interno e chiedi di creare un set di chiavi adatto al tuo ambiente. Gli strumenti e le applicazioni che possono essere utilizzati per la creazione di questi due file sono molteplici.

   Sotto è riportato un esempio che mostra la creazione di questi tipi di file nell'ambiente shell di Unix. Si tratta solo di un esempio di come è possibile procedere e può essere un utile punto di riferimento per comunicare i requisiti necessari al tuo team o gruppo di rete interno.

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

   Carica e testa la chiave pubblica. Connect to the Adobe FTP account and create a [!DNL .ssh] directory, if it does not already exist. Upload the [!DNL authorized_keys] file to this [!DNL .ssh] directory. Per questo passaggio puoi procedere in modi diversi (da riga di comando, da client FTP grafico, e così via). È richiesta solamente la capacità di creare una directory e di caricare un file.

   Di seguito è riportato un altro esempio che prevede sempre l'utilizzo della shell di UNIX.

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

