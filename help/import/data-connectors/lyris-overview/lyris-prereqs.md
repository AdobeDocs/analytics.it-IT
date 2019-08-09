---
description: Descrive i prerequisiti per l'integrazione con successo.
seo-description: Descrive i prerequisiti per l'integrazione con successo.
seo-title: Prerequisiti per l'integrazione
solution: Analytics
title: Prerequisiti per l'integrazione
uuid: ac 93 bf 4 d-a 071-4 fac -9 d 42-c 4856463 cbb 6
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Prerequisiti per l'integrazione{#integration-prerequisites}

Descrive i prerequisiti per l'integrazione con successo.

Prima di attivare questa integrazione, controllate i seguenti elementi in relazione alle implementazioni di Adobe Analytics e del software e-mail.

Questo garantisce che le best practice e i prerequisiti appropriati siano inseriti prima dell'attivazione, il che darà luogo a un'integrazione ottimale e riuscita.

## Prerequisiti per Adobe Analytics {#section-ddb9d4f3b283438ea33788f47f35e69a}

* **Report-Suite specific**: Attenzione: questa integrazione è specifica per la suite di rapporti. Verificate di aver selezionato la suite di rapporti desiderata prima di attivare l'integrazione
* **Variabili Analytics disponibili e configurate**: Questa integrazione richiede eventi personalizzati e evar personalizzati ed eventualmente altri eventi e evar aggiuntivi.

   Consultate [Configurare le variabili di Analytics per Lyris](../lyris-overview/lyris-analytics-variables.md#task-e70a62dc096d4f548d5070a67822f5e7)

* **Rappresentante autorizzato**: Tieni presente che l'abilitazione di questa integrazione potrebbe causare il sequestro delle tariffe da parte della società in conformità con l'accordo di servizio con Adobe, Inc. o con il tuo contratto di servizio con uno dei partner affidabili di Adobe, a seconda delle necessità. L'attivazione di questa integrazione vi rappresenta un rappresentante autorizzato della società, e, come tali, la società accetta di pagare le eventuali quote nel contratto di servizio descritto in precedenza.
* **Data warehouse di Adobe Analytics**: Questa integrazione richiede l'attivazione del data warehouse di Adobe Analytics per generare segmenti di ricommercializzazione. Se non hai attivato il data warehouse, contatta Adobe per ulteriori dettagli.
* **ID destinatario**: L'integrazione richiede l'acquisizione e l'archiviazione di un «ID visitatore» all'interno di una variabile di Analytics (evar). L'ID visitatore (spesso denominato "ID destinatario") è una rappresentazione codificata o numerica di un indirizzo e-mail dal sistema Lyris. Questo "ID destinatario" è associato al comportamento dei visitatori a valle sul sito (carrello, acquisti, ecc.) che viene nuovamente reinserito nel sistema Lyris e può essere sfruttato a scopo di ricommercializzazione. Come parte del processo di configurazione, quando richiesto dalla procedura guidata devi identificare un evar a questo scopo.
* **Tracciamento esterno**: Se non state seguendo la procedura ottimale per abilitare il tracciamento esterno per ogni campagna e-mail inviata, dovete farlo per garantire un'integrazione corretta. Consulta la sezione Lyris di seguito per i dettagli
* **Conformità alla privacy**: È importante comprendere che abilitando il tracciamento ID visitatore o visitatore, questa funzione potrebbe tenere traccia delle informazioni personali di visitatori del sito. Ciò ha implicazioni sulla privacy, che richiedono l'implementazione di procedure appropriate dall'organizzazione, ad esempio fornire avviso e autorizzare i visitatori del sito.

## Prerequisiti per Lyris emaillabs {#section-84abae9401224a3699fed861f715ebde}

* **Account Lyris valido**: Per utilizzare questa integrazione con il Connettore dati, è necessario disporre di un account Lyris valido.
* **Informazioni account**: Durante questa configurazione dell'integrazione dovrete disporre delle seguenti informazioni sull'account Lyris:

   * *Chiave API di Lyris*: Utilizzata per la popolazione dati
   * *Parametri stringa query*: Questi vengono aggiunti nell'URL della pagina di destinazione per ID messaggio e ID destinatario (ID visitatore).
   * *Server/URL Lyris*: Il valore del server utilizzato nel sistema Lyris
   * *ID sito Lyris*: Noto anche come "ID cliente", questo è il valore univoco per l'istanza di Lyris HQ. Questo può essere presente in «Informazioni sul cliente» nella sezione «Home dell'account» di emaillabs.

