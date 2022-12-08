---
title: Ruoli di amministratore in Adobe Analytics
description: Scopri come iniziare a utilizzare Adobe Analytics, i tipi di ruolo generali e l’accesso all’interfaccia utente.
feature: Admin Tools
exl-id: 9d10716f-5b66-42dc-b288-af34da203c35
source-git-commit: 9057cc83881a72fa039e9398ed3daaf4259ef2bf
workflow-type: tm+mt
source-wordcount: '1090'
ht-degree: 56%

---

# Ruoli di amministratore in Adobe Analytics

Adobe Analytics supporta vari tipi di amministratori. Gli amministratori Adobe Analytics completi possono accedere a tutto in Adobe Analytics, mentre altri amministratori e utenti possono eseguire attività più specializzate.

>[!NOTE]
>
>Prima di poter assegnare ruoli a qualsiasi utente in Adobe Analytics, è necessario assegnare a quest’ultimo il ruolo di primo amministratore nell’Experience Cloud . Il primo amministratore può quindi eseguire il provisioning degli utenti nell’organizzazione con altri ruoli chiave, come descritto in questo articolo. Per ulteriori informazioni sul primo amministratore, consulta [Prima guida per l’amministratore di Adobe Analytics](/help/admin/admin-console/first-admin-guide.md).


## Ruoli chiave in Experience Cloud e Adobe Analytics

Quando utilizzi Adobe Analytics, considera i seguenti ruoli chiave:

* **Amministratori Adobe Analytics completi:** Questi utenti hanno accesso completo a tutto ciò che si trova in Adobe Analytics, incluse le impostazioni della suite di rapporti e le autorizzazioni per gli utenti. A seconda di come è strutturata la tua organizzazione, persone o team diversi possono essere responsabili di diversi aspetti dell’amministrazione di Analytics. Ad esempio, può esserci un responsabile della designazione delle variabili da utilizzare in un’implementazione. Un’altra persona può essere responsabile di consentire agli utenti di estrarre correttamente i rapporti garantendo a tutti le autorizzazioni corrette. Identifica almeno un utente come responsabile delle impostazioni della suite di rapporti di Analytics e delle autorizzazioni utente in modo che possa invitare da lì altri amministratori di Analytics.
* **Amministratori della raccolta dati:** Questi utenti hanno accesso completo a tutto ciò che si trova nella raccolta dati di Adobe Experience Platform, comprese le autorizzazioni di pubblicazione, creazione di contenitori e autorizzazioni per gli utenti. Questi utenti non sono necessariamente programmatori, ma è utile che abbiano una conoscenza almeno da principiante di HTML, CSS e JavaScript. Sono responsabili di lavorare con i proprietari del sito web della tua organizzazione per implementare i tag sul tuo sito. Identifica almeno un utente responsabile dell’implementazione dell’organizzazione: si occuperà di invitare altri amministratori di raccolta dati da lì.
* **Amministratori del profilo di prodotto:** Questi utenti possono aggiungere o rimuovere utenti a un profilo di prodotto, regolare gli elementi delle autorizzazioni nel loro profilo di prodotto e assegnare o rimuovere profili di prodotto a gruppi di utenti. Gli amministratori del profilo di prodotto non hanno accesso completo ad Adobe Analytics. Tuttavia, sono ideali per i lead o i manager del team che devono concedere e gestire l’accesso ad Adobe Analytics per il proprio team. Per ulteriori informazioni sui profili di prodotto, consulta [Profili di prodotto per Adobe Analytics](/help/admin/admin-console/permissions/product-profile.md).
* **Delegati di supporto**: noti anche come utenti supportati, non dispongono di privilegi aggiuntivi nell’interfaccia di Analytics. Al contrario, ricevono privilegi aggiuntivi durante la comunicazione con l’Assistenza clienti Adobe. Questi utenti sono quasi sempre amministratori di Analytics, poiché questo consente all’Assistenza clienti di collaborare per risolvere i problemi. Identifica almeno un amministratore di Analytics responsabile di facilitare le interazioni tra gli utenti finali e l’Assistenza clienti di Adobe.
* **Proprietari del sito web:** questi utenti singoli o team sono responsabili della codifica e dello sviluppo del sito web. Non hanno bisogno di account, ma devono essere pronti a collaborare con gli amministratori di raccolta dati per ottenere il codice tag e implementarlo sul sito web.
* **Utenti finali:** in genere questi utenti visualizzano i rapporti e cercano le risposte alle domande aziendali. Gli amministratori di Analytics concedono a questi utenti le autorizzazioni per lavorare nel prodotto.

## Concedere l’accesso completo all’amministratore del prodotto per Analytics

Gli amministratori a livello di sistema non hanno accesso diretto ai prodotti; tuttavia, possono concedersi l’accesso aggiungendo se stessi come amministratore a livello di prodotto.

Per consentire ad Adobe Analytics di accedere a te stesso o ad altri:

