---
description: L'inoltro lato server è progettato per i clienti che desiderano condividere in tempo reale i dati da  Analytics ad altre soluzioni Experience Cloud . Se abilitata, l'inoltro lato server consente anche  Analytics di inviare i dati ad altre soluzioni Experience Cloud  e che tali soluzioni inviino i dati a  Analytics durante il processo di raccolta dei dati.
solution: Audience Manager
title: Panoramica sull'inoltro lato server
uuid: 22ddbde5-6805-4eba-8f82-62772644dcaa
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '850'
ht-degree: 14%

---


# Panoramica sull&#39;inoltro lato server

L&#39;inoltro lato server è progettato per i clienti che desiderano condividere in tempo reale i dati da  Analytics ad altre soluzioni Experience Cloud . Se abilitata, l&#39;inoltro lato server consente anche  Analytics di inviare i dati ad altre soluzioni Experience Cloud  e che tali soluzioni inviino i dati a  Analytics durante il processo di raccolta dei dati.

L&#39;inoltro lato server migliora la raccolta dati perché:

* Riduce le chiamate dalla pagina. Con l&#39;inoltro lato server, [!DNL Audience Manager] i clienti non devono più utilizzare DIL per la raccolta dei dati perché viene inoltrata da  Analytics. Rimuovere DIL significa eliminare una `"/event"` chiamata. Con un numero minore di chiamate è possibile migliorare i tempi di caricamento delle pagine, migliorando così l&#39;esperienza dei clienti sul sito.
* Consente di sfruttare la condivisione dei dati tra  soluzioni Experience Cloud.
* Si conforma alle nostre best practice per  implementazione e implementazione del codice Audience Manager.

>[!TIP]
>
>Gli attuali clienti Audience Manager  che utilizzano  Analytics devono effettuare la migrazione all’inoltro lato server. I nuovi clienti Adobe  Analytics e  Audience Manager devono implementare l’inoltro lato server (anziché DIL) come metodo predefinito di raccolta e trasferimento dei dati.

>[!IMPORTANT]
>In base al regolamento UE sulla conformità ai cookie, i titolari del trattamento dei dati (clienti Analytics) hanno ora la possibilità di limitare i dati divulgati prima del consenso ad Adobe Analytics e di impedire che vengano inoltrati al server ad Adobe Audience Manager (AAM). Una nuova variabile di contesto dell&#39;implementazione consente di contrassegnare le richieste dove non è stato ricevuto il consenso. La variabile, quando impostata, impedisce che queste richieste vengano inviate all&#39;AAM fino al ricevimento del consenso. Per ulteriori informazioni, consultate Conformità [GDPR_ePrivacy e inoltro](/help/admin/admin/c-server-side-forwarding/ssf-gdpr.md)lato server.

Per comprendere a che punto si trova l&#39;organizzazione in termini di implementazione dell&#39;inoltro lato server, procedere come segue:

## ![step1_icon.png immagine](assets/step1_icon.png) Verificare l&#39;implementazione del servizio ECID

Verifica se  servizio Experience Cloud ID (ECID) è implementato, ispezionando la richiesta [di tracciamento](https://docs.adobe.com/content/help/en/id-service/using/implementation/test-verify.html)Analytics.

Nella scheda Richiesta, verificare che sia stato impostato un valore ECID. Questo indica che il servizio identità è stato implementato correttamente, un prerequisito per l&#39;inoltro lato server.

* Se viene visualizzato un valore ECID, continuate con il passaggio 2.
* Se non viene visualizzato un valore ECID, [implementa Identity Service](https://docs.adobe.com/content/help/it-IT/id-service/using/implementation/implementation-guides.html) prima di procedere con il passaggio 2.

## ![step2_icon.png immagine](assets/step2_icon.png) Verificare la versione di implementazione dell&#39;inoltro lato server

Verifica di disporre già di una versione dell&#39;inoltro lato server implementata, [esaminando la richiesta](/help/admin/admin/c-server-side-forwarding/ssf-verify.md)di tracciamento Analytics .

Nella scheda &quot;Risposta&quot;, verificate che la risposta contenga  dati Audience Manager. Se viene visualizzato:

* Una risposta **JSON da  Audience Manager che include elementi come &quot;postback&quot; o &quot;dcs_region&quot;**: è già abilitata una qualche forma di inoltro lato server. Continuate fino al punto 3.
* Lo **&quot;status&quot;:&quot;SUCCESS&quot;**: hai implementato il modulo Gestione dell&#39;audience, ma non hai configurato correttamente l&#39;inoltro lato server. Continuate fino al punto 3.
* Un&#39;immagine **** 2 x 2: non hai implementato l&#39;inoltro lato server o il modulo Gestione dell&#39;audience. Per correggere il problema:

   * **Clienti AAM con DIL**: coordinare in stretta collaborazione i due elementi seguenti:

      1. Rimuovete il codice DIL e installate il codice della pagina del modulo [Gestione dell&#39;](https://docs.adobe.com/content/help/it-IT/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html) audience.
      1. Abilitare l&#39;inoltro lato server nell&#39;interfaccia utente  amministratore Analytics come descritto al punto 3. Se si abilita questa impostazione prima di rimuovere il codice DIL, i dati verranno duplicati e verranno create chiamate server fatturate aggiuntive a  Audience Manager.
   * **Nuovi clienti** AAM: installa il codice della pagina del modulo [Gestione dell&#39;](https://docs.adobe.com/content/help/it-IT/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html) audience e continua il passaggio 3. I dati non verranno inviati a  Audience Manager fino a quando non verrà attivato l&#39;inoltro lato server nel passaggio 3.


## ![step3_icon.png immagine](assets/step3_icon.png) Verificare l&#39;implementazione dell&#39;inoltro lato server della suite di rapporti

Verificate che l&#39;inoltro lato server sia implementato a livello di suite di rapporti, anziché nell&#39;approccio server di tracciamento legacy.

L’inoltro lato server a livello di suite di rapporti è consigliato rispetto all’approccio server di tracciamento legacy, perché puoi controllare a un livello più preciso quali dati vengono condivisi da  Analytics. È inoltre un prerequisito per l&#39;integrazione di Audience  Analytics.

Vai a **Analytics** > **Amministratore** > **Suite** di rapporti > (seleziona suite **di** rapporti) > **Modifica impostazioni** **** ****> Generale > Inoltro lato server. Se la casella di controllo è:

* **Inattivo** (non è possibile effettuare una selezione o il menu non esiste): le suite di rapporti selezionate non sono mappate sull’organizzazione IMS. Assicurati che le suite di rapporti applicabili siano mappate sulla  corretta organizzazione Experience Cloud utilizzando l&#39;interfaccia utente [di mappatura delle suite di](https://docs.adobe.com/content/help/it-IT/core-services/interface/about-core-services/report-suite-mapping.html)rapporti.
* **Disattivato**: Il nuovo inoltro lato server non è attivato. Leggete il contenuto della pagina e continuate ad attivare la funzione.
* **Abilitato**: È stato effettuato il provisioning per l&#39;inoltro lato server. Puoi anche configurare questa integrazione di Audience  Analytics.

>[!NOTE]
>
>I dati non verranno visualizzati in altre soluzioni  Experience Cloud, come [Audience Manager](https://docs.adobe.com/content/help/it-IT/audience-manager/user-guide/aam-home.html) o [Audience](https://docs.adobe.com/content/help/it-IT/core-services/interface/audiences/audience-library.html) fino al completamento di tutti e tre i passaggi. Una volta attivata questa opzione, per rendere effettive le impostazioni sono necessarie diverse ore.

