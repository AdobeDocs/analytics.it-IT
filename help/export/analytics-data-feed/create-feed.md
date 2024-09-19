---
title: Creare un feed di dati
description: Scopri come creare un feed di dati.
feature: Data Feeds
exl-id: 36c8a40e-6137-4836-9d4b-bebf17b932bc
source-git-commit: 8e8f59f747ddacc5462cbc177d199a5e0e91908a
workflow-type: tm+mt
source-wordcount: '4115'
ht-degree: 46%

---

# Creare un feed di dati

Durante la creazione di un feed di dati, fornisci ad Adobe:

* Informazioni sulla destinazione in cui si desidera inviare i file di dati non elaborati

* Dati da includere in ciascun file

>[!NOTE]
>
>Prima di creare un feed di dati, è importante avere una conoscenza di base dei feed di dati e assicurarsi di soddisfare tutti i prerequisiti. Per ulteriori informazioni, consulta [Panoramica sui feed di dati](data-feed-overview.md).

## Creare e configurare un feed dati

1. Accedi a [experiencecloud.adobe.com](https://experiencecloud.adobe.com) utilizzando le credenziali Adobe ID.
1. Seleziona l&#39;icona a 9 quadrati in alto a destra, quindi seleziona [!UICONTROL **Analytics**].
1. Nella barra di navigazione superiore, passa a [!UICONTROL **Amministratore**] > [!UICONTROL **Feed dati**].
1. Seleziona [!UICONTROL **Aggiungi**].

   ![Aggiungi feed dati](assets/datafeed-add.png)

   Viene visualizzata una pagina con tre categorie principali: [!UICONTROL **Informazioni feed**], [!UICONTROL **Destinazione**] e [!UICONTROL **Definizioni colonne dati**].
1. Nella sezione [!UICONTROL **Informazioni feed**], completa i campi seguenti:

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **Nome**] | Nome del feed dati. Deve essere univoco all’interno della suite di rapporti selezionata e può contenere fino a 255 caratteri. |
   | [!UICONTROL **Suite di rapporti**] | La suite di rapporti su cui si basa il feed di dati. Se vengono creati più feed di dati per la stessa suite di rapporti, devono avere definizioni di colonne diverse. Solo le suite di rapporti di origine supportano i feed di dati; le suite di rapporti virtuali non sono supportate. |
   | [!UICONTROL **Invia e-mail al termine**] | L’indirizzo e-mail da notificare al termine dell’elaborazione di un feed. L’indirizzo e-mail deve essere formattato correttamente. |
   | [!UICONTROL **Intervallo feed**] | Seleziona **Giornaliero** per la retrocompilazione o i dati cronologici. I feed giornalieri contengono dati relativi a un’intera giornata, dalla mezzanotte alla mezzanotte nel fuso orario della suite di rapporti. Seleziona **Oraria** per continuare i dati (se preferisci, è disponibile anche la funzione Giornaliera per continuare i feed). I feed orari contengono dati relativi a una sola ora. |
   | [!UICONTROL **Ritarda elaborazione**] | Attendi un determinato periodo di tempo prima di elaborare un file di feed dati. Un ritardo può essere utile per dare alle implementazioni mobili l’opportunità ai dispositivi offline di connettersi e inviare dati. Può essere utilizzato anche per adattarsi ai processi lato server della tua organizzazione nella gestione dei file elaborati in precedenza. Nella maggior parte dei casi, non è necessario attendere. Un feed può essere ritardato fino a 120 minuti. |
   | [!UICONTROL **Date di inizio e fine**] | La data di inizio indica la data in cui desideri che inizi il feed di dati. Per iniziare immediatamente a elaborare i feed di dati per i dati storici, imposta questa data su una data nel passato in cui vengono raccolti i dati. Le date di inizio e fine si basano sul fuso orario della suite di rapporti. |
   | [!UICONTROL **Feed continuo**] | Questa casella di controllo rimuove la data di fine e consente l’esecuzione indefinita di un feed. Al termine dell’elaborazione dei dati storici, un feed attende che i dati vengano raccolti per una determinata ora o giorno. Al termine dell’ora o del giorno corrente, l’elaborazione inizia dopo il ritardo specificato. |

