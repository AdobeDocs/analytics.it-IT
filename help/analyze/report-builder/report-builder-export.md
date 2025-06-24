---
title: Esportare rapporti da Report Builder
description: Descrive come esportare dati da Report Builder a destinazioni sicure
role: User, Admin
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 5829482b-3a5e-416b-9c82-404face30b29
source-git-commit: ecb08c3d9dfe7394ecff5415c08be7a38b0cba6a
workflow-type: tm+mt
source-wordcount: '1212'
ht-degree: 30%

---

# Pianificare le cartelle di lavoro esportandole in destinazioni cloud

Puoi esportare le cartelle di lavoro di Adobe Analytics da Report Builder a provider cloud come Google, Azure e Amazon.

In alternativa, è possibile condividere le cartelle di lavoro con altri utenti tramite posta elettronica, come descritto in [Pianificare le cartelle di lavoro per la condivisione tramite posta elettronica](/help/analyze/report-builder/schedule-reportbuilder.md).

[I vantaggi dell&#39;esportazione di report da Report Builder al cloud](#advantages-of-exporting-to-the-cloud) includono la possibilità di utilizzare report in strumenti di terze parti o di combinarli con dati esterni.

Prima di esportare le cartelle di lavoro da Report Builder in una destinazione cloud, assicurati che i blocchi di dati, l&#39;ambiente e le autorizzazioni soddisfino i [requisiti di esportazione](#export-requirements).

## Comprendere il processo di esportazione

Per esportare le cartelle di lavoro da Report Builder nel cloud, attenersi alla procedura descritta di seguito.

1. [Configurare un account cloud](/help/components/locations/configure-import-accounts.md)

1. [Configurare una posizione sull’account](/help/components/locations/configure-import-locations.md)

1. [Esportare un rapporto da Report Builder](#export-a-report-from-report-builder)

## Esportare un rapporto da Report Builder

>[!NOTE]
>
>Prima di esportare i dati come descritto in questa sezione, ulteriori informazioni sul [processo di esportazione](#understand-the-export-process) nella sezione precedente.

Per esportare rapporti da Report Builder:

1. Se non lo hai già fatto, configura un account e una posizione di esportazione, come descritto in [Configurare gli account di esportazione cloud](/help/components/locations/configure-import-accounts.md).

1. Nel foglio di calcolo di Excel contenente i dati da esportare, aprire il pannello destro **[!UICONTROL Adobe Report Builder]**.

1. Seleziona [!UICONTROL **Pianificazione**].

<!-- add screenshot -->

1. Nella scheda **[!UICONTROL Workbooks]**, seleziona l&#39;icona più per creare una nuova pianificazione

   ![Scheda Pianificazioni di Report Builder](assets/report-builder-schedule-cloud.png)

   Oppure

   Per esportare la cartella di lavoro in base a una pianificazione già creata, selezionare la pianificazione dall&#39;elenco delle pianificazioni, quindi selezionare **[!UICONTROL Send on schedule]**.

1. Nel pannello di destra [!UICONTROL **Adobe Report Builder**], specifica le seguenti informazioni per continuare a creare una nuova pianificazione:

   | Nome campo: | Funzione |
   |---------|----------|
   | **[!UICONTROL File]** | Visualizza il file della cartella di lavoro attualmente selezionato per l&#39;esportazione. Selezionare l&#39;icona della cartella di lavoro ![TabellaSeleziona](/help/assets/icons/TableSelect.svg) accanto al nome del file per scegliere la cartella di lavoro corrente, se non è già selezionata. |
   | **[!UICONTROL Filename]** <!--should be File name --> | Consente di modificare il nome del file prima di esportare la cartella di lavoro.<p>Il nome predefinito del file della cartella di lavoro è il nome della cartella di lavoro</p> |
   | **[!UICONTROL File type]** | Scegliere il tipo di file per il file esportato. È possibile scegliere Excel, PDF o CSV.<p>Quando selezioni **[!UICONTROL CSV]**, tieni presente che la cartella di lavoro pianificata viene inviata come allegato ZIP. Alcune amministrazioni e-mail aziendali potrebbero bloccare le e-mail con allegati ZIP. Di conseguenza viene visualizzato un avviso.</p> |
   | **[!UICONTROL Append time stamp to file name]** | Selezionare questa opzione per includere una marca temporale dell&#39;esportazione nel nome del file esportato. |
   | **[!UICONTROL Filename preview]** <!--should be File name preview --> | Mostra un&#39;anteprima di come verrà visualizzato il nome del file dopo l&#39;esportazione. |
   | **[!UICONTROL Password protect the workbook]** | Specificare una password per proteggere il file esportato in modo che solo gli utenti con la password possano accedervi. <p>Le password devono avere almeno 8 caratteri e contenere almeno 1 numero e 1 carattere speciale (ad esempio `!`,`@`,`#` e `$`).</p> |
   | **[!UICONTROL Email]** | Selezionare questa opzione per inviare il file a un indirizzo di posta elettronica specifico. Per ulteriori informazioni su questa opzione, vedere [Pianificare le cartelle di lavoro condividendo tramite e-mail](/help/analyze/report-builder/schedule-reportbuilder.md). |
   | **[!UICONTROL Other deliveries]** | Selezionare questa opzione per inviare il file a un account cloud, quindi utilizzare i menu a discesa **[!UICONTROL Account]** e **[!UICONTROL Location]** descritti di seguito per selezionare l&#39;account e il percorso. |
   | **[!UICONTROL Account]** | Seleziona l’account di esportazione cloud in cui desideri inviare i dati. <p>In alternativa, se non hai già configurato un account cloud da utilizzare, puoi configurare un nuovo account:<ol><li>Seleziona [!UICONTROL **Aggiungi account**], quindi specifica le seguenti informazioni:<ul><li>[!UICONTROL **Nome account di posizione**]: specifica un nome per l’account di posizione. Questo nome viene visualizzato durante la creazione di una posizione </li><li>[!UICONTROL **Descrizione account di posizione**]: fornisci una breve descrizione dell’account per distinguerlo da altri account dello stesso tipo.</li><li>**[!UICONTROL Make account available to all users in your organization]**: selezionare questa opzione per consentire ad altri utenti dell&#39;organizzazione di utilizzare l&#39;account. Quando condividi gli account, tieni presente quanto segue:<ul><li>Gli account condivisi non possono essere non condivisi.</li><li>Gli account condivisi possono essere modificati solo dal proprietario dell&#39;account.</li><li>Chiunque può creare una posizione per l&#39;account condiviso.</li></ul></li><li>[!UICONTROL **Tipo di account**]: selezionare il tipo di account cloud in cui si desidera esportare i dati. I tipi di account disponibili sono Amazon S3 Role ARN, Google Cloud Platform, Azure SAS e Azure RBAC.</li></ul><li>Per completare la configurazione dell&#39;account, continuare con il passaggio 6 in [Configurare gli account di importazione ed esportazione cloud](/help/components/locations/configure-import-accounts.md), quindi espandere la sezione corrispondente al [!UICONTROL **tipo di account**] selezionato. <p>Sono disponibili i seguenti tipi di account:</p><ul><li>Amazon S3 con ruolo ARN</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li></ul></ol> |
   | **[!UICONTROL Location]** | Seleziona la posizione dell’account in cui desideri inviare i dati di esportazione.<p>Oppure, se non hai già configurato la posizione da utilizzare sull’account selezionato, puoi configurarne una nuova:<ol><li>Seleziona [!UICONTROL **Aggiungi posizione**], quindi specifica le seguenti informazioni: <ul><li>[!UICONTROL **Nome**]: il nome della posizione.</li><li>[!UICONTROL **Descrizione**]: fornisci una breve descrizione della posizione per distinguerla da altre posizioni nell’account.</li><li>**[!UICONTROL Make location available to all users in your organization]**: selezionare questa opzione per consentire ad altri utenti dell&#39;organizzazione di utilizzare il percorso. Quando condividi gli account, tieni presente quanto segue:<ul><li>Le posizioni condivise non possono essere annullate.</li><li>Le posizioni condivise possono essere modificate solo dal proprietario dell&#39;account.</li><li>Le posizioni possono essere condivise solo se è condiviso anche l’account a cui è associata la posizione.</li></ul></li><li>[!UICONTROL **Account di posizione**]: seleziona l’account in cui desideri creare la posizione.</li></ul><li>Per completare la configurazione della posizione, continua con il collegamento seguente corrispondente al tipo di account selezionato nel campo [!UICONTROL **Account di posizione**]:<ul><li>[Amazon S3 Role ARN](/help/components/locations/configure-import-locations.md#amazon-s3-role-arn)</li><li>[Google Cloud Platform](/help/components/locations/configure-import-locations.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/locations/configure-import-locations.md#azure-sas)</li><li>[Azure RBAC](/help/components/locations/configure-import-locations.md#azure-rbac)</li></ul> |
   | **[!UICONTROL Show scheduling options]** | Selezionare questa opzione per visualizzare ulteriori opzioni per la programmazione dell&#39;esportazione. Lascia deselezionata questa opzione se desideri inviare l’esportazione una sola volta. Se questa opzione è deselezionata, l’esportazione viene avviata immediatamente. |
   | **[!UICONTROL Starting on]** | Giorno e ora in cui dovrebbe iniziare l’esportazione pianificata. <p>Questa opzione è disponibile solo quando si sceglie una frequenza di esportazione pianificata.</p> |
   | **[!UICONTROL Ending on]** | Giorno e ora di scadenza dell’esportazione pianificata. L’esportazione pianificata non viene più eseguita dopo la data e l’ora impostate. <p>Questa opzione è disponibile solo quando si sceglie una frequenza di esportazione pianificata.</p> |
   | **[!UICONTROL Frequency]** | Puoi impostare la frequenza in modo che sia ogni ora, giorno, settimana, mese o anno in un giorno specifico. Ad esempio, puoi impostare una pianificazione per inviare la cartella di lavoro la prima domenica notte del mese in modo che i destinatari abbiano l’e-mail nella loro casella in entrata prima cosa il lunedì mattina. |

   {style="table-layout:auto"}

1. Selezionare [!UICONTROL **Invia secondo programma**] per esportare la cartella di lavoro.

   I dati vengono inviati all’account cloud specificato alla frequenza specificata.

   Nella parte inferiore dell&#39;hub Report Builder viene visualizzato un avviso popup di conferma e la cartella di lavoro pianificata è elencata nella scheda Cartelle di lavoro.

## Vantaggi dell’esportazione nel cloud

L’esportazione dei dati di Adobe Analytics nel cloud consente di:

* Esporta in una posizione condivisa, ad esempio Google Cloud Platform, Microsoft Azure e Amazon S3.

* Memorizzare grandi quantità di dati storici.

  Questo tipo di dati può essere utilizzato per rilevare le tendenze a lungo termine al fine di acquisire una business intelligence e, in ultima analisi, per giungere a un processo decisionale migliore.

* Includi le metriche calcolate nei dati Adobe Analytics esportati.

* Strutturare l’output dei dati come valori concatenati.

* Esporta una tantum o in base a una pianificazione.

* Esporta file in formato Excel, PDF o CSV.

* Esporta blocchi di dati che includono più dimensioni.

## Requisiti per l’esportazione {#export-requirements}

### Requisiti minimi

Assicurati che i blocchi di dati, l’ambiente e le autorizzazioni soddisfino i seguenti requisiti:

* **Blocchi di dati:** tutti i blocchi di dati devono includere almeno un componente in una colonna, riga o valore.

* **Ambiente:** Assicurati che gli [indirizzi IP](/help/technotes/ip-addresses.md) e i [domini](/help/technotes/domains.md) utilizzati da Adobe Analytics siano consentiti tramite il firewall dell&#39;organizzazione.


<!--
## Manage exports

After data is exported from Analysis Workspace, you can edit, re-export, duplicate, tag, or delete existing exports, as described in [Manage exports](/help/components/exports/manage-exports.md). 

-->

## Gestire le cartelle di lavoro pianificate

Per informazioni sulla gestione delle cartelle di lavoro già pianificate, vedere [Gestione delle cartelle di lavoro pianificate](/help/analyze/report-builder/manage-schedules-reportbuilder.md).
