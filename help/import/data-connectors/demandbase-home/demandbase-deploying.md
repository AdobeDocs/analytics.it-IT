---
description: La distribuzione di questa integrazione è un processo semplice che richiede le seguenti azioni.
title: Distribuzione dell'integrazione
uuid: 9c116ca8-4dbf-44eb-a832-574527ee88b7
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '1304'
ht-degree: 1%

---


# Distribuzione dell&#39;integrazione{#deploying-the-integration}

La distribuzione di questa integrazione è un processo semplice che richiede le seguenti azioni.

## Completamento della procedura guidata di integrazione di Adobe{#completing-the-adobe-integration-wizard}

Per attivare l&#39;integrazione, è necessario completare la procedura guidata di configurazione all&#39;interno dell&#39;interfaccia Connettori dati.

1. Passa all&#39;area Connettori dati (precedentemente Genesis) in Adobe Experience Cloud.
1. Avviate la procedura guidata di integrazione Demandbase 2.0.
1. Scegliete la suite di rapporti desiderata e specificate un nome per l&#39;integrazione.
1. Configurate i seguenti elementi:

<table id="table_8D60DC7C48C144DC9934749E7F9F65FF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Indirizzo e-mail </td> 
   <td colname="col2"> L'indirizzo e-mail del contatto principale. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Descrizione </td> 
   <td colname="col2"> (Facoltativo) Descrizione per questa configurazione di integrazione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Chiave API Demandbase </td> 
   <td colname="col2"> Puoi ottenere questo dal tuo rappresentante Demandbase. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimensione Demandbase personalizzata #N </td> 
   <td colname="col2"> Questi sono gli ID per le 8 dimensioni facoltative. Per ulteriori informazioni, vedere Demandbase Custom Dimensions. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Invia a  Adobe Target </td> 
   <td colname="col2">Se è "true", anche le dimensioni Demandbase vengono inviate al Adobe Target  utilizzando una mbox nascosta. <p>Nota:  Per poter raccogliere le dimensioni, è necessario implementare un file mbox.js configurato sulla pagina Web. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Configura i seguenti elementi di mappatura variabili:

   | Elemento | Descrizione |
   |---|---|
   | Dimensioni Demandbase | Scegli una variabile eVar disponibile dalla suite di rapporti. |
   | Dimensioni personalizzate Demandbase (facoltativo) | Scegli una variabile eVar disponibile dalla suite di rapporti. |

1. Configura i nomi per la Dimensione personalizzata (se applicabile).

   1. Se al punto 4 avete scelto di includere le dimensioni personalizzate e mappato l&#39;eVar opzionale al punto 5, dovete fornire nomi descrittivi per tali dimensioni. Ad esempio, se si sceglie di immettere &quot;stock_ticker&quot; come Dimensione personalizzata 1, è necessario modificare la casella contenente &quot;Dimension 1&quot; in &quot;Stock Ticker&quot;.
   1. NON **modificate** i nomi delle dimensioni standard 8 (ad es. Demandbase SID, Nome società, Industria, ecc.).

1. Selezionare la casella per creare automaticamente il dashboard Integrazione Demandbase (consigliato).
1. Rivedete tutti gli elementi di configurazione e fate clic su **[!UICONTROL Activate Now]**.

## Distribuzione del codice di integrazione{#deploying-the-integration-code}

Dopo aver completato la procedura guidata di integrazione, dovete distribuire il codice di integrazione nel codice di distribuzione Adobe  Analytics (s_code).

>[!NOTE]
>
>Se avete utilizzato Adobe TagManager o Gestione tag dinamica per distribuire Adobe  Analytics, potete aggiungere facilmente il codice di integrazione utilizzando uno di questi strumenti.

1. Passate alla **[!UICONTROL Support]** scheda e scaricate e salvate la `integration code v2_0_1` risorsa dall&#39;area Risorse dell&#39;integrazione.

1. Se del caso, apportare le modifiche necessarie al codice. Per ulteriori informazioni, consultate Modifica del codice di integrazione (in questa pagina).
1. Includete il modulo Integrate se non è già presente nel codice di distribuzione Adobe  Analytics.
1. Distribuite il codice utilizzando uno dei seguenti metodi:

   * Utilizza Adobe TagManager o Gestione tag dinamica per aggiungere il codice.
   * In alternativa, distribuisci il codice alla risorsa organizzativa incaricata di aggiornare il codice di distribuzione Adobe  Analytics.

