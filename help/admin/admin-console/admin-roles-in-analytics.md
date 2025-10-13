---
title: Ruoli di amministratore in Adobe Analytics
description: Scopri come iniziare a utilizzare Adobe Analytics, i tipi di ruolo generali e l’accesso all’interfaccia utente.
feature: Admin Tools
exl-id: 9d10716f-5b66-42dc-b288-af34da203c35
role: Admin
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '1103'
ht-degree: 51%

---

# Ruoli di amministratore in Adobe Analytics

Adobe Analytics supporta vari tipi di amministratori. Gli amministratori Adobe Analytics completi hanno accesso a tutto in Adobe Analytics, mentre altri amministratori e utenti possono eseguire attività più specializzate.

>[!NOTE]
>
>Prima che a qualsiasi utente possano essere assegnati ruoli in Adobe Analytics, deve essere assegnato un utente come primo amministratore in Experience Cloud. Il primo amministratore può quindi assegnare agli utenti dell’organizzazione altri ruoli chiave, come descritto in questo articolo. Per ulteriori informazioni sul primo amministratore, consulta [Prima guida amministratore di Adobe Analytics](/help/admin/admin-console/first-admin-guide.md).


## Ruoli chiave in Experience Cloud e Adobe Analytics

Quando utilizzi Adobe Analytics, considera i seguenti ruoli chiave:

* **Amministratori Full Adobe Analytics:** questi utenti hanno accesso completo a tutto ciò che si trova in Adobe Analytics, incluse le impostazioni della suite di rapporti e le autorizzazioni per gli utenti. A seconda di come è strutturata la tua organizzazione, persone o team diversi possono essere responsabili di diversi aspetti dell’amministrazione di Analytics. Ad esempio, può esserci un responsabile della designazione delle variabili da utilizzare in un’implementazione. Un’altra persona può essere responsabile di consentire agli utenti di estrarre correttamente i rapporti garantendo a tutti le autorizzazioni corrette. Identifica almeno un utente come responsabile delle impostazioni della suite di rapporti di Analytics e delle autorizzazioni utente in modo che possa invitare da lì altri amministratori di Analytics.
* **Amministratori raccolta dati:** questi utenti hanno accesso completo a tutto ciò che si trova in Raccolta dati di Adobe Experience Platform, incluse le autorizzazioni di pubblicazione, creazione di contenitori e autorizzazioni per gli utenti. Questi utenti non sono necessariamente programmatori, ma è utile che abbiano una conoscenza almeno da principiante di HTML, CSS e JavaScript. Essi sono responsabili dell’utilizzo dei proprietari del sito web della tua organizzazione per implementare i tag sul sito. Identifica almeno un utente responsabile dell’implementazione dell’organizzazione: si occuperà di invitare altri amministratori di raccolta dati da lì.
* **Amministratore di prodotto:** Un amministratore di prodotto gestisce un prodotto in Admin Console, nonché i diritti utente a tale prodotto.
* **Amministratori dei profili di prodotto:** questi utenti possono aggiungere o rimuovere utenti a un profilo di prodotto, modificare gli elementi delle autorizzazioni nel loro profilo di prodotto e assegnare o rimuovere profili di prodotto a gruppi di utenti. Gli amministratori dei profili di prodotto non hanno accesso completo ad Adobe Analytics. Tuttavia, sono ideali per i lead o i manager dei team che devono concedere e gestire l’accesso ad Adobe Analytics per il proprio team. Per ulteriori informazioni sui profili di prodotto, vedere [Profili di prodotto per Adobe Analytics](/help/admin/admin-console/permissions/product-profile.md).
* **Amministratore supporto**: noti anche come utenti supportati, non dispongono di privilegi aggiuntivi nell&#39;interfaccia di Analytics. Al contrario, ricevono privilegi aggiuntivi durante la comunicazione con l’Assistenza clienti Adobe. Questi utenti sono quasi sempre amministratori di Analytics, poiché questo consente all’Assistenza clienti di collaborare per risolvere i problemi. Identifica almeno un amministratore di Analytics responsabile di facilitare le interazioni tra gli utenti finali e l’Assistenza clienti di Adobe.
* **Proprietari del sito web:** questi utenti singoli o team sono responsabili della codifica e dello sviluppo del sito web. Non hanno bisogno di account, ma devono essere pronti a collaborare con gli amministratori di raccolta dati per ottenere il codice tag e implementarlo sul sito web.
* **Utenti finali:** in genere questi utenti visualizzano i rapporti e cercano le risposte alle domande aziendali. Gli amministratori di Analytics concedono a questi utenti le autorizzazioni per lavorare nel prodotto.

## Concedere l’accesso completo come amministratore del prodotto per Analytics

Gli amministratori a livello di sistema non hanno accesso diretto ai prodotti, ma possono accedervi aggiungendo se stessi come amministratore a livello di prodotto.

Per consentire ad Adobe Analytics di accedere a te stesso o ad altri utenti:

