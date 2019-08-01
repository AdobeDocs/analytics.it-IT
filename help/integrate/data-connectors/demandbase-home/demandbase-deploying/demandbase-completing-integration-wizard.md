---
description: Per attivare l'integrazione, devi completare la procedura guidata di configurazione nell'interfaccia dei Connettori dati.
seo-description: Per attivare l'integrazione, devi completare la procedura guidata di configurazione nell'interfaccia dei Connettori dati.
seo-title: Completamento della procedura guidata Integrazione Adobe
title: Completamento della procedura guidata Integrazione Adobe
uuid: 75260 b 92-a 6 f 5-44 b 6-b 3 ea-d 5945 fdd 1 ecb
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Completing the Adobe Integration Wizard{#completing-the-adobe-integration-wizard}

Per attivare l'integrazione, devi completare la procedura guidata di configurazione nell'interfaccia dei Connettori dati.

1. Passa all'area Connettori dati (precedentemente Genesis) all'interno di Adobe Marketing Cloud.
1. Avviate la procedura guidata di integrazione Demandbase 2.0.
1. Scegli la suite di rapporti desiderata e specifica un nome per l'integrazione.
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
   <td colname="col2"> Indirizzo e-mail del contatto principale. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Descrizione </td> 
   <td colname="col2"> (Facoltativo) Descrizione per questa configurazione dell'integrazione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Demandbase API key </td> 
   <td colname="col2"> Potete ottenerlo dal rappresentante Demandbase. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Custom Demandbase Dimension # N </td> 
   <td colname="col2"> Questi sono gli ID per le 8 dimensioni facoltative. Per ulteriori informazioni, vedi Demandbase Custom Dimensions. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Invia ad Adobe Target </td> 
   <td colname="col2">Se «true», anche le dimensioni Demandbase vengono inviate ad Adobe Target utilizzando una mbox nascosta. <p>Nota: Un file mbox. js configurato deve essere implementato sulla pagina Web per le dimensioni da raccogliere. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Configura i seguenti elementi Mappature variabili:

   | Elemento | Descrizione |
   |---|---|
   | Dimensions Dbase Dimensions | Scegli una variabile evar disponibile dalla suite di rapporti. |
   | Demandbase Custom Dimensions (facoltativo) | Scegli una variabile evar disponibile dalla suite di rapporti. |

1. Configura i nomi per Dimensione personalizzata (se applicabile).

   1. Se hai scelto di includere Dimensioni personalizzate nel passaggio 4 e hai mappato l'evar opzionale nel passaggio 5, devi fornire nomi descrittivi per tali dimensioni. Ad esempio, se hai scelto di inserire «stock_ ticker» come Dimensione personalizzata 1, devi cambiare la casella contenente «Dimension 1» in «Stock Ticker».
   1. **NON** modificate i nomi delle dimensioni standard di 8 dimensioni (ovvero Demandbase SID, Nome società, Settore, ecc.).

1. Selezionate la casella per creare automaticamente il dashboard Integrazione Demandbase (consigliato).
1. Review all configuration items and click **[!UICONTROL Activate Now]**.

