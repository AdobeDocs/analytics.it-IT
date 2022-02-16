---
title: Prima guida dell'amministratore di Adobe Analytics
description: Scopri come iniziare a utilizzare Adobe Analytics, i tipi di ruolo generali e ad accedere all’interfaccia utente di .
exl-id: fbbbd335-0d22-473e-adef-f92f8eab7bf0
feature: Admin Tools
source-git-commit: 2c0aef13bdb88b0a7aa9f100c72c21f66a14c8dd
workflow-type: tm+mt
source-wordcount: '921'
ht-degree: 2%

---

# Prima guida dell&#39;amministratore di Adobe Analytics

Un primo amministratore è il punto di partenza per consentire al resto dell’organizzazione di utilizzare ogni soluzione di Experience Cloud. Una volta firmato un contratto, un team di provisioning in Adobe si prepara alla creazione dell’account. Il primo amministratore riceve un&#39;e-mail con le credenziali di accesso prima della data di inizio del contratto. È vivamente consigliato garantire che le informazioni di contatto del primo amministratore siano fornite ad Adobe e precise prima della firma del contratto.

## Ruoli chiave nell’utilizzo dell’Experience Cloud

Se la tua organizzazione ha acquistato Adobe Analytics, ci sono diversi ruoli chiave da considerare:

* **Amministratori Adobe Analytics:** Questi utenti hanno accesso completo a tutto ciò che si trova in Adobe Analytics, incluse le impostazioni della suite di rapporti e le autorizzazioni per gli utenti. A seconda di come è strutturata la tua organizzazione, persone o team diversi possono essere responsabili di diversi aspetti dell’amministrazione di Analytics. Ad esempio, una persona è responsabile della designazione delle variabili da utilizzare in un’implementazione. Un’altra persona può essere responsabile di consentire agli utenti di estrarre correttamente i rapporti garantendo a tutti le autorizzazioni corrette. Identifica almeno un utente che può essere responsabile delle impostazioni della suite di rapporti di Analytics e delle autorizzazioni utente e può invitare altri amministratori di Analytics da lì.
* **Amministratori della raccolta dati:** Questi utenti hanno accesso completo a tutto ciò che si trova nell’interfaccia utente di raccolta dati (precedentemente interfaccia utente del Experience Platform Launch), comprese le autorizzazioni di pubblicazione, creazione di contenitori e autorizzazioni per gli utenti. Questi utenti non sono necessariamente programmatori, ma avere almeno una conoscenza di HTML, CSS e JavaScript da parte di un principiante è utile. Sono responsabili della collaborazione con i proprietari del sito web della tua organizzazione per implementare i tag di Experience Platform sul tuo sito. Identifica almeno un utente responsabile dell&#39;implementazione della tua organizzazione e può invitare altri amministratori di raccolta dati da lì.
* **Delegati di supporto**: Noti anche come utenti supportati, non dispongono di privilegi aggiuntivi nell’interfaccia di Analytics. Al contrario, ricevono privilegi aggiuntivi durante la comunicazione con l’Assistenza clienti Adobe. Questi utenti sono quasi sempre amministratori di Analytics, in quanto aiuta l’Assistenza clienti a risolvere i problemi con loro. Identifica almeno un amministratore di Analytics responsabile di facilitare le interazioni tra gli utenti finali e l’Assistenza clienti di Adobe.
* **Proprietari del sito web:** Questi individui o team sono responsabili della codifica e dello sviluppo del tuo sito web. Non richiedono account, ma desiderano collaborare con gli amministratori di raccolta dati per ottenere il codice tag e implementarlo sul sito web.
* **Utenti finali:** in genere questi utenti visualizzano i rapporti e cercano le risposte alle domande aziendali. Gli amministratori di Analytics concedono a questi utenti le autorizzazioni per lavorare nel prodotto.

Come primo amministratore, il tuo ruolo può sovrapporsi in uno o più di questi ruoli. Se sono coperte tutte queste responsabilità di base, puoi concedere autorizzazioni per far sì che altri utenti all’interno della tua organizzazione funzionino correttamente.

## Concessione dell’accesso dell’amministratore del prodotto per Analytics

