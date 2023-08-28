---
title: Creare un feed di dati
description: Scopri come creare un feed di dati.
feature: Data Feeds
exl-id: 36c8a40e-6137-4836-9d4b-bebf17b932bc
source-git-commit: 6681eedee327a5bb9cbfcb8ccf00ac32628f5a1f
workflow-type: tm+mt
source-wordcount: '3171'
ht-degree: 3%

---

# Creare un feed di dati

Durante la creazione di un feed di dati, fornisci ad Adobe:

* Informazioni sulla destinazione in cui si desidera inviare i file di dati non elaborati

* Dati da includere in ciascun file

>[!NOTE]
>
>Prima di creare un feed di dati, è importante avere una conoscenza di base dei feed di dati e assicurarsi di soddisfare tutti i prerequisiti necessari. Per ulteriori informazioni, consulta [Panoramica sui feed dati](data-feed-overview.md).

## Creare e configurare un feed dati

1. Accedi a [experiencecloud.adobe.com](https://experiencecloud.adobe.com) utilizzando le credenziali Adobe ID.
1. Seleziona l’icona a 9 quadrati in alto a destra, quindi seleziona [!UICONTROL **Analytics**].
1. Nella barra di navigazione superiore, vai a [!UICONTROL **Amministratore**] > [!UICONTROL **Feed dati**].
1. Seleziona [!UICONTROL **Aggiungi**].

   ![Aggiungi feed dati](assets/datafeed-add.png)

   Viene visualizzata una pagina con tre categorie principali: [!UICONTROL **Informazioni feed**], [!UICONTROL **Destinazione**], e [!UICONTROL **Definizioni delle colonne dati**].
1. In [!UICONTROL **Informazioni sui feed**] , completare i campi seguenti:

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **Nome**] | Nome del feed dati. Deve essere univoco all’interno della suite di rapporti selezionata e può contenere fino a 255 caratteri. |
   | [!UICONTROL **Suite di rapporti**] | La suite di rapporti su cui si basa il feed di dati. Se vengono creati più feed di dati per la stessa suite di rapporti, devono avere definizioni di colonne diverse. Solo le suite di rapporti di origine supportano i feed di dati; le suite di rapporti virtuali non sono supportate. |
   | [!UICONTROL **E-mail al termine**] | L’indirizzo e-mail da notificare al termine dell’elaborazione di un feed. L’indirizzo e-mail deve essere formattato correttamente. |
   | [!UICONTROL **Intervallo feed**] | Seleziona **Giornaliero** per la retrocompilazione o la cronologia dei dati. I feed giornalieri contengono dati relativi a un’intera giornata, dalla mezzanotte alla mezzanotte nel fuso orario della suite di rapporti.  Seleziona **Ogni ora** per dati continui (giornalieri è disponibile anche per feed continui, se lo desideri). I feed orari contengono dati relativi a una sola ora. |
   | [!UICONTROL **Ritarda elaborazione**] | Attendi un determinato periodo di tempo prima di elaborare un file di feed dati. Un ritardo può essere utile per dare alle implementazioni mobili l’opportunità ai dispositivi offline di connettersi e inviare dati. Può essere utilizzato anche per adattarsi ai processi lato server della tua organizzazione nella gestione dei file elaborati in precedenza. Nella maggior parte dei casi, non è necessario attendere. Un feed può essere ritardato fino a 120 minuti. |
   | [!UICONTROL **Date di inizio e fine**] | La data di inizio indica la data in cui desideri che inizi il feed di dati. Per iniziare immediatamente a elaborare i feed di dati per i dati storici, imposta questa data su una data nel passato in cui vengono raccolti i dati. Le date di inizio e fine si basano sul fuso orario della suite di rapporti. |
   | [!UICONTROL **Alimentazione continua**] | Questa casella di controllo rimuove la data di fine e consente l’esecuzione indefinita di un feed. Al termine dell’elaborazione dei dati storici, un feed attende che i dati vengano raccolti per una determinata ora o giorno. Al termine dell’ora o del giorno corrente, l’elaborazione inizia dopo il ritardo specificato. |

