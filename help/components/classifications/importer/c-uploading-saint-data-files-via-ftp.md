---
description: Come caricare i file di dati tramite FTP.
title: Importazione FTP
feature: Classifications
exl-id: 3e93b35c-6f65-4a93-887d-d94e4d359bdc
source-git-commit: f71b80dce9d447c431130901d86947d23e28d378
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 4%

---

# Importazione FTP

>[!IMPORTANT]
>
>Non è più consigliabile utilizzare l’FTP per l’importazione come descritto in questa pagina.
>
>L&#39;FTP non è consigliato perché è un metodo non crittografato di condivisione dei file, il che significa che chiunque può intercettare il contenuto del file, nonché il nome utente e la password utilizzati per l&#39;account.
>
>Configura invece un account cloud come descritto in [Configurare account di importazione cloud](/help/components/locations/configure-import-accounts.md).

Passaggi che descrivono come caricare i file di dati tramite FTP.

## Importazione FTP {#concept_2F965BE873254546A61FB755F25299FD}

Per caricare i file di dati tramite FTP:

1. **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.

I seguenti limiti consigliati sono importanti.

>[!IMPORTANT]
>
>La presenza di troppi file di piccole dimensioni o di singoli file di grandi dimensioni può creare un carico di elaborazione non necessario sui server di elaborazione. L’Adobe consiglia di suddividere i file di grandi dimensioni in blocchi da 50 MB e di combinare file di piccole dimensioni.

La configurazione iniziale popola il database delle classificazioni con un ampio set di dati originali o ristruttura le classificazioni, anziché riclassificare alcune righe o aggiungere righe.

In seguito a un caricamento iniziale in una suite di rapporti (per una determinata variabile o rapporto), l’Adobe consiglia di caricare solo le righe nuove e aggiornate nelle importazioni successive. Le righe che non vengono modificate devono essere omesse dai caricamenti futuri.

Ogni nuovo valore chiave caricato viene conteggiato rispetto ai valori univoci per tale variabile per il mese.

Se hai superato i valori univoci per il mese, nei rapporti non verranno visualizzati i dati di classificazione corrispondenti per i valori univoci superati. Puoi vedere queste classificazioni in Data Warehouse.

>[!NOTE]
>
>Il tempo necessario per elaborare un file di dati di classificazione varia in base alle dimensioni del file e al numero corrente di file già elaborati dai server Adobe. L’elaborazione dei file di dati in genere non richiede più di 72 ore.

## Creare un account FTP

Prima di caricare i dati tramite FTP, crea un account FTP. >

Consulta [FTP e sFTP](/help/export/ftp-and-sftp/ftp-overview.md) per ulteriori dettagli sui server FTP di Adobe.

1. Fai clic su **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. Fai clic su **[!UICONTROL Import File]**, quindi su **[!UICONTROL FTP Import]**.
1. Nella scheda **[!UICONTROL Import File]** fai clic su **[!UICONTROL Add New]**.
1. Specifica i dettagli dell&#39;account FTP:

   | Elemento | Descrizione |
   |---|---|
   | **Nome** | Il nome dell’account FTP. |
   | **Set di dati da classificare** | Dall’elenco a discesa, seleziona il set di dati (variabile del rapporto di marketing) che desideri classificare. |
   | **Selezionare suite di rapporti** | Seleziona le suite di rapporti in cui desideri classificare il set di dati selezionato. Per selezionare più suite di rapporti, le classificazioni per ciascuna delle suite di rapporti selezionate devono essere identiche. |
   | **Sovrascrivi i dati sui conflitti** | Selezionare questa opzione per sovrascrivere i dati duplicati. Questa opzione è utile se aggiorni le classificazioni esistenti. Se è attiva la [architettura di classificazione più recente](../sets/overview.md), questa impostazione è sempre abilitata. |
   | **Dopo il completamento dell’importazione** | Seleziona questa opzione per esportare automaticamente il set di dati aggiornato nello stesso account FTP una volta specificato l’indirizzo e-mail per ricevere notifiche su questo account FTP una volta completata l’importazione. Se è attiva la [architettura di classificazione più recente](../sets/overview.md), opzione non disponibile. |
   | **Destinatario notifica** | Specifica l&#39;indirizzo e-mail per ricevere notifiche su questo account FTP. |
   | **Autorizza** | (Obbligatorio) Autorizza l’Adobe a importare automaticamente tutti i file di dati inviati al nuovo account FTP. |

1. Fai clic su **[!UICONTROL Save]** (Usa modello di attribuzione non predefinito).

Una volta creati, è possibile modificare o eliminare gli account FTP facendo clic sul collegamento appropriato accanto all&#39;account FTP desiderato.

>[!NOTE]
>
>Se un’importazione non introduce modifiche in una classificazione, non vengono inviate notifiche. Un’e-mail viene inviata solo se ha esito positivo e comporta modifiche a una classificazione.

## Importare classificazioni tramite FTP

Puoi utilizzare un account FTP per importare le classificazioni in Adobe Analytics.

Per importare le classificazioni tramite FTP:

1. Fai clic su **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. Fai clic su **[!UICONTROL Import File]**, quindi su **[!UICONTROL FTP Import]**.
1. Accanto all&#39;account FTP che si desidera utilizzare, fare clic su **[!UICONTROL View]**.
1. Utilizza le informazioni di accesso FTP (host, accesso, password) per accedere al server FTP utilizzando un client FTP di tua scelta.
1. Carica il file di dati ( `.tab` o `.txt`) al server FTP.
1. Dopo aver caricato il file di dati, carica un file FIN che indica che il file è pronto per l’elaborazione.

   Il file FIN è un file vuoto che ha lo stesso nome del file di dati, con un `.fin` estensione del nome file. Ad esempio, se il file di dati è `classdata1.tab`, il nome del file FIN è `classdata1.fin`.

A intervalli regolari, Adobe recupera i file di dati caricati a cui è associato un file FIN. Adobe le importa nelle suite di rapporti e nei set di dati specificati nella configurazione dell’account FTP.

Una volta che Adobe Analytics ha letto ed elaborato i file caricati nella cartella FTP, questi vengono automaticamente rimossi dal sito FTP.