1. Nella sezione [!UICONTROL **Destinazione**], nel menu a discesa [!UICONTROL **Tipo**], seleziona la destinazione in cui desideri inviare i dati.

   >[!NOTE]
   >
   >Quando configuri la destinazione di rapporto, tieni presente quanto segue:
   >
   >* È consigliabile utilizzare un account cloud per la destinazione del rapporto. [Sono disponibili account FTP e SFTP precedenti](#legacy-destinations), ma non sono consigliati.
   >* Qualsiasi account cloud configurato in precedenza è disponibile per l’utilizzo nei feed di dati. Puoi configurare gli account cloud in uno dei seguenti modi:
   >
   >   * Durante la configurazione degli account cloud per [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)
   >   
   >   * Durante l&#39;importazione di [dati di classificazione Adobe Analytics](/help/components/locations/locations-manager.md) (non è possibile utilizzare le posizioni configurate per l&#39;importazione dei dati di classificazione).
   >   
   >   * Dal gestore Percorsi, in [Componenti > Percorsi](/help/components/locations/configure-import-accounts.md)
   >
   >* Gli account cloud sono associati al tuo account utente di Adobe Analytics. Gli altri utenti non possono utilizzare o visualizzare gli account cloud che configuri.
   >
   >* È possibile modificare qualsiasi posizione creata dalla gestione delle posizioni in [Componenti > Posizioni](/help/components/locations/configure-import-accounts.md)

   ![Menu a discesa della destinazione del feed dati](assets/datafeed-destinations-dropdown.png)

   Utilizza uno dei seguenti tipi di destinazione durante la creazione di un feed di dati. Per le istruzioni di configurazione, espandi il tipo di destinazione. Sono disponibili anche ulteriori [destinazioni legacy](#legacy-destinations), ma non sono consigliate.

   +++Amazon S3

   Puoi inviare feed direttamente ai bucket di Amazon S3. Questo tipo di destinazione richiede solo l’account Amazon S3 e la posizione (bucket).

   Adobe Analytics utilizza l’autenticazione tra account diversi per caricare i file da Adobe Analytics nella posizione specificata nell’istanza Amazon S3.

   Per configurare un bucket Amazon S3 come destinazione per un feed di dati:

   1. Iniziare a creare un feed dati come descritto in [Creare e configurare un feed dati](#create-and-configure-a-data-feed).

   1. Nella sezione [!UICONTROL **Destinazione**], nel menu a discesa [!UICONTROL **Tipo**], selezionare [!UICONTROL **Amazon S3**].

      ![Destinazione Amazon S3](assets/datafeed-destination-amazons3.png)

   1. Seleziona [!UICONTROL **Seleziona percorso**].

      Viene visualizzata la pagina Posizioni di esportazione di Amazon S3.

   1. (Condizionale) Se in Adobe Analytics è già stato configurato un account Amazon S3 (e una posizione su tale account), puoi utilizzarlo come destinazione del feed dati:

      >[!NOTE]
      >
      >Gli account sono disponibili solo se sono stati configurati o se sono stati condivisi con un’organizzazione di cui fai parte.

      1. Seleziona l’account dal menu a discesa [!UICONTROL **Seleziona account**].

         È possibile utilizzare qualsiasi account cloud configurato in una delle seguenti aree di Adobe Analytics:

         * Durante l’importazione dei dati di classificazione di Adobe Analytics, come descritto nello [schema](/help/components/classifications/sets/manage/schema.md).

           Tuttavia, non è possibile utilizzare le posizioni configurate per l’importazione dei dati di classificazione. Aggiungi invece una nuova destinazione come descritto di seguito.

         * Durante la configurazione di account e posizioni nell’area delle posizioni, come descritto in [Configurare account cloud di importazione ed esportazione](/help/components/locations/configure-import-accounts.md) e [Configurare posizioni cloud di importazione ed esportazione](/help/components/locations/configure-import-locations.md).

      1. Selezionare il percorso dal menu a discesa [!UICONTROL **Seleziona percorso**].

      1. Seleziona [!UICONTROL **Salva**] > [!UICONTROL **Salva**].

      La destinazione è ora configurata per inviare dati alla posizione Amazon S3 specificata.

   1. (Condizionale) Se non hai aggiunto in precedenza un account Amazon S3:

      1. Seleziona [!UICONTROL **Aggiungi account**], quindi specifica le seguenti informazioni:

         | Campo | Funzione |
         |---------|----------|
         | [!UICONTROL **Nome account**] | Un nome per l’account. Può essere qualsiasi nome scelto. |
         | [!UICONTROL **Descrizione account**] | Descrizione dell&#39;account. |
         | [!UICONTROL **Ruolo ARN**] | È necessario fornire un ruolo ARN (nome risorsa Amazon - Amazon Resource Name) che Adobe può utilizzare per accedere all’account Amazon S3. A tale scopo, crea un criterio di autorizzazione IAM per l’account di origine, associa il criterio a un utente e quindi crea un ruolo per l’account di destinazione. Per informazioni specifiche, consulta [questa documentazione di AWS](https://repost.aws/it/knowledge-center/cross-account-access-iam). |
         | [!UICONTROL **Utente ARN**] | L’utente ARN (nome risorsa Amazon) è fornito da Adobe. È necessario collegare questo utente al criterio creato. |

         {style="table-layout:auto"}

      1. Seleziona [!UICONTROL **Aggiungi percorso**], quindi specifica le seguenti informazioni:

         | Campo | Funzione |
         |---------|----------|
         | [!UICONTROL **Nome**] | Un nome per l’account. |
         | [!UICONTROL **Descrizione**] | Descrizione dell&#39;account. |
         | [!UICONTROL **Bucket**] | Il bucket all’interno dell’account Amazon S3 in cui desideri inviare i dati di Adobe Analytics. <p>Assicurati che l’utente ARN fornito da Adobe disponga dell’autorizzazione `S3:PutObject` per caricare i file in questo bucket. Questa autorizzazione consente all’utente ARN di caricare i file iniziali e di sovrascrivere i file per i caricamenti successivi.</p><p>I nomi dei bucket devono soddisfare regole di denominazione specifiche. Ad esempio, devono contenere da 3 a 63 caratteri, possono essere composte solo da lettere minuscole, numeri, punti (.) e trattini (-) e devono iniziare e terminare con una lettera o un numero. [Un elenco completo delle regole di denominazione è disponibile nella documentazione di AWS](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucketnamingrules.html?lang=it). </p> |
         | [!UICONTROL **Prefisso**] | La cartella all’interno del bucket in cui desideri inserire i dati. Specifica il nome di una cartella, quindi aggiungi una barra rovesciata dopo il nome per creare la cartella. Ad esempio: `folder_name/` |

         {style="table-layout:auto"}

      1. Seleziona [!UICONTROL **Crea**] > [!UICONTROL **Salva**].

         La destinazione è ora configurata per inviare dati alla posizione Amazon S3 specificata.

      1. (Condizionale) Se devi gestire la destinazione (account e percorso) appena creata, questa è disponibile nel [Gestione posizioni](/help/components/locations/locations-manager.md).

+++

   +++Azure RBAC

   Puoi inviare feed direttamente a un contenitore di Azure utilizzando l’autenticazione RBAC. Questo tipo di destinazione richiede un ID applicazione, un ID tenant e un segreto.

   Per configurare un account RBAC di Azure come destinazione per un feed di dati:

   1. Se non lo hai già fatto, crea un’applicazione Azure che Adobe Analytics può utilizzare per l’autenticazione, quindi concedi le autorizzazioni di accesso in Controllo degli accessi (IAM).

      Per informazioni, consultare la [documentazione di Microsoft Azure relativa alla creazione di un&#39;applicazione Azure Active Directory](https://learn.microsoft.com/en-us/azure/active-directory/develop/howto-create-service-principal-portal).

   1. Nella sezione [!UICONTROL **Destinazione**] di Adobe Analytics Admin Console, nel menu a discesa [!UICONTROL **Tipo**], selezionare [!UICONTROL **Azure RBAC**].

      ![Destinazione RBAC di Azure](assets/datafeed-destination-azurerbac.png)

   1. Seleziona [!UICONTROL **Seleziona percorso**].

      Viene visualizzata la pagina Percorsi di esportazione RBAC di Azure.

   1. (Condizionale) Se in Adobe Analytics è già stato configurato un account Azure RBAC (e una posizione su tale account), puoi utilizzarlo come destinazione del feed dati:

      >[!NOTE]
      >
      >Gli account sono disponibili solo se sono stati configurati o se sono stati condivisi con un’organizzazione di cui fai parte.

      1. Seleziona l’account dal menu a discesa [!UICONTROL **Seleziona account**].

      È possibile utilizzare qualsiasi account cloud configurato in una delle seguenti aree di Adobe Analytics:

      * Durante l’importazione dei dati di classificazione di Adobe Analytics, come descritto nello [schema](/help/components/classifications/sets/manage/schema.md).

        Tuttavia, non è possibile utilizzare le posizioni configurate per l’importazione dei dati di classificazione. Aggiungi invece una nuova destinazione come descritto di seguito.

      * Durante la configurazione di account e posizioni nell’area delle posizioni, come descritto in [Configurare account cloud di importazione ed esportazione](/help/components/locations/configure-import-accounts.md) e [Configurare posizioni cloud di importazione ed esportazione](/help/components/locations/configure-import-locations.md).

      1. Selezionare il percorso dal menu a discesa [!UICONTROL **Seleziona percorso**].

      1. Seleziona [!UICONTROL **Salva**] > [!UICONTROL **Salva**].

         La destinazione è ora configurata per inviare i dati al percorso RBAC di Azure specificato.

   1. (Condizionale) Se non hai aggiunto in precedenza un account Azure RBAC:

      1. Seleziona [!UICONTROL **Aggiungi account**], quindi specifica le seguenti informazioni:

         | Campo | Funzione |
         |---------|----------|
         | [!UICONTROL **Nome account**] | Nome dell&#39;account RBAC di Azure. Questo nome viene visualizzato nel campo a discesa [!UICONTROL **Seleziona account**] e può essere qualsiasi nome scelto. |
         | [!UICONTROL **Descrizione account**] | Descrizione dell&#39;account Azure RBAC. Questa descrizione viene visualizzata nel campo a discesa [!UICONTROL **Seleziona account**] e può essere qualsiasi nome scelto. |
         | [!UICONTROL **ID applicazione**] | Copia questo ID dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nella scheda **Panoramica** all’interno dell’applicazione. Per ulteriori informazioni, consulta la [Documentazione di Microsoft Azure su come registrare un’applicazione con Microsoft Identity Platform](https://learn.microsoft.com/it-it/entra/identity-platform/quickstart-register-app). |
         | [!UICONTROL **ID tenant**] | Copia questo ID dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nella scheda **Panoramica** all’interno dell’applicazione. Per ulteriori informazioni, consulta la [Documentazione di Microsoft Azure su come registrare un’applicazione con Microsoft Identity Platform](https://learn.microsoft.com/it-it/entra/identity-platform/quickstart-register-app). |
         | [!UICONTROL **Segreto**] | Copia il segreto dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nella scheda **Certificati e segreti** all’interno dell’applicazione. Per ulteriori informazioni, consulta la [Documentazione di Microsoft Azure su come registrare un’applicazione con Microsoft Identity Platform](https://learn.microsoft.com/it-it/entra/identity-platform/quickstart-register-app). |

         {style="table-layout:auto"}

      1. Seleziona [!UICONTROL **Aggiungi percorso**], quindi specifica le seguenti informazioni:

         | Campo | Funzione |
         |---------|----------|
         | [!UICONTROL **Nome**] | Un nome per la posizione. Questo nome viene visualizzato nel campo a discesa [!UICONTROL **Seleziona percorso**] e può essere qualsiasi nome scelto. |
         | [!UICONTROL **Descrizione**] | Una descrizione della posizione. Questa descrizione viene visualizzata nel campo a discesa [!UICONTROL **Seleziona percorso**] e può essere qualsiasi nome scelto. |
         | [!UICONTROL **Account**] | Account di archiviazione Azure. |
         | [!UICONTROL **Contenitore**] | Il contenitore all’interno dell’account specificato nel punto in cui desideri inviare i dati di Adobe Analytics. Assicurati di concedere le autorizzazioni per caricare i file nell’applicazione Azure creata in precedenza. |
         | [!UICONTROL **Prefisso**] | La cartella all’interno del contenitore in cui desideri inserire i dati. Specifica il nome di una cartella, quindi aggiungi una barra rovesciata dopo il nome per creare la cartella. Ad esempio: `folder_name/`<p>Accertati che l’ID applicazione specificato durante la configurazione dell’account RBAC di Azure disponga del ruolo `Storage Blob Data Contributor` per accedere al contenitore (cartella).</p> <p>Per ulteriori informazioni, consulta [Ruoli incorporati di Azure](https://learn.microsoft.com/it-it/azure/role-based-access-control/built-in-roles).</p> |

         {style="table-layout:auto"}

      1. Seleziona [!UICONTROL **Crea**] > [!UICONTROL **Salva**].

         La destinazione è ora configurata per inviare i dati al percorso RBAC di Azure specificato.

      1. (Condizionale) Se devi gestire la destinazione (account e percorso) appena creata, questa è disponibile nel [Gestione posizioni](/help/components/locations/locations-manager.md).

+++

   +++Azure SAS

   È possibile inviare feed direttamente a un contenitore di Azure utilizzando l’autenticazione SAS. Questo tipo di destinazione richiede un ID applicazione, un ID tenant, un URI dell&#39;insieme di credenziali delle chiavi, un nome del segreto dell&#39;insieme di credenziali delle chiavi e un segreto.

   Per configurare Azure SAS come destinazione per un feed di dati:

   1. Se non lo hai già fatto, crea un’applicazione Azure che Adobe Analytics può utilizzare per l’autenticazione.

      Per informazioni, consultare la [documentazione di Microsoft Azure relativa alla creazione di un&#39;applicazione Azure Active Directory](https://learn.microsoft.com/en-us/azure/active-directory/develop/howto-create-service-principal-portal).

   1. Nella sezione [!UICONTROL **Destinazione**] di Adobe Analytics Admin Console selezionare [!UICONTROL **Azure SAS**].

      ![Destinazione SAS di Azure](assets/datafeed-destination-azuresas.png)

   1. Seleziona [!UICONTROL **Seleziona percorso**].

      Viene visualizzata la pagina Percorsi di esportazione SAS di Azure.

   1. (Condizionale) Se in Adobe Analytics è già stato configurato un account SAS di Azure (e una posizione su tale account), puoi utilizzarlo come destinazione del feed dati:

      >[!NOTE]
      >
      >Gli account sono disponibili solo se sono stati configurati o se sono stati condivisi con un’organizzazione di cui fai parte.

      1. Seleziona l’account dal menu a discesa [!UICONTROL **Seleziona account**].

         È possibile utilizzare qualsiasi account cloud configurato in una delle seguenti aree di Adobe Analytics:

         * Durante l’importazione dei dati di classificazione di Adobe Analytics, come descritto nello [schema](/help/components/classifications/sets/manage/schema.md).

           Tuttavia, non è possibile utilizzare le posizioni configurate per l’importazione dei dati di classificazione. Aggiungi invece una nuova destinazione come descritto di seguito.

         * Durante la configurazione di account e posizioni nell’area delle posizioni, come descritto in [Configurare account cloud di importazione ed esportazione](/help/components/locations/configure-import-accounts.md) e [Configurare posizioni cloud di importazione ed esportazione](/help/components/locations/configure-import-locations.md).

      1. Selezionare il percorso dal menu a discesa [!UICONTROL **Seleziona percorso**].

      1. Seleziona [!UICONTROL **Salva**] > [!UICONTROL **Salva**].

         La destinazione è ora configurata per inviare i dati al percorso SAS di Azure specificato.

   1. (Condizionale) Se non è stato aggiunto in precedenza un account SAS di Azure:

      1. Seleziona [!UICONTROL **Aggiungi account**], quindi specifica le seguenti informazioni:

         | Campo | Funzione |
         |---------|----------|
         | [!UICONTROL **Nome account**] | Nome dell&#39;account SAS di Azure. Questo nome viene visualizzato nel campo a discesa [!UICONTROL **Seleziona account**] e può essere qualsiasi nome scelto. |
         | [!UICONTROL **Descrizione account**] | Descrizione dell&#39;account SAS di Azure. Questa descrizione viene visualizzata nel campo a discesa [!UICONTROL **Seleziona account**] e può essere qualsiasi nome scelto. |
         | [!UICONTROL **ID applicazione**] | Copia questo ID dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nella scheda **Panoramica** all’interno dell’applicazione. Per ulteriori informazioni, consulta la [Documentazione di Microsoft Azure su come registrare un’applicazione con Microsoft Identity Platform](https://learn.microsoft.com/it-it/entra/identity-platform/quickstart-register-app). |
         | [!UICONTROL **ID tenant**] | Copia questo ID dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nella scheda **Panoramica** all’interno dell’applicazione. Per ulteriori informazioni, consulta [Documentazione di Microsoft Azure su come registrare un’applicazione con Microsoft Identity Platform](https://learn.microsoft.com/it-it/entra/identity-platform/quickstart-register-app). |
         | [!UICONTROL **URI di Key Vault**] | <p>Percorso dell&#39;URI SAS nell&#39;insieme di credenziali delle chiavi di Azure. Per configurare Azure SAS, è necessario memorizzare un URI SAS come segreto utilizzando Azure Key Vault. Per informazioni, consulta [Documentazione di Microsoft Azure su come impostare e recuperare un segreto da Azure Key Vault](https://learn.microsoft.com/it-it/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>Dopo la creazione dell’URI di Key Vault:<ul><li>Aggiungi un criterio di accesso a Key Vault per concedere l’autorizzazione all’applicazione Azure creata.<p>Per informazioni, consulta [Documentazione di Microsoft Azure su come assegnare un criterio di accesso a Key Vault](https://learn.microsoft.com/it-it/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p><p>Oppure</p><p>Se si desidera concedere direttamente un ruolo di accesso senza creare un criterio di accesso, vedere la [documentazione di Microsoft Azure relativa all&#39;assegnazione dei ruoli di Azure tramite il portale di Azure](https://learn.microsoft.com/en-us/azure/role-based-access-control/role-assignments-portal). Questo aggiunge l’assegnazione del ruolo per l’ID applicazione per accedere all’URI dell’insieme di credenziali delle chiavi. </p></li><li>Assicurati che all’ID applicazione sia stato assegnato il ruolo incorporato di `Key Vault Certificate User` per accedere all’URI di Key Vault</br><p>Per ulteriori informazioni, consulta [Ruoli incorporati di Azure](https://learn.microsoft.com/it-it/azure/role-based-access-control/built-in-roles).</p></li></ul> |
         | [!UICONTROL **Nome segreto di Key Vault**] | Nome segreto creato quando si aggiunge il segreto ad Azure Key Vault. In Microsoft Azure, queste informazioni si trovano nel Key Vault creato, nelle pagine delle impostazioni di **Key Vault**. Per informazioni, consulta [Documentazione di Microsoft Azure su come impostare e recuperare un segreto Azure Key Vault](https://learn.microsoft.com/it-it/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
         | [!UICONTROL **Segreto**] | Copia il segreto dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nella scheda **Certificati e segreti** all’interno dell’applicazione. Per ulteriori informazioni, consulta la [Documentazione di Microsoft Azure su come registrare un’applicazione con Microsoft Identity Platform](https://learn.microsoft.com/it-it/entra/identity-platform/quickstart-register-app). |

         {style="table-layout:auto"}

      1. Seleziona [!UICONTROL **Aggiungi percorso**], quindi specifica le seguenti informazioni:

         | Campo | Funzione |
         |---------|----------|
         | [!UICONTROL **Nome**] | Un nome per la posizione. Questo nome viene visualizzato nel campo a discesa [!UICONTROL **Seleziona percorso**] e può essere qualsiasi nome scelto. |
         | [!UICONTROL **Descrizione**] | Una descrizione della posizione. Questa descrizione viene visualizzata nel campo a discesa [!UICONTROL **Seleziona percorso**] e può essere qualsiasi nome scelto. |
         | [!UICONTROL **Contenitore**] | Il contenitore all’interno dell’account specificato nel punto in cui desideri inviare i dati di Adobe Analytics. |
         | [!UICONTROL **Prefisso**] | La cartella all’interno del contenitore in cui desideri inserire i dati. Specifica il nome di una cartella, quindi aggiungi una barra rovesciata dopo il nome per creare la cartella. Ad esempio: `folder_name/`<p>Accertati che l’archivio dell’URI SAS specificato nel campo nome segreto di Key Vault durante la configurazione dell’account SAS di Azure abbia l’autorizzazione `Write`. Questo consente all’URI SAS di creare file nel contenitore Azure. <p>Se desideri che l’URI SAS sovrascriva anche i file, assicurati che l’archivio dell’URI SAS disponga dell’autorizzazione `Delete`.</p><p>Per ulteriori informazioni, consulta [Risorse di archiviazione BLOB](https://learn.microsoft.com/it-it/azure/storage/blobs/storage-blobs-introduction#blob-storage-resources) nella documentazione dell’archiviazione BLOB di Azure.</p> |

         {style="table-layout:auto"}

      1. Seleziona [!UICONTROL **Crea**] > [!UICONTROL **Salva**].

         La destinazione è ora configurata per inviare i dati al percorso SAS di Azure specificato.

      1. (Condizionale) Se devi gestire la destinazione (account e percorso) appena creata, questa è disponibile nel [Gestione posizioni](/help/components/locations/locations-manager.md).

+++

   +++Google Cloud Platform

   Puoi inviare feed direttamente ai bucket di Google Cloud Platform (GCP). Questo tipo di destinazione richiede solo il nome dell’account GCP e la posizione (bucket).

   Adobe Analytics utilizza l’autenticazione tra account diversi per caricare i file da Adobe Analytics nella posizione specificata nell’istanza GCP.

   Per configurare un bucket GCP come destinazione per un feed di dati:

   1. Nella sezione [!UICONTROL **Destinazione**] di Adobe Analytics Admin Console, seleziona [!UICONTROL **Piattaforma Google Cloud**].

      ![Destinazione piattaforma Google Cloud](assets/datafeed-destination-gcp.png)

   1. Seleziona [!UICONTROL **Seleziona percorso**].

      Viene visualizzata la pagina Posizioni di esportazione GCP.

   1. (Condizionale) Se un account Google Cloud Platform (e una posizione su tale account) è già stato configurato in Adobe Analytics, puoi utilizzarlo come destinazione del feed dati:

      >[!NOTE]
      >
      >Gli account sono disponibili solo se sono stati configurati o se sono stati condivisi con un’organizzazione di cui fai parte.

      1. Seleziona l’account dal menu a discesa [!UICONTROL **Seleziona account**].

         È possibile utilizzare qualsiasi account cloud configurato in una delle seguenti aree di Adobe Analytics:

         * Durante l’importazione dei dati di classificazione di Adobe Analytics, come descritto nello [schema](/help/components/classifications/sets/manage/schema.md).

           Tuttavia, non è possibile utilizzare le posizioni configurate per l’importazione dei dati di classificazione. Aggiungi invece una nuova destinazione come descritto di seguito.

         * Durante la configurazione di account e posizioni nell’area delle posizioni, come descritto in [Configurare account cloud di importazione ed esportazione](/help/components/locations/configure-import-accounts.md) e [Configurare posizioni cloud di importazione ed esportazione](/help/components/locations/configure-import-locations.md).

      1. Selezionare il percorso dal menu a discesa [!UICONTROL **Seleziona percorso**].

      1. Seleziona [!UICONTROL **Salva**] > [!UICONTROL **Salva**].

         La destinazione è ora configurata per inviare dati alla posizione specificata nella piattaforma Google Cloud.

   1. (Condizionale) Se non hai aggiunto in precedenza un account GCP:

      1. Seleziona [!UICONTROL **Aggiungi account**], quindi specifica le seguenti informazioni:

         | Campo | Funzione |
         |---------|----------|
         | [!UICONTROL **Nome account**] | Un nome per l’account. Può essere qualsiasi nome scelto. |
         | [!UICONTROL **Descrizione account**] | Descrizione dell&#39;account. |
         | [!UICONTROL **ID Progetto**] | ID personale progetto Google Cloud. Consulta la [Documentazione di Google Cloud su come ottenere un ID progetto](https://cloud.google.com/resource-manager/docs/creating-managing-projects?hl=it#identifying_projects). |

         {style="table-layout:auto"}

      1. Seleziona [!UICONTROL **Aggiungi percorso**], quindi specifica le seguenti informazioni:

         | Campo | Funzione |
         |---------|----------|
         | [!UICONTROL **Entità**] | L’entità è fornita dall’Adobe. È necessario concedere l&#39;autorizzazione per la ricezione di feed a questa entità principale. |
         | [!UICONTROL **Nome**] | Un nome per l’account. |
         | [!UICONTROL **Descrizione**] | Descrizione dell&#39;account. |
         | [!UICONTROL **Bucket**] | Il bucket all’interno dell’account GCP in cui desideri inviare i dati di Adobe Analytics. <p>Accertati di aver concesso una delle seguenti autorizzazioni all’entità principale fornita da Adobe. Per informazioni sulla concessione delle autorizzazioni, consulta [Aggiungere un’entità principale a un criterio a livello di bucket](https://cloud.google.com/storage/docs/access-control/using-iam-permissions?hl=it#bucket-add) nella documentazione di Google Cloud.<ul><li>`roles/storage.objectCreator`: utilizza questa autorizzazione se desideri limitare l’entità principale alla sola creazione di file nell’account GCP. </br>**Importante:** se utilizzi questa autorizzazione per il reporting pianificato, utilizza un nome file univoco per ogni nuova esportazione pianificata. In caso contrario, la generazione dei rapporti non riuscirà perché l’entità principale non ha accesso alla sovrascrittura dei file esistenti.</li><li>(scelta consigliata) `roles/storage.objectUser`: utilizzare questa autorizzazione se si desidera che l&#39;entità abbia accesso alla visualizzazione, all&#39;elenco, all&#39;aggiornamento e all&#39;eliminazione dei file nell&#39;account GCP.</br>Questa autorizzazione consente all’entità principale di sovrascrivere i file esistenti per i caricamenti successivi, senza la necessità di generare automaticamente nomi di file univoci per ogni nuova esportazione pianificata.</li></ul><p>Se l’organizzazione utilizza [Vincoli dei criteri dell&#39;organizzazione](https://cloud.google.com/storage/docs/org-policy-constraints?hl=it) per accettare solo l’account Google Cloud Platform nel tuo elenco consentiti, è necessario il seguente ID organizzazione di Google Cloud Platform di proprietà di Adobe: <ul><li>`DISPLAY_NAME`: `adobe.com`</li><li>`ID`: `178012854243`</li><li>`DIRECTORY_CUSTOMER_ID`: `C02jo8puj`</li></ul> </p> |
         | [!UICONTROL **Prefisso**] | La cartella all’interno del bucket in cui desideri inserire i dati. Specifica il nome di una cartella, quindi aggiungi una barra rovesciata dopo il nome per creare la cartella. Ad esempio: `folder_name/` |

         {style="table-layout:auto"}

      1. Seleziona [!UICONTROL **Crea**] > [!UICONTROL **Salva**].

         La destinazione è ora configurata per inviare dati alla posizione GCP specificata.

      1. (Condizionale) Se devi gestire la destinazione (account e percorso) appena creata, questa è disponibile nel [Gestione posizioni](/help/components/locations/locations-manager.md).

+++

1. Nella sezione [!UICONTROL **Definizioni colonne dati**], seleziona il modello [!UICONTROL **All Adobe Columns**] più recente nel menu a discesa, quindi completa i campi seguenti:

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **Rimuovi caratteri di escape**] | Durante la raccolta dei dati, alcuni caratteri (ad esempio le nuove righe) possono causare problemi. Selezionare questa casella se si desidera rimuovere questi caratteri dai file di feed. |
   | [!UICONTROL **Formato di compressione**] | Tipo di compressione utilizzata. **Gzip** restituisce i file in formato `.tar.gz`. **Zip** restituisce i file in formato `.zip`. |
   | [!UICONTROL **Tipo di pacchetto**] | Selezionare [!UICONTROL **Più file**] per la maggior parte dei feed di dati. Questa opzione impagina i dati in blocchi non compressi da 2 GB. Se l&#39;opzione [!UICONTROL **Più file**] è selezionata e i dati non compressi per la finestra di reporting sono inferiori a 2 GB, viene inviato un file. Se si seleziona **File singolo**, il file `hit_data.tsv` verrà restituito in un unico file, potenzialmente di grandi dimensioni. |
   | [!UICONTROL **Manifesto**] | Determina se Adobe deve consegnare un [file manifesto](c-df-contents/datafeeds-contents.md#feed-manifest) alla destinazione quando non vengono raccolti dati per un intervallo di feed. Se si seleziona **File manifesto**, verrà visualizzato un file manifesto simile al seguente quando non vengono raccolti dati:<p>`text`</p><p>`Datafeed-Manifest-Version: 1.0`</p><p>`Lookup-Files: 0`</p><p>`Data-Files: 0`</p><p> `Total-Records: 0`</p> |
   | [!UICONTROL **Modelli di colonna**] | Durante la creazione di molti feed di dati, l’Adobe consiglia di creare un modello di colonna. Quando si seleziona un modello di colonna, le colonne specificate vengono incluse automaticamente nel modello. Per impostazione predefinita, in Adobe sono inoltre disponibili diversi modelli. |
   | [!UICONTROL **Colonne disponibili**] | Tutte le colonne di dati disponibili in Adobe Analytics. Fare clic su [!UICONTROL Add all] per includere tutte le colonne in un feed di dati. |
   | [!UICONTROL **Colonne incluse**] | Colonne da includere in un feed di dati. Fare clic su [!UICONTROL Remove all] per rimuovere tutte le colonne da un feed di dati. |
   | [!UICONTROL **Scarica CSV**] | Scarica un file CSV contenente tutte le colonne incluse. |

1. Seleziona [!UICONTROL **Salva**] in alto a destra.

   L’elaborazione dei dati storici inizia immediatamente. Al termine dell’elaborazione dei dati per un giorno, il file viene inviato alla destinazione configurata.

   Per informazioni su come accedere al feed dati e per comprenderne meglio il contenuto, vedere [Contenuto feed dati - panoramica](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md).

## Destinazioni legacy

>[!IMPORTANT]
>
>Le destinazioni descritte in questa sezione sono legacy e non sono consigliate. Al contrario, utilizza una delle seguenti destinazioni durante la creazione di un feed di dati: Amazon S3, Google Cloud Platform, Azure RBAC o Azure SAS. Per informazioni dettagliate su ciascuna di queste destinazioni consigliate, vedere [Creare e configurare un feed di dati](#create-and-configure-a-data-feed).


Le informazioni seguenti forniscono informazioni di configurazione per ciascuna destinazione legacy:

### FTP

I dati del feed dati possono essere inviati a un Adobe o a una posizione FTP ospitata dal cliente. Richiede un host FTP, un nome utente e una password. Utilizza il campo del percorso per inserire i file di feed in una cartella. Le cartelle devono già esistere. I feed generano un errore se il percorso specificato non esiste.

Per completare i campi disponibili, utilizza le seguenti informazioni:

* [!UICONTROL **Host**]: immetti l&#39;URL di destinazione FTP desiderato. Esempio: `ftp://ftp.omniture.com`.
* [!UICONTROL **Percorso**]: può essere lasciato vuoto
* [!UICONTROL **Nome utente**]: immetti il nome utente per accedere al sito FTP.
* [!UICONTROL **Password e conferma password**]: immetti la password per accedere al sito FTP.

### SFTP

È disponibile il supporto SFTP per i feed di dati. Richiede un host SFTP, un nome utente e il sito di destinazione per contenere una chiave pubblica RSA o DSA valida. Puoi scaricare la chiave pubblica adatta al momento della creazione del feed.

### S3

Puoi inviare feed direttamente ai bucket di Amazon S3. Questo tipo di destinazione richiede un nome bucket, un ID chiave di accesso e una chiave segreto. Consulta [Requisiti di denominazione del bucket Amazon S3](https://docs.aws.amazon.com/it_it/AmazonS3/latest/userguide/bucketnamingrules.html) nella documentazione di Amazon S3 per ulteriori informazioni.

L&#39;utente fornito per il caricamento dei feed di dati deve disporre delle seguenti [autorizzazioni](https://docs.aws.amazon.com/it_it/AmazonS3/latest/API/API_Operations_Amazon_Simple_Storage_Service.html):

* s3:GetObject
* s3:PutObject
* s3:PutObjectAcl

  >[!NOTE]
  >
  >Per ogni caricamento in un bucket Amazon S3, [!DNL Analytics] aggiunge il proprietario del bucket all&#39;ACL BucketOwnerFullControl, indipendentemente dal fatto che il bucket disponga di criteri che lo richiedano. Per ulteriori informazioni, vedere &quot;[Qual è l&#39;impostazione BucketOwnerFullControl per i feed di dati di Amazon S3?](df-faq.md#BucketOwnerFullControl)&quot;

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

### BLOB di Azure

I feed di dati supportano le destinazioni BLOB di Azure. Richiede un contenitore, un account e una chiave. Amazon crittografa automaticamente i dati inattivi. Quando scarichi i dati, questi vengono decrittografati automaticamente. Per ulteriori informazioni, consulta [Creare un account di archiviazione](https://learn.microsoft.com/it-it/azure/storage/common/storage-account-create?tabs=azure-portal#view-and-copy-storage-access-keys) nelle documentazioni di Microsoft Azure.

>[!NOTE]
>
>È necessario implementare un processo personalizzato per gestire lo spazio su disco nella destinazione del feed. Adobe non elimina dati dal server.
