---
description: Configura l’account di importazione cloud e il percorso in cui è possibile caricare i dati di classificazione
keywords: Analysis Workspace
title: Configurare i percorsi di importazione ed esportazione cloud
feature: Classifications
exl-id: 55179868-6228-44ff-835c-f4a7b38e929b
source-git-commit: 9b263b0b2d41533630f225d4d4dcc9b1e0c4f1df
workflow-type: tm+mt
source-wordcount: '1686'
ht-degree: 31%

---

# Configurare i percorsi di importazione ed esportazione cloud

<!-- This page is almost duplicated with the "Configure cloud export locations" article in CJA. Differences are that Snowflake isn't supported here and there is a Suffix field for each account type. -->

>[!NOTE]
>
>Quando crei e modifichi posizioni, tieni presente quanto segue:<ul><li>Gli amministratori di sistema possono impedire agli utenti di creare percorsi, come descritto in [Specificare se gli utenti possono creare percorsi](/help/components/locations/locations-manager.md#configure-whether-users-can-create-locations). Se non è possibile creare i percorsi come descritto in questa sezione, contattare l&#39;amministratore di sistema.</li><li>Una posizione può essere modificata solo dall’utente che l’ha creata o da un amministratore di sistema.</li></ul>

Dopo aver [configurato un account cloud](/help/components/locations/configure-import-accounts.md), puoi configurare una posizione su tale account. Una singola posizione può essere utilizzata per uno dei seguenti scopi (una singola posizione non può essere associata a più scopi):

* Esportazione di file tramite [feed dati](/help/export/analytics-data-feed/create-feed.md)
* Esportazione di report tramite [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)
* Importazione di schemi tramite [Set di classificazione](/help/components/classifications/sets/overview.md)

Devi configurare Adobe Analytics con le informazioni necessarie per accedere al tuo account cloud. Questo processo consiste nell&#39;aggiungere e configurare l&#39;account (ad esempio ARN per il ruolo Amazon S3, Google Cloud Platform e così via) come descritto in [Configurare gli account di importazione ed esportazione cloud](/help/components/locations/configure-import-accounts.md), quindi aggiungere e configurare la posizione all&#39;interno dell&#39;account (come descritto in questo articolo).

Per informazioni su come visualizzare ed eliminare i percorsi esistenti, vedere [Gestione percorsi](/help/components/locations/locations-manager.md).

## Inizia a creare o modificare una posizione

1. In Adobe Analytics, seleziona [!UICONTROL **Componenti**] > [!UICONTROL **Percorsi**].

1. Nella pagina [!UICONTROL Locations], seleziona la scheda [!UICONTROL **Percorsi**].

1. (Condizionale) Se sei un amministratore di sistema, puoi abilitare l&#39;opzione [!UICONTROL **Visualizza percorsi per tutti gli utenti**] per visualizzare i percorsi creati da tutti gli utenti dell&#39;organizzazione.
   ![visualizza percorsi per tutti gli utenti](assets/locations-all-users.png)

1. Per aggiungere una nuova posizione, selezionare [!UICONTROL **Aggiungi posizione**]. (Se non hai già aggiunto un account, aggiungine uno come descritto in [Configurare gli account di importazione ed esportazione cloud](/help/components/locations/configure-import-accounts.md).)

   Viene visualizzata la finestra di dialogo [!UICONTROL **Aggiungi percorso**]

   Oppure

   Per modificare una posizione esistente, seleziona il menu a tre punti accanto al nome della posizione, quindi seleziona [!UICONTROL **Modifica**].

   Viene visualizzata la finestra di dialogo [!UICONTROL **Dettagli località**].

1. Specifica le seguenti informazioni:

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **Nome**] | Nome della posizione. |
   | [!UICONTROL **Descrizione**] | Fornisci una breve descrizione dell’account per distinguerlo da altri account dello stesso tipo. |
   | [!UICONTROL **Usa con**] | Seleziona se desideri utilizzare questa posizione con [!UICONTROL **feed di dati**], [!UICONTROL **Data Warehouse**] o [!UICONTROL **set di classificazione**]. <p>Quando effettuate una selezione, tenete presente quanto segue:</p><ul><li>Una singola posizione non può essere utilizzata per più scopi. Ad esempio, una posizione utilizzata per i feed di dati non può essere utilizzata anche per set di Data Warehouse o di classificazione.</li><li>Per evitare conflitti di file all&#39;interno di un percorso, non modificare il valore del campo [!UICONTROL **Usa con**] dopo l&#39;utilizzo del percorso.</li><li>Se stai creando un percorso per un account di posta elettronica, seleziona [!UICONTROL **Data Warehouse**] in questo campo. Le posizioni e-mail non sono supportate con feed di dati e set di classificazione.</li></ul> |
   | [!UICONTROL **Rendi la posizione disponibile a tutti gli utenti dell&#39;organizzazione**] | Abilita questa opzione per consentire ad altri utenti dell’organizzazione di utilizzare la posizione.<p>Quando condividi le posizioni, tieni presente quanto segue:</p><ul><li>Le posizioni condivise non possono essere annullate.</li><li>Le posizioni condivise possono essere modificate solo dal proprietario della posizione.</li><li>Le posizioni possono essere condivise solo se è condiviso anche l’account a cui è associata la posizione.</li></ul> |
   | [!UICONTROL **Account località**] | Selezionare l&#39;account della posizione in cui si desidera creare la posizione. Per informazioni su come creare un account, vedere [Configurare gli account di importazione ed esportazione cloud](/help/components/locations/configure-import-accounts.md). |

1. Per completare il modulo per la configurazione del percorso, continuare con la sezione seguente che corrisponde al tipo di account selezionato nel campo [!UICONTROL **Account percorso**]. Sono disponibili anche altri tipi di account legacy, ma non sono consigliati.

### Amazon S3 con ruolo ARN

Per configurare una posizione ARN per il ruolo Amazon S3, specifica le seguenti informazioni:

1. [Inizia a creare o modificare un percorso](#begin-creating-or-editing-a-location), come descritto in precedenza.

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **Bucket**] | Il bucket all’interno dell’account Amazon S3 in cui desideri inviare i dati di Adobe Analytics. <p>Assicurati che l&#39;ARN utente fornito da Adobe disponga dell&#39;autorizzazione `S3:PutObject` per caricare i file in questo bucket. </p><p>I nomi dei bucket devono soddisfare regole di denominazione specifiche. Ad esempio, devono contenere da 3 a 63 caratteri, possono essere composte solo da lettere minuscole, numeri, punti (.) e trattini (-) e devono iniziare e terminare con una lettera o un numero. [Un elenco completo delle regole di denominazione è disponibile nella documentazione di AWS](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucketnamingrules.html?lang=it). </p> |
   | [!UICONTROL **Prefisso**] | La cartella all’interno del bucket in cui desideri inserire i dati. Specifica il nome di una cartella, quindi aggiungi una barra rovesciata dopo il nome per creare la cartella. Ad esempio, folder_name/ |

   {style="table-layout:auto"}

1. Seleziona [!UICONTROL **Salva**].

   Ora puoi importare o esportare dati da o verso l’account e la posizione configurati. Per esportare i dati, utilizzare [Feed dati](/help/export/analytics-data-feed/create-feed.md) o [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). Per importare i dati, utilizzare [Set di classificazione](/help/components/classifications/sets/overview.md).

   I dati importati non vengono eliminati dalla destinazione cloud dopo l’importazione.

   >[!NOTE]
   >
   >   Se in precedenza hai utilizzato [FTP per importare classificazioni](/help/components/classifications/importer/c-uploading-saint-data-files-via-ftp.md) in Adobe Analytics, devi caricare un file FIN. Questo file FIN non è necessario per l’importazione da account cloud.


### Google Cloud Platform

Per configurare una posizione di Google Cloud Platform, specifica le informazioni seguenti:

1. [Inizia a creare o modificare un percorso](#begin-creating-or-editing-a-location), come descritto in precedenza.

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **Bucket**] | Il bucket all’interno dell’account GCP in cui desideri inviare i dati di Adobe Analytics. Assicurati di aver concesso all’entità fornita da Adobe l’autorizzazione per caricare i file in questo bucket. |
   | [!UICONTROL **Prefisso**] | La cartella all’interno del bucket in cui desideri inserire i dati. Specifica il nome di una cartella, quindi aggiungi una barra rovesciata dopo il nome per creare la cartella. Ad esempio, folder_name/ |

   {style="table-layout:auto"}

1. Seleziona [!UICONTROL **Salva**].

   Ora puoi importare o esportare dati da o verso l’account e la posizione configurati. Per esportare i dati, utilizzare [Feed dati](/help/export/analytics-data-feed/create-feed.md) o [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). Per importare i dati, utilizzare [Set di classificazione](/help/components/classifications/sets/overview.md).

   I dati importati non vengono eliminati dalla destinazione cloud dopo l’importazione.

   >[!NOTE]
   >
   >   Se in precedenza hai utilizzato [FTP per importare classificazioni](/help/components/classifications/importer/c-uploading-saint-data-files-via-ftp.md) in Adobe Analytics, devi caricare un file FIN. Questo file FIN non è necessario per l’importazione da account cloud.


### Azure SAS

Per configurare una posizione SAS di Azure, specifica le informazioni seguenti:

1. [Inizia a creare o modificare un percorso](#begin-creating-or-editing-a-location), come descritto in precedenza.

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **Contenitore**] | Il contenitore all’interno dell’account specificato nel punto in cui desideri inviare i dati di Adobe Analytics. |
   | [!UICONTROL **Prefisso**] | La cartella all’interno del contenitore in cui desideri inserire i dati. Specifica il nome di una cartella, quindi aggiungi una barra rovesciata dopo il nome per creare la cartella. Ad esempio: `folder_name/` |

   {style="table-layout:auto"}

1. Seleziona [!UICONTROL **Salva**].

   Ora puoi importare o esportare dati da o verso l’account e la posizione configurati. Per esportare i dati, utilizzare [Feed dati](/help/export/analytics-data-feed/create-feed.md) o [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). Per importare i dati, utilizzare [Set di classificazione](/help/components/classifications/sets/overview.md).

   I dati importati non vengono eliminati dalla destinazione cloud dopo l’importazione.

   >[!NOTE]
   >
   >   Se in precedenza hai utilizzato [FTP per importare classificazioni](/help/components/classifications/importer/c-uploading-saint-data-files-via-ftp.md) in Adobe Analytics, devi caricare un file FIN. Questo file FIN non è necessario per l’importazione da account cloud.


### Azure RBAC

Per configurare una posizione RBAC di Azure, specifica le informazioni seguenti:

1. [Inizia a creare o modificare un percorso](#begin-creating-or-editing-a-location), come descritto in precedenza.

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **Account**] | Account di archiviazione Azure. |
   | [!UICONTROL **Contenitore**] | Il contenitore all’interno dell’account specificato nel punto in cui desideri inviare i dati di Adobe Analytics. Assicurati di concedere le autorizzazioni per caricare i file nell’applicazione Azure creata in precedenza. |
   | [!UICONTROL **Prefisso**] | La cartella all’interno del contenitore in cui desideri inserire i dati. Specifica il nome di una cartella, quindi aggiungi una barra rovesciata dopo il nome per creare la cartella. Ad esempio: `folder_name/` |

   {style="table-layout:auto"}

1. Seleziona [!UICONTROL **Salva**].

   Ora puoi importare o esportare dati da o verso l’account e la posizione configurati. Per esportare i dati, utilizzare [Feed dati](/help/export/analytics-data-feed/create-feed.md) o [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). Per importare i dati, utilizzare [Set di classificazione](/help/components/classifications/sets/overview.md).

   I dati importati non vengono eliminati dalla destinazione cloud dopo l’importazione.

   >[!NOTE]
   >
   >   Se in precedenza hai utilizzato [FTP per importare classificazioni](/help/components/classifications/importer/c-uploading-saint-data-files-via-ftp.md) in Adobe Analytics, devi caricare un file FIN. Questo file FIN non è necessario per l’importazione da account cloud.

### E-mail

Per configurare un percorso e-mail, specifica le seguenti informazioni:

1. [Inizia a creare o modificare un percorso](#begin-creating-or-editing-a-location), come descritto in precedenza.

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **Oggetto**] | Oggetto del messaggio e-mail. |
   | [!UICONTROL **Note**] | Il contenuto del messaggio e-mail. |

   {style="table-layout:auto"}

1. Seleziona [!UICONTROL **Salva**].

   È ora possibile esportare i dati nell&#39;account e nel percorso configurati durante l&#39;utilizzo di [Feed dati](/help/export/analytics-data-feed/create-feed.md). (I percorsi e-mail non sono supportati con [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md) o [Set di classificazione](/help/components/classifications/sets/overview.md)).

### Tipi di account legacy

Questi tipi di account legacy sono disponibili solo quando si esportano dati con [Feed dati](/help/export/analytics-data-feed/create-feed.md) e [Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md). Queste opzioni non sono disponibili durante l&#39;importazione di dati con [Set di classificazione](/help/components/classifications/sets/manage/schema.md).

+++FTP

I dati del feed dati possono essere inviati a un Adobe o a una posizione FTP ospitata dal cliente. Specificare la directory Utilizzare il campo percorso per inserire i file di feed in una cartella.

| Campo | Funzione |
|---------|----------|
| [!UICONTROL **Percorso directory**] | Immettere il percorso della directory sul server FTP. Le cartelle devono già esistere. I feed generano un errore se il percorso specificato non esiste. </br>Ad esempio, `/folder_name/folder_name`. |

{style="table-layout:auto"}

+++

+++SFTP

I dati del feed dati possono essere consegnati a una posizione SFTP Adobe o ospitata dal cliente. Il sito di destinazione deve contenere una chiave pubblica RSA o DSA valida. Puoi scaricare la chiave pubblica adatta al momento della creazione del feed.

| Campo | Funzione |
|---------|----------|
| [!UICONTROL **Percorso directory**] | Immettere il percorso della directory sul server FTP. Le cartelle devono già esistere. I feed generano un errore se il percorso specificato non esiste. </br>Ad esempio, `/folder_name/folder_name`. |

{style="table-layout:auto"}

+++

+++S3

Puoi inviare i dati di Data Warehouse direttamente ai bucket Amazon S3. Questo tipo di destinazione richiede un nome bucket, un ID chiave di accesso e una chiave segreto. Consulta [Requisiti di denominazione del bucket Amazon S3](https://docs.aws.amazon.com/it_it/AmazonS3/latest/userguide/bucketnamingrules.html) nella documentazione di Amazon S3 per ulteriori informazioni.

L’utente fornito per il caricamento dei dati di Data Warehouse deve disporre delle seguenti [autorizzazioni](https://docs.aws.amazon.com/it_it/AmazonS3/latest/API/API_Operations_Amazon_Simple_Storage_Service.html):

* s3:GetObject
* s3:PutObject
* s3:PutObjectAcl

Sono supportate le seguenti 16 aree geografiche standard di AWS (utilizzando l’algoritmo di firma appropriato, se necessario):

* us-east-2
* us-east-1
* us-west-1
* us-west-2
* ap-south-1
* ap-northeast-2
* ap-southeast-1
* ap-southeast-2
* ap-northeast-1
* ca-central-1
* eu-central-1
* eu-west-1
* eu-west-2
* eu-west-3
* eu-north-1
* sa-east-1

>[!NOTE]
>
>L’area geografica cn-north-1 non è supportata.

+++

+++BLOB di Azure

Data warehouse supporta le destinazioni BLOB di Azure. Richiede un contenitore, un account e una chiave. Amazon crittografa automaticamente i dati inattivi. Quando scarichi i dati, questi vengono decrittografati automaticamente. Per ulteriori informazioni, consulta [Creare un account di archiviazione](https://learn.microsoft.com/it-it/azure/storage/common/storage-account-create?tabs=azure-portal#view-and-copy-storage-access-keys) nelle documentazioni di Microsoft Azure.

>[!NOTE]
>
>È necessario implementare un processo personalizzato per gestire lo spazio su disco nella destinazione di Data Warehouse. Adobe non elimina dati dal server.

+++