1. Accedi ad [Admin Console](https://adminconsole.adobe.com/) con le tue credenziali Adobe ID.
1. Fai clic sulla scheda **[!UICONTROL Products]** in alto. Tutti i prodotti acquistati dalla tua organizzazione sono a sinistra. Fai clic su **[!UICONTROL Adobe Analytics]**, quindi fai clic su **[!UICONTROL New Profile]** pulsante .
1. Assegna un nome a questo profilo &quot;Accesso completo all’amministratore di Analytics&quot;, quindi fai clic su **[!UICONTROL Next]** > **[!UICONTROL Save]**.
1. Nella pagina Profili di prodotto , fai clic sul nuovo profilo creato, quindi fai clic sul **[!UICONTROL Permissions]** scheda .
1. Fai clic su uno degli elementi della riga delle autorizzazioni. Se **[!UICONTROL Auto-include]** è disponibile, attivalo. Se **[!UICONTROL Auto-include]** non è disponibile, fai clic su **[!UICONTROL Add all]**. Entrambe le opzioni spostano tutti gli elementi delle autorizzazioni nella colonna a destra.
1. Fai clic su **[!UICONTROL Save]**.
Ripeti il passaggio precedente per tutte le categorie di autorizzazione.
1. Dopo aver concesso tutte le categorie di autorizzazioni al profilo, torna alla pagina Prodotti facendo clic su **[!UICONTROL Product]** in alto.
1. Nella sezione Adobe Analytics, fai clic su **[!UICONTROL Assign Users]**.
1. Immetti l’indirizzo e-mail a cui desideri dare accesso completo ad Analytics e assegnagli il profilo di accesso completo di amministrazione appena creato. Fai clic su **[!UICONTROL Save]**.

L’utente ora dispone dell’accesso completo ad Adobe Analytics.

## Concedere l’accesso dell’amministratore di prodotto per la raccolta dati in Experience Platform

L’accesso come amministratore di prodotto per la raccolta dati in Experience Platform è quasi identico a quello dell’amministratore di prodotto in Analytics.

1. Accedi ad [Adobe Admin Console](https://adminconsole.adobe.com) con le credenziali Adobe ID.
1. Fai clic sulla scheda **[!UICONTROL Products]** in alto. Tutti i prodotti acquistati dalla tua organizzazione sono a sinistra. Fai clic su **[!UICONTROL Experience Platform Launch]**, quindi su **[!UICONTROL New Profile]**.
1. Chiama questo profilo “Accesso completo come amministratore di raccolta dati”, quindi fai clic su **[!UICONTROL Done]**.
1. Ritorna sulla pagina **[!UICONTROL Product Profiles]**, fai clic sul nuovo profilo creato, quindi sulla scheda **[!UICONTROL Permissions]**.
1. Fai clic su uno degli elementi della riga delle autorizzazioni. Se **[!UICONTROL Auto-include]** è disponibile, attivalo. Se l’opzione di inclusione automatica non è disponibile, fai clic su **[!UICONTROL Add all]**. Entrambe le opzioni spostano tutti gli elementi delle autorizzazioni nella colonna a destra.
1. Fai clic su **[!UICONTROL Save]**. Ripeti il passaggio precedente per tutte le categorie di autorizzazione.
1. Una volta che tutte le categorie di autorizzazione sono state concesse al profilo, torna alla pagina Panoramica facendo clic su **[!UICONTROL Overview]** in alto.
1. Sotto il riquadro [!UICONTROL Experience Platform Launch], fai clic su **[!UICONTROL Assign Users]**.
1. Immetti l’indirizzo e-mail a cui desideri dare accesso completo ad Analytics e assegnagli il profilo di accesso completo di amministrazione appena creato. Fai clic su **[!UICONTROL Save]**.
1. L’utente ora dispone dell’accesso completo alla raccolta dati di Experience Platform.

## Concedere l’accesso dell’amministratore di prodotto per i profili di prodotto

Per informazioni sull’assegnazione degli utenti come amministratori del profilo di prodotto, consulta la sezione &quot;Gestisci amministratori del profilo di prodotto&quot; nell’articolo, [Gestione dei profili di prodotto per gli utenti aziendali](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html) nella guida utente Enterprise.

## Passaggi successivi

[Creare una suite di rapporti](/help/admin/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md): Chiedi all&#39;amministratore di Analytics di accedere allo strumento e creare una suite di rapporti per la raccolta dati

[Creare una proprietà tag di Analytics](/help/implement/launch/create-analytics-property.md): chiedi all’amministratore della raccolta dati di accedere allo strumento e creare una proprietà da implementare sul tuo sito

Prima di poter assegnare ruoli a qualsiasi utente in Adobe Analytics, è necessario assegnare a quest’ultimo il ruolo di primo amministratore nell’Experience Cloud . Il primo amministratore può quindi eseguire il provisioning degli utenti nell’organizzazione con altri ruoli chiave, come descritto in questo articolo.

Un primo amministratore è il punto di partenza per consentire al resto dell’organizzazione di utilizzare ogni soluzione di Experience Cloud.

Dopo la firma di un contratto

1. Il team di provisioning di Adobe si prepara alla creazione dell’account.

1. Il primo amministratore riceve un’e-mail con le credenziali di accesso prima della data di inizio del contratto.

>[!IMPORTANT]
>
>   È vivamente consigliato assicurarsi di fornire ad Adobe informazioni di contatto precise del primo amministratore prima della firma del contratto.
