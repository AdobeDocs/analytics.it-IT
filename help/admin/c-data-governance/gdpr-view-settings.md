---
description: La finestra di dialogo Data Governance (Governance dei dati) negli strumenti dell’amministratore offre una panoramica delle suite di rapporti configurate per la governance dei dati, indica se sono state mappate in un’organizzazione Experience Cloud e se per essa sono stati impostati i criteri di conservazione dei dati.
title: Visualizzare/gestire le impostazioni di governance dei dati della suite di rapporti
feature: Data Governance
exl-id: 87b0be42-1098-4e72-8eb8-0c1bb56791f8
source-git-commit: 196e7672026a284591c0dba2336cb11fc3661c72
workflow-type: ht
source-wordcount: '500'
ht-degree: 100%

---

# Visualizzare/gestire le impostazioni di governance dei dati della suite di rapporti

La finestra di dialogo Data Governance (Governance dei dati) negli strumenti dell’amministratore offre una panoramica delle suite di rapporti configurate per la governance dei dati, indica se sono state mappate in un’organizzazione Experience Cloud e se per essa sono stati impostati i criteri di conservazione dei dati.

1. Accedi ad Adobe Experience Cloud.
1. Passa a  **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Data Governance]**.

>[!NOTE]
>
>Se questa voce di menu non viene visualizzata, è necessario aggiungerla a un [profilo di prodotto in Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/product-profile.html?lang=it) con autorizzazioni per questa funzionalità.

1. Visualizza tutte le suite di rapporti che fanno parte della società di accesso:

   ![](assets/privacy_setup_an.png)

| Impostazione | Descrizione |
| --- | --- |
| **[!UICONTROL Report Suites]** | La prima riga elenca il nome descrittivo della suite di rapporti. La seconda riga contiene il nome interno della suite di rapporti. Se ti è consentito impostare le etichette per una suite di rapporti, la prima riga sarà un collegamento cliccabile che ti porta alla pagina di etichettatura. |
| **[!UICONTROL Organization Mapping]** | <ul><li>Mappata: questa suite di rapporti è già stata mappata nella stessa organizzazione Experience Cloud della società di accesso di Analytics in cui hai effettuato l’accesso. È possibile etichettare solo le suite di rapporti che hanno questa impostazione.</li><li>Mapped to Another Organization (Mappata in un’altra organizzazione): un’altra organizzazione ha già mappato questa suite di rapporti al proprio interno.</li></ul> |
| **[!UICONTROL Data Retention Policy]** | Per implementare la Privacy dei dati in Analytics è necessario aver impostato i criteri di conservazione dei dati. Questa impostazione consente di vedere se:<ul><li>sono stati impostati i criteri di conservazione dei dati per questa suite di rapporti; e</li><li>per quanto tempo i dati vengono conservati da Adobe prima di essere eliminati. Il periodo di conservazione dei dati predefinito è di 25 mesi.</li></ul>**Nota**: in Adobe Analytics non è possibile ricevere assistenza per elaborare le richieste per l’API Privacy dei dati, ovvero per elaborare le richieste di accesso o di cancellazione ricevute dagli utenti finali, se non è stato impostato il periodo di conservazione dei dati. Contatta il tuo Customer Success Manager per impostare il periodo di conservazione dei dati. |
| **[!UICONTROL Groups]** | La funzionalità di raggruppamento al momento non è implementata. |
| Barra laterale a sinistra | Fai clic sull’icona dell’imbuto per aprire o chiudere la barra laterale. La sezione [!UICONTROL Organization Mapping] mostra il numero di suite di rapporti che rientrano in ognuna delle categorie descritte. La sezione [!UICONTROL Data Retention Policy] mostra tutti i criteri univoci di conservazione dei dati validi per l’organizzazione e il numero di suite di rapporti assegnate a quei criteri. |
| **[!UICONTROL Export to CSV]** | Se indichi il segno di spunta accanto a una o più suite di rapporti, viene visualizzata l’opzione Esporta in CSV. Questa opzione ti consente di scaricare un file CSV contenente tutte le definizioni delle etichette attuali per tutte le variabili per tutte le suite di rapporti selezionate. Consigliamo al team legale di esaminare le scelte di etichettatura; questa opzione facilita la revisione. Invece di dover eseguire la revisione quando sei autenticato nell’interfaccia utente della governance dei dati, puoi condividere il file .CSV. |

{style=&quot;table-layout:auto&quot;}
