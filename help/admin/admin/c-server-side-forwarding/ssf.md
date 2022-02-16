---
description: L’inoltro lato server è progettato per i clienti che desiderano condividere in tempo reale dati da Analytics ad altre soluzioni Experience Cloud. Quando abilitato, l’inoltro lato server consente ad Analytics di inviare dati push ad altre soluzioni Experience Cloud e a queste soluzioni di inviare dati in Analytics durante il processo di raccolta dei dati.
solution: Analytics
title: Panoramica sull'inoltro lato server
feature: Server-Side Forwarding
exl-id: e3cd72d2-9588-4770-a7c2-64b13a1e9519
source-git-commit: ee56267979979f8e03b1c6a0d849ccf994599024
workflow-type: tm+mt
source-wordcount: '821'
ht-degree: 12%

---

# Panoramica sull&#39;inoltro lato server

L’inoltro lato server è progettato per i clienti che desiderano condividere in tempo reale dati da Analytics ad altre soluzioni Experience Cloud. Quando abilitato, l’inoltro lato server consente ad Analytics di inviare dati push ad altre soluzioni Experience Cloud e a queste soluzioni di inviare dati in Analytics durante il processo di raccolta dei dati.

L&#39;inoltro lato server migliora la raccolta dati perché:

* Riduce le chiamate dalla pagina. Con inoltro lato server, [!DNL Audience Manager] i clienti non devono più utilizzare DIL per la raccolta dati perché viene inoltrato da Analytics. Rimuovere DIL significa eliminare un `"/event"` chiama. Con un numero inferiore di chiamate è possibile migliorare i tempi di caricamento delle pagine, garantendo al cliente una migliore esperienza sul sito.
* Consente di sfruttare la condivisione di dati tra le soluzioni Experience Cloud.
* È conforme alle nostre best practice per l’implementazione e la distribuzione del codice di Audience Manager.

>[!TIP]
>
>I clienti attuali di Audience Manager che utilizzano Analytics devono migrare all’inoltro lato server. I nuovi clienti Adobe Analytics ed Audience Manager devono implementare l’inoltro lato server (anziché DIL) come metodo predefinito di raccolta e trasferimento dei dati.

>[!IMPORTANT]
>In base al regolamento UE sulla conformità ai cookie, i titolari del trattamento dei dati (clienti Analytics) hanno ora la possibilità di limitare i dati divulgati prima del consenso ad Adobe Analytics e di impedire che vengano inoltrati al server ad Adobe Audience Manager (AAM). Una nuova variabile di contesto dell&#39;implementazione consente di contrassegnare le richieste dove non è stato ricevuto il consenso. La variabile, quando impostata, impedisce che queste richieste vengano inviate all&#39;AAM fino al ricevimento del consenso. Per ulteriori informazioni, consulta [Conformità a RGPD_ePrivacy e inoltro lato server](/help/admin/admin/c-server-side-forwarding/ssf-gdpr.md).

Per capire dove si trova la tua organizzazione in termini di implementazione dell&#39;inoltro lato server, segui questi passaggi di convalida:

## ![immagine step1_icon.png](assets/step1_icon.png) Verificare l’implementazione del servizio ECID

Verifica se il servizio Experience Cloud ID (ECID) è implementato, controllando il [Richiesta di tracciamento di Analytics](https://experienceleague.adobe.com/docs/id-service/using/implementation/test-verify.html?lang=it).

Nella scheda Request (Richiesta), verifica che sia impostato un valore ECID. Questo indica che il servizio Identity è implementato correttamente, il che è un prerequisito per l’inoltro lato server.

* Se viene visualizzato un valore ECID, continuare con il passaggio 2.
* Se non viene visualizzato un valore ECID, [implementare il servizio Identity](https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-guides.html) prima di procedere alla fase 2.

## ![immagine step2_icon.png](assets/step2_icon.png) Verifica della versione di implementazione lato server

Verifica di disporre di una versione dell&#39;inoltro lato server implementata, tramite [ispezione della richiesta di tracciamento di Analytics](/help/admin/admin/c-server-side-forwarding/ssf-verify.md).

Nella scheda &quot;Risposta&quot;, controlla che la risposta contenga dati di Audience Manager. Se vedi:

* A **Risposta JSON da un Audience Manager che include elementi come &quot;postback&quot; o &quot;dcs_region&quot;**: hai già abilitato alcune forme di inoltro lato server. Procedi al punto 3.
* La **&quot;status&quot;:&quot;SUCCESS&quot;**: hai implementato il modulo Gestione dell&#39;audience, ma non hai configurato correttamente l&#39;inoltro lato server. Procedi al punto 3.
* A **2 x 2 immagini**: non hai implementato l&#39;inoltro lato server o il modulo Gestione dell&#39;audience. Per correggere il problema:

   * **Clienti AAM con DIL**: coordinare in stretto collegamento i due elementi seguenti:

      1. Rimuovi il codice DIL e installa il [Modulo Gestione dell&#39;audience](https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html?lang=it) codice della pagina.
      1. Abilita l’inoltro lato server nell’interfaccia utente di amministrazione di Analytics come descritto al passaggio 3. Se abiliti questa impostazione prima di rimuovere il codice DIL, i dati verranno duplicati e verranno create chiamate server fatturate aggiuntive per Audience Manager.
   * **Nuovi clienti AAM** - installare [Modulo Gestione dell&#39;audience](https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html) codice della pagina e continuare al passaggio 3. I dati verranno inviati ad Audience Manager solo dopo l&#39;attivazione dell&#39;inoltro lato server al passaggio 3.


## ![immagine step3_icon.png](assets/step3_icon.png) Verifica dell&#39;implementazione lato server della suite di rapporti

Verifica di avere implementato l&#39;inoltro lato server a livello di suite di rapporti, anziché l&#39;approccio legacy al server di tracciamento.

L’inoltro lato server a livello di suite di rapporti è consigliato rispetto all’approccio server di tracciamento legacy, perché puoi controllare a un livello più preciso quali dati vengono condivisi da Analytics. È anche un prerequisito per questa integrazione di Audience Analytics.

Vai a **Analytics** > **Amministratore** > **Suite di rapporti** > (seleziona **suite di rapporti**) > **Modifica impostazioni** > **Generale** > **Server Side Forwarding**. Se la casella di controllo è:

* **Inattivo** (Impossibile effettuare una selezione o il menu non esiste): le suite di rapporti selezionate non sono mappate su un’organizzazione IMS. Contatta l’Assistenza clienti per assicurarti che la suite di rapporti sia mappata correttamente.
* **Disabilitato**: Il nuovo inoltro lato server non è attivato. Leggi il contenuto della pagina e continua ad abilitare la funzione.
* **Abilitato**: È stato effettuato il provisioning per un nuovo inoltro lato server. Puoi anche configurare questa integrazione di Audience Analytics.

>[!NOTE]
>
>I dati non verranno visualizzati in altre soluzioni di Experience Cloud, come [Audience Manager](https://docs.adobe.com/content/help/it-IT/experience-cloud/user-guides/home.translate.html) o [Tipi di pubblico](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html) fino al completamento di tutti e 3 i passaggi. Una volta abilitate, saranno necessarie diverse ore prima che queste impostazioni abbiano effetto.
