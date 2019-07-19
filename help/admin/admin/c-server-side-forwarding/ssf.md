---
description: L'inoltro lato server è progettato per i clienti che desiderano condividere dati da Analytics ad altre soluzioni Experience Cloud in tempo reale. Quando abilitata, l'inoltro lato server consente anche ad Analytics di inviare dati ad altre soluzioni Experience Cloud e a quelle soluzioni per inviare dati ad Analytics durante il processo di raccolta dati.
seo-description: L'inoltro lato server è progettato per i clienti che desiderano condividere dati da Analytics ad altre soluzioni Experience Cloud in tempo reale. Quando abilitata, l'inoltro lato server consente anche ad Analytics di inviare dati ad altre soluzioni Experience Cloud e a quelle soluzioni per inviare dati ad Analytics durante il processo di raccolta dati.
seo-title: Panoramica sull'inoltro lato server
solution: Audience Manager
title: Panoramica sull'inoltro lato server
uuid: 22 ddbde 5-6805-4 eba -8 f 82-62772644 dcaa
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Panoramica sull'inoltro lato server

L'inoltro lato server è progettato per i clienti che desiderano condividere dati da Analytics ad altre soluzioni Experience Cloud in tempo reale. Quando abilitata, l'inoltro lato server consente anche ad Analytics di inviare dati ad altre soluzioni Experience Cloud e a quelle soluzioni per inviare dati ad Analytics durante il processo di raccolta dati.

L'inoltro lato server migliora la raccolta dei dati perché:

* Riduce le chiamate dalla pagina. With server-side forwarding, [!DNL Audience Manager] customers no longer need to use DIL for data collection because it is being forwarded from Analytics. Removing DIL means eliminating an `"/event"` call. Un minor numero di chiamate consente di migliorare i tempi di caricamento delle pagine, per una migliore esperienza cliente sul sito.
* Consente di sfruttare la condivisione dei dati tra le soluzioni Experience Cloud.
* Conformità alle procedure ottimali per implementazione e implementazione del codice Audience Manager.

>[!TIP]
>
>I clienti attuali di Audience Manager che usano Analytics devono effettuare la migrazione all'inoltro lato server. I nuovi clienti di Adobe Analytics e Audience Manager implementano l'inoltro lato server (anziché DIL) come raccolta dati e metodo di trasferimento predefiniti.

>[!IMPORTANT]
>In base al regolamento UE sulla conformità ai cookie, i titolari del trattamento dei dati (clienti Analytics) hanno ora la possibilità di limitare i dati divulgati prima del consenso ad Adobe Analytics e di impedire che vengano inoltrati al server ad Adobe Audience Manager (AAM). Una nuova variabile di contesto dell'implementazione consente di contrassegnare le richieste dove non è stato ricevuto il consenso. La variabile, quando impostata, impedisce che queste richieste vengano inviate all'AAM fino al ricevimento del consenso. Per ulteriori informazioni, consulta Conformità alla eprivacy GDPR_ eprivacy e inoltro lato server.

Per capire dove l'organizzazione è in termini di implementazione dell'inoltro lato server, seguite questi passaggi di convalida:

## ![step 1_ icon. png image](assets/step1_icon.png) Verifica l'implementazione del servizio MID

Verify whether Experience Cloud ID (MID) service is implemented, by inspecting the [Analytics tracking request](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-test-verify.html).

Nella scheda Richiesta, verifica che sia impostato un valore MID. Questo indica che il servizio Identità è implementato correttamente, che è un prerequisito per l'inoltro lato server.

* Se visualizzi un valore MID, continua al passaggio 2.
* If you do not see a MID value, [implement Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-implementation-guides.html) before proceeding to step 2.

## ![step 2_ icon. png image](assets/step2_icon.png) Verificare la versione di implementazione lato server

Verify whether you already have a version of server-side forwarding implemented, by [inspecting the Analytics tracking request](../../../admin/admin/c-server-side-forwarding/ssf-verify.md).

Nella scheda «Risposta» verificate che la risposta contenga i dati di Audience Manager. Se visualizzi:

* A **JSON response from Audience Manager that includes items such as “postbacks” or “dcs_region”**: you have some form of server-side forwarding already enabled. Continuate al punto 3.
* The **“status":"SUCCESS”**: you have the Audience Management Module implemented, but do not have server side forwarding properly configured. Continuate al punto 3.
* A **2 x 2 image**: you do not have server-side forwarding or the Audience Management Module implemented. Per correggere questo problema:

   * **Clienti AAM con DIL**: coordinate i seguenti 2 elementi in prossimità:

      1. Remove the DIL code and install the [Audience Management Module](https://marketing.adobe.com/resources/help/en_US/aam/c_profiles_audiences.html) page code.
      1. Abilita l'inoltro lato server nell'interfaccia utente amministratore di Analytics come descritto al punto 3. Attivando questa impostazione prima di rimuovere il codice DIL, si duplicheranno i dati e si creano chiamate server fatturate ad Audience Manager.
   * **Nuovi clienti AAM** - installa il codice [della pagina Modulo](https://marketing.adobe.com/resources/help/en_US/aam/c_profiles_audiences.html) gestione pubblico e continua al passaggio 3. I dati non verranno inviati ad Audience Manager finché non viene attivato il passaggio lato server al passaggio 3.


## ![step 3_ icon. png Immagine](assets/step3_icon.png) Verifica l'implementazione lato server della suite di rapporti

Verifica se l'inoltro lato server è implementato a livello di report-suite, piuttosto che nell'approccio server di tracciamento legacy.

L'inoltro lato server a livello di report è consigliato rispetto all'approccio del server di tracciamento legacy, in quanto è possibile controllare a un livello più preciso i dati condivisi da Analytics. È anche un prerequisito per questa integrazione di Audience Analytics.

Go to **Analytics** &gt; **Admin** &gt; **Report Suites** &gt; (select **report suites**) &gt; **Edit Settings** &gt; **General** &gt; **Server Side Forwarding**. Se la casella di controllo è:

* **Non attivo** (non è possibile effettuare una selezione o il menu non esiste): non hai le suite di rapporti selezionate mappate all'organizzazione IMS. Assicurati che le suite di rapporti applicabili siano mappate all'interfaccia IMS appropriata utilizzando l'interfaccia utente Mappatura suite [di rapporti](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html).
* **Disattivato**: Non hai attivato il nuovo inoltro lato server. Leggere il contenuto sulla pagina e procedere con l'attivazione della funzione.
* **Attivato**: Ti verrà fornito il provisioning per un nuovo inoltro lato server. Potete anche configurare questa integrazione di Audience Analytics.

<!-- Meike, check Report Suite Mapping UI link above -->

>[!NOTE]
>
>Data will not appear in other Experience Cloud solutions, such as [Audience Manager](https://marketing.adobe.com/resources/help/en_US/aam/c_aam_home.html) or [Audiences](https://marketing.adobe.com/resources/help/en_US/mcloud/audience_library.html) until all 3 steps are complete. Una volta attivata, potrebbero essere necessarie diverse ore per rendere effettive queste impostazioni.

