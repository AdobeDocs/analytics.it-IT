---
description: Configura l’account di importazione cloud e il percorso in cui è possibile caricare i dati di classificazione
keywords: Analysis Workspace
title: Configurare i percorsi di importazione ed esportazione cloud
feature: Classifications
exl-id: 55179868-6228-44ff-835c-f4a7b38e929b
source-git-commit: 9b36cfef9fbc3f6ce4e1fc1485a3eb8c2240a96c
workflow-type: tm+mt
source-wordcount: '1465'
ht-degree: 31%

---

# Configurare i percorsi di importazione ed esportazione cloud

<!-- This page is almost duplicated with the "Configure cloud export locations" article in CJA. Differences are that Snowflake isn't supported here and there is a Suffix field for each account type. -->

Puoi configurare un account cloud (e una posizione sull’account). Un’unica posizione può essere utilizzata per uno dei seguenti scopi (una singola posizione non può essere associata a più scopi, ad esempio Feed dati e Data Warhouse o Set di Data Warehouse e classificazione):

* Esportazione di file tramite [Feed dati](/help/export/analytics-data-feed/create-feed.md)
* Esportazione di rapporti tramite [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)
* Importazione degli schemi tramite [Set di classificazione](/help/components/classifications/sets/overview.md)

Devi configurare Adobe Analytics con le informazioni necessarie per accedere al tuo account cloud. Questo processo consiste nell’aggiungere e configurare l’account (ad esempio ARN per il ruolo Amazon S3, Google Cloud Platform e così via) come descritto in [Configurare account di importazione ed esportazione cloud](/help/components/locations/configure-import-accounts.md), quindi aggiungendo e configurando la posizione all’interno dell’account (come descritto in questo articolo).

## Inizio della creazione o della modifica di un percorso di esportazione cloud

1. In Adobe Analytics, seleziona [!UICONTROL **Componenti**] > [!UICONTROL **Posizioni**].
1. Il giorno [!UICONTROL Locations] , seleziona la [!UICONTROL **Posizioni**] scheda.
1. Per creare una nuova posizione, seleziona [!UICONTROL **Aggiungi posizione**]. (Se non hai già aggiunto un account, aggiungine uno come descritto in [Configurare account di importazione ed esportazione cloud](/help/components/locations/configure-import-accounts.md).)

   Oppure

   Per modificare una posizione esistente, selezionare il menu a 3 punti nella [!UICONTROL **Nome posizione**] per la posizione da modificare, quindi seleziona [!UICONTROL **Modifica**].
Viene visualizzata la finestra di dialogo Posizione.

1. Specifica le seguenti informazioni: |Campo | Funzione | ---------- --------- | [!UICONTROL **Nome**] | Nome della posizione.  |
| [!UICONTROL **Descrizione**] | Fornisci una breve descrizione dell’account per distinguerlo da altri dello stesso tipo. | | [!UICONTROL **Uso con**] | Seleziona se desideri utilizzare questa posizione con [!UICONTROL **Feed dati**], [!UICONTROL **Data Warehouse**], o [!UICONTROL **Set di classificazione**]. <p>Quando effettuate una selezione, tenete presente quanto segue:</p><ul><li>Una singola posizione non può essere utilizzata per più scopi. Ad esempio, una posizione utilizzata per i feed di dati non può essere utilizzata anche per set di Data Warehouse o di classificazione.</li><li>Per evitare conflitti di file all&#39;interno di una posizione, non modificare il valore di [!UICONTROL **Uso con**] dopo l’utilizzo della posizione.</li></ul> | | [!UICONTROL **Account località**] | Selezionare l&#39;account della posizione in cui si desidera creare la posizione. Per informazioni su come creare un account, consulta [Aggiungi un account](#add-an-account). |

1. Nella sezione [!UICONTROL **Proprietà posizione**], specifica le informazioni specifiche sul tipo di account dell’account di posizione.

   Continua con la sezione seguente che corrisponde al tipo di account selezionato in [!UICONTROL **Account ubicazione**] campo. Sono disponibili anche altri tipi di account legacy, ma non sono consigliati.



