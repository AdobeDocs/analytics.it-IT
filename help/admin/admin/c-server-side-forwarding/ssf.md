---
description: L’inoltro lato server è progettato per i clienti che desiderano condividere in tempo reale i dati da Analytics ad altre soluzioni Experience Cloud. Se abilitata, l'inoltro lato server consente anche ad Analytics di inviare dati ad altre soluzioni Experience Cloud e a queste soluzioni di inviare dati in push ad Analytics durante il processo di raccolta dei dati.
seo-description: L’inoltro lato server è progettato per i clienti che desiderano condividere in tempo reale i dati da Analytics ad altre soluzioni Experience Cloud. Se abilitata, l'inoltro lato server consente anche ad Analytics di inviare dati ad altre soluzioni Experience Cloud e a queste soluzioni di inviare dati in push ad Analytics durante il processo di raccolta dei dati.
seo-title: Panoramica sull'inoltro lato server
solution: Audience Manager
title: Panoramica sull'inoltro lato server
uuid: 22dbde5-6805-4eba-8f82-62772644dcaa
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Panoramica sull'inoltro lato server

L’inoltro lato server è progettato per i clienti che desiderano condividere in tempo reale i dati da Analytics ad altre soluzioni Experience Cloud. Se abilitata, l'inoltro lato server consente anche ad Analytics di inviare dati ad altre soluzioni Experience Cloud e a queste soluzioni di inviare dati in push ad Analytics durante il processo di raccolta dei dati.

L'inoltro lato server migliora la raccolta dati perché:

* Riduce le chiamate dalla pagina. Con l'inoltro lato server, [!DNL Audience Manager] i clienti non devono più utilizzare DIL per la raccolta dati perché viene inoltrata da Analytics. Rimuovere DIL significa eliminare una `"/event"` chiamata. Con un numero minore di chiamate è possibile migliorare i tempi di caricamento delle pagine, migliorando l'esperienza dei clienti sul sito.
* Consente di sfruttare la condivisione dei dati tra le soluzioni Experience Cloud.
* È conforme alle nostre best practice per l’implementazione e la distribuzione del codice di Audience Manager.

>[!TIP]
>
>I clienti correnti di Audience Manager che utilizzano Analytics devono effettuare la migrazione all’inoltro lato server. I nuovi clienti Adobe Analytics e Audience Manager devono implementare l’inoltro lato server (invece di DIL) come metodo di raccolta e trasferimento dei dati predefinito.

>[!IMPORTANT]
>In base al regolamento UE sulla conformità ai cookie, i titolari del trattamento dei dati (clienti Analytics) hanno ora la possibilità di limitare i dati divulgati prima del consenso ad Adobe Analytics e di impedire che vengano inoltrati al server ad Adobe Audience Manager (AAM). Una nuova variabile di contesto dell'implementazione consente di contrassegnare le richieste dove non è stato ricevuto il consenso. La variabile, quando impostata, impedisce che queste richieste vengano inviate all'AAM fino al ricevimento del consenso. Per ulteriori informazioni, consulta Conformità GDPR_ePrivacy e inoltro lato server.

Per comprendere a che punto si trova l'organizzazione in termini di implementazione dell'inoltro lato server, procedere come segue:

## ![step1_icon.png immagine](assets/step1_icon.png) Verifica implementazione del servizio MID

Verifica se il servizio Experience Cloud ID (MID) è implementato, esaminando la richiesta [di tracciamento di](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-test-verify.html)Analytics.

Nella scheda Richiesta, verifica che sia impostato un valore MID. Questo indica che il servizio identità è stato implementato correttamente, un prerequisito per l'inoltro lato server.

* Se viene visualizzato un valore MID, continuate con il passaggio 2.
* Se non trovi un valore MID, [implementa il servizio](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-implementation-guides.html) identità prima di procedere con il passaggio 2.

## ![step2_icon.png immagine](assets/step2_icon.png) Verificare la versione di implementazione dell'inoltro lato server

Verifica di disporre già di una versione dell'inoltro lato server implementata, [esaminando la richiesta](/help/admin/admin/c-server-side-forwarding/ssf-verify.md)di tracciamento di Analytics.

Nella scheda "Risposta", verificate che la risposta contenga dati di Audience Manager. Se visualizzate:

* Una risposta **JSON di Audience Manager che include elementi come "postback" o "dcs_region"**: è già abilitata una sorta di inoltro lato server. Continuate fino al punto 3.
* Lo **"status":"SUCCESS"**: hai implementato il modulo Gestione dell'audience, ma non hai configurato correttamente l'inoltro lato server. Continuate fino al punto 3.
* Un'immagine **** 2 x 2: non hai implementato l'inoltro lato server o il modulo Gestione dell'audience. Per correggere il problema:

   * **Clienti AAM con DIL**: coordinare in stretta collaborazione i due elementi seguenti:

      1. Rimuovi il codice DIL e installa il codice della pagina del modulo [Gestione dell'](https://marketing.adobe.com/resources/help/en_US/aam/c_profiles_audiences.html) audience.
      1. Abilita l'inoltro lato server nell'interfaccia utente di amministrazione di Analytics come descritto al punto 3. Se si abilita questa impostazione prima di rimuovere il codice DIL, i dati verranno duplicati e verranno create chiamate server fatturate aggiuntive ad Audience Manager.
   * **Nuovi clienti** AAM: installa il codice della pagina del modulo [Gestione dell'](https://marketing.adobe.com/resources/help/en_US/aam/c_profiles_audiences.html) audience e continua il passaggio 3. I dati verranno inviati ad Audience Manager solo dopo l’attivazione dell’inoltro lato server nel passaggio 3.


## ![step3_icon.png immagine](assets/step3_icon.png) Verificare l'implementazione dell'inoltro lato server della suite di rapporti

Verificate che l'inoltro lato server sia implementato a livello di suite di rapporti, anziché nell'approccio server di tracciamento legacy.

L’inoltro lato server a livello di suite di rapporti è consigliato rispetto all’approccio del server di tracciamento legacy, perché puoi controllare a un livello più preciso quali dati vengono condivisi da Analytics. È anche un prerequisito per questa integrazione con Audience Analytics.

Vai a **Analytics** &gt; **Amministratore** &gt; **Suite** di rapporti &gt; (seleziona suite **di** rapporti) &gt; **Modifica impostazioni** **** ****&gt; Generale &gt; Inoltro lato server. Se la casella di controllo è:

* **Inattivo** (non è possibile effettuare una selezione o il menu non esiste): le suite di rapporti selezionate non sono mappate sull’organizzazione IMS. Accertatevi che le suite di rapporti applicabili siano mappate sull’organizzazione IMS corretta tramite l’interfaccia utente [Mappatura suite di](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html)rapporti.
* **Disattivato**: Il nuovo inoltro lato server non è attivato. Leggete il contenuto della pagina e continuate ad attivare la funzione.
* **Abilitato**: È stato effettuato il provisioning per l'inoltro lato server. Puoi anche configurare questa integrazione con Audience Analytics.

<!-- Meike, check Report Suite Mapping UI link above -->

> [!NOTE] I dati non verranno visualizzati in altre soluzioni Experience Cloud, come [Audience Manager](https://marketing.adobe.com/resources/help/en_US/aam/c_aam_home.html) o [Audience](https://marketing.adobe.com/resources/help/en_US/mcloud/audience_library.html) finché tutti e tre i passaggi non saranno completati. Una volta attivata questa opzione, per rendere effettive le impostazioni sono necessarie diverse ore.

