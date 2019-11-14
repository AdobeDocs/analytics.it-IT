---
description: Le società utilizzano Analytics per determinare il successo di una campagna e-mail.
keywords: Analytics Implementation
solution: Analytics
title: Tracciamento e-mail esterno
topic: Developer and implementation
uuid: fa450f45-14cf-4d0d-a87c-14a946512a9b
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Tracciamento e-mail esterno

Le società utilizzano Analytics per determinare il successo di una campagna e-mail.

[!DNL Analytics] può segnalare i dati di analisi delle campagne e-mail in diverse metriche chiave, tra cui:

| Metrica | Descrizione |
|---|---|
| Clickthrough | Visualizza il numero di clic tracciati dall’e-mail alla pagina di destinazione. |
| Acquisti e/o successi | Visualizza il numero di acquisti risultanti dall’e-mail. |
| Ordini | Visualizza il numero di ordini inseriti come risultato dell'e-mail. |
| Rendimento | Visualizza l’importo in dollari per visita generato dall’e-mail. |
| Conversione | Visualizza il numero di lead, registrazioni o qualsiasi altro evento di successo generato dall’e-mail. |

Per acquisire le metriche chiave indicate sopra, sono necessarie modifiche al corpo e-mail HTML e alla libreria JavaScript.

## Implementazione {#section_8A42A8F4A6CD4A1BAF4B9F99F709AF7A}

Per visualizzare correttamente i dati di analisi delle campagne e-mail, è necessario seguire diversi passaggi. I passaggi descritti di seguito:

1. Crea codici di tracciamento univoci.

   Spesso gli utenti chiedono di tenere traccia delle raccomandazioni per ogni campagna univoca. Questo dipende interamente da loro, in base a ciò che funziona meglio. Ogni utente è diverso. Adobe consiglia a ogni utente di generare codici di tracciamento descrittivi, come illustrato nell'esempio seguente:

   * sc_cid=A1123A321 &gt; Campagna di affiliazione con flag "A"
   * sc_cid=EM033007 &gt; Campagna e-mail con flag "EM"
   * sc_cid=GG987123 &gt; "GG" significa Google ed è una campagna di ricerca a pagamento
   Contatta Adobe [!DNL Customer Care] per informazioni su come impostare e utilizzare i codici di monitoraggio.

1. Aggiungete i parametri delle stringhe di query ai collegamenti e-mail HTML.

   Per tenere traccia di un click-through utente e degli eventi di successo successivi, è necessario aggiungere un parametro della stringa di query a ogni collegamento contenuto nel messaggio e-mail HTML. Potete scegliere di tracciare ciascun collegamento separatamente o di tracciare tutti i collegamenti insieme. Ogni collegamento può avere un codice di tracciamento univoco, oppure tutti i collegamenti possono avere lo stesso codice di tracciamento. Considerate il seguente ipotetico collegamento contenuto nell’e-mail a un sito Web:

   ```js
   <a href="https://www.mycompany.com/index.asp">Visit our home page</a>
   ```

   Al collegamento sopra vanno aggiunti i seguenti parametri della stringa di query ?sc_cid=112233B:

   ```js
   <a href= "https://www.mycompany.com/index.asp?sc_cid=112233B">Visit our home page</a>
   ```

1. Aggiornare la libreria JavaScript.

   Modificando il codice nel file JavaScript [!DNL s_code.js], potete acquisire quanti utenti (e quali utenti) hanno fatto clic nel messaggio e-mail e hanno partecipato a eventi di successo successivi. Esistono due passaggi per aggiornare la libreria JavaScript.

   1. Personalizza [!DNL s_code.js] chiamando [!UICONTROL getQueryParam].

      Il [!DNL s_code.js] file deve essere posizionato in una posizione sul server Web in cui ogni pagina Web può accedervi. La *`doPlugins`* funzione all'interno del file deve essere modificata in modo da acquisire i parametri della stringa di query sui collegamenti e-mail. Ad esempio:

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

      Ogni parametro della stringa di query che deve essere copiato in una variabile deve avere una [!UICONTROL getQueryParam] chiamata. Nell'esempio precedente, il parametro della stringa di query [!UICONTROL sc_cid] viene copiato in *`campaign`*.

      Per acquisire i click-through [!UICONTROL getQueryParam] è necessaria solo la prima chiamata a. Contattate Adobe [!DNL Customer Care] per implementare questa funzione e assicuratevi che la versione del file JavaScript contenga il [!UICONTROL getQueryParam] plug-in.

   1. Assicurarsi che i tag da Codice a Incolla JavaScript siano presenti su tutte le pagine di destinazione. Il codice da incollare deve fare riferimento alla versione [!DNL s_code.js] modificata nella parte A.

      Durante l'aggiornamento della libreria JavaScript è importante tenere presenti i punti seguenti. Tali punti sono elencati di seguito.

      * Il parametro della stringa di query [!UICONTROL sc_cid] deve essere visibile nell’URL della pagina di destinazione finale, altrimenti non viene registrata alcuna conversione click-through.
      * Il [!UICONTROL sc_cid] parametro è un esempio di parametro di una stringa di query. Qualsiasi parametro di stringa di query può essere utilizzato e acquisito dal [!UICONTROL getQueryParam] plug-in. Accertatevi che i parametri della stringa di query siano utilizzati solo per il tracciamento della campagna. Ogni volta che i parametri vengono visualizzati in una stringa di query, i relativi valori vengono copiati in *`campaign`*.

1. Utilizzate [!UICONTROL SAINT] per classificare i codici di tracciamento campagna.

   I codici [!UICONTROL SAINT Campaign Management Tool] possono essere utilizzati per convertire i codici di tracciamento in nomi semplici. Può essere utilizzato anche per riepilogare il successo di ogni campagna e-mail. Il passaggio 5, di seguito, illustra il processo necessario per impostare una campagna e-mail.

1. Consultate il percorso per campagna e-mail (facoltativo).

   L’analisi dei percorsi per campagna e-mail può essere eseguita in modo simile al percorso di un’altra campagna. Potete utilizzare una variabile per visualizzare il percorso per campagna, come illustrato nei passaggi seguenti:

   1. Consultate Adobe [!DNL Customer Care] sull’attivazione del percorso per una [!UICONTROL Custom Insight] variabile (prop)

   1. Su tutte le pagine, copiate il nome della pagina nella pagina designata [!DNL s.prop].
   1. Nella pagina di destinazione e-mail, aggiungete il nome della campagna e-mail al prop. Il risultato viene visualizzato come illustrato di seguito:

      ```js
      s.prop1="Home Page : 123456"
      ```

      Quando il percorso è abilitato per la [!UICONTROL Custom Insight] variabile, puoi utilizzare [!UICONTROL Path] rapporti (come [!UICONTROL Next Page Flow] o [!UICONTROL Fallout]) per visualizzare la navigazione dei visitatori dalla pagina di destinazione.

