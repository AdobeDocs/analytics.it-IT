---
description: I download dei file consentono di comprendere con quale frequenza i visitatori scaricano i file dal sito. Alcuni esempi di download dei file possono essere documenti di elaboratore testi, fogli di calcolo, file audio, file filmato, manuali utente e così via. Ciò include entrambi i file salvati e aperti direttamente dal browser, nonché i file salvati nel computer dell'utente. Il rapporto mostra il nome del file scaricato, compreso l'URL completo richiesto per accedere al file.
seo-description: I download dei file consentono di comprendere con quale frequenza i visitatori scaricano i file dal sito. Alcuni esempi di download dei file possono essere documenti di elaboratore testi, fogli di calcolo, file audio, file filmato, manuali utente e così via. Ciò include entrambi i file salvati e aperti direttamente dal browser, nonché i file salvati nel computer dell'utente. Il rapporto mostra il nome del file scaricato, compreso l'URL completo richiesto per accedere al file.
seo-title: Download dei file
solution: Analytics
title: Download dei file
topic: Rapporti
uuid: 897 fc 221-aa 30-4 eac-aca 6-bccb 76 adaf 71
translation-type: tm+mt
source-git-commit: 5a30ea6ac47ddd8612728e488afda868491a1ddc

---


# Download dei file

I download dei file consentono di comprendere con quale frequenza i visitatori scaricano i file dal sito. Alcuni esempi di download dei file possono essere documenti di elaboratore testi, fogli di calcolo, file audio, file filmato, manuali utente e così via. Ciò include entrambi i file salvati e aperti direttamente dal browser, nonché i file salvati nel computer dell'utente. Il rapporto mostra il nome del file scaricato, compreso l'URL completo richiesto per accedere al file.

**Navigazione**

**[!UICONTROL Reports]** &gt; **[!UICONTROL Site Content]** &gt; **[!UICONTROL Links]** &gt; **[!UICONTROL File Downloads]**

Se il rapporto non è disponibile nel percorso predefinito, rivolgetevi agli amministratori che possono aver modificato la struttura del menu predefinita in modo da soddisfare le esigenze specifiche della vostra organizzazione.

Utilizzate questo rapporto per:

* Consente di determinare i file scaricati più frequentemente dal sito.
* Verifica se alcuni file vengono scaricati più spesso in periodi specifici.
* Verificare che tutti i formati per un determinato documento siano obbligatori.

   Ad esempio, state trasmettendo i manuali degli utenti in dodici lingue e rendendoli disponibili tramite il sito Web. Grazie alla generazione di rapporti sui download dei file, potete sapere con quale frequenza viene scaricata ogni versione manuale dell'utente e valutare il valore di continuare a tradurre il manuale utente in tutte le dodici lingue.

**Risoluzione dei problemi**

I rapporti di marketing acquisiscono informazioni sui file scaricati da qualsiasi pagina del sito che contiene codice javascript. Tuttavia, alcune variabili devono essere presenti e impostate correttamente in modo che possano essere riportate informazioni sul download del file. Se il rapporto non mostra i dati, o non mostra i valori previsti, segui i passaggi indicati di seguito per convalidare la tua implementazione.

1. Nel sito, individuate il file javascript globale. This is frequently named [!DNL s_code.js], but may have been renamed. If it has been renamed, you can search the JavaScript files on your site for the value *`s.account`*, which is a part of the JavaScript code.

1. In the file, locate the [s.trackDownloadLinks](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_trackdownllinks) variable. Ensure that it is set to *true*

1. Locate the [s.linkDownloadFileTypes](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_linkdownfiletypes) variable. Assicurarsi che in questo elenco siano presenti tutte le estensioni di file desiderate. If necessary, add missing extensions like [!DNL .zip], [!DNL .pdf], and so on.)

If these variables appear to be configured correctly, but the [!UICONTROL File Downloads Report] still is not receiving data, your organization's supported users should contact Customer Care.
