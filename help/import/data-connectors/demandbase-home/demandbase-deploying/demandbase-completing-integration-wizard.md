---
description: Per attivare l'integrazione, è necessario completare la procedura guidata di configurazione all'interno dell'interfaccia Connettori dati.
seo-description: Per attivare l'integrazione, è necessario completare la procedura guidata di configurazione all'interno dell'interfaccia Connettori dati.
seo-title: Completamento della procedura guidata di integrazione di Adobe
title: Completamento della procedura guidata di integrazione di Adobe
uuid: 75260b92-a6f5-44b6-b3ea-d5945fdd1ecb
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Completamento della procedura guidata di integrazione di Adobe{#completing-the-adobe-integration-wizard}

Per attivare l'integrazione, è necessario completare la procedura guidata di configurazione all'interno dell'interfaccia Connettori dati.

1. Passa all'area Connettori dati (precedentemente Genesis) in Adobe Experience Cloud.
1. Avviate la procedura guidata di integrazione Demandbase 2.0.
1. Scegliete la suite di rapporti desiderata e specificate un nome per l'integrazione.
1. Configura i seguenti elementi:

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
   <td colname="col2"> Indirizzo e-mail del contatto principale. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Descrizione </td> 
   <td colname="col2"> (Facoltativo) Descrizione per questa configurazione di integrazione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Chiave API Demandbase </td> 
   <td colname="col2"> Puoi ottenere questo da Demandbase. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimensione Demandbase personalizzata #N </td> 
   <td colname="col2"> Questi sono gli ID per le 8 dimensioni facoltative. Per ulteriori informazioni, vedere Demandbase Custom Dimensions. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Invia ad Adobe Target </td> 
   <td colname="col2">Se "true", anche le dimensioni Demandbase saranno inviate ad Adobe Target utilizzando una mbox nascosta. <p>Nota:  Per poter raccogliere le dimensioni, è necessario implementare un file mbox.js configurato sulla pagina Web. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Configura i seguenti elementi di mappatura variabili:

   | Elemento | Descrizione |
   |---|---|
   | Dimensioni Demandbase | Scegli una variabile eVar disponibile dalla suite di rapporti. |
   | Dimensioni personalizzate Demandbase (facoltativo) | Scegli una variabile eVar disponibile dalla suite di rapporti. |

1. Configura i nomi per la Dimensione personalizzata (se applicabile).

   1. Se al punto 4 avete scelto di includere le dimensioni personalizzate e mappato l'eVar opzionale al punto 5, dovete fornire nomi descrittivi per tali dimensioni. Ad esempio, se si sceglie di immettere "stock_ticker" come Dimensione personalizzata 1, è necessario modificare la casella contenente "Dimension 1" in "Stock Ticker".
   1. NON **modificate** i nomi delle dimensioni standard 8 (ad esempio Demandbase SID, Nome società, Industria, ecc.).

1. Selezionare la casella per creare automaticamente il dashboard Integrazione Demandbase (consigliato).
1. Rivedete tutti gli elementi di configurazione e fate clic su **[!UICONTROL Activate Now]**.

