---
description: Configura l’account di importazione cloud e il percorso in cui è possibile caricare i dati di classificazione
keywords: Analysis Workspace
title: Configurare account di importazione ed esportazione cloud
feature: Classifications
exl-id: 40d3d3f1-1047-4c37-8caf-6b0aabaa590a
source-git-commit: f0a5f72667fd6fc7847ede82d5196d9159fc558c
workflow-type: tm+mt
source-wordcount: '1488'
ht-degree: 54%

---

# Configurare account di importazione ed esportazione cloud

<!-- This page is almost duplicated with the "Configure cloud export locations" article in CJA. Differences are that Snowflake isn't supported here and there is a Suffix field for each account type. -->

>[!NOTE]
>
>Quando crei e modifichi account, tieni presente quanto segue: <ul><li>Gli amministratori di sistema possono impedire agli utenti di creare account, come descritto in [Specificare se gli utenti possono creare account](/help/components/locations/locations-manager.md#configure-whether-users-can-create-accounts). Se non è possibile creare gli account come descritto in questa sezione, contattare l&#39;amministratore di sistema.</li><li>Un account può essere modificato solo dall’utente che lo ha creato o da un amministratore di sistema.</li></ul>

Puoi configurare un account cloud utilizzato per uno o tutti i seguenti scopi:

* Esportazione di file tramite [feed dati](/help/export/analytics-data-feed/create-feed.md)
* Esportazione di report tramite [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)
* Esportazione di file con [Report Builder](/help/analyze/report-builder/report-builder-export.md)
* Importazione di schemi tramite [Set di classificazione](/help/components/classifications/sets/overview.md)

Devi configurare Adobe Analytics con le informazioni necessarie per accedere al tuo account cloud. Questo processo consiste nell&#39;aggiungere e configurare l&#39;account (ad esempio ARN per il ruolo di Amazon S3, Google Cloud Platform e così via) come descritto in questo articolo, quindi aggiungere e configurare il percorso all&#39;interno dell&#39;account (ad esempio una cartella all&#39;interno dell&#39;account) come descritto in [Configurare i percorsi di importazione ed esportazione cloud](/help/components/locations/configure-import-locations.md).

Per informazioni su come visualizzare ed eliminare gli account esistenti, vedere [Gestione posizioni](/help/components/locations/locations-manager.md).

Per configurare un account di importazione o esportazione cloud:

1. In Adobe Analytics, seleziona [!UICONTROL **Componenti**] > [!UICONTROL **Percorsi**].
1. Nella pagina [!UICONTROL Locations], selezionare la scheda [!UICONTROL **Account località**].
1. (Condizionale) Se sei un amministratore di sistema, puoi abilitare l&#39;opzione [!UICONTROL **Visualizza account per tutti gli utenti**] per visualizzare gli account creati da tutti gli utenti dell&#39;organizzazione.
   ![visualizza account per tutti gli utenti](assets/accounts-all-users.png)
1. Per creare un nuovo account, selezionare [!UICONTROL **Aggiungi account**].

   Viene visualizzata la finestra di dialogo [!UICONTROL **Dettagli account località**].

   Oppure

   Per modificare un account esistente, individuare l&#39;account che si desidera modificare, quindi selezionare il pulsante [!UICONTROL **Modifica dettagli**].

   Viene visualizzata la finestra di dialogo [!UICONTROL **Aggiungi account**].

1. Specifica le seguenti informazioni:

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **Nome account località**] | Nome dell&#39;account di posizione. Questo nome viene visualizzato durante la creazione di una posizione |
   | [!UICONTROL **Descrizione account località**] | Fornisci una breve descrizione dell’account per distinguerlo da altri account dello stesso tipo. |
   | [!UICONTROL **Rendi l&#39;account disponibile a tutti gli utenti dell&#39;organizzazione**] | Abilita questa opzione per consentire ad altri utenti dell’organizzazione di utilizzare l’account.<p>Quando condividi gli account, tieni presente quanto segue:</p><ul><li>Gli account condivisi non possono essere non condivisi.</li><li>Gli account condivisi possono essere modificati solo dal proprietario dell&#39;account.</li><li>Chiunque può creare una posizione per l&#39;account condiviso.</li></ul> |
   | [!UICONTROL **Tipo di account**] | Seleziona il tuo tipo di account cloud. È consigliabile disporre di un singolo account per ogni tipo, con più posizioni secondo necessità all’interno di tale account.<p>Gli amministratori di sistema possono limitare i tipi di account che possono essere creati dagli utenti, come descritto in [Specificare se gli utenti possono creare account](/help/components/locations/locations-manager.md#configure-whether-users-can-create-accounts). Se non è possibile creare gli account come descritto in questa sezione, contattare l&#39;amministratore di sistema.</p> |

1. Nella sezione [!UICONTROL **Proprietà account**], specifica informazioni specifiche sul tipo di account selezionato.

   Per istruzioni di configurazione, espandere la sezione seguente che corrisponde al tipo di account [!UICONTROL **selezionato**]. Sono disponibili anche altri tipi di account legacy, ma non sono consigliati.

   **Tipi di account**

   +++Amazon S3 con ruolo ARN

   **NOTA:** quando si utilizza Amazon S3 con feed di dati e Data Warehouse, è supportata solo la crittografia SSE-S3.

   Per configurare un account Amazon S3 con ruolo ARN, specifica le seguenti informazioni:

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

   Per configurare un account SAS di Azure, specifica le informazioni seguenti:

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **ID applicazione**] | Copia questo ID dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nella scheda **Panoramica** all’interno dell’applicazione. Per ulteriori informazioni, consulta la [Documentazione di Microsoft Azure su come registrare un’applicazione con Microsoft Identity Platform](https://learn.microsoft.com/it-it/entra/identity-platform/quickstart-register-app). |
   | [!UICONTROL **ID tenant**] | Copia questo ID dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nella scheda **Panoramica** all’interno dell’applicazione. Per ulteriori informazioni, consulta [Documentazione di Microsoft Azure su come registrare un’applicazione con Microsoft Identity Platform](https://learn.microsoft.com/it-it/entra/identity-platform/quickstart-register-app). |
   | [!UICONTROL **URI di Key Vault**] | <p>Percorso per il token SAS in Azure Key Vault.  Per configurare Azure SAS, è necessario memorizzare un token SAS come segreto utilizzando Azure Key Vault. Per informazioni, consulta [Documentazione di Microsoft Azure su come impostare e recuperare un segreto da Azure Key Vault](https://learn.microsoft.com/it-it/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>Dopo la creazione dell’URI dell’insieme di credenziali delle chiavi, aggiungi un criterio di accesso nell’insieme di credenziali delle chiavi per concedere l’autorizzazione all’applicazione Azure creata. Per informazioni, consulta [Documentazione di Microsoft Azure su come assegnare un criterio di accesso a Key Vault](https://learn.microsoft.com/it-it/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
   | [!UICONTROL **Nome segreto di Key Vault**] | Nome segreto creato quando si aggiunge il segreto all&#39;insieme di credenziali delle chiavi di Azure. In Microsoft Azure, queste informazioni si trovano nell&#39;insieme di credenziali delle chiavi creato, nella pagina delle impostazioni di **Insieme di credenziali delle chiavi**. Per informazioni, consulta [Documentazione di Microsoft Azure su come impostare e recuperare un segreto da Azure Key Vault](https://learn.microsoft.com/it-it/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
   | [!UICONTROL **Segreto account località**] | Copia il segreto dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nella scheda **Certificati e segreti** all’interno dell’applicazione. Per ulteriori informazioni, consulta la [Documentazione di Microsoft Azure su come registrare un’applicazione con Microsoft Identity Platform](https://learn.microsoft.com/it-it/entra/identity-platform/quickstart-register-app). |

   {style="table-layout:auto"}

   +++   

   +++Azure RBAC

   Per configurare un account RBAC di Azure, specifica le informazioni seguenti:

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **ID applicazione**] | Copia questo ID dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nella scheda **Panoramica** all’interno dell’applicazione. Per ulteriori informazioni, consulta la [Documentazione di Microsoft Azure su come registrare un’applicazione con Microsoft Identity Platform](https://learn.microsoft.com/it-it/entra/identity-platform/quickstart-register-app). |
   | [!UICONTROL **ID tenant**] | Copia questo ID dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nella scheda **Panoramica** all’interno dell’applicazione. Per ulteriori informazioni, consulta la [Documentazione di Microsoft Azure su come registrare un’applicazione con Microsoft Identity Platform](https://learn.microsoft.com/it-it/entra/identity-platform/quickstart-register-app). |
   | [!UICONTROL **Segreto account località**] | Copia il segreto dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nella scheda **Certificati e segreti** all’interno dell’applicazione. Per ulteriori informazioni, consulta la [Documentazione di Microsoft Azure su come registrare un’applicazione con Microsoft Identity Platform](https://learn.microsoft.com/it-it/entra/identity-platform/quickstart-register-app). |

   {style="table-layout:auto"}

   +++

   +++E-mail

   >[!NOTE]
   >
   >Gli account di posta elettronica possono essere utilizzati solo con [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). (Gli account di posta elettronica non sono supportati con [Feed dati](/help/export/analytics-data-feed/create-feed.md) o [Set di classificazione](/help/components/classifications/sets/overview.md)).

   Per configurare un account RBAC di Azure, specifica le informazioni seguenti:

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **Recipients (Destinatari)**] | Le notifiche e-mail possono essere inviate a utenti specifici una volta inviato il rapporto. Specifica un singolo indirizzo e-mail o un elenco di indirizzi e-mail separati da virgole. |

   {style="table-layout:auto"}

   +++

   **Tipi di account legacy**

   Questi tipi di account legacy sono disponibili solo quando si esportano dati con [Feed dati](/help/export/analytics-data-feed/create-feed.md) e [Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md). Queste opzioni non sono disponibili durante l&#39;importazione di dati con [Set di classificazione](/help/components/classifications/sets/manage/schema.md).

   +++FTP

   I dati del feed dati possono essere inviati a una posizione FTP di Adobe o ospitata dal cliente. Richiede un host FTP, un nome utente e una password. Utilizza il campo del percorso per inserire i file di feed in una cartella. Le cartelle devono già esistere. I feed generano un errore se il percorso specificato non esiste.

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **Host**] | Immetti l&#39;URL di destinazione FTP desiderato. Ad esempio: `ftp.adobe.com`. |
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

1. Continua con [Configurare i percorsi di importazione ed esportazione del cloud](/help/components/locations/configure-import-locations.md).
