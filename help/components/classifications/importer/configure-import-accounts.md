---
description: Configura l’account di importazione cloud e il percorso in cui è possibile caricare i dati di classificazione
keywords: Analysis Workspace
title: Configurare i percorsi di importazione cloud
feature: Classifications
source-git-commit: 8d6ee33e867da274334c8adc557105af4942c894
workflow-type: tm+mt
source-wordcount: '1354'
ht-degree: 3%

---

# Configurare i percorsi di importazione cloud

<!-- This page is almost duplicated with the "Configure cloud export locations" article in CJA. Differences are that Snowflake isn't supported here and there is a Suffix field for each account type. -->

Prima di poter importare i dati di classificazione Adobe Analytics da una destinazione cloud, devi aggiungere e configurare il percorso in cui desideri raccogliere i dati di classificazione.

Questo processo consiste nell’aggiungere e configurare l’account (ad esempio ARN per il ruolo di Amazon S3, Google Cloud Platform e così via) e la posizione all’interno dell’account (ad esempio una cartella all’interno dell’account).

## Aggiungi un account

Devi configurare Adobe Analytics con le informazioni necessarie per accedere al tuo account di destinazione cloud.

1. In Adobe Analytics, seleziona [!UICONTROL **Componenti**] > [!UICONTROL **Posizioni**].
1. Il giorno [!UICONTROL Locations] , seleziona la [!UICONTROL **Credenziali posizione**] scheda.
1. Seleziona [!UICONTROL **Aggiungi account**]. <!-- add screenshot? -->

   Viene visualizzata la finestra di dialogo Aggiungi account.
1. Specifica le seguenti informazioni: |Campo | Funzione | ---------- --------- | [!UICONTROL **Nome account località**] | Nome del conto di ubicazione. Questo nome viene visualizzato durante la creazione di una posizione | | [!UICONTROL **Descrizione del conto di ubicazione**] | Fornisci una breve descrizione del conto per distinguerlo da altri conti dello stesso tipo. | | [!UICONTROL **Tipo di account**] | Seleziona il tipo di account cloud. È consigliabile disporre di un singolo account per ogni tipo di account, con più posizioni in base alle esigenze all’interno dell’account. |
1. In [!UICONTROL **Proprietà account**] , specificare informazioni specifiche per il tipo di account selezionato.

   Per le istruzioni di configurazione, espandi la sezione seguente che corrisponde a [!UICONTROL **Tipo di account**] che hai selezionato.

   +++ARN per ruolo Amazon S3

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
   | [!UICONTROL **Segreto account località**] | Copia il segreto dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nel **Certificati e segreti** nell&#39;applicazione. Per ulteriori informazioni, vedere [Documentazione di Microsoft Azure su come registrare un’applicazione con la piattaforma Microsoft Identity](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

   {style="table-layout:auto"}

+++

   +++RBAC di Azure

   Specificare le informazioni seguenti per configurare un account RBAC di Azure:

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **ID applicazione**] | Copia questo ID dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nel **Panoramica** nell&#39;applicazione. Per ulteriori informazioni, vedere [Documentazione di Microsoft Azure su come registrare un’applicazione con la piattaforma Microsoft Identity](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **ID tenant**] | Copia questo ID dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nel **Panoramica** nell&#39;applicazione. Per ulteriori informazioni, vedere [Documentazione di Microsoft Azure su come registrare un’applicazione con la piattaforma Microsoft Identity](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **Segreto account località**] | Copia il segreto dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nel **Certificati e segreti** nell&#39;applicazione. Per ulteriori informazioni, vedere [Documentazione di Microsoft Azure su come registrare un’applicazione con la piattaforma Microsoft Identity](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

   {style="table-layout:auto"}

+++

1. Seleziona [!UICONTROL **Salva**].

1. Continua con [Aggiungi una posizione](#add-a-location).

## Aggiungi una posizione

1. È necessario aggiungere un account prima di poter aggiungere una posizione. [Aggiungi un account](#add-an-account) se non lo hai già fatto.
1. In Adobe Analytics, seleziona [!UICONTROL **Componenti**] > [!UICONTROL **Posizioni**].
1. Il giorno [!UICONTROL Locations] , seleziona la [!UICONTROL **Posizioni**] scheda.
1. Seleziona [!UICONTROL **Aggiungi posizione**]. <!-- add screenshot? -->

   Viene visualizzata la finestra di dialogo Posizione.
1. Specifica le seguenti informazioni: |Campo | Funzione | ---------- --------- | [!UICONTROL **Nome**] | Nome della posizione.  | | [!UICONTROL **Descrizione**] | Fornisci una breve descrizione del conto per distinguerlo da altri conti dello stesso tipo. | | [!UICONTROL **Account località**] | Seleziona l&#39;account località creato in [Aggiungi un account](#add-an-account). |

1. In [!UICONTROL **Proprietà posizione**] , specificare informazioni specifiche sul tipo di account dell&#39;account di posizione.

   Per le istruzioni di configurazione, espandi la sezione seguente che corrisponde al tipo di account selezionato in [!UICONTROL **Account ubicazione**] campo.

   +++ARN per ruolo Amazon S3

   Specifica le seguenti informazioni per configurare una posizione ARN per il ruolo Amazon S3:

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
   | [!UICONTROL **Nome del bucket**] | Il bucket all’interno dell’account GCP in cui desideri inviare i dati di Adobe Analytics. Assicurati di aver concesso all’entità fornita da Adobe l’autorizzazione per caricare i file in questo bucket. |
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