---
description: Se si verifica un errore, viene riportato un errore nella colonna Stato processo.
keywords: Feed dati;processo;risoluzione dei problemi;errore;ftp;chdir;connect;login;put
seo-description: Se si verifica un errore, viene riportato un errore nella colonna Stato processo.
seo-title: Risoluzione dei problemi dei processi
solution: Analytics
title: Risoluzione dei problemi dei processi
uuid: 8fbb914e-03db-434e-b4d3-8594144ff2b7
translation-type: tm+mt
source-git-commit: ee9a6462138fe3483ca8a4ba042cb4eb39536031

---


# Risoluzione dei problemi dei processi

In caso di problemi durante la visualizzazione di un feed di dati sul tuo sito FTP, usa questa pagina per capire perché.

## Codici di errore

Se si verifica un errore, viene riportato un errore nella colonna Stato processo.

### Errore di connessione FTP

Il feed non può navigare o scrivere nella cartella specificata. Verificate che la cartella di destinazione esista sul sito FTP e che le credenziali fornite dispongano delle autorizzazioni di lettura/scrittura corrette per tale cartella.

### Errore di connessione FTP

Impossibile connettersi alla destinazione FTP. Verificate che la destinazione FTP sia corretta e valida.

### Errore FTP

Errore generico in cui il feed non è in grado di scrivere il file sul sito FTP. Questo errore può provenire dal disco del server FTP pieno o dalla quota superata. L'errore può anche essere causato da un errore del server di rete o di destinazione.

### Errore di accesso FTP

Il feed non può effettuare l'accesso utilizzando le credenziali fornite. Accertatevi che il nome utente e la password FTP siano corretti.

### Errore di caricamento FTP

Il feed non può scrivere file sul sito FTP. Assicurati che il login FTP disponga delle autorizzazioni corrette per leggere e scrivere i dati sul tuo sito FTP. Questo errore può anche provenire da un disco intero o superare la quota del disco sul server FTP.

## Passaggi per la risoluzione dei problemi

Accedete al vostro sito FTP e caricate qualsiasi file al suo interno. Nella maggior parte dei casi, è possibile determinare il punto di errore utilizzando questi passaggi.

1. Effettuate l'accesso al sito FTP utilizzando Esplora file (Windows) o il Finder (Mac). Accertatevi di utilizzare il protocollo FTP (`ftp://`). Se non riesci a raggiungere il sito FTP, puoi collaborare con il proprietario del sito FTP per determinare la destinazione corretta.

   ![Esplora file](assets/file_explorer.png)

2. Viene visualizzata una finestra a comparsa in cui viene richiesto un nome utente e una password. Immettete le credenziali di autenticazione. Se le credenziali vengono accettate, la finestra mostra il contenuto corrente sul sito FTP. Se le credenziali non vengono accettate, potete collaborare con il proprietario dell'FTP per verificare che il nome utente e la password siano corretti.
3. Caricate un file sul sito FTP trascinandolo nella finestra autenticata. Qualsiasi immagine o documento di testo è adeguato. Se si verifica un errore durante il tentativo di inserire un file sul sito FTP, rivolgersi al proprietario dell'FTP per verificare che lo spazio su disco sia sufficiente e che il nome utente disponga delle autorizzazioni di scrittura per il sito FTP.
4. Una volta confermato che il file si trova sul sito FTP, potete eliminare il file caricato nel passaggio precedente.
5. Se tutti i passaggi indicati funzionano e si verifica comunque un errore FTP, l'assistenza clienti deve contattare l'Assistenza clienti.
