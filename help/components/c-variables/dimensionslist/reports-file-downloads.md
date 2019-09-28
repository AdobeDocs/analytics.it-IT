---
description: I download dei file consentono di capire con quale frequenza i visitatori scaricano i file dal sito. Esempi di download di file possono essere documenti del processore testi, fogli di calcolo, file audio, file video, manuali utente e così via. Ciò include sia i file salvati e aperti direttamente dal browser, sia i file salvati nel computer dell'utente. Il rapporto mostra il nome del file che si sta scaricando, incluso l'URL completo richiesto per accedere al file.
seo-description: I download dei file consentono di capire con quale frequenza i visitatori scaricano i file dal sito. Esempi di download di file possono essere documenti del processore testi, fogli di calcolo, file audio, file video, manuali utente e così via. Ciò include sia i file salvati e aperti direttamente dal browser, sia i file salvati nel computer dell'utente. Il rapporto mostra il nome del file che si sta scaricando, incluso l'URL completo richiesto per accedere al file.
seo-title: Download dei file
solution: Analytics
title: Download dei file
topic: Rapporti
uuid: 897fc221-aa30-4eac-aca6-bccb76adaf71
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Download dei file

I download dei file consentono di capire con quale frequenza i visitatori scaricano i file dal sito. Esempi di download di file possono essere documenti del processore testi, fogli di calcolo, file audio, file video, manuali utente e così via. Ciò include sia i file salvati e aperti direttamente dal browser, sia i file salvati nel computer dell'utente. Il rapporto mostra il nome del file che si sta scaricando, incluso l'URL completo richiesto per accedere al file.

**Navigazione**

**[!UICONTROL Reports]** &gt; **[!UICONTROL Site Content]** &gt; **[!UICONTROL Links]** &gt; **[!UICONTROL File Downloads]**

Se il rapporto non è disponibile nel percorso predefinito, consulta gli amministratori, che potrebbero aver modificato la struttura del menu predefinita per soddisfare al meglio le esigenze specifiche della tua organizzazione.

Utilizzate questo rapporto per:

* Determinare i file scaricati più frequentemente dal sito.
* Comprendere se alcuni file vengono scaricati più spesso durante periodi di tempo specifici.
* Verificare che tutti i formati per un dato documento siano obbligatori.

   Ad esempio, al momento si sta traducendo i manuali utente in dodici lingue e li sta rendendo disponibili tramite il sito Web. Con il rapporto sul download dei file, è possibile sapere con quale frequenza viene scaricata ogni versione manuale dell'utente e valutare il valore di continuare a tradurre il manuale dell'utente in tutte e dodici le lingue.

**Risoluzione dei problemi**

I rapporti di marketing acquisiscono informazioni sui file scaricati da qualsiasi pagina del sito che contiene codice JavaScript. Tuttavia, alcune variabili devono essere presenti e impostate correttamente in modo da poter segnalare le informazioni di download dei file. Se il rapporto non visualizza i dati o non mostra i valori previsti, segui i passaggi indicati di seguito per convalidare l’implementazione.

1. Sul sito, individuare il file JavaScript globale. Questo nome è spesso [!DNL s_code.js], ma potrebbe essere stato rinominato. Se è stato rinominato, è possibile cercare il valore nei file JavaScript del sito, *`s.account`* che fa parte del codice JavaScript.

1. Nel file, individua la variabile [s.trackDownloadLinks](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_trackdownllinks.html) . Assicurarsi che sia impostato su *true*

1. Individua la variabile [s.linkDownloadFileTypes](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_linkdownfiletypes.html) . Assicurarsi che tutte le estensioni di file desiderate siano presenti in questo elenco. Se necessario, aggiungere estensioni mancanti come [!DNL .zip], [!DNL .pdf], ecc.)

Se queste variabili appaiono configurate correttamente, ma [!UICONTROL File Downloads Report] non ricevono ancora i dati, gli utenti supportati della tua organizzazione devono contattare l'Assistenza clienti.
