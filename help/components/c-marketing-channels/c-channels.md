---
description: Aggiungi o abilita canali di marketing in Marketing Channel Manager. Per le suite di rapporti prive di canali di marketing, una configurazione automatica consente di creare diversi canali per voi, insieme alle relative regole. Potete modificare i canali predefiniti in base alle vostre esigenze o crearne di nuovi (fino a un totale di 25).
seo-description: Aggiungi o abilita canali di marketing in Marketing Channel Manager. Per le suite di rapporti prive di canali di marketing, una configurazione automatica consente di creare diversi canali per voi, insieme alle relative regole. Potete modificare i canali predefiniti in base alle vostre esigenze o crearne di nuovi (fino a un totale di 25).
seo-title: Gestire i canali di marketing
solution: Analytics
subtopic: Canali di marketing
title: Gestire i canali di marketing
topic: Reports and Analytics
uuid: 9d367bb6-a17b-49b8-9cd5-24face35ae982
translation-type: tm+mt
source-git-commit: 57fe1f6d613b9f54a5191ac8684d36bccfebf4e5

---


# Gestire i canali di marketing

Aggiungi o abilita canali di marketing in Marketing Channel Manager. Per le suite di rapporti prive di canali di marketing, una configurazione automatica consente di creare diversi canali per voi, insieme alle relative regole. Potete modificare i canali predefiniti in base alle vostre esigenze o crearne di nuovi (fino a un totale di 25).

Di seguito sono riportate alcune linee guida per la creazione di canali:

* Pianificate in anticipo creando un elenco di tutti i canali, in modo che tutti gli hit visitatore siano organizzati per categorie sul canale giusto.
* Includi sempre canali per le categorie di hit [interni](/help/components/c-marketing-channels/c-faq.md) e [diretti](/help/components/c-marketing-channels/c-faq.md) .

L'aggiunta di canali alla [!UICONTROL Marketing Channels] pagina viene effettuata indipendentemente dalla creazione di regole nella pagina Regole [di elaborazione dei canali](/help/components/c-marketing-channels/t-rules.md) di marketing. Le regole vengono associate ai canali al momento della creazione della regola.

## Aggiunta di canali di marketing {#add-mktg-channels}

Aggiungi canali di marketing in Marketing Channel Manager.

> [!NOTE] Non è possibile eliminare un canale. Se non si desidera utilizzare un canale, è possibile disattivarlo o rinominarlo e conservarlo per un uso successivo.

1. Clic **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**.
1. Sulla [!UICONTROL Report Suite Manager] pagina, seleziona una suite di rapporti.

   Se selezionate più suite di rapporti, selezionate un modello che copia le impostazioni dal modello alle suite di rapporti selezionate.

   See [Apply template report suite settings to multiple report suites](/help/components/c-marketing-channels/t-template.md).

1. Clic **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Marketing Channels]** &gt; **[!UICONTROL Marketing Channel Manager]**.

   Se nella suite di rapporti non sono definiti canali, viene visualizzata la pagina Configurazione [](/help/components/c-marketing-channels/c-channel-autosetup.md) automatica.

1. Sulla [!UICONTROL Marketing Channel Manager] pagina fare clic su **[!UICONTROL Add Channel]**.

   Questa opzione non è disponibile quando sono definiti 25 canali.

1. Fai clic su **[!UICONTROL Save.]**
1. Per configurare le regole per il canale, fai clic su **[!UICONTROL Marketing Channel Processing Rules]**.

   See [Create Marketing Channel processing rules](/help/components/c-marketing-channels/t-rules.md).

## Marketing Channel Manager - Definizioni dell'interfaccia {#mktg-channel-mgr}

Definizioni dei campi per la [!UICONTROL Marketing Channel Manager] pagina.

<table id="table_C18A0F1C9E214EB585A29801BA2400F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Campo </p> </th> 
   <th colname="col2" class="entry"> <p>Definizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Abilitato </p> </td> 
   <td colname="col2"> <p> Abilita o disabilita questo canale di marketing. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nome canale </p> </td> 
   <td colname="col2"> <p>Il nome descrittivo del canale di marketing. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ignora ultimo canale di tocco </p> </td> 
   <td colname="col2"> <p> Consente di scegliere se ignorare un canale esistente persistente con il canale selezionato. Se selezionate questa casella di controllo, qualsiasi canale (inclusi Diretto e Interno) sovrascrive un canale dell’ultimo tocco esistente. Il risultato è che la conversione viene attribuita a un canale che potrebbe non meritare credito. Ad esempio, questa opzione può garantire che il canale Direct non riceva credito per la conversione se l'utente era stato precedentemente acquisito tramite il canale di ricerca naturale. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Suddivisione canale </p> </td> 
   <td colname="col2"> <p>Consente di suddividere un canale per questo valore. Puoi aggiungere possibili analisi dei canali (canali secondari) durante la creazione di classificazioni dei canali di marketing. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Type (Tipo) </p> </td> 
   <td colname="col2"> <p> Specifica in che modo l’utente è arrivato sul sito. Potete selezionare <span class="uicontrol"> Online</span> o <span class="uicontrol"> Offline</span>. Utilizza i canali online per i visitatori che passano attraverso un motore di ricerca o una campagna e-mail. I canali offline si applicano ai visitatori che hanno trovato il tuo sito tramite annunci pubblicitari di giornali o riviste. I canali offline in genere includono i dati importati tramite Origini dati di reporting. </p> <p>Vedere <a href="https://marketing.adobe.com/resources/help/en_US/sc/datasources/"  > Origini</a>dati. </p> <p>See <a href="/help/components/c-marketing-channels/t-offline-data.md"   > Add Offline Data</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Colore </p> </td> 
   <td colname="col2"> <p>Colore associato a questo canale di marketing. Questo colore rappresenta il canale nel report <span class="wintitle"> Marketing Channel</span> . </p> </td> 
  </tr> 
 </tbody> 
</table>

