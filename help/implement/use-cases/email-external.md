---
title: Tracciamento e-mail esterno
description: Utilizza Adobe Analytics per tenere traccia del contenuto delle e-mail.
feature: Implementation Basics
exl-id: 9f7920e0-471c-46bc-9314-7b0a7c93fdce
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '711'
ht-degree: 1%

---

# Tracciamento e-mail esterno

Le aziende utilizzano Analytics per determinare il successo di una campagna e-mail.

[!DNL Analytics] può segnalare i dati di analisi delle campagne e-mail in diverse metriche chiave, tra cui:

| Metrica | Descrizione |
|---|---|
| Clickthrough | Visualizza il numero di click-through tracciati dall’e-mail alla pagina di destinazione. |
| Acquisti e/o successi | Visualizza il numero di acquisti risultanti dall’e-mail. |
| Ordini | Visualizza il numero di ordini inseriti a seguito dell’e-mail. |
| Rendimento | Visualizza l’importo in dollari per visita generato dall’e-mail. |
| Conversione | Visualizza il numero di lead, registrazioni o qualsiasi altro evento di successo generato dall’e-mail. |

Sono necessarie modifiche al corpo dell’e-mail di HTML e alla libreria JavaScript per acquisire le metriche chiave mostrate sopra.

## Implementazione {#section_8A42A8F4A6CD4A1BAF4B9F99F709AF7A}

Sono disponibili diversi passaggi da seguire per visualizzare correttamente i dati di analisi delle campagne e-mail. I passaggi sono descritti come segue:

1. Crea codici di tracciamento univoci.

   Spesso, gli utenti chiedono di tenere traccia dei consigli per ogni campagna univoca. Questo dipende interamente da loro, in base a ciò che funziona meglio. Ogni utente è diverso. L’Adobe consiglia a ogni utente di generare codici di tracciamento descrittivi, come mostrato nell’esempio seguente:

   * sc_cid=A1123A321 > Campagna di affiliazione &quot;A&quot; flag
   * sc_cid=EM033007 > Campagna e-mail flag &quot;EM&quot;
   * sc_cid=GG987123 > &quot;GG&quot; significa Google ed è una campagna di ricerca a pagamento

   Adobe di contatto [!DNL Customer Care] per informazioni dettagliate sull’impostazione e l’utilizzo dei codici di tracciamento.

1. Aggiungi parametri della stringa di query ai collegamenti e-mail di HTML.

   Per tenere traccia del click-through di un utente e degli eventi di successo successivi, è necessario aggiungere un parametro della stringa di query a ciascun collegamento presente nell’e-mail di HTML. Puoi scegliere di tenere traccia di ogni collegamento separatamente o di tutti i collegamenti insieme. Ogni collegamento può avere un codice di tracciamento univoco, oppure tutti i collegamenti possono avere lo stesso codice di tracciamento. Considera il seguente collegamento ipotetico all’interno dell’e-mail a un sito web:

   ```js
   <a href="https://www.example.com/index.asp">Visit our home page</a>
   ```

   Al collegamento di cui sopra devono essere aggiunti i seguenti parametri della stringa di query ?sc_cid=112233B:

   ```js
   <a href= "https://www.example.com/index.asp?sc_cid=112233B">Visit our home page</a>
   ```

1. Aggiorna la libreria JavaScript.

   Modifica del codice nel file JavaScript, [!DNL s_code.js], ti consente di acquisire quanti utenti (e quali utenti) hanno fatto clic sul collegamento dall’e-mail e hanno partecipato a eventi di successo successivi. Sono disponibili due passaggi per aggiornare la libreria JavaScript.

   1. Personalizza [!DNL s_code.js] chiamando [!UICONTROL getQueryParam].

      La [!DNL s_code.js] Il file deve essere posizionato in un percorso del server Web in cui ogni pagina Web può accedervi. La *`doPlugins`* la funzione all’interno di questo file deve essere modificata in modo da acquisire i parametri della stringa di query sui collegamenti e-mail. Ad esempio:

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

      Ogni parametro della stringa di query che deve essere copiato in una variabile deve avere un [!UICONTROL getQueryParam] chiama. Nell’esempio precedente, il parametro della stringa di query [!UICONTROL sc_cid] viene copiato in *`campaign`*.

      Solo la prima chiamata a [!UICONTROL getQueryParam] è necessario per acquisire i click-through. Adobe di contatto [!DNL Customer Care] per implementare questa funzione e verificare che la versione del file JavaScript contenga [!UICONTROL getQueryParam] plug-in.

   1. Assicurati che i tag da Codice a Incolla JavaScript si trovino su tutte le pagine di destinazione. Il codice da incollare deve fare riferimento alla versione di [!DNL s_code.js] modificato nella parte A.

      I seguenti punti sono importanti da ricordare quando si aggiorna la libreria JavaScript. Questi punti sono elencati di seguito.

      * Parametro della stringa di query [!UICONTROL sc_cid] deve essere visibile nell’URL nella pagina di destinazione finale, altrimenti non viene registrata alcuna conversione click-through.
      * La [!UICONTROL sc_cid] è un esempio di parametro di una stringa di query. Qualsiasi parametro della stringa di query può essere utilizzato e acquisito da [!UICONTROL getQueryParam] plug-in. Assicurati che i parametri della stringa di query siano utilizzati solo per il tracciamento della campagna. Ogni volta che i parametri compaiono in una stringa di query, i loro valori vengono copiati in *`campaign`*.

1. Utilizzo [!UICONTROL SAINT] per classificare i codici di tracciamento delle campagne.

   La [!UICONTROL SAINT Campaign Management Tool] può essere utilizzato per convertire i codici di tracciamento in nomi descrittivi. Può essere utilizzato anche per riepilogare il successo di ogni campagna e-mail. Il passaggio 5, di seguito, illustra il processo necessario per impostare una campagna e-mail.

1. Consulta Percorsi per campagna e-mail (facoltativo).

   L’analisi dei percorsi per campagna e-mail può essere eseguita in modo simile al percorso per un’altra campagna. Puoi utilizzare una variabile per visualizzare i percorsi per campagna, come spiegato nei passaggi seguenti:

   1. Consulta l’Adobe [!DNL Customer Care] circa l&#39;attivazione dei percorsi per un [!UICONTROL Custom Insight] variabile (prop)

   1. In tutte le pagine, copia il nome della pagina nel [!DNL s.prop].
   1. Nella pagina di destinazione e-mail, aggiungi il nome della campagna e-mail al prop. Il risultato viene visualizzato come mostrato di seguito:

      ```js
      s.prop1="Home Page : 123456"
      ```

      Quando il percorso è abilitato per la [!UICONTROL Custom Insight] puoi utilizzare [!UICONTROL Path] rapporti, come [!UICONTROL Next Page Flow] o [!UICONTROL Fallout]) per visualizzare la navigazione dei visitatori dalla pagina di destinazione.
