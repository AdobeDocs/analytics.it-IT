---
description: Configura l’account di importazione cloud e il percorso in cui è possibile caricare i dati di classificazione
keywords: Analysis Workspace
title: Configurare account di importazione ed esportazione cloud
feature: Classifications
exl-id: 40d3d3f1-1047-4c37-8caf-6b0aabaa590a
source-git-commit: 888f7bef389f113538f0e62ab0098d9e809a905e
workflow-type: tm+mt
source-wordcount: '1223'
ht-degree: 56%

---

# Configurare account di importazione ed esportazione cloud

<!-- This page is almost duplicated with the "Configure cloud export locations" article in CJA. Differences are that Snowflake isn't supported here and there is a Suffix field for each account type. -->

Puoi configurare un account cloud utilizzato per uno o tutti i seguenti scopi:

* Esportazione di file tramite [Feed dati](/help/export/analytics-data-feed/create-feed.md)
* Esportazione di rapporti tramite [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)
* Importazione degli schemi tramite [Set di classificazione](/help/components/classifications/sets/overview.md)

Devi configurare Adobe Analytics con le informazioni necessarie per accedere al tuo account cloud. Questo processo consiste nell’aggiungere e configurare l’account (ad esempio ARN per il ruolo di Amazon S3, Google Cloud Platform e così via) come descritto in questo articolo, quindi aggiungere e configurare la posizione all’interno dell’account (ad esempio una cartella all’interno dell’account) come descritto in [Configurare i percorsi di importazione ed esportazione cloud](/help/components/locations/configure-import-locations.md).

Per configurare un account di importazione o esportazione cloud:

1. In Adobe Analytics, seleziona [!UICONTROL **Componenti**] > [!UICONTROL **Posizioni**].
1. Il giorno [!UICONTROL Locations] , seleziona la [!UICONTROL **Account ubicazione**] scheda.
1. Per creare un nuovo account, seleziona [!UICONTROL **Aggiungi account**].

   Viene visualizzata la finestra di dialogo Aggiungi account.

   Oppure

   Per modificare un account esistente, seleziona [!UICONTROL **Visualizza dettagli**] nella sezione in cui è elencato l’account che desideri modificare.
Viene visualizzata la finestra di dialogo Posizione.

   Viene visualizzata la finestra di dialogo Dettagli account località


