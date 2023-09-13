---
description: Passaggi che descrivono come creare una richiesta Data Warehouse.
title: Configurare una destinazione di rapporto per una richiesta Data Warehouse
feature: Data Warehouse
source-git-commit: 3af2cca02675e424b3f704a95d46de92886a88d8
workflow-type: tm+mt
source-wordcount: '1623'
ht-degree: 3%

---

# Configurare una destinazione di rapporto per una richiesta Data Warehouse

{{release-limited-testing}}

Durante la creazione di una richiesta Data Warehouse sono disponibili varie opzioni di configurazione. Le informazioni seguenti descrivono come configurare una destinazione di rapporto per la richiesta.

Per informazioni su come iniziare a creare una richiesta, nonché collegamenti ad altre importanti opzioni di configurazione, vedi [Creare una richiesta Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

>[!NOTE]
>
>Quando configuri una destinazione di rapporto, tieni presente quanto segue:
>
>* È consigliabile utilizzare un account cloud o un messaggio e-mail per la destinazione del rapporto. Gli account FTP e SFTP legacy sono disponibili ma non sono consigliati.
>
>* Gli account cloud sono associati al tuo account utente di Adobe Analytics. Gli altri utenti non possono utilizzare o visualizzare gli account cloud configurati dall’utente.
>
>* Tutti gli account cloud che hai precedentemente [configurato per feed dati](/help/export/analytics-data-feed/create-feed.md) sono disponibili per l’utilizzo in Data Warehouse.
>
>* Account cloud configurati per [importazione dei dati di classificazione di Adobe Analytics](/help/components/locations/locations-manager.md) da una destinazione cloud può essere utilizzato durante la configurazione di una destinazione di rapporto. Tuttavia, non è possibile utilizzare le posizioni configurate per l’importazione dei dati di classificazione.

Per configurare la destinazione in cui vengono inviati i rapporti Data Warehouse:

1. Inizia a creare una richiesta in Adobe Analytics selezionando **[!UICONTROL Tools]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Aggiungi**].

   Per ulteriori dettagli, vedi [Creare una richiesta Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Nella pagina Nuova richiesta Data Warehouse, seleziona la [!UICONTROL **Destinazione del rapporto**] scheda.

   ![Scheda Destinazione rapporto](assets/dw-report-destination.png)

1. (Condizionale) Se in precedenza hai configurato un account (e una destinazione su tale account) che desideri utilizzare come destinazione del rapporto:

   1. Seleziona l’account da [!UICONTROL **Seleziona account**] menu a discesa.

      Qualsiasi account cloud configurato per [importazione dei dati di classificazione di Adobe Analytics](/help/components/locations/locations-manager.md) da una destinazione cloud sono mostrati qui e possono essere utilizzati. Tuttavia, non è possibile utilizzare le posizioni configurate per l’importazione dei dati di classificazione. Aggiungi invece una nuova destinazione come descritto di seguito.

   1. Seleziona la destinazione associata all’account da [!UICONTROL **Seleziona destinazione**] menu a discesa. <!-- Is this correct? -->

1. (Condizionale) Se non hai configurato in precedenza un account:

   1. Seleziona [!UICONTROL **Aggiungi account**], quindi specifica le seguenti informazioni:

      | Campo | Funzione |
      |---------|----------|
      | [!UICONTROL **Tipo di account**] | Seleziona il tipo di account cloud. È consigliabile disporre di un singolo account per ogni tipo di account, con più posizioni in base alle esigenze all’interno dell’account. <p>Dopo aver scelto un tipo di conto, vengono visualizzati i campi specifici per tale tipo di conto. Per istruzioni di configurazione per ogni tipo di account, espandi la sezione seguente che corrisponde al selezionato. </p> |
      | [!UICONTROL **Nome account**] | Specifica un nome per l’account. Questo nome viene visualizzato durante la creazione di una posizione. <!-- true? --> |
      | [!UICONTROL **Descrizione account**] | Fornisci una breve descrizione dell’account per distinguerlo da altri account dello stesso tipo. |

      Per le istruzioni di configurazione, espandi la sezione seguente che corrisponde a [!UICONTROL **Tipo di account**] che hai selezionato.

      Utilizza uno dei seguenti tipi di account durante la configurazione di una destinazione di rapporto. Per istruzioni di configurazione, espandi il tipo di account. (Destinazioni legacy aggiuntive <!-- add link --> sono disponibili, ma non sono consigliati.)

      +++Amazon S3

      Specifica le seguenti informazioni per configurare un account ARN per il ruolo Amazon S3:

      | Campo | Funzione |
      |---------|----------|
      | [!UICONTROL **ARN per ruolo**] | È necessario fornire un ARN per il ruolo (Amazon Resource Name) che l’Adobe può utilizzare per accedere all’account Amazon S3. A tale scopo, creare un criterio di autorizzazione IAM per l&#39;account di origine, associare il criterio a un utente e quindi creare un ruolo per l&#39;account di destinazione. Per informazioni specifiche, consulta [questa documentazione di AWS](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). |
      | [!UICONTROL **ARN utente**] | L’ARN utente (Amazon Resource Name) è fornito da Adobe. È necessario collegare questo utente al criterio creato. |

      {style="table-layout:auto"}

+++

      +++Piattaforma Google Cloud

      Specifica le seguenti informazioni per configurare un account di Google Cloud Platform:

      | Campo | Funzione |
      |---------|----------|
      | [!UICONTROL **ID Progetto**] | ID progetto Google Cloud. Consulta la [Documentazione di Google Cloud sull’ottenimento di un ID progetto](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |

      {style="table-layout:auto"}

+++

      +++SAS di Azure

      Specificare le informazioni seguenti per configurare un account SAS di Azure:

      | Campo | Funzione |
      |---------|----------|
      | [!UICONTROL **ID applicazione**] | Copia questo ID dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nel **Panoramica** nell&#39;applicazione. Per ulteriori informazioni, vedere [Documentazione di Microsoft Azure su come registrare un’applicazione con la piattaforma Microsoft Identity](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **ID tenant**] | Copia questo ID dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nel **Panoramica** nell&#39;applicazione. Per ulteriori informazioni, vedere [Documentazione di Microsoft Azure su come registrare un’applicazione con la piattaforma Microsoft Identity](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **URI insieme di credenziali delle chiavi**] | <p>Percorso del token SAS nell&#39;insieme di credenziali delle chiavi di Azure.  Per configurare Azure SAS, è necessario memorizzare un token SAS come segreto utilizzando Azure Key Vault. Per informazioni, vedere [Documentazione di Microsoft Azure su come impostare e recuperare un segreto dall&#39;insieme di credenziali delle chiavi di Azure](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>Dopo la creazione dell’URI dell’insieme di credenziali delle chiavi, aggiungi un criterio di accesso nell’insieme di credenziali delle chiavi per concedere l’autorizzazione all’applicazione Azure creata. Per informazioni, vedere [Documentazione di Microsoft Azure su come assegnare un criterio di accesso all’insieme di credenziali delle chiavi](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
      | [!UICONTROL **Nome segreto archivio chiavi**] | Nome segreto creato quando si aggiunge il segreto all&#39;insieme di credenziali delle chiavi di Azure. In Microsoft Azure, queste informazioni si trovano nell&#39;insieme di credenziali delle chiavi creato, nel **Key Vault** pagine delle impostazioni. Per informazioni, vedere [Documentazione di Microsoft Azure su come impostare e recuperare un segreto dall&#39;insieme di credenziali delle chiavi di Azure](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
      | [!UICONTROL **Segreto**] | Copia il segreto dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nel **Certificati e segreti** nell&#39;applicazione. Per ulteriori informazioni, vedere [Documentazione di Microsoft Azure su come registrare un’applicazione con la piattaforma Microsoft Identity](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

      {style="table-layout:auto"}

+++

      +++RBAC di Azure

      Specificare le informazioni seguenti per configurare un account RBAC di Azure:

      | Campo | Funzione |
      |---------|----------|
      | [!UICONTROL **ID applicazione**] | Copia questo ID dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nel **Panoramica** nell&#39;applicazione. Per ulteriori informazioni, vedere [Documentazione di Microsoft Azure su come registrare un’applicazione con la piattaforma Microsoft Identity](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **ID tenant**] | Copia questo ID dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nel **Panoramica** nell&#39;applicazione. Per ulteriori informazioni, vedere [Documentazione di Microsoft Azure su come registrare un’applicazione con la piattaforma Microsoft Identity](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **Segreto**] | Copia il segreto dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nel **Certificati e segreti** nell&#39;applicazione. Per ulteriori informazioni, vedere [Documentazione di Microsoft Azure su come registrare un’applicazione con la piattaforma Microsoft Identity](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

      {style="table-layout:auto"}

+++

      +++E-mail

      Specifica le seguenti informazioni per configurare un account e-mail:

      | Campo | Funzione |
      |---------|----------|
      | [!UICONTROL **Recipients (Destinatari)**] | Le notifiche e-mail possono essere inviate a utenti specifici quando il rapporto viene inviato. Specifica un singolo indirizzo e-mail o un elenco di indirizzi e-mail separati da virgole. <!-- How does this differ from the Notification email tab? --> |

   1. Seleziona [!UICONTROL **Aggiungi posizione**], quindi specifica le seguenti informazioni: |Campo | Funzione | ---------- --------- | [!UICONTROL **Nome**] | Nome della posizione.  | | [!UICONTROL **Descrizione**] | Fornisci una breve descrizione del conto per distinguerlo da altri conti dello stesso tipo. | | [!UICONTROL **Account località**] | Seleziona l&#39;account località creato in [Aggiungi un account](#add-an-account). |

   1. In [!UICONTROL **Proprietà posizione**] , specificare informazioni specifiche sul tipo di account dell&#39;account di posizione.

      Per le istruzioni di configurazione, espandi la sezione seguente che corrisponde al tipo di account selezionato in precedenza.

      +++Amazon S3

      Per configurare un percorso Amazon S3, specifica le seguenti informazioni:

      | Campo | Funzione |
      |---------|----------|
      | [!UICONTROL **Nome del bucket**] | Il bucket all’interno dell’account Amazon S3 in cui desideri inviare i dati di Adobe Analytics. Assicurati che l’ARN utente fornito da Adobe abbia accesso al caricamento di file in questo bucket. |
      | [!UICONTROL **Prefisso chiave**] | La cartella all’interno del bucket in cui desideri inserire i dati. Specifica il nome di una cartella, quindi aggiungi una barra rovesciata dopo il nome per creare la cartella. Ad esempio, nome_cartella/ |

      {style="table-layout:auto"}

+++

      +++Piattaforma Google Cloud

      Per configurare il percorso di una piattaforma Google Cloud, specifica le seguenti informazioni:

      | Campo | Funzione |
      |---------|----------|
      | [!UICONTROL **Nome del bucket**] | Il bucket all’interno dell’account GCP in cui desideri inviare i dati di Adobe Analytics. Assicurati di aver concesso all’entità fornita da Adobe l’autorizzazione per caricare i file in questo bucket. Per informazioni sulla concessione delle autorizzazioni, consulta [Aggiungere un’entità a un criterio a livello di bucket](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-add) nella documentazione di Google Cloud. |
      | [!UICONTROL **Prefisso chiave**] | La cartella all’interno del bucket in cui desideri inserire i dati. Specifica il nome di una cartella, quindi aggiungi una barra rovesciata dopo il nome per creare la cartella. Ad esempio, nome_cartella/ |

      {style="table-layout:auto"}

+++

      +++SAS di Azure

      Specificare le informazioni seguenti per configurare un percorso SAS di Azure:

      | Campo | Funzione |
      |---------|----------|
      | [!UICONTROL **Nome contenitore**] | Il contenitore all’interno dell’account specificato nel punto in cui desideri inviare i dati di Adobe Analytics. |
      | [!UICONTROL **Prefisso chiave**] | La cartella all’interno del contenitore in cui desideri inserire i dati. Specifica il nome di una cartella, quindi aggiungi una barra rovesciata dopo il nome per creare la cartella. Ad esempio, `folder_name/` |

      {style="table-layout:auto"}

+++

      +++RBAC di Azure

      Specificare le informazioni seguenti per configurare un percorso RBAC di Azure:

      | Campo | Funzione |
      |---------|----------|
      | [!UICONTROL **Nome contenitore**] | Il contenitore all’interno dell’account specificato nel punto in cui desideri inviare i dati di Adobe Analytics. Accertati di concedere le autorizzazioni per caricare i file nell’applicazione Azure creata in precedenza. |
      | [!UICONTROL **Prefisso chiave**] | La cartella all’interno del contenitore in cui desideri inserire i dati. Specifica il nome di una cartella, quindi aggiungi una barra rovesciata dopo il nome per creare la cartella. Ad esempio, `folder_name/` |
      | [!UICONTROL **Nome account**] | Account di archiviazione Azure. |

      {style="table-layout:auto"}

+++

   1. Seleziona [!UICONTROL **Salva**].

      Ora puoi importare i dati nell’account e nella posizione configurati.

1. Continua a configurare la richiesta Data Warehouse in [!UICONTROL **Opzioni di report**] scheda. Per ulteriori informazioni, consulta [Configurare le opzioni di rapporto per una richiesta Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-options.md).