Gli amministratori a livello di sistema non hanno accesso diretto ai prodotti, ma possono accedervi aggiungendo se stessi come amministratore a livello di prodotto. Se desideri consentire a te stesso o agli altri utenti di accedere ad Adobe Analytics, puoi seguire questi passaggi.

1. Accedi a [Admin Console](https://adminconsole.adobe.com/) con le tue credenziali Adobe ID.
1. Fai clic sulla scheda Prodotti in alto. Tutti i prodotti acquistati dalla tua organizzazione sono a sinistra. Fai clic su Adobe Analytics, quindi sul pulsante Nuovo profilo .
1. Assegna un nome a questo profilo &quot;Accesso completo all’amministratore di Analytics&quot;, quindi fai clic su Fine.
1. Nella pagina Profili di prodotto , fai clic sul nuovo profilo creato, quindi sulla scheda Autorizzazioni .
1. Fai clic su uno degli elementi della riga delle autorizzazioni. Se è disponibile l’opzione di inclusione automatica, abilitala. Se l&#39;opzione di inclusione automatica non è disponibile, fare clic su Aggiungi tutto. Entrambe le opzioni spostano tutti gli elementi delle autorizzazioni nella colonna a destra.
1. Fai clic su salva. Ripeti il passaggio precedente per tutte le categorie di autorizzazioni.
1. Una volta che tutte le categorie di autorizzazioni sono state concesse al profilo, torna alla pagina Panoramica facendo clic su Panoramica in alto.
1. Nella sezione Adobe Analytics, fai clic su &quot;Assegna utenti&quot;.
1. Immetti l’indirizzo e-mail a cui desideri dare accesso completo ad Analytics e assegnagli il profilo di accesso completo all’amministratore appena creato. Fai clic su Salva.
1. L’utente ora dispone dell’accesso completo ad Adobe Analytics.

## Concessione dell’accesso dell’amministratore del prodotto per la raccolta dei dati in Experience Platform

L’accesso dell’amministratore di prodotto per la raccolta dati in Experience Platform è quasi identico a quello concesso all’amministratore di prodotto per Analytics.

1. Accedi a [Adobe Admin Console](https://adminconsole.adobe.com) con le tue credenziali Adobe ID.
1. Fai clic sul pulsante **[!UICONTROL Products]** in alto. Tutti i prodotti acquistati dalla tua organizzazione sono a sinistra. Fai clic su **[!UICONTROL Experience Platform Launch]**, quindi su **[!UICONTROL New Profile]**.
1. Denomina questo profilo &#39;Data Collection full admin access&#39;, quindi fai clic su **[!UICONTROL Done]**.
1. Indietro sul **[!UICONTROL Product Profiles]** , fai clic sul nuovo profilo creato, quindi fai clic sul **[!UICONTROL Permissions]** scheda .
1. Fai clic su uno degli elementi della riga delle autorizzazioni. Se **[!UICONTROL Auto-include]** è disponibile, attivalo. Se l&#39;opzione di inclusione automatica non è disponibile, fai clic su **[!UICONTROL Add all]**. Entrambe le opzioni spostano tutti gli elementi delle autorizzazioni nella colonna a destra.
1. Fai clic su **[!UICONTROL Save]**. Ripeti il passaggio precedente per tutte le categorie di autorizzazioni.
1. Una volta che tutte le categorie di autorizzazioni sono state concesse al profilo, torna alla pagina Panoramica facendo clic su **[!UICONTROL Overview]** in alto.
1. Sotto la [!UICONTROL Experience Platform Launch] riquadro, fai clic su **[!UICONTROL Assign Users]**.
1. Immetti l’indirizzo e-mail a cui desideri dare accesso completo ad Analytics e assegnagli il profilo di accesso completo all’amministratore appena creato. Fai clic su **[!UICONTROL Save]**.
1. L’utente ora dispone dell’accesso completo alla raccolta dati di Experience Platform.

## Passaggi successivi

[Creare una suite di rapporti](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md): Chiedi all&#39;amministratore di Analytics di accedere allo strumento e creare una suite di rapporti per la raccolta dati

[Creare una proprietà tag di Analytics](/help/implement/launch/create-analytics-property.md): Chiedi all&#39;amministratore della raccolta dati di accedere allo strumento e crea una proprietà da implementare sul tuo sito