### ARN per ruolo Amazon S3

Per configurare una posizione ARN per il ruolo Amazon S3, specifica le seguenti informazioni:

1. [Inizio della creazione o della modifica di un percorso di esportazione cloud](#begin-creating-or-editing-a-cloud-export-location), come descritto in precedenza.

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **Nome del bucket**] | Il bucket all’interno dell’account Amazon S3 in cui desideri inviare i dati di Adobe Analytics. <p>Assicurati che l&#39;ARN utente fornito da Adobe disponga del `S3:PutObject` per caricare i file in questo bucket. </p><p>I nomi dei bucket devono soddisfare regole di denominazione specifiche. Ad esempio, devono contenere da 3 a 63 caratteri, possono essere composte solo da lettere minuscole, numeri, punti (.) e trattini (-) e devono iniziare e terminare con una lettera o un numero. [Un elenco completo delle regole di denominazione è disponibile nella documentazione di AWS](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucketnamingrules.html). </p> |
   | [!UICONTROL **Prefisso chiave**] | La cartella all’interno del bucket in cui desideri inserire i dati. Specifica il nome di una cartella, quindi aggiungi una barra rovesciata dopo il nome per creare la cartella. Ad esempio, folder_name/ |

   {style="table-layout:auto"}

1. Seleziona [!UICONTROL **Salva**].

   Ora puoi importare o esportare dati da o verso l’account e la posizione configurati. Per esportare i dati, utilizza [Feed dati](/help/export/analytics-data-feed/create-feed.md) o [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). Per importare i dati, utilizza [Set di classificazione](/help/components/classifications/sets/overview.md).

   I dati importati non vengono eliminati dalla destinazione cloud dopo l’importazione.

   >[!NOTE]
   >
   >   Se in precedenza è stato utilizzato [FTP per importare le classificazioni](/help/components/classifications/importer/c-uploading-saint-data-files-via-ftp.md) in Adobe Analytics, era necessario caricare un file FIN. Questo file FIN non è necessario per l’importazione da account cloud.


### Google Cloud Platform

Per configurare un percorso di Google Cloud Platform, specifica le seguenti informazioni:

1. [Inizio della creazione o della modifica di un percorso di esportazione cloud](#begin-creating-or-editing-a-cloud-export-location), come descritto in precedenza.

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **Nome del bucket**] | Il bucket all’interno dell’account GCP in cui desideri inviare i dati di Adobe Analytics. Assicurati di aver concesso all’entità fornita da Adobe l’autorizzazione per caricare i file in questo bucket. |
   | [!UICONTROL **Prefisso chiave**] | La cartella all’interno del bucket in cui desideri inserire i dati. Specifica il nome di una cartella, quindi aggiungi una barra rovesciata dopo il nome per creare la cartella. Ad esempio, folder_name/ |

   {style="table-layout:auto"}

1. Seleziona [!UICONTROL **Salva**].

   Ora puoi importare o esportare dati da o verso l’account e la posizione configurati. Per esportare i dati, utilizza [Feed dati](/help/export/analytics-data-feed/create-feed.md) o [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). Per importare i dati, utilizza [Set di classificazione](/help/components/classifications/sets/overview.md).

   I dati importati non vengono eliminati dalla destinazione cloud dopo l’importazione.

   >[!NOTE]
   >
   >   Se in precedenza è stato utilizzato [FTP per importare le classificazioni](/help/components/classifications/importer/c-uploading-saint-data-files-via-ftp.md) in Adobe Analytics, era necessario caricare un file FIN. Questo file FIN non è necessario per l’importazione da account cloud.


### Azure SAS

Per configurare un percorso SAS di Azure, specificare le informazioni seguenti:

1. [Inizio della creazione o della modifica di un percorso di esportazione cloud](#begin-creating-or-editing-a-cloud-export-location), come descritto in precedenza.

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **Nome contenitore**] | Il contenitore all’interno dell’account specificato nel punto in cui desideri inviare i dati di Adobe Analytics. |
   | [!UICONTROL **Prefisso chiave**] | La cartella all’interno del contenitore in cui desideri inserire i dati. Specifica il nome di una cartella, quindi aggiungi una barra rovesciata dopo il nome per creare la cartella. Ad esempio: `folder_name/` |

   {style="table-layout:auto"}

