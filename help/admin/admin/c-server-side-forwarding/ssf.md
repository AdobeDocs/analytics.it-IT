---
description: L’inoltro lato server è progettato per i clienti che vogliono condividere in tempo reale dati da Analytics ad altre soluzioni Experience Cloud. Se abilitato, l’inoltro lato server consente ad Analytics di trasmettere i dati ad altre soluzioni Experience Cloud e a queste di trasmetterli ad Analytics durante il processo di raccolta dei dati.
solution: Analytics
title: Panoramica sull’inoltro lato server
feature: Server-Side Forwarding
exl-id: e3cd72d2-9588-4770-a7c2-64b13a1e9519
source-git-commit: ee56267979979f8e03b1c6a0d849ccf994599024
workflow-type: tm+mt
source-wordcount: '821'
ht-degree: 100%

---

# Panoramica sull’inoltro lato server

L’inoltro lato server è progettato per i clienti che vogliono condividere in tempo reale dati da Analytics ad altre soluzioni Experience Cloud. Se abilitato, l’inoltro lato server consente ad Analytics di trasmettere i dati ad altre soluzioni Experience Cloud e a queste di trasmetterli ad Analytics durante il processo di raccolta dei dati.

L’inoltro lato server migliora la raccolta dati perché:

* Riduce le chiamate dalla pagina. Con l’inoltro lato server, i clienti di [!DNL Audience Manager] non dovranno più utilizzare DIL per la raccolta dati, in quanto questi vengono inoltrati da Analytics. La rimozione di DIL comporta l’eliminazione di una chiamata `"/event"`. Un numero inferiore di chiamate consente di migliorare i tempi di caricamento della pagina, assicurando una migliore esperienza del cliente sul sito.
* Consente di sfruttare la condivisione dati tra soluzioni Experience Cloud.
* Rispetta le nostre best practice per l’implementazione e la distribuzione del codice di Audience Manager.

>[!TIP]
>
>Gli attuali clienti di Audience Manager che utilizzano Analytics devono eseguire la migrazione ala funzione di inoltro lato server. I nuovi clienti Adobe Analytics e Audience Manager devono implementare l’inoltro lato server (anziché DIL) come metodo predefinito per la raccolta e il trasferimento dei dati.

>[!IMPORTANT]
>In base al regolamento UE sulla conformità dei cookie, i titolari del trattamento dei dati (clienti Analytics) hanno ora la possibilità di limitare i dati divulgati prima del consenso ad Adobe Analytics e di impedire che vengano inoltrati dal server ad Adobe Audience Manager (AAM). Una nuova variabile di contesto dell’implementazione consente di contrassegnare ogni hit per cui non è stato ricevuto il consenso. La variabile, se impostata, impedisce che tali hit vengano inviati ad AAM finché non sia stato ricevuto il consenso. Per ulteriori informazioni, consulta [Conformità RGPD_ePrivacy e inoltro lato server](/help/admin/admin/c-server-side-forwarding/ssf-gdpr.md).

Per individuare la posizione della tua organizzazione in termini di implementazione dell’inoltro lato server, segui questi passaggi di convalida:

## ![immagine step1_icon.png](assets/step1_icon.png) Verificare l’implementazione del servizio ECID

Verifica se il servizio Experience Cloud ID (ECID) è implementato, esaminando la [richiesta di tracciamento di Analytics](https://experienceleague.adobe.com/docs/id-service/using/implementation/test-verify.html?lang=it).

Nella scheda Request (Richiesta), verifica che sia impostato un valore ECID. Ciò indica che il servizio Identity, prerequisito per l’inoltro lato server, è implementato correttamente.

* Se trovi un valore ECID, procedi al passaggio 2.
* Se non trovi un valore ECID, [implementa il servizio Identity](https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-guides.html?lang=it) prima di procedere al passaggio 2.

## ![immagine step2_icon.png](assets/step2_icon.png) Verificare la versione di implementazione di Inoltro lato server

Verifica di disporre di una versione della funzione di inoltro lato server implementata, [esaminando la richiesta di tracciamento di Analytics](/help/admin/admin/c-server-side-forwarding/ssf-verify.md).

Nella scheda “Response” (Risposta), verifica che la risposta contenga dati di Audience Manager. Se trovi:

* Una **risposta JSON da Audience Manager che include elementi come “postback” o “dcs_region”**: è già stato abilitato un qualche tipo di inoltro lato server. Procedi al passaggio 3.
* **&quot;status&quot;:&quot;SUCCESS&quot;**: hai implementato il modulo Audience Management, ma l’inoltro lato server non è stato configurato correttamente. Procedi al passaggio 3.
* Un’**immagine 2 x 2**: l’inoltro lato server o il modulo Audience Management non è stato implementato. Per risolvere il problema:

   * **Clienti AAM con DIL**: coordina le seguenti due operazione in stretta congiunzione:

      1. Rimuovi il codice DIL e installa il codice della pagina del [modulo Audience Management](https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html?lang=it).
      1. Abilita l’inoltro lato server nell’interfaccia utente di amministrazione di Analytics, come indicato al passaggio 3. Se abiliti l’impostazione prima di rimuovere il codice DIL, i dati verranno duplicati e verranno create chiamate server fatturate aggiuntive per Audience Manager.
   * **Nuovi clienti AAM**: installa il codice della pagina del [modulo Audience Management](https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html) e procedi al passaggio 3. I dati verranno inviati ad Audience Manager solo dopo l’attivazione dell’inoltro lato server al passaggio 3.


## ![immagine step3_icon.png](assets/step3_icon.png) Verificare l’implementazione lato server della suite di rapporti

Verifica che l’inoltro lato server sia stato implementato a livello della suite di rapporti, anziché l’approccio precedente basato sul server di tracciamento.

L’inoltro lato server a livello della suite di rapporti è consigliato rispetto al precedente approccio per il server di tracciamento, in quanto consente di controllare in modo più preciso quali dati vengono condivisi da Analytics. Inoltre, è un prerequisito per l’integrazione di Audience Analytics.

Vai a **Analytics** > **Admin** > **Report Suites** > (seleziona una **suite di rapporti**) > **Edit Settings** > **General** > **Server Side Forwardin** (Modifica impostazioni > Generale > Inoltro lato server). Se la casella di controllo è:

* **Inattiva** (non disponibile o non selezionabile): non hai eseguito la mappatura delle suite di rapporti selezionate su un’organizzazione IMS. Contatta l’Assistenza clienti per assicurarti che la mappatura della suite di rapporti sia corretta.
* **Disabilitata**: non hai attivato la nuova funzione di inoltro lato server. Leggi il contenuto della pagina, quindi procedi all’abilitazione della funzione.
* **Abilitata**: è stato effettuato il provisioning per la nuova funzione di inoltro lato server. Puoi anche configurare questa integrazione di Audience Analytics.

>[!NOTE]
>
>I dati non verranno visualizzati in altre soluzioni Experience Cloud, come [Audience Manager](https://experienceleague.adobe.com/docs/audience-manager/user-guide/aam-home.html?lang=it) o [Audiences](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=it) fino al completamento di tutti e 3 i passaggi. Una volta abilitata, l’applicazione delle impostazioni richiederà alcune ore.
