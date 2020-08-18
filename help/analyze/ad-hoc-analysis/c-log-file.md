---
title: File di registro
description: Ottenete un file di registro per la risoluzione dei problemi.
translation-type: tm+mt
source-git-commit: aea3b4448b61e8b1b217b4f74b0b80c9fbedd070
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 3%

---


# File di registro

Quando si risolvono problemi con  Ad Hoc Analysis, talvolta è necessario ottenere il relativo file di registro.  Adobe può utilizzare il file di registro per individuare la causa principale del problema e fornire una risoluzione. Il `discover.log` file contiene tutte le interazioni degli utenti, le informazioni sul caricamento dei rapporti e i messaggi di errore Java per tutte le sessioni. Interrompe qualsiasi informazione protetta, ad esempio la password dell&#39;utente. I file di registro di grandi dimensioni sono suddivisi in incrementi di 10 MB. Quando fornite  Adobe con i file di registro, accertatevi che tutti i file siano selezionati.

## Windows

Ottenete il `discover.log` file per Windows:

1. Fare clic sul menu Start e selezionare **Esegui** oppure premere `[Win]` + `[R]`.
2. Incollate quanto segue nel campo di testo e fate clic su **OK**:

   ```text
   %appdata%/../Local/Adobe/Discover/log
   ```

3. Evidenziate tutti i file nella cartella, quindi fate clic con il pulsante destro del mouse e scegliete **Invia a > Cartella** compressa.
4. Fornite al rappresentante del Adobe  il file .zip.

## Mac

Per ottenere il `discover.log` file per Mac OS, effettuate le seguenti operazioni:

1. Apri il Finder e passa a `/Users/your-user/.adobe/Discover/log`
2. Evidenziate tutti i file nella cartella, quindi fate clic con il pulsante destro del mouse e scegliete **Comprimi**.
3. Fornite al rappresentante del Adobe  il file .zip.

Se la dimensione totale di un file compresso supera i 10 MB, un rappresentante di Adobe  può fornire una posizione FTP temporanea.
