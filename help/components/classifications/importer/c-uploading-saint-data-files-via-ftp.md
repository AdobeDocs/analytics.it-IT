---
description: Come caricare i file di dati tramite FTP.
title: Importazione FTP
feature: Classifications
exl-id: 3e93b35c-6f65-4a93-887d-d94e4d359bdc
source-git-commit: 1b1cea9b9e336a1836e824906e620a0761c364e4
workflow-type: tm+mt
source-wordcount: '642'
ht-degree: 5%

---

# Importazione FTP

Passaggi che descrivono come caricare i file di dati tramite FTP.

## Importazione FTP {#concept_2F965BE873254546A61FB755F25299FD}

Per caricare file di dati tramite FTP:

1. **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.

I seguenti limiti consigliati sono importanti. Troppi

>[!IMPORTANT]
>
>L&#39;utilizzo di troppi file di piccole dimensioni o di file di grandi dimensioni singoli può creare un carico di elaborazione non necessario sui server di elaborazione. Adobe consiglia di suddividere file di grandi dimensioni in blocchi da 50 MB e di combinare file di piccole dimensioni.

La configurazione iniziale popola il database delle classificazioni con un ampio set di dati originali o ristruttura le classificazioni, anziché riclassificare alcune righe o aggiungere altre righe.

Dopo un caricamento iniziale in una suite di rapporti (per una determinata variabile o rapporto), Adobe consiglia di caricare solo righe nuove e aggiornate nelle importazioni successive. Le righe che non vengono modificate devono essere omesse dai caricamenti futuri.

Ogni nuovo valore chiave caricato viene conteggiato rispetto agli univoci per quella variabile per il mese.

Se hai superato gli univoci per il mese, non vedrai i dati di classificazione corrispondenti per gli univoci superati nei rapporti. Puoi vedere queste classificazioni nella Data Warehouse.

>[!NOTE]
>
>Il tempo necessario per elaborare un file di dati di classificazione varia in base alle dimensioni del file e al numero corrente di file già elaborati dai server di Adobe. L&#39;elaborazione dei file di dati in genere richiede non più di 72 ore.

## Creare un account FTP

Prima di caricare i dati tramite FTP, crea un account FTP. >

Vedi [FTP e sFTP](/help/export/ftp-and-sftp/ftp-overview.md) per ulteriori informazioni sui server FTP di Adobe.

1. Fai clic su **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. Fai clic su **[!UICONTROL Import File]**, quindi su **[!UICONTROL FTP Import]**.
1. Nella scheda **[!UICONTROL Import File]** fai clic su **[!UICONTROL Add New]**.
1. Specifica i dettagli dell&#39;account FTP:

   | Elemento | Descrizione |
   |---|---|
   | **Nome** | Nome account FTP. |
   | **Set di dati da classificare** | Dall’elenco a discesa, seleziona il set di dati (variabile del rapporto di marketing) da classificare. |
   | **Selezionare suite di rapporti** | Seleziona le suite di rapporti in cui desideri classificare il set di dati selezionato. Per selezionare più suite di rapporti, le classificazioni per ciascuna suite di rapporti selezionata devono essere identiche. |
   | **Sovrascrivi i dati sui conflitti** | Selezionare questa opzione per sovrascrivere i dati duplicati. Questa opzione è utile se stai aggiornando le classificazioni esistenti. Se sei sul [architettura di classificazione più recente](../sets/overview.md), questa impostazione è sempre attivata. |
   | **Dopo il completamento dell’importazione** | Seleziona questa opzione per esportare automaticamente il set di dati aggiornato sullo stesso account FTP una volta Specificate l’indirizzo e-mail per ricevere le notifiche su questo account FTP una volta completata l’importazione. Se sei sul [architettura di classificazione più recente](../sets/overview.md), questa opzione non è disponibile. |
   | **Destinatario delle notifiche** | Specifica l&#39;indirizzo e-mail per ricevere le notifiche relative a questo account FTP. |
   | **Autorizzare** | (Obbligatorio) Autorizza Adobe ad importare automaticamente tutti i file di dati inviati al nuovo account FTP. |

1. Fai clic su **[!UICONTROL Save]** (Usa modello di attribuzione non predefinito).

Una volta creato, puoi modificare o eliminare gli account FTP facendo clic sul collegamento appropriato accanto all&#39;account FTP desiderato.

>[!NOTE]
>
>Le notifiche non vengono inviate se un’importazione non introduce modifiche a una classificazione. Un messaggio e-mail viene inviato solo se ha esito positivo e determina modifiche a una classificazione.

## Importare classificazioni tramite FTP

Puoi utilizzare un account FTP per importare le classificazioni in Adobe Analytics.

Per importare le classificazioni tramite FTP:

1. Fai clic su **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. Fai clic su **[!UICONTROL Import File]**, quindi su **[!UICONTROL FTP Import]**.
1. Accanto all&#39;account FTP che desideri utilizzare, fai clic su **[!UICONTROL View]**.
1. Utilizza le informazioni di accesso FTP (Host, Accesso, Password) per accedere al server FTP utilizzando un client FTP scelto.
1. Carica il file di dati ( `.tab` o `.txt`) al server FTP.
1. Dopo aver caricato il file di dati, carica un file FIN che indica che il file è pronto per l&#39;elaborazione.

   Il file FIN è un file vuoto con lo stesso nome del file di dati, con un `.fin` estensione del nome file. Ad esempio, se il file di dati è `classdata1.tab`, il nome del file FIN è `classdata1.fin`.

A intervalli regolari, Adobe recupera i file di dati caricati con un file FIN associato. Adobe li importa nelle suite di rapporti e nei set di dati specificati nella configurazione dell’account FTP.

Una volta che Adobe Analytics ha letto ed elaborato i file caricati nella cartella FTP, questi vengono automaticamente rimossi dal sito FTP.