>[!IMPORTANT]
>
>Prima di distribuirla in un ambiente di produzione, verificate che la distribuzione dell&#39;integrazione sia verificata in un ambiente di sviluppo/pre-produzione.

## Modifica del codice di integrazione{#modifying-the-integration-code}

Nella maggior parte dei casi, non sarà necessario apportare alcuna modifica al codice di integrazione prodotto dalla procedura guidata Connettore dati.

Tuttavia, se è necessario apportare delle modifiche, alcune delle impostazioni del codice sono descritte di seguito.

<table id="table_5405A73CEFD44466B3C39559F4A037C9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Impostazione codice </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> s.maxDelay </td> 
   <td colname="col2">Il numero massimo di millisecondi per cui la richiesta di immagini Adobe  Analytics attenderà i dati Demandbase prima di essere attivata sul server di raccolta  Analytics. <p>Nota:  Questa impostazione si applica a tutte le integrazioni che potrebbero essere in esecuzione tramite il modulo Integrate. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db._key </td> 
   <td colname="col2"> La chiave API Demandbase. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db._apiURL </td> 
   <td colname="col2"> Modello URL per l'API Demandbase. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db._delim </td> 
   <td colname="col2"> Il delimitatore utilizzato per separare i valori delle dimensioni Demandbase quando vengono inviati ad Adobe  Analytics. Modificando questa impostazione è possibile che le regole di classificazione predefinite non funzionino correttamente. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db._setTnt </td> 
   <td colname="col2">Se true, il codice di integrazione tenterà di utilizzare una mbox nascosta per inviare le dimensioni Demandbase al Adobe Target  come parametri di profilo. <p>Nota:  Ciò richiede che il codice mbox.js esista sulla pagina. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db._tntVarPrefix </td> 
   <td colname="col2"> Questa stringa viene anteposta al nome di ogni dimensione Demandbase prima dell'invio a  Adobe Target. Ad esempio, se questa impostazione ha il valore "db_", la dimensione "industria" verrà inviata al Adobe Target  come "db_Industry". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db._DimensionsArray </td> 
   <td colname="col2"> Le dimensioni standard di Demandbase inviate ad Adobe  Analytics. È consigliabile non modificare questa impostazione. La proprietà "max_size" è il numero di caratteri consentiti per la dimensione prima del troncamento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db._DimensionsArrayCustom </td> 
   <td colname="col2"> Le dimensioni Demandbase personalizzate che vengono inviate ad Adobe  Analytics. La proprietà "max_size" è il numero di caratteri consentiti per la dimensione prima del troncamento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db._cName </td> 
   <td colname="col2"> Nome del cookie di sessione utilizzato per mantenere lo stato per la comunicazione API Demandbase. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db._contextName </td> 
   <td colname="col2"> Nome della variabile contextData utilizzata per inviare le dimensioni standard ad Adobe  Analytics. È consigliabile non modificare questa impostazione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db._contextNameCustom </td> 
   <td colname="col2"> Nome della variabile contextData utilizzata per inviare le dimensioni personalizzate ad Adobe  Analytics. È consigliabile non modificare questa impostazione. </td> 
  </tr> 
 </tbody> 
</table>

## Inclusione del modulo Integrate{#including-the-integrate-module}

Il codice di integrazione richiede che il modulo Integrate sia presente nella distribuzione Adobe  Analytics.

Se non disponete già del modulo Integrate come parte della distribuzione, completate i seguenti passaggi a seconda del tipo di implementazione disponibile.

### Per AppMeasurement v1.0+ {#section-f28d090bf2404cabaae34cd9c66fc575}

1. Decomprimete il file zip AppMeasurement scaricato da **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL CodeManager]**.

1. Aprire il file denominato [!DNL AppMeasurement_Module_Integrate.js].
1. Copiate e incollate il contenuto di questo file nel [!DNL AppMeasurement.js] file principale.

   >[!NOTE]
   >
   >Incollarla immediatamente prima del commento NON MODIFICARE NULLA SOTTO QUESTA RIGA all&#39;interno del file.

