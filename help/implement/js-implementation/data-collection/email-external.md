---
description: Le aziende utilizzano Analytics per determinare il successo di una campagna e-mail.
keywords: Implementazione di Analytics
seo-description: Le aziende utilizzano Analytics per determinare il successo di una campagna e-mail.
seo-title: Tracciamento e-mail esterno
solution: Analytics
title: Tracciamento e-mail esterno
topic: Sviluppatore e implementazione
uuid: fa 450 f 45-14 cf -4 d 0 d-a 87 c -14 a 946512 a 9 b
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Tracciamento e-mail esterno

Le aziende utilizzano Analytics per determinare il successo di una campagna e-mail.

[!DNL Analytics] possono riportare i dati di analisi delle campagne e-mail in diverse metriche chiave, inclusi i seguenti:

| Metrica | Descrizione |
|---|---|
| Click-through | Visualizza il numero di click-through tracciate dall'e-mail alla pagina di destinazione. |
| Acquisti e/o successi | Visualizza il numero di acquisti risultanti dall'e-mail. |
| Ordini | Visualizza il numero di ordini inseriti a seguito dell'e-mail. |
| Risultato | Visualizza l'importo in dollari per visita generato dall'e-mail. |
| Conversione   | Visualizza il numero di lead, registrazioni o qualsiasi altro evento di successo generato dall'e-mail. |

Le modifiche al corpo e alla libreria javascript HTML sono necessarie per acquisire le metriche chiave mostrate sopra.

## Implementazione {#section_8A42A8F4A6CD4A1BAF4B9F99F709AF7A}

Esistono diversi passaggi da seguire per visualizzare correttamente i dati di analisi delle campagne e-mail. I passaggi sono descritti di seguito:

1. Crea codici di tracciamento univoci.

   Spesso, gli utenti chiedono di tenere traccia delle raccomandazioni per ogni campagna univoca. Questa funzione è completa, in base al maggior successo. Ogni utente è diverso. Adobe consiglia a ciascun utente di generare codici di tracciamento semplici, come illustrato nell'esempio seguente:

   * sc_ cid = A 1123 A 321 &gt; "A" flags affiliate campaign
   * sc_ cid = EM 033007 &gt; "EM" flag email campaign
   * sc_ cid = GG 987123 &gt; "GG" indica Google ed è una campagna di ricerca pagata
   Contact Adobe [!DNL Customer Care] for details on setting up and using tracking codes.

1. Aggiungete parametri stringa di query ai collegamenti e-mail HTML.

   Per tenere traccia di un click-through utente e di successivi eventi di successo, è necessario aggiungere un parametro stringa query a ogni collegamento nel messaggio e-mail HTML. Puoi scegliere di tenere traccia separatamente di ciascun collegamento o di tenere traccia di tutti i collegamenti. Ogni collegamento può avere un codice di tracciamento univoco, oppure tutti i collegamenti possono avere lo stesso codice di tracciamento. Considerate il seguente collegamento ipotetico all'interno dell'e-mail a un sito Web:

   ```js
   <a href="https://www.mycompany.com/index.asp">Visit our home page</a>
   ```

   I seguenti parametri di stringa query? sc_ cid = 112233 B deve essere aggiunto al collegamento precedente:

   ```js
   <a href= "https://www.mycompany.com/index.asp?sc_cid=112233B">Visit our home page</a>
   ```

1. Aggiornare la libreria javascript.

   Altering code in the JavaScript file, [!DNL s_code.js], lets you capture how many users (and which users) clicked-through from the email and participated in subsequent success events. Esistono due passaggi per aggiornare la libreria javascript.

   1. Customize [!DNL s_code.js] by calling [!UICONTROL getQueryParam].

      [!DNL s_code.js] Il file deve trovarsi in una posizione sul server Web in cui può accedervi ogni pagina Web. The *`doPlugins`* function within this file should be altered so it captures the query string parameters on the email links. Ad esempio:

      ```js
      /* Plugin Config */ 
      s.usePlugins=true 
      function s_doPlugins(s) { 
       /* Add calls to plugins here */ 
       // External Campaigns 
      s.campaign=s.getQueryParam('source') 
      } 
      s.doPlugins=s_doPlugins 
      ```

      Each query string parameter that needs to be copied into a variable should have one [!UICONTROL getQueryParam] call. In the example above, the query string parameter [!UICONTROL sc_cid] is copied into *`campaign`*.

      Only the first call to [!UICONTROL getQueryParam] is required to capture click-throughs. Contact Adobe [!DNL Customer Care] to implement this function and ensure that your version of the JavaScript file contains the [!UICONTROL getQueryParam] plug-in.

   1. Assicurati che i tag Codice da incollare siano su tutte le pagine di destinazione. This Code to Paste must reference the version of [!DNL s_code.js] altered in Part A.

      I punti seguenti sono importanti per ricordare quando si aggiorna la libreria javascript. Questi punti sono elencati di seguito.

      * The query string parameter [!UICONTROL sc_cid] must be visible in the URL on the final landing page otherwise no click-through conversion is recorded.
      * The [!UICONTROL sc_cid] parameter is an example of a query string parameter. Any query string parameter can be used and captured by the [!UICONTROL getQueryParam] plug-in. Verificate che i parametri della stringa query siano utilizzati solo per il tracciamento della campagna. Any time the parameters appear in a query string, their values are copied into *`campaign`*.

1. Use [!UICONTROL SAINT] to classify campaign tracking codes.

   The [!UICONTROL SAINT Campaign Management Tool] can be used to convert tracking codes into user-friendly names. Può essere utilizzato anche per riepilogare il successo di ogni campagna e-mail. Il passaggio 5, sotto, evidenzia il processo necessario per configurare una campagna e-mail.

1. Consultate percorsi per campagna e-mail (facoltativo).

   L'analisi dei percorsi per campagna e-mail può essere eseguita in modo simile ai percorsi da un'altra campagna. Potete utilizzare una variabile per mostrare percorsi per campagna, come descritto nei passaggi seguenti:

   1. Consult Adobe [!DNL Customer Care] about turning on pathing for a [!UICONTROL Custom Insight] variable (prop)

   1. On all pages, copy the page name into the designated [!DNL s.prop].
   1. Nella pagina di destinazione e-mail, aggiungete il nome della campagna e-mail al prop. Il risultato viene visualizzato come mostrato di seguito:

      ```js
      s.prop1="Home Page : 123456"
      ```

      When pathing is enabled for the [!UICONTROL Custom Insight] variable, you can use [!UICONTROL Path] reports (such as [!UICONTROL Next Page Flow] or [!UICONTROL Fallout]) to see visitor navigation from the landing page.

