---
description: La connessione senza password agli account FTP è possibile solo utilizzando sia una connessione SFTP che un metodo di autenticazione alternativo. Questo comporta un set di due file (uno da risiedere sull’account FTP e l’altro da risiedere sul computer) denominati combinazione di chiave pubblica e privata.
keywords: ftp;sftp
title: Connessione ad Adobe tramite SFTP senza password
feature: FTP Export
exl-id: 7ff9511c-50a2-466f-b5af-6bbd59941ce5
TQID: https://experienceleague.adobe.com/qQmzBUalqWjJ7FYow1DBCEfVixzultPI2PJSNhOsLlY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 609
ht-degree: 2%

---

# Connessione ad Adobe tramite SFTP senza password

La connessione senza password agli account FTP è possibile solo utilizzando sia una connessione SFTP che un metodo di autenticazione alternativo. Questo comporta un set di due file (uno da risiedere sull’account FTP e l’altro da risiedere sul computer) denominati combinazione di chiave pubblica e privata.

Non è meno sicuro dell’autenticazione tramite password. Si tratta di un’altra forma di autenticazione che non richiede all’utente di digitare ogni volta una password. Se utilizzati correttamente, questi file consentono al computer di accedere senza dover specificare una password. È necessario configurarlo computer per computer. Tutte le altre connessioni che non utilizzano questi file di chiave devono comunque specificare una password.

Alcuni client richiedono un SFTP (Secure File Transfer Protocol) per la trasmissione di dati sensibili. Una connessione SFTP è più sicura di una normale connessione FTP perché consente la comunicazione di dati crittografati. Per impostazione predefinita, tutti gli account FTP di Adobe sono pronti per SFTP. È possibile aprire una connessione SFTP con un nome utente e una password validi utilizzando un client SFTP che si connette alla porta 22 (normali connessioni FTP non protette dalla porta 21).

Quando utilizzi SFTP, in determinate condizioni è possibile utilizzare chiavi private per connettersi all’account senza una password. Questo metodo consente al computer di utilizzare i file chiave per l&#39;autenticazione anziché la normale autenticazione tramite password. Ciò significa che solo il computer in cui è memorizzata la chiave privata può connettersi senza password. Tutti gli altri computer/utenti devono ancora utilizzare l&#39;autenticazione tramite password (a meno che non siano state configurate anche chiavi private in questi altri computer).

**Per impostare e utilizzare chiavi private per l&#39;autenticazione senza password**

1. Account FTP creato (Adobe).

   Un rappresentante di Adobe può creare un account FTP, se non ne esiste già uno. Contatta il team del tuo account Adobe o l’Assistenza clienti di Adobe per creare un account.
1. Creazione di chiavi pubbliche/private (cliente).

   Crea una combinazione di chiavi pubblica e privata. La chiave privata è un file privato del computer/server e che si trova in tale posizione. Il file della chiave pubblica deve essere caricato nell’account Adobe. Se utilizzato in questo modo, è possibile connettersi senza autenticazione tramite password. Il file della chiave pubblica in Adobe corrisponde al file della chiave privata sul computer/server e si autentica in questo modo.

   Per creare questi file, rivolgiti al gruppo di supporto di rete interno per creare un set di chiavi appropriato per il tuo ambiente. Esistono molti strumenti e applicazioni che possono essere utilizzati per creare questi due file.

   Di seguito è riportato un esempio di come eseguire questa operazione in un ambiente shell UNIX. Questo è solo un esempio di come ciò possa essere fatto e funge da utile punto di riferimento per la comunicazione dei requisiti al tuo team o gruppo di rete interno.

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

1. Carica la chiave pubblica nell&#39;account FTP (cliente).

   Carica e verifica la chiave pubblica. Connettersi all&#39;account FTP di Adobe e creare una directory [!DNL .ssh], se non esiste già. Caricare il file [!DNL authorized_keys] in questa directory [!DNL .ssh]. Questa operazione può essere eseguita in diversi modi (riga di comando, client FTP grafico e così via). È sufficiente creare una directory e caricare un file.

   Di nuovo, ecco un esempio di come farlo utilizzando una shell UNIX.

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
