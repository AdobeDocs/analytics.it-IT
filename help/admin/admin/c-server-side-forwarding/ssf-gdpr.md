---
description: nulle
title: Conformità GDPR/ePrivacy e inoltro lato server
uuid: 1b90c567-3321-4dbd-a699-38c04e809fa4
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Conformità GDPR/ePrivacy e inoltro lato server

In questa sezione sono illustrati i recenti miglioramenti all'inoltro lato server, che sono stati introdotti dalla normativa [](https://ec.europa.eu/ipg/basics/legal/cookies/index_en.htm)UE sulla conformità ai cookie, entrata in vigore il 30 settembre 2017.

L'inoltro lato server viene utilizzato per condividere in tempo reale i dati da Adobe Analytics ad altri [!DNL Experience Cloud Solutions], come Audience Manager. Se abilitata, l'inoltro lato server consente anche ad Analytics di inviare dati ad altre soluzioni Experience Cloud e a queste soluzioni di inviare dati in push ad Analytics durante il processo di raccolta dei dati.

Fino a poco tempo fa, l'inoltro lato server non aveva un modo per delineare tra eventi/hit di consenso e pre-consenso. A partire dal 1° novembre 2018, il titolare del trattamento dei dati (cliente Adobe Analytics) ha la possibilità di limitare il consenso preventivo ad Adobe Analytics e impedire che venga inoltrato ad AAM. Una nuova variabile di contesto dell'implementazione consente di contrassegnare le richieste dove non è stato ricevuto il consenso. La variabile, quando impostata, impedisce che queste richieste vengano inviate all'AAM fino al ricevimento del consenso.

Quando questa nuova variabile di contesto `cm.ssf=1`, esiste in un hit, l’hit viene contrassegnato e non viene inoltrato ad AAM sul lato server. Al contrario, se questa stringa non viene visualizzata su un hit, l’hit viene inoltrato ad AAM.

L'inoltro lato server è bidirezionale, il che significa che quando viene applicato a un hit e l'hit viene inoltrato ad AAM, Audience Analytics riceve le informazioni sul segmento per quell'hit da AAM e lo invia nuovamente ad Analytics. Di conseguenza, eventuali hit non inoltrati sul lato server da Analytics ad AAM non saranno arricchiti con l’elenco degli ID del segmento da AAM. Di conseguenza, sarà presente un sottoinsieme di hit/traffico che non riceverà informazioni ID segmento da AAM.

## Dettagli implementazione {#section_FFA8B66085BF469FAB5365C944FE38F7}

A seconda del metodo di implementazione, attenetevi alla seguente procedura.

| Metodo di implementazione | Passaggi |
|--- |--- |
| Adobe Experience Platform Launch | Se avete installato l’estensione Adobe Analytics, aggiungete la seguente definizione di variabile di dati di contesto all’editor di codice personalizzato nella configurazione Azione di una regola: <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` <br/>Nota:  Definite la variabile contextdata e impostatela su 1 se il cliente non acconsente al marketing di destinazione. Impostate la `contextdata` variabile su *0* per i clienti che hanno acconsentito al marketing di destinazione. |
| DTM | Aggiungi la definizione della variabile di dati contestuali all’editor del codice pagina personalizzato: <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` <br/>Nota:  Definite la variabile contextdata e impostatela su 1 se il cliente non acconsente al marketing di destinazione. Impostate la variabile contextdata su 0 per i clienti che hanno acconsentito al marketing di destinazione. |
| AppMeasurement | Aggiungi la definizione della variabile di dati contestuali al file AppMeasurement.js: <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` <br/>Nota:  Definite la variabile contextdata e impostatela su 1 se il cliente non acconsente al marketing di destinazione. Impostate la variabile contextdata su 0 per i clienti che hanno acconsentito al marketing di destinazione. |

## Reporting (facoltativo) {#section_6AD4028EC11C4DABA2A34469DDC99E89}

Puoi utilizzare Adobe Analytics per segnalare la quantità di traffico basata sul consenso e, di conseguenza, il traffico è stato inoltrato sul lato server, rispetto alla quantità di traffico non basata sul consenso e non è stata inoltrata ad AAM.

Per configurare questo tipo di rapporto, mappate la nuova variabile di contesto su una variabile di traffico personalizzata (prop) tramite le regole di elaborazione. Per eseguire questa operazione

1. Implementate la variabile "cm.ssf" (come mostrato sopra).
1. [Abilitate la proprietà.](/help/admin/admin/c-traffic-variables/traffic-var.md)
1. Utilizzare le regole di elaborazione per mappare la variabile di contesto alla proprietà.

   1. Vai a **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]** , quindi seleziona una suite di rapporti.
   1. Clic  **[!UICONTROL Edit Report Suite]** &gt; **[!UICONTROL General]** &gt; **[!UICONTROL Processing Rules]** .
   1. Fai clic su **[!UICONTROL Add Rule.]**
   1. In **[!UICONTROL Always Execute]** questa sezione, sovrascrivete il valore del prop attivato con la variabile di contesto "cm.ssf(Context Data)".
   1. Fai clic su **[!UICONTROL Save]**.

