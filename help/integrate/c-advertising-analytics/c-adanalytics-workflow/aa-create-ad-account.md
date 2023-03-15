---
title: Come impostare un account Advertising in Advertising Analytics
description: Consente di creare nuovi account pubblicitari e di mappare più account su più suite di rapporti.
feature: Advertising Analytics
exl-id: f593c714-e85f-4000-85b2-6294cad81e25
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 4%

---

# Configurare un account Advertising

Gli amministratori di Adobe Analytics possono creare nuovi account pubblicitari e mappare più account su più suite di rapporti (1:1, 1:Many, Many:Many).

Gli amministratori possono inoltre [concedere l’accesso agli utenti non amministratori](/help/integrate/c-advertising-analytics/overview.md#section_FCC58EB635954A32990D4E67B52B4369) per la creazione di account pubblicitari.

![](assets/aa_accounts.png)

1. In Adobe Analytics, passa a **[!UICONTROL Admin]** > **[!UICONTROL Advertising Accounts]**.
1. Accettare i termini del Contratto di Licenza con l&#39;utente finale (solo per il primo utilizzo).
1. Fai clic su **[!UICONTROL + Add]** (Usa modello di attribuzione non predefinito).
1. Il [!UICONTROL New Search Engine Account] viene visualizzata una finestra di dialogo:

   ![](assets/aa_new_se_account.png)

1. Compila il **[!UICONTROL Search Engine Settings]** segue le seguenti linee guida:

   | Impostazione | Descrizione |
   | --- | --- |
   | Tipo | Sono disponibili 2 opzioni: Google AdWords e Microsoft Bing Ads.  Nota: Yahoo Gemini è stata assorbita da Microsoft Bing il 31 marzo 2019. Di conseguenza, l’opzione per l’account per annunci Yahoo Gemini non è più disponibile. |
   | Nome account | Puoi scegliere di impostare questo nome account su un nome che ti soddisfi. Questo è il nome descrittivo dell’account che verrà visualizzato nell’interfaccia utente di. |
   | Token OAuth | **Nota:**  OAuth è uno standard aperto per la delega degli accessi, comunemente utilizzato per consentire ai siti web o alle applicazioni di accedere alle loro informazioni su altri siti web, ma senza fornire loro le password. Noterai che verrai indirizzato a un URL di terze parti (efrontier.com). Adobe utilizza efrontier per alimentare il processo di autenticazione OAuth per tutti e tre i motori di ricerca. Se si utilizza Internet Explorer 11 (o versioni precedenti), non sarà possibile recuperare correttamente il token Oauth per nessuno dei tre motori di ricerca. Usa altri browser web.<p>Clic **[!UICONTROL Retrieve Token]** avvia il processo di autenticazione OAuth2. Ti verrà chiesto di accedere al tuo account di ricerca Google/Bing utilizzando le tue credenziali. A seconda del motore di ricerca scelto, il processo è leggermente diverso: <ul><li>Google Adwords: specifica l&#39;ID account Google</li><li>Microsoft Bing: fornisci l’ID account Bing e l’ID cliente Bing.</li></ul>Fai riferimento a [Individua l&#39;ID account](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-locate-account-id.md) per informazioni su questi ID. Dopo aver effettuato l’accesso, **[!UICONTROL OAuth Token]** visualizzazioni campi **[!UICONTROL Retrieved]**. |

1. In **[!UICONTROL Tracking]** , fornisci informazioni sul modo in cui i dati del motore di ricerca vengono tracciati dall’implementazione di Adobe Analytics. Questo passaggio è necessario per integrare correttamente i dati di Adobe Analytics con i dati del motore di ricerca.
Compila il **[!UICONTROL Tracking Settings]** segue le seguenti linee guida:

   | Impostazione | Descrizione |
   | --- | --- |
   | Tipo | <ul><li>**Automatico:** Consente al motore di Advertising Cloud di decidere in che modo i parametri di tracciamento vengono aggiunti agli URL di destinazione o ai modelli di tracciamento del motore di ricerca. Questo è l’approccio più semplice, ma potrebbe non risultare nel set di dati meglio integrato.<br>**Importante:** Per configurare un account del motore di ricerca in &quot;Modalità automatica&quot;, è necessario effettuare le seguenti operazioni:<br>- Il parametro e il valore &quot;s_kwcid&quot; verranno aggiunti ai modelli di tracciamento dell’account o agli URL della pagina di destinazione nell’account aggiunto. Verrà inserito alla fine dell’URL. Di conseguenza, potrebbe essere necessaria un’azione aggiuntiva da parte tua se il server web richiede una determinata coppia chiave=valore alla fine dell’URL OPPURE un aggiornamento per supportare qualsiasi nuova coppia chiave=valore nell’URL. **Nota:** Ulteriori informazioni sull’aggiunta di questo parametro al [Informativa sulla sicurezza dei contenuti](https://experienceleague.adobe.com/docs/id-service/using/reference/csp.html).<br>- Inoltre, le parole chiave possono essere inserite nell’URL di destinazione come parte del valore &quot;s_kwcid&quot;, quindi se contengono caratteri o simboli speciali, conferma che il server web può supportare tali caratteri (un esempio di caratteri speciali comuni è &quot;+&quot;, utilizzato nelle parole chiave &quot;Broad Match Modified&quot;).</li><li>**Manuale:** Consente di gestire il modo in cui i parametri di tracciamento vengono aggiunti ai modelli di tracciamento/URL di destinazione del motore di ricerca. [Fai riferimento a questi esempi di tracciamento manuale per ogni motore di ricerca](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manual-vs-automatic-tracking.md).</li></ul> |

1. In **[!UICONTROL Mapping]** sezione, scegli le suite di rapporti da collegare a questo account del motore di ricerca. Devi fornire almeno una suite di rapporti prima di poter salvare l’account Advertising. Puoi mappare più account su più suite di rapporti (1:1, 1:Many, Many:Many). I dati che AMO estrae dal motore di ricerca vengono semplicemente copiati in qualsiasi suite di rapporti mappata, quindi non si verifica alcuna suddivisione dei dati.

   >[!IMPORTANT]
   >
   >Sono disponibili per la selezione solo le suite di rapporti mappate su un’organizzazione di Experienci Cloud. Se la suite di rapporti non viene visualizzata nell’elenco, consulta [Risoluzione dei problemi di Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-troubleshooting.md).

   Per **[!UICONTROL Mapping Settings]** segue le seguenti linee guida:

   | Impostazione | Descrizione |
   | --- | --- |
   | Mappatura suite di rapporti | La mappatura suite di rapporti determina la suite di rapporti che viene collegata a questo account del motore di ricerca. In altre parole, determina in quali suite di rapporti vengono inviati i dati del motore di ricerca. |


1. Fai clic su **[!UICONTROL Save]** (Usa modello di attribuzione non predefinito).
1. Dopo il salvataggio, una liberatoria visualizza un elenco di avvertenze. Ti viene chiesto di confermare di aver letto e compreso questo contratto. Fai clic sulla casella di controllo, quindi fai clic su **[!UICONTROL OK]**.

   Ora sei portato sugli account Advertising [Interfaccia utente di gestione](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manage-ad-accounts.md), dove deve essere elencato l’account appena creato.

>[!NOTE]
>
>Devi aspettare almeno 24 ore prima che i dati del motore di ricerca inizino a popolare i rapporti di Analytics.