1. In [!UICONTROL **Destinazione**] , nella sezione [!UICONTROL **Tipo**] selezionare la destinazione in cui si desidera inviare i dati.

   >[!NOTE]
   >
   >Quando configuri una destinazione di rapporto, tieni presente quanto segue:
   >
   >* È consigliabile utilizzare un account cloud per la destinazione del rapporto. [Account FTP e SFTP legacy](#legacy-destinations) sono disponibili, ma non sono consigliati.
   >
   >* Gli account cloud sono associati al tuo account utente di Adobe Analytics. Gli altri utenti non possono utilizzare o visualizzare gli account cloud configurati dall’utente.
   >

   ![Menu a discesa della destinazione del feed dati](assets/datafeed-destinations-dropdown.png)

   Utilizza uno dei seguenti tipi di destinazione durante la creazione di un feed di dati. Per le istruzioni di configurazione, espandi il tipo di destinazione. (aggiuntivo [destinazioni legacy](#legacy-destinations) sono disponibili, ma non sono consigliati.)

   +++Amazon S3

   Puoi inviare feed direttamente ai bucket di Amazon S3. Questo tipo di destinazione richiede solo l’account Amazon S3 e la posizione (bucket).

   Adobe Analytics utilizza l’autenticazione tra account diversi per caricare i file da Adobe Analytics nella posizione specificata nell’istanza Amazon S3.

   Per configurare un bucket Amazon S3 come destinazione per un feed di dati:

   1. In Admin Console di Adobe Analytics, nella sezione [!UICONTROL **Destinazione**] sezione, seleziona [!UICONTROL **Amazon S3**].

      ![Destinazione Amazon S3](assets/datafeed-destination-amazons3.png)

   1. Seleziona [!UICONTROL **Seleziona posizione**].

      Viene visualizzata la pagina Posizioni di esportazione di Amazon S3.

   1. (Condizionale) Se in precedenza hai aggiunto un account Amazon S3 e la posizione:

      1. Seleziona l’account da [!UICONTROL **Seleziona account**] menu a discesa.

      1. Seleziona la posizione da [!UICONTROL **Seleziona posizione**] menu a discesa.

      1. Seleziona [!UICONTROL **Salva**] > [!UICONTROL **Salva**].

         La destinazione è ora configurata per inviare dati alla posizione Amazon S3 specificata.

   1. (Condizionale) Se non hai aggiunto in precedenza un account Amazon S3:

      1. Seleziona [!UICONTROL **Aggiungi account**], quindi specifica le seguenti informazioni:

         | Campo | Funzione |
         |---------|----------|
         | [!UICONTROL **Nome account**] | Un nome per l’account. Può essere qualsiasi nome scelto. |
         | [!UICONTROL **Descrizione account**] | Descrizione dell&#39;account. |
         | [!UICONTROL **ARN per ruolo**] | È necessario fornire un ARN per il ruolo (Amazon Resource Name) che l’Adobe può utilizzare per accedere all’account Amazon S3. A tale scopo, creare un criterio di autorizzazione IAM per l&#39;account di origine, associare il criterio a un utente e quindi creare un ruolo per l&#39;account di destinazione. Per informazioni specifiche, consulta [questa documentazione di AWS](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). |
         | [!UICONTROL **ARN utente**] | L’ARN utente (Amazon Resource Name) è fornito da Adobe. È necessario collegare questo utente al criterio creato. |

         {style="table-layout:auto"}

         1. Seleziona [!UICONTROL **Aggiungi posizione**], quindi specifica le seguenti informazioni:

         | Campo | Funzione |
         |---------|----------|
         | [!UICONTROL **Nome**] | Un nome per l’account. |
         | [!UICONTROL **Descrizione**] | Descrizione dell&#39;account. |
         | [!UICONTROL **Bucket**] | Il bucket all’interno dell’account Amazon S3 in cui desideri inviare i dati di Adobe Analytics. Assicurati che l’ARN utente fornito da Adobe abbia accesso al caricamento di file in questo bucket. |
         | [!UICONTROL **Prefisso**] | La cartella all’interno del bucket in cui desideri inserire i dati. Specifica il nome di una cartella, quindi aggiungi una barra rovesciata dopo il nome per creare la cartella. Ad esempio, `folder_name/` |

         {style="table-layout:auto"}

      1. Seleziona [!UICONTROL **Crea**] > [!UICONTROL **Salva**].

         La destinazione è ora configurata per inviare dati alla posizione Amazon S3 specificata.

+++

   +++RBAC di Azure

   Puoi inviare feed direttamente a un contenitore di Azure utilizzando l’autenticazione RBAC. Questo tipo di destinazione richiede un nome bucket, un ID applicazione, un ID tenant e una chiave segreta.

   Per configurare un bucket RBAC di Azure come destinazione per un feed di dati:

   1. Se non lo hai già fatto, crea un’applicazione Azure che Adobe Analytics può utilizzare per l’autenticazione, quindi concedi le autorizzazioni di accesso in Controllo degli accessi (IAM).

      Per informazioni, fare riferimento a [Documentazione di Microsoft Azure sulla creazione di un&#39;applicazione Azure Active Directory](https://learn.microsoft.com/en-us/azure/active-directory/develop/howto-create-service-principal-portal).

   1. In Admin Console di Adobe Analytics, nella sezione [!UICONTROL **Destinazione**] sezione, seleziona [!UICONTROL **RBAC di Azure**].

      ![Destinazione Azure RBAC](assets/datafeed-destination-azurerbac.png)

   1. Seleziona [!UICONTROL **Seleziona posizione**].

      Viene visualizzata la pagina Percorsi di esportazione RBAC di Azure.

   1. (Condizionale) Se in precedenza hai aggiunto un account e una posizione di Azure RBAC:

      1. Seleziona l’account da [!UICONTROL **Seleziona account**] menu a discesa.

      1. Seleziona la posizione da [!UICONTROL **Seleziona posizione**] menu a discesa.

      1. Seleziona [!UICONTROL **Salva**] > [!UICONTROL **Salva**].

         La destinazione è ora configurata per inviare i dati al percorso RBAC di Azure specificato.

   1. (Condizionale) Se non hai aggiunto in precedenza un account Azure RBAC:

      1. Seleziona [!UICONTROL **Aggiungi account**], quindi specifica le seguenti informazioni:

         | Campo | Funzione |
         |---------|----------|
         | [!UICONTROL **Nome account**] | Nome dell&#39;account RBAC di Azure. Questo nome viene visualizzato nel [!UICONTROL **Seleziona account**] e può essere qualsiasi nome scelto. |
         | [!UICONTROL **Descrizione account**] | Descrizione dell&#39;account Azure RBAC. Questa descrizione viene visualizzata nel [!UICONTROL **Seleziona account**] e può essere qualsiasi nome scelto. |
         | [!UICONTROL **ID applicazione**] | Copia questo ID dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nel **Panoramica** nell&#39;applicazione. Per ulteriori informazioni, vedere [Documentazione di Microsoft Azure su come registrare un’applicazione con la piattaforma Microsoft Identity](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **ID tenant**] | Copia questo ID dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nel **Panoramica** nell&#39;applicazione. Per ulteriori informazioni, vedere [Documentazione di Microsoft Azure su come registrare un’applicazione con la piattaforma Microsoft Identity](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **Segreto**] | Copia il segreto dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nel **Certificati e segreti** nell&#39;applicazione. Per ulteriori informazioni, vedere [Documentazione di Microsoft Azure su come registrare un’applicazione con la piattaforma Microsoft Identity](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

         {style="table-layout:auto"}

      1. Seleziona [!UICONTROL **Aggiungi posizione**], quindi specifica le seguenti informazioni:

         | Campo | Funzione |
         |---------|----------|
         | [!UICONTROL **Nome**] | Un nome per la posizione. Questo nome viene visualizzato nel [!UICONTROL **Seleziona posizione**] e può essere qualsiasi nome scelto. |
         | [!UICONTROL **Descrizione**] | Una descrizione della posizione. Questa descrizione viene visualizzata nel [!UICONTROL **Seleziona posizione**] e può essere qualsiasi nome scelto. |
         | [!UICONTROL **Account**] | Account di archiviazione Azure. |
         | [!UICONTROL **Contenitore**] | Il contenitore all’interno dell’account specificato nel punto in cui desideri inviare i dati di Adobe Analytics. Accertati di concedere le autorizzazioni per caricare i file nell’applicazione Azure creata in precedenza. |
         | [!UICONTROL **Prefisso**] | La cartella all’interno del contenitore in cui desideri inserire i dati. Specifica il nome di una cartella, quindi aggiungi una barra rovesciata dopo il nome per creare la cartella. Ad esempio, `folder_name/` |

         {style="table-layout:auto"}

      1. Seleziona [!UICONTROL **Crea**] > [!UICONTROL **Salva**].

         La destinazione è ora configurata per inviare i dati al percorso RBAC di Azure specificato.

+++

   +++SAS di Azure

   È possibile inviare feed direttamente a un contenitore di Azure utilizzando l’autenticazione SAS. Questo tipo di destinazione richiede un nome bucket, un ID applicazione, un ID tenant, un URI di insieme di credenziali delle chiavi, un nome segreto di insieme di credenziali delle chiavi e una chiave segreta.

   Per configurare un bucket SAS di Azure come destinazione per un feed di dati:

   1. Se non lo hai già fatto, crea un’applicazione Azure che Adobe Analytics può utilizzare per l’autenticazione.

      Per informazioni, fare riferimento a [Documentazione di Microsoft Azure sulla creazione di un&#39;applicazione Azure Active Directory](https://learn.microsoft.com/en-us/azure/active-directory/develop/howto-create-service-principal-portal).

   1. In Admin Console di Adobe Analytics, nella sezione [!UICONTROL **Destinazione**] sezione, seleziona [!UICONTROL **SAS di Azure**].

      ![Destinazione SAS di Azure](assets/datafeed-destination-azuresas.png)

   1. Seleziona [!UICONTROL **Seleziona posizione**].

      Viene visualizzata la pagina Percorsi di esportazione SAS di Azure.

   1. (Condizionale) Se in precedenza è stato aggiunto un account e una posizione SAS di Azure:

      1. Seleziona l’account da [!UICONTROL **Seleziona account**] menu a discesa.

      1. Seleziona la posizione da [!UICONTROL **Seleziona posizione**] menu a discesa.

      1. Seleziona [!UICONTROL **Salva**] > [!UICONTROL **Salva**].

         La destinazione è ora configurata per inviare i dati al percorso SAS di Azure specificato.

   1. (Condizionale) Se non è stato aggiunto in precedenza un account SAS di Azure:

      1. Seleziona [!UICONTROL **Aggiungi account**], quindi specifica le seguenti informazioni:

         | Campo | Funzione |
         |---------|----------|
         | [!UICONTROL **Nome account**] | Nome dell&#39;account SAS di Azure. Questo nome viene visualizzato nel [!UICONTROL **Seleziona account**] e può essere qualsiasi nome scelto. |
         | [!UICONTROL **Destinazione account**] | Descrizione dell&#39;account SAS di Azure. Questa descrizione viene visualizzata nel [!UICONTROL **Seleziona account**] e può essere qualsiasi nome scelto. |
         | [!UICONTROL **ID applicazione**] | Copia questo ID dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nel **Panoramica** nell&#39;applicazione. Per ulteriori informazioni, vedere [Documentazione di Microsoft Azure su come registrare un’applicazione con la piattaforma Microsoft Identity](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **ID tenant**] | Copia questo ID dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nel **Panoramica** nell&#39;applicazione. Per ulteriori informazioni, vedere [Documentazione di Microsoft Azure su come registrare un’applicazione con la piattaforma Microsoft Identity](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **URI insieme di credenziali delle chiavi**] | <p>Percorso del token SAS nell&#39;insieme di credenziali delle chiavi di Azure.  Per configurare Azure SAS, è necessario memorizzare un token SAS come segreto utilizzando Azure Key Vault. Per informazioni, vedere [Documentazione di Microsoft Azure su come impostare e recuperare un segreto dall&#39;insieme di credenziali delle chiavi di Azure](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>Dopo la creazione dell’URI dell’insieme di credenziali delle chiavi, aggiungi un criterio di accesso nell’insieme di credenziali delle chiavi per concedere l’autorizzazione all’applicazione Azure creata. Per informazioni, vedere [Documentazione di Microsoft Azure su come assegnare un criterio di accesso all’insieme di credenziali delle chiavi](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
         | [!UICONTROL **Nome segreto archivio chiavi**] | Nome segreto creato quando si aggiunge il segreto all&#39;insieme di credenziali delle chiavi di Azure. In Microsoft Azure, queste informazioni si trovano nell&#39;insieme di credenziali delle chiavi creato, nel **Key Vault** pagine delle impostazioni. Per informazioni, vedere [Documentazione di Microsoft Azure su come impostare e recuperare un segreto dall&#39;insieme di credenziali delle chiavi di Azure](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
         | [!UICONTROL **Segreto**] | Copia il segreto dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nel **Certificati e segreti** nell&#39;applicazione. Per ulteriori informazioni, vedere [Documentazione di Microsoft Azure su come registrare un’applicazione con la piattaforma Microsoft Identity](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

         {style="table-layout:auto"}

      1. Seleziona [!UICONTROL **Aggiungi posizione**], quindi specifica le seguenti informazioni:

         | Campo | Funzione |
         |---------|----------|
         | [!UICONTROL **Nome**] | Un nome per la posizione. Questo nome viene visualizzato nel [!UICONTROL **Seleziona posizione**] e può essere qualsiasi nome scelto. |
         | [!UICONTROL **Descrizione**] | Una descrizione della posizione. Questa descrizione viene visualizzata nel [!UICONTROL **Seleziona posizione**] e può essere qualsiasi nome scelto. |
         | [!UICONTROL **Contenitore**] | Il contenitore all’interno dell’account specificato nel punto in cui desideri inviare i dati di Adobe Analytics. |
         | [!UICONTROL **Prefisso**] | La cartella all’interno del contenitore in cui desideri inserire i dati. Specifica il nome di una cartella, quindi aggiungi una barra rovesciata dopo il nome per creare la cartella. Ad esempio, `folder_name/` |

         {style="table-layout:auto"}

      1. Seleziona [!UICONTROL **Crea**] > [!UICONTROL **Salva**].

         La destinazione è ora configurata per inviare i dati al percorso SAS di Azure specificato.

+++

   +++Piattaforma Google Cloud

   Puoi inviare feed direttamente ai bucket di Google Cloud Platform (GCP). Questo tipo di destinazione richiede solo il nome dell’account GCP e la posizione (bucket).

   Adobe Analytics utilizza l’autenticazione tra account diversi per caricare i file da Adobe Analytics nella posizione specificata nell’istanza GCP.

   Per configurare un bucket GCP come destinazione per un feed di dati:

   1. In Admin Console di Adobe Analytics, nella sezione [!UICONTROL **Destinazione**] sezione, seleziona [!UICONTROL **Piattaforma Google Cloud**].

      ![Destinazione piattaforma Google Cloud](assets/datafeed-destination-gcp.png)

   1. Seleziona [!UICONTROL **Seleziona posizione**].

      Viene visualizzata la pagina Posizioni di esportazione GCP.

   1. (Condizionale) Se in precedenza hai aggiunto un account GCP e una posizione:

      1. Seleziona l’account da [!UICONTROL **Seleziona account**] menu a discesa.

      1. Seleziona la posizione da [!UICONTROL **Seleziona posizione**] menu a discesa.

      1. Seleziona [!UICONTROL **Salva**] > [!UICONTROL **Salva**].

         La destinazione è ora configurata per inviare dati alla posizione GCP specificata.

   1. (Condizionale) Se non hai aggiunto in precedenza un account GCP:

      1. Seleziona [!UICONTROL **Aggiungi account**], quindi specifica le seguenti informazioni:

         | Campo | Funzione |
         |---------|----------|
         | [!UICONTROL **Nome account**] | Un nome per l’account. Può essere qualsiasi nome scelto. |
         | [!UICONTROL **Descrizione account**] | Descrizione dell&#39;account. |
         | [!UICONTROL **ID Progetto**] | ID progetto Google Cloud. Consulta la [Documentazione di Google Cloud sull’ottenimento di un ID progetto](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |

         {style="table-layout:auto"}

         1. Seleziona [!UICONTROL **Aggiungi posizione**], quindi specifica le seguenti informazioni:

         | Campo | Funzione |
         |---------|----------|
         | [!UICONTROL **Entità**] | L’entità è fornita dall’Adobe. È necessario concedere l&#39;autorizzazione per la ricezione di feed a questa entità principale. |
         | [!UICONTROL **Nome**] | Un nome per l’account. |
         | [!UICONTROL **Descrizione**] | Descrizione dell&#39;account. |
         | [!UICONTROL **Bucket**] | Il bucket all’interno dell’account GCP in cui desideri inviare i dati di Adobe Analytics. Assicurati di aver concesso all’entità fornita da Adobe l’autorizzazione per caricare i file in questo bucket. |
         | [!UICONTROL **Prefisso**] | La cartella all’interno del bucket in cui desideri inserire i dati. Specifica il nome di una cartella, quindi aggiungi una barra rovesciata dopo il nome per creare la cartella. Ad esempio, `folder_name/` |

         {style="table-layout:auto"}

      1. Seleziona [!UICONTROL **Crea**] > [!UICONTROL **Salva**].

         La destinazione è ora configurata per inviare dati alla posizione GCP specificata.

+++

1. In  [!UICONTROL **Definizioni delle colonne dati**] , seleziona l&#39;ultima [!UICONTROL **Tutti Adobe Columns**] nel menu a discesa, quindi completa i campi seguenti:

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **Rimuovi caratteri di escape**] | Durante la raccolta dei dati, alcuni caratteri (ad esempio le nuove righe) possono causare problemi. Selezionare questa casella se si desidera rimuovere questi caratteri dai file di feed. |
   | [!UICONTROL **Formato di compressione**] | Tipo di compressione utilizzata. **Gzip** restituisce i file in `.tar.gz` formato. **Zip** restituisce i file in `.zip` formato. |
   | [!UICONTROL **Tipo di imballaggio**] | Seleziona **Più file** per la maggior parte dei feed di dati. Questa opzione impagina i dati in blocchi non compressi da 2 GB. Se sono selezionati più file e i dati non compressi per la finestra di reporting sono inferiori a 2 GB, viene inviato un file. Selezione **File singolo** produce `hit_data.tsv` file in un unico file, potenzialmente di grandi dimensioni. |
   | [!UICONTROL **Manifesto**] | Indica se Adobe deve fornire o meno un [file manifesto](c-df-contents/datafeeds-contents.md#feed-manifest) alla destinazione quando non vengono raccolti dati per un intervallo di feed. Se si seleziona **File manifesto**, quando non vengono raccolti dati, si riceve un file manifesto simile al seguente:<p>`text`</p><p>`Datafeed-Manifest-Version: 1.0`</p><p>`Lookup-Files: 0`</p><p>`Data-Files: 0`</p><p> `Total-Records: 0`</p> |
   | [!UICONTROL **Modelli di colonna**] | Durante la creazione di molti feed di dati, l’Adobe consiglia di creare un modello di colonna. Quando si seleziona un modello di colonna, le colonne specificate vengono incluse automaticamente nel modello. Per impostazione predefinita, in Adobe sono inoltre disponibili diversi modelli. |
   | [!UICONTROL **Colonne disponibili**] | Tutte le colonne di dati disponibili in Adobe Analytics. Clic [!UICONTROL Add all] per includere tutte le colonne in un feed di dati. |
   | [!UICONTROL **Colonne incluse**] | Colonne da includere in un feed di dati. Clic [!UICONTROL Remove all] per rimuovere tutte le colonne da un feed di dati. |
   | [!UICONTROL **Scarica come CSV**] | Scarica un file CSV contenente tutte le colonne incluse. |

1. Seleziona [!UICONTROL **Salva**] in alto a destra.

   L’elaborazione dei dati storici inizia immediatamente. Al termine dell’elaborazione dei dati per un giorno, il file viene inviato alla destinazione configurata.

   Per informazioni su come accedere al feed di dati e per comprenderne meglio il contenuto, consulta [Contenuti feed dati: panoramica](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md).

## Destinazioni legacy

>[!IMPORTANT]
>
>Le destinazioni descritte in questa sezione sono legacy e non sono consigliate. Al contrario, utilizza una delle seguenti destinazioni durante la creazione di un feed di dati: Amazon S3, Google Cloud Platform, Azure RBAC o Azure SAS. Consulta [Creare e configurare un feed dati](#create-and-configure-a-data-feed) per informazioni dettagliate su ciascuna di queste destinazioni consigliate.


Le informazioni seguenti forniscono informazioni di configurazione per ciascuna destinazione legacy:

### FTP

I dati del feed dati possono essere inviati a un Adobe o a una posizione FTP ospitata dal cliente. Richiede un host FTP, un nome utente e una password. Utilizza il campo percorso per inserire i file di feed in una cartella. Le cartelle devono già esistere. I feed generano un errore se il percorso specificato non esiste.

Per completare i campi disponibili, utilizza le seguenti informazioni:

* [!UICONTROL **Host**]: immetti l’URL di destinazione FTP desiderato. Esempio: `ftp://ftp.omniture.com`.
* [!UICONTROL **Percorso**]: può essere lasciato vuoto
* [!UICONTROL **Nome utente**]: immetti il nome utente per accedere al sito FTP.
* [!UICONTROL **Password e conferma password**]: immetti la password per accedere al sito FTP.

### SFTP

È disponibile il supporto SFTP per i feed di dati. Richiede un host SFTP, un nome utente e il sito di destinazione per contenere una chiave pubblica RSA o DSA valida. Puoi scaricare la chiave pubblica adatta al momento della creazione del feed.

### S3

Puoi inviare feed direttamente ai bucket di Amazon S3. Questo tipo di destinazione richiede un nome bucket, un ID chiave di accesso e una chiave segreta. Consulta [Requisiti di denominazione del bucket Amazon S3](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-s3-bucket-naming-requirements.html) nella documentazione di Amazon S3 per ulteriori informazioni.

L’utente fornito per il caricamento dei feed di dati deve disporre dei seguenti elementi [autorizzazioni](https://docs.aws.amazon.com/AmazonS3/latest/API/API_Operations_Amazon_Simple_Storage_Service.html):

* s3:GetObject
* s3:PutObject
* s3:PutObjectAcl

  >[!NOTE]
  >
  >Per ogni caricamento in un bucket Amazon S3, [!DNL Analytics] aggiunge il proprietario del bucket all’ACL BucketOwnerFullControl, indipendentemente dal fatto che il bucket disponga di un criterio che lo richieda. Per ulteriori informazioni, consulta la sezione &quot;[Qual è l’impostazione BucketOwnerFullControl per i feed di dati Amazon S3?](df-faq.md#BucketOwnerFullControl)&quot;

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
>L&#39;area cn-north-1 non è supportata.

### BLOB di Azure

I feed di dati supportano le destinazioni BLOB di Azure. Richiede un contenitore, un account e una chiave. Amazon crittografa automaticamente i dati inattivi. Quando scarichi i dati, questi vengono decrittografati automaticamente. Consulta [Creare un account di archiviazione](https://docs.microsoft.com/en-us/azure/storage/common/storage-quickstart-create-account?tabs=azure-portal#view-and-copy-storage-access-keys) nei documenti di Microsoft Azure per ulteriori informazioni.

>[!NOTE]
>
>È necessario implementare un processo personalizzato per gestire lo spazio su disco nella destinazione del feed. Adobe non elimina dati dal server.