1. Seleziona [!UICONTROL **Salva**].

   Ora puoi importare o esportare dati da o verso l’account e la posizione configurati. Per esportare i dati, utilizza [Feed dati](/help/export/analytics-data-feed/create-feed.md) o [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). Per importare i dati, utilizza [Set di classificazione](/help/components/classifications/sets/overview.md).

   I dati importati non vengono eliminati dalla destinazione cloud dopo l’importazione.

   >[!NOTE]
   >
   >   Se in precedenza è stato utilizzato [FTP per importare le classificazioni](/help/components/classifications/importer/c-uploading-saint-data-files-via-ftp.md) in Adobe Analytics, era necessario caricare un file FIN. Questo file FIN non è necessario per l’importazione da account cloud.


### Azure RBAC

Per configurare un percorso RBAC di Azure, specificare le informazioni seguenti:

1. [Inizio della creazione o della modifica di un percorso di esportazione cloud](#begin-creating-or-editing-a-cloud-export-location), come descritto in precedenza.

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **Nome contenitore**] | Il contenitore all’interno dell’account specificato nel punto in cui desideri inviare i dati di Adobe Analytics. Assicurati di concedere le autorizzazioni per caricare i file nell’applicazione Azure creata in precedenza. |
   | [!UICONTROL **Prefisso chiave**] | La cartella all’interno del contenitore in cui desideri inserire i dati. Specifica il nome di una cartella, quindi aggiungi una barra rovesciata dopo il nome per creare la cartella. Ad esempio: `folder_name/` |
   | [!UICONTROL **Nome account**] | Account di archiviazione Azure. |

   {style="table-layout:auto"}

1. Seleziona [!UICONTROL **Salva**].

   Ora puoi importare o esportare dati da o verso l’account e la posizione configurati. Per esportare i dati, utilizza [Feed dati](/help/export/analytics-data-feed/create-feed.md) o [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). Per importare i dati, utilizza [Set di classificazione](/help/components/classifications/sets/overview.md).

   I dati importati non vengono eliminati dalla destinazione cloud dopo l’importazione.

   >[!NOTE]
   >
   >   Se in precedenza è stato utilizzato [FTP per importare le classificazioni](/help/components/classifications/importer/c-uploading-saint-data-files-via-ftp.md) in Adobe Analytics, era necessario caricare un file FIN. Questo file FIN non è necessario per l’importazione da account cloud.

### Tipi di account legacy

Questi tipi di account legacy sono disponibili solo quando si esportano dati con [Feed dati](/help/export/analytics-data-feed/create-feed.md) e [Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md). Queste opzioni non sono disponibili quando si importano dati con [Set di classificazione](/help/components/classifications/sets/manage/schema.md).

+++FTP

I dati del feed dati possono essere inviati a un Adobe o a una posizione FTP ospitata dal cliente. Specificare la directory Utilizzare il campo percorso per inserire i file di feed in una cartella.

| Campo | Funzione |
|---------|----------|
| [!UICONTROL **Percorso directory**] | Immettere il percorso della directory sul server FTP. Le cartelle devono già esistere. I feed generano un errore se il percorso specificato non esiste. </br>Ad esempio: `/folder_name/folder_name`. |

{style="table-layout:auto"}

+++

+++SFTP

I dati del feed dati possono essere consegnati a una posizione SFTP Adobe o ospitata dal cliente. Il sito di destinazione deve contenere una chiave pubblica RSA o DSA valida. Puoi scaricare la chiave pubblica adatta al momento della creazione del feed.

| Campo | Funzione |
|---------|----------|
| [!UICONTROL **Percorso directory**] | Immettere il percorso della directory sul server FTP. Le cartelle devono già esistere. I feed generano un errore se il percorso specificato non esiste. </br>Ad esempio: `/folder_name/folder_name`. |

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