### Per codice legacy (H-code) {#section-bba8ad8c715e4f97883e7de3269f681a}

1. Scaricate il modulo Integrate dall&#39;area &quot;Risorse&quot; nell&#39;interfaccia utente dei Connettori dati (nella scheda Assistenza).

   ![](assets/h_code.png)

1. Copiare e incollare il contenuto di tale file nel [!DNL s_code] file.

   >[!NOTE]
   >
   >Incollarla immediatamente prima del commento NON MODIFICARE NULLA SOTTO QUESTA RIGA all&#39;interno del file.

## Verifica dell&#39;integrazione{#verifying-the-integration}

Verificare che l&#39;integrazione acquisisca correttamente i dati controllando il tracciamento live e la generazione di rapporti.

### Tracciamento live {#section-9c20e8ff6b404ae09387ee07d675c9e2}

Utilizzate lo strumento DigitalPulse Debugger per verificare che i dati della dimensione Demandbase vengano inviati ad Adobe  Analytics. Dopo aver eliminato i cookie, ricaricate una pagina del sito Web in cui è stato distribuito il codice di integrazione. Presupponendo che l’IP corrente venga mappato su un’organizzazione riconosciuta da Demandbase, è necessario visualizzare risultati simili a quelli indicati di seguito.

**Reports &amp;  Analytics (ex SiteCatalyst) include due variabili di dati contestuali Demandbase:**

![](assets/debugger1.png)

**Target Mbox include i parametri del profilo Demandbase:**
Questo verrà visualizzato solo se Target è stato implementato sulla pagina E l&#39;integrazione è stata configurata per  Adobe Target. Consultate il Passaggio 4 nella procedura guidata di integrazione di Adobe.

![](assets/debugger2.png)

### Generazione di rapporti {#section-1792fe75dc3249d0ad063dfd87a89162}

Rivedete i rapporti Demandbase in Adobe  Analytics utilizzando il dashboard creato automaticamente tramite la procedura guidata di integrazione Adobe (passaggio 7).

In alternativa, puoi accedere al report Demandbase nella struttura di menu di Adobe  Analytics, come illustrato di seguito.

>[!NOTE]
>
>Questi dati devono essere visualizzati entro 24-48 ore dalla distribuzione completata.

![](assets/reporting1.png)

![](assets/reporting2.png)

### Domande frequenti {#section-d926b160a2ef4f07b43ea1bc67ac2a0a}

**Cosa significa &quot;[n/a]&quot;?**

Il connettore dati Demandbase indica se un attributo è &quot;Non disponibile&quot; impostando questo valore predefinito. Esistono due scenari comuni in cui è impostato il valore predefinito:

* Demandbase rileva che il visitatore proviene da un indirizzo IP che non appartiene a una società.
* Viene utilizzato un attributo Account Watch (che inizia con &quot;watch_list&quot;), ma la società non è inclusa nell&#39;elenco Account Watch.

**Perché`[n/a]`&quot; appare più spesso per alcuni attributi?**

Demandbase classifica tutti gli indirizzi IP e fornisce gli attributi audience e audience_segmento anche quando il visitatore non proviene da un IP aziendale. Quando l&#39;audience restituisce valori come &quot;Residenziale&quot;, &quot;Wireless&quot; e &quot;Ospitalità&quot;, gli altri attributi probabilmente non sono disponibili.

A volte, il pubblico di un visitatore sarà &quot;SMB&quot;, ma altri attributi saranno mostrati &quot;`[n/a]`&quot;. Ciò significa che Demandbase è in grado di classificare il visitatore come una piccola azienda, ma il profilo aziendale completo non è disponibile. Questo accade generalmente per le aziende più piccole, quando più piccole imprese utilizzano lo stesso provider di servizi o lo stesso blocco di indirizzi IP.

### Considerazioni per sviluppatori {#section-d33fff55bc4b4db99f82dee418ef1bc2}

Per regolare il valore predefinito nell’implementazione, aggiorna la riga:

```
_db._nonOrgMatchLabel = "[n/a]";
```
