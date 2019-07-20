---
description: Aggiungi o abilita i canali di marketing in Marketing Channel Manager. Per le suite di rapporti che non hanno canali di marketing, una configurazione automatica ti consente di creare diversi canali, insieme alle relative regole. Potete modificare i canali predefiniti in base alle vostre esigenze, oppure creare il vostro (fino a un totale di 25).
seo-description: Aggiungi o abilita i canali di marketing in Marketing Channel Manager. Per le suite di rapporti che non hanno canali di marketing, una configurazione automatica ti consente di creare diversi canali, insieme alle relative regole. Potete modificare i canali predefiniti in base alle vostre esigenze, oppure creare il vostro (fino a un totale di 25).
seo-title: Gestire i canali di marketing
solution: Analytics
subtopic: Canali di marketing
title: Gestire i canali di marketing
topic: Reports & Analytics
uuid: 9 d 367 bb 6-a 17 b -49 b 8-9 cd 5-24 fac 35 ae 982
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Gestire i canali di marketing

Aggiungi o abilita i canali di marketing in Marketing Channel Manager. Per le suite di rapporti che non hanno canali di marketing, una configurazione automatica ti consente di creare diversi canali, insieme alle relative regole. Potete modificare i canali predefiniti in base alle vostre esigenze, oppure creare il vostro (fino a un totale di 25).

## Manage marketing channels {#topic_45CF1C6A783B4F96ABF6317EAB6A854F}

Add or enable marketing channels in the [!UICONTROL Marketing Channel Manager]. Per le suite di rapporti che non hanno canali di marketing, una configurazione automatica ti consente di creare diversi canali, insieme alle relative regole. Potete modificare i canali predefiniti in base alle vostre esigenze, oppure creare il vostro (fino a un totale di 25).

Di seguito sono riportate le linee guida per la creazione di canali:

* Pianifica anticipatamente un elenco di tutti i tuoi canali, in modo che tutti gli hit dei visitatori siano organizzati in categorie al canale giusto.
* Always include channels for the categories of [Internal](../../components/c-marketing-channels/c-faq.md#section_179A2BE5C8E24719A9E5C0DC09AF0947) hits and [Direct](../../components/c-marketing-channels/c-faq.md#section_D0A1DD9D5EEF4A05A1CC81F9EADC074A) hits.

Adding channels to the [!UICONTROL Marketing Channels] page is done independently of creating rules on the [Marketing Channel Processing Rules](../../components/c-marketing-channels/t-rules.md#task_84EDE9F46F404CB9B7CA0537328CEE08) page. Potete associare regole ai canali durante la creazione della regola.

## Add marketing channels {#task_98C9D3F5DBBC4B198E0A9ED4D3891E03}

Aggiungi canali di marketing in Marketing Channel Manager.

>[!NOTE]
>
>Non potete eliminare un canale. Se non desiderate usare un canale, potete disattivarlo o rinominarlo e conservarlo per l'utilizzo successivo.

1. Click **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**.
1. On the [!UICONTROL Report Suite Manager] page, select a report suite.

   Se selezioni più suite di rapporti, seleziona un modello che copia le impostazioni dal modello alle suite di rapporti selezionate.

   See [Apply template report suite settings to multiple report suites](../../components/c-marketing-channels/t-template.md#task_0DE0A320EDA94FC5A6E5912868B6E2DC).

1. Click **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Marketing Channels]** &gt; **[!UICONTROL Marketing Channel Manager]**.

   If your report suite does not have channels defined, the [Auto Setup](../../components/c-marketing-channels/c-channel-autosetup.md#topic_E9ABE9E9E71B4E40A4E7EA9AD2C0372B) page displays.

1. On the [!UICONTROL Marketing Channel Manager] page, click **[!UICONTROL Add Channel]**.

   Questa opzione non è disponibile quando sono stati definiti 25 canali.

1. Fai clic su **[!UICONTROL Save.]**
1. To configure rules for the channel, click **[!UICONTROL Marketing Channel Processing Rules]**.

   See [Create Marketing Channel processing rules](../../components/c-marketing-channels/t-rules.md#task_84EDE9F46F404CB9B7CA0537328CEE08).

## Marketing Channel Manager - interface definitions {#reference_01779A2928054BF48339897D4033AFB9}

Field definitions for the [!UICONTROL Marketing Channel Manager] page.

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
   <td colname="col1"> <p>Override Last-Touch Channel </p> </td> 
   <td colname="col2"> <p> Consente di scegliere se sovrascrivere un canale precedente e permanente costante con il canale selezionato. Se selezionate questa casella di controllo, qualsiasi canale (incluso Diretto e Interno) sovrascrive un ultimo canale di tocco. Il risultato viene convertito in un canale che potrebbe non meritare credito. Ad esempio, questa opzione può garantire che il canale diretto non riceva credito per la conversione se l'utente è stato precedentemente acquisito tramite il canale di ricerca naturale. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Suddivisione canale </p> </td> 
   <td colname="col2"> <p>Consente di suddividere un canale in base a questo valore. Puoi aggiungere possibili suddivisioni dei canali (sottocanali) durante la creazione di classificazioni dei canali di marketing. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Type (Tipo) </p> </td> 
   <td colname="col2"> <p> Specifica in che modo l'utente è entrato nel sito. You can select <span class="uicontrol"> Online</span> or <span class="uicontrol"> Offline</span>. Utilizzate i canali online per i visitatori che arrivano attraverso un motore di ricerca o una campagna e-mail. I canali offline si applicano ai visitatori che hanno trovato il tuo sito tramite i coupon di quotidiani o gli annunci pubblicitari delle riviste. I canali offline includono in genere i dati importati tramite il reporting Origini dati. </p> <p>See <a href="https://marketing.adobe.com/resources/help/en_US/sc/datasources/" scope="external" format="http"> Data Sources</a>. </p> <p>See <a href="../../components/c-marketing-channels/t-offline-data.md#task_FC96E6A48F0D4D37A79BD234E90DAA26" type="task" format="dita" scope="local"> Add Offline Data</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Colore </p> </td> 
   <td colname="col2"> <p>Colore associato a questo canale di marketing. This color represents the channel in the <span class="wintitle"> Marketing Channel</span> report. </p> </td> 
  </tr> 
 </tbody> 
</table>

