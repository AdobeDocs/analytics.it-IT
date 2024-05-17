---
title: Come impostare un account Advertising in Advertising Analytics
description: Questo articolo spiega come creare nuovi account pubblicitari e mappare più account su più suite di rapporti.
feature: Advertising Analytics
exl-id: f593c714-e85f-4000-85b2-6294cad81e25
source-git-commit: a34dfc63c47b6fe4b91b2b67ea21cdddafb0bfd0
workflow-type: tm+mt
source-wordcount: '763'
ht-degree: 4%

---

# Configurare un account Advertising

Gli amministratori di Adobe Analytics possono creare nuovi account pubblicitari e mappare più account su più suite di rapporti (1 : 1, 1 : Many, Many : Many).

Gli amministratori possono inoltre [concedere l’accesso agli utenti non amministratori](/help/integrate/c-advertising-analytics/overview.md#section_FCC58EB635954A32990D4E67B52B4369) per la creazione di account pubblicitari.

<!--
![](assets/aa_accounts.png)
-->

1. In Adobe Analytics, passa a **[!UICONTROL Admin]** > **[!UICONTROL Advertising Accounts]**.
1. Accettare i termini del Contratto di Licenza con l&#39;utente finale (solo per il primo utilizzo).
1. Seleziona **[!UICONTROL + Add]**.
1. Il [!UICONTROL New search engine setting] viene visualizzata una finestra di dialogo.

   ![](assets/aa-new-se-account.png)

1. Compila il **[!UICONTROL search engine Settings]** segue le seguenti linee guida:

   | Impostazione | Descrizione |
   | --- | --- |
   | **[!UICONTROL Type]** | Sono disponibili 2 opzioni: **[!UICONTROL Google Adwords]** e **[!UICONTROL Bing Ads]**.  Nota: Yahoo Gemini è stata assorbita da Microsoft Bing il 31 marzo 2019. Di conseguenza, l’opzione per l’account per annunci Yahoo Gemini non è più disponibile. |
   | Nome account | Puoi scegliere di impostare questo nome account su un nome che ti soddisfi.  Nome account è il nome descrittivo dell’account visualizzato nell’interfaccia utente. |
   | Token OAuth | **Nota**: OAuth è uno standard aperto per la delega degli accessi, comunemente utilizzato come modo per consentire ai siti web o alle applicazioni di accedere alle informazioni sui siti web ma senza fornire password. Noti che vieni indirizzato a un URL di terze parti (efrontier.com). Adobe utilizza Adobe Media Optimizer per attivare la procedura di autenticazione OAuth per tutti e tre i motori di ricerca. Se si utilizza Internet Explorer 11 (o versioni precedenti), non è possibile recuperare il token Oauth per nessuno dei tre motori di ricerca. Usa altri browser web.<p>Seleziona **[!UICONTROL Retrieve Token]** per avviare il processo di autenticazione OAuth2. Viene richiesto di accedere all&#39;account di ricerca Google/Bing utilizzando le credenziali. A seconda della scelta effettuata, il processo è leggermente diverso: <ul><li>Google Adwords: specifica l&#39;ID account Google</li><li>Microsoft Bing: fornisci l’ID account Bing e l’ID cliente Bing.</li></ul>Fai riferimento a [Individua l&#39;ID account](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-locate-account-id.md) per informazioni su questi ID. Dopo aver effettuato l’accesso, **[!UICONTROL OAuth Token]** visualizzazioni campi **[!UICONTROL Retrieved]**. |

1. In **[!UICONTROL Tracking]** fornisci informazioni su come tracciare i dati utilizzando la tua implementazione di Adobe Analytics. Il tracciamento è un passaggio necessario per integrare correttamente i dati di Adobe Analytics con i dati del motore di ricerca.
Compila il **[!UICONTROL Tracking Settings]** segue le seguenti linee guida:

   | Impostazione | Descrizione |
   | --- | --- |
   | Tipo | <ul><li>**Automatico**: consente al motore di Advertising Cloud di decidere in che modo i parametri di tracciamento vengono aggiunti agli URL di destinazione/modelli di tracciamento di. [!UICONTROL Auto Type Tracking] è l’approccio più semplice, ma potrebbe non risultare nel set di dati meglio integrato.<br>**Importante:** Per configurare un account del motore di ricerca con [!UICONTROL Auto Type Tracking], è tua responsabilità eseguire le azioni seguenti:<ul><li>Il `s_kwcid` Il parametro e il valore vengono aggiunti ai modelli di tracciamento dell’account o agli URL della pagina di destinazione nell’account aggiunto. Il parametro e il valore vengono inseriti alla fine dell’URL. Può essere necessaria un&#39;azione aggiuntiva se il server web richiede un determinato `key=value` alla fine dell’URL. Oppure un aggiornamento per supportare qualsiasi nuova `key=value` è necessario inserire una coppia nell’URL. **Nota**: ulteriori informazioni sull’aggiunta di questo parametro al [Informativa sulla sicurezza dei contenuti](https://experienceleague.adobe.com/en/docs/id-service/using/reference/csp).</li><li>Inoltre, è possibile inserire parole chiave nell’URL di destinazione come parte del `s_kwcid` valore. Se le parole chiave contengono caratteri o simboli speciali, verificare che il server Web in uso supporti tali caratteri. Esempio di caratteri speciali comuni: `+`, utilizzato nelle parole chiave &quot;Broad Match Modified&quot;.</li></ul></li><li>**Manuale**: consente di gestire il modo in cui i parametri di tracciamento vengono aggiunti ai modelli di tracciamento/URL di destinazione del motore di ricerca. [Fai riferimento a questi esempi di tracciamento manuale per ogni motore di ricerca](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manual-vs-automatic-tracking.md).</li></ul> |

1. In **[!UICONTROL Mapping]** sezione, seleziona una o più suite di rapporti da collegare a questo account del motore di ricerca. Devi fornire almeno una suite di rapporti prima di poter salvare l’account Advertising. Puoi mappare più account su più suite di rapporti (1 : 1, 1 : Many, Many : Many). I dati estratti da Adobe Media Optimizer dal motore di ricerca vengono semplicemente copiati in qualsiasi suite di rapporti mappata, pertanto non vi è alcuna suddivisione dei dati.

   >[!IMPORTANT]
   >
   >Sono disponibili per la selezione solo le suite di rapporti mappate su un’organizzazione di Experienci Cloud. Se la suite di rapporti non viene visualizzata nell’elenco, consulta [Risoluzione dei problemi di Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-troubleshooting.md).

   Per **[!UICONTROL Mapping Settings]** segue le seguenti linee guida:

   | Impostazione | Descrizione |
   | --- | --- |
   | Mappatura suite di rapporti | La mappatura suite di rapporti determina la suite di rapporti che viene collegata a questo account del motore di ricerca. In altre parole, determina in quali suite di rapporti vengono inviati i dati del motore di ricerca. |


1. Seleziona **[!UICONTROL Save]**.
1. Una liberatoria visualizza un elenco di avvertenze. Conferma di aver letto e compreso il presente contratto. Seleziona la casella di controllo, quindi seleziona **[!UICONTROL OK]**.

   Ora sei portato sugli account Advertising [Interfaccia utente di gestione](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manage-ad-accounts.md), dove deve essere elencato l’account appena creato.

>[!NOTE]
>
>Devi aspettare almeno 24 ore prima che i dati del motore di ricerca inizino a popolare i rapporti di Analytics.