1. Accedi ad [Admin Console](https://adminconsole.adobe.com/) con le tue credenziali Adobe ID.
1. Fai clic sulla scheda **[!UICONTROL Products]** in alto. Tutti i prodotti acquistati dalla tua organizzazione sono a sinistra. Fare clic su **[!UICONTROL Adobe Analytics]**, quindi sul pulsante **[!UICONTROL New Profile]**.
1. Assegna al profilo il nome &#39;Accesso completo come amministratore di Analytics&#39;, quindi fai clic su **[!UICONTROL Next]** > **[!UICONTROL Save]**.
1. Nella pagina Profili di prodotto, fai clic sul nuovo profilo creato, quindi sulla scheda **[!UICONTROL Permissions]**.
1. Fai clic su uno degli elementi della riga delle autorizzazioni. Se **[!UICONTROL Auto-include]** è disponibile, abilitalo. Se **[!UICONTROL Auto-include]** non è disponibile, fare clic su **[!UICONTROL Add all]**. Entrambe le opzioni spostano tutti gli elementi delle autorizzazioni nella colonna a destra.
1. Fare clic su **[!UICONTROL Save]**.
Ripeti il passaggio precedente per tutte le categorie di autorizzazione.
1. Dopo aver concesso tutte le categorie di autorizzazione al profilo, torna alla pagina Prodotti facendo clic su **[!UICONTROL Product]** in alto.
1. Nel riquadro Adobe Analytics fare clic su **[!UICONTROL Assign Users]**.
1. Immetti l’indirizzo e-mail a cui desideri dare accesso completo ad Analytics e assegnagli il profilo di accesso completo di amministrazione appena creato. Fai clic su **[!UICONTROL Save]**.

L’utente ora dispone dell’accesso completo ad Adobe Analytics.

## Concedere l’accesso come amministratore del prodotto per la raccolta dati in Experience Platform

L’accesso come amministratore di prodotto per la raccolta dati in Experience Platform è quasi identico a quello dell’amministratore di prodotto in Analytics.

1. Accedi ad [Adobe Admin Console](https://adminconsole.adobe.com) con le credenziali Adobe ID.
1. Fai clic sulla scheda **[!UICONTROL Products]** in alto. Tutti i prodotti acquistati dalla tua organizzazione sono a sinistra. Fai clic su **[!UICONTROL Experience Platform Launch]**, quindi su **[!UICONTROL New Profile]**.
1. Chiama questo profilo “Accesso completo come amministratore di raccolta dati”, quindi fai clic su **[!UICONTROL Done]**.
1. Ritorna sulla pagina **[!UICONTROL Product Profiles]**, fai clic sul nuovo profilo creato, quindi sulla scheda **[!UICONTROL Permissions]**.
1. Fai clic su uno degli elementi della riga delle autorizzazioni. Se **[!UICONTROL Auto-include]** è disponibile, abilitalo. Se l’opzione di inclusione automatica non è disponibile, fai clic su **[!UICONTROL Add all]**. Entrambe le opzioni spostano tutti gli elementi delle autorizzazioni nella colonna a destra.
1. Fai clic su **[!UICONTROL Save]**. Ripeti il passaggio precedente per tutte le categorie di autorizzazione.
1. Una volta che tutte le categorie di autorizzazione sono state concesse al profilo, torna alla pagina Panoramica facendo clic su **[!UICONTROL Overview]** in alto.
1. Sotto il riquadro [!UICONTROL Experience Platform Launch], fai clic su **[!UICONTROL Assign Users]**.
1. Immetti l’indirizzo e-mail a cui desideri dare accesso completo ad Analytics e assegnagli il profilo di accesso completo di amministrazione appena creato. Fai clic su **[!UICONTROL Save]**.
1. L’utente ora dispone dell’accesso completo alla raccolta dati di Experience Platform.

## Concedere l’accesso come amministratore del prodotto per i profili di prodotto

Per informazioni sull&#39;assegnazione degli utenti come amministratori dei profili di prodotto, consulta la sezione &quot;Gestire gli amministratori dei profili di prodotto&quot; nell&#39;articolo [Gestire i profili di prodotto per gli utenti Enterprise](https://helpx.adobe.com/it/enterprise/using/manage-product-profiles.html?lang=it) nella guida utente Enterprise.

## Passaggi successivi

[Creare una suite di rapporti](/help/admin/tools/manage-rs/new-rs/t-create-a-report-suite.md): chiedi all&#39;amministratore di Analytics di accedere allo strumento e creare una suite di rapporti per la raccolta dati

[Creare una proprietà tag di Analytics](/help/implement/launch/create-analytics-property.md): chiedi all’amministratore della raccolta dati di accedere allo strumento e creare una proprietà da implementare sul tuo sito

Prima che a qualsiasi utente possano essere assegnati ruoli in Adobe Analytics, deve essere assegnato un utente come primo amministratore in Experience Cloud. Il primo amministratore può quindi assegnare agli utenti dell’organizzazione altri ruoli chiave, come descritto in questo articolo.

Un primo amministratore è il punto di partenza per consentire al resto dell’organizzazione di utilizzare ogni soluzione Experience Cloud.

Dopo la firma di un contratto

1. Il team di provisioning in Adobe si prepara alla creazione dell’account.

1. Il primo amministratore riceve un’e-mail con le credenziali di accesso prima della data di inizio del contratto.

>[!IMPORTANT]
>
>   È vivamente consigliato assicurarsi di fornire ad Adobe informazioni di contatto precise del primo amministratore prima della firma del contratto.
