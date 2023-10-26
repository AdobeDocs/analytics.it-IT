---
description: Configura l’account di importazione cloud e il percorso in cui è possibile caricare i dati di classificazione
keywords: Analysis Workspace
title: Configurare i percorsi di importazione cloud
feature: Classifications
exl-id: 55179868-6228-44ff-835c-f4a7b38e929b
source-git-commit: c43d7bbdad0ad0265e038ee273c74bec136f1c72
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 5%

---

# Configurare i percorsi di importazione cloud

<!-- This page is almost duplicated with the "Configure cloud export locations" article in CJA. Differences are that Snowflake isn't supported here and there is a Suffix field for each account type. -->

Prima di poter importare i dati di classificazione Adobe Analytics da una destinazione cloud, devi aggiungere e configurare l’account e la posizione all’interno dell’account in cui desideri raccogliere i dati di classificazione.

Questo processo consiste nell’aggiungere e configurare l’account (ad esempio ARN per il ruolo di Amazon S3, Google Cloud Platform e così via) e la posizione all’interno dell’account (ad esempio una cartella all’interno dell’account).

Per configurare un percorso di importazione cloud:

1. È necessario aggiungere un account prima di poter aggiungere una posizione. Se non lo hai già fatto, aggiungi un account come descritto in [Configurare account di importazione cloud](/help/components/locations/configure-import-accounts.md).
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
   | [!UICONTROL **Nome del bucket**] | Il bucket all’interno dell’account Amazon S3 in cui desideri inviare i dati di Adobe Analytics. |
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