1. Specifica le seguenti informazioni: |Campo | Funzione | ---------- --------- | [!UICONTROL **Nome account località**] | Nome dell&#39;account di posizione. Questo nome viene visualizzato durante la creazione di una posizione | | [!UICONTROL **Descrizione del conto di ubicazione**] | Fornisci una breve descrizione dell’account per distinguerlo da altri account dello stesso tipo. | | [!UICONTROL **Tipo di account**] | Seleziona il tipo di account cloud. È consigliabile disporre di un singolo account per ogni tipo di account, con più posizioni in base alle esigenze all’interno dell’account. |
1. In [!UICONTROL **Proprietà account**] , specificare informazioni specifiche per il tipo di account selezionato.

   Per le istruzioni di configurazione, espandi la sezione seguente che corrisponde a [!UICONTROL **Tipo di account**] che hai selezionato. Sono disponibili anche altri tipi di account legacy, ma non sono consigliati.

   **Tipi di account**

   +++ARN per ruolo Amazon S3

   Per configurare un account Amazon S3 Role ARN, specifica le seguenti informazioni:

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **Ruolo ARN**] | È necessario fornire un ruolo ARN (nome risorsa Amazon - Amazon Resource Name) che Adobe può utilizzare per accedere all’account Amazon S3. A tale scopo, crea un criterio di autorizzazione IAM per l’account di origine, associa il criterio a un utente e quindi crea un ruolo per l’account di destinazione. Per informazioni specifiche, consulta [questa documentazione di AWS](https://repost.aws/it/knowledge-center/cross-account-access-iam). |

   {style="table-layout:auto"}

+++

   +++Google Cloud Platform

   Per configurare un account di Google Cloud Platform, specifica le seguenti informazioni:

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **ID Progetto**] | ID personale progetto Google Cloud. Consulta la [Documentazione di Google Cloud su come ottenere un ID progetto](https://cloud.google.com/resource-manager/docs/creating-managing-projects?hl=it#identifying_projects). |

   {style="table-layout:auto"}

+++

   +++Azure SAS

   Per configurare un account SAS di Azure, specificare le informazioni seguenti:

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **ID applicazione**] | Copia questo ID dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nella scheda **Panoramica** all’interno dell’applicazione. Per ulteriori informazioni, consulta la [Documentazione di Microsoft Azure su come registrare un’applicazione con Microsoft Identity Platform](https://learn.microsoft.com/it-it/entra/identity-platform/quickstart-register-app). |
   | [!UICONTROL **ID tenant**] | Copia questo ID dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nella scheda **Panoramica** all’interno dell’applicazione. Per ulteriori informazioni, consulta [Documentazione di Microsoft Azure su come registrare un’applicazione con Microsoft Identity Platform](https://learn.microsoft.com/it-it/entra/identity-platform/quickstart-register-app). |
   | [!UICONTROL **URI di Key Vault**] | <p>Percorso per il token SAS in Azure Key Vault.  Per configurare Azure SAS, è necessario memorizzare un token SAS come segreto utilizzando Azure Key Vault. Per informazioni, consulta [Documentazione di Microsoft Azure su come impostare e recuperare un segreto da Azure Key Vault](https://learn.microsoft.com/it-it/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>Dopo la creazione dell’URI dell’insieme di credenziali delle chiavi, aggiungi un criterio di accesso nell’insieme di credenziali delle chiavi per concedere l’autorizzazione all’applicazione Azure creata. Per informazioni, consulta [Documentazione di Microsoft Azure su come assegnare un criterio di accesso a Key Vault](https://learn.microsoft.com/it-it/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
   | [!UICONTROL **Nome segreto di Key Vault**] | Nome segreto creato quando si aggiunge il segreto all&#39;insieme di credenziali delle chiavi di Azure. In Microsoft Azure, queste informazioni si trovano nell&#39;insieme di credenziali delle chiavi creato, nel **Key Vault** impostazioni. Per informazioni, consulta [Documentazione di Microsoft Azure su come impostare e recuperare un segreto da Azure Key Vault](https://learn.microsoft.com/it-it/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
   | [!UICONTROL **Segreto account località**] | Copia il segreto dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nella scheda **Certificati e segreti** all’interno dell’applicazione. Per ulteriori informazioni, consulta la [Documentazione di Microsoft Azure su come registrare un’applicazione con Microsoft Identity Platform](https://learn.microsoft.com/it-it/entra/identity-platform/quickstart-register-app). |

   {style="table-layout:auto"}

+++

   +++Azure RBAC

   Per configurare un account RBAC di Azure, specificare le informazioni seguenti:

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **ID applicazione**] | Copia questo ID dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nella scheda **Panoramica** all’interno dell’applicazione. Per ulteriori informazioni, consulta la [Documentazione di Microsoft Azure su come registrare un’applicazione con Microsoft Identity Platform](https://learn.microsoft.com/it-it/entra/identity-platform/quickstart-register-app). |
   | [!UICONTROL **ID tenant**] | Copia questo ID dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nella scheda **Panoramica** all’interno dell’applicazione. Per ulteriori informazioni, consulta la [Documentazione di Microsoft Azure su come registrare un’applicazione con Microsoft Identity Platform](https://learn.microsoft.com/it-it/entra/identity-platform/quickstart-register-app). |
   | [!UICONTROL **Segreto account località**] | Copia il segreto dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nella scheda **Certificati e segreti** all’interno dell’applicazione. Per ulteriori informazioni, consulta la [Documentazione di Microsoft Azure su come registrare un’applicazione con Microsoft Identity Platform](https://learn.microsoft.com/it-it/entra/identity-platform/quickstart-register-app). |

   {style="table-layout:auto"}

+++

   **Tipi di account legacy**

   Questi tipi di account legacy sono disponibili solo quando si esportano dati con [Feed dati](/help/export/analytics-data-feed/create-feed.md) e [Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md). Queste opzioni non sono disponibili quando si importano dati con [Set di classificazione](/help/components/classifications/sets/manage/schema.md).

   +++FTP

   I dati del feed dati possono essere inviati a un Adobe o a una posizione FTP ospitata dal cliente. Richiede un host FTP, un nome utente e una password. Utilizza il campo del percorso per inserire i file di feed in una cartella. Le cartelle devono già esistere. I feed generano un errore se il percorso specificato non esiste.

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **Host**] | Immetti l&#39;URL di destinazione FTP desiderato. Esempio: `ftp://ftp.omniture.com`. |
   | [!UICONTROL **Percorso**] | Può essere lasciato vuoto. |
   | [!UICONTROL **Nome utente**] | Immetti il nome utente per accedere al sito FTP. |
   | [!UICONTROL **Password e conferma password**] | Immettere la password per accedere al sito FTP. |

   {style="table-layout:auto"}

+++

   +++SFTP

   È disponibile il supporto SFTP per i feed di dati. Richiede un host SFTP, un nome utente e il sito di destinazione per contenere una chiave pubblica RSA o DSA valida. Puoi scaricare la chiave pubblica adatta al momento della creazione del feed.

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

1. Seleziona [!UICONTROL **Salva**].

1. Continua con [Configurare i percorsi di importazione ed esportazione cloud](/help/components/locations/configure-import-locations.md).
