---
description: Configurare le impostazioni comportamentali globali. Ad esempio, è possibile configurare le impostazioni di salvataggio automatico, grafico e tabella e specificare il font e le impostazioni internazionali.
title: Impostazioni
uuid: 34444052-479b-4923-b379-a03ca614bf3e
translation-type: tm+mt
source-git-commit: 5d96a2868bee48e2294ec2fb27e0340a3bcc50ae
workflow-type: tm+mt
source-wordcount: '608'
ht-degree: 4%

---


# Impostazioni

>[!IMPORTANT]
>
> Adobe si sta muovendo  Ad Hoc Analysis fino alla fine del suo ciclo di vita il 1 marzo 2021. [Ulteriori informazioni](https://adobe.ly/discoverworkspace)

Configurare le impostazioni comportamentali globali. Ad esempio, è possibile configurare le impostazioni di salvataggio automatico, grafico e tabella e specificare il font e le impostazioni internazionali.

## Impostazioni {#concept_D21E3D6F13EA4F97913F60C243B72173}

Configurare le impostazioni comportamentali globali. Ad esempio, è possibile configurare le impostazioni di salvataggio automatico, grafico e tabella e specificare il font e le impostazioni internazionali.

Fate clic su **[!UICONTROL Tools]** > **[!UICONTROL Settings]** per accedere [!UICONTROL Global Settings].

## Scheda Impostazioni generali - Definizioni {#reference_EADAF83466994F89BCC6B0F49A9A53DB}

Configurare le impostazioni comportamentali per le origini dati, il salvataggio del progetto, i grafici e le tabelle.

<!-- 

r_dsc_general_settings.xml

 -->

<table id="table_C18A0F1C9E214EB585A29801BA2400F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Campo </p> </th> 
   <th colname="col2" class="entry"> <p>Definizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Impostazioni dati </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Conteggio istanze</span>ripetute: Specifica se le istanze vengono conteggiate nei report. Ciò significa che, se si dispone di più valori sequenziali per la stessa variabile, è possibile conteggiarli come una o più istanze della variabile. </p> <p>Ad esempio, è possibile che vengano visualizzati ricarichi di pagina ripetuti, ovvero il numero di volte in cui le pagine del sito Web vengono ricaricate o aggiornate durante una singola visita. Questa opzione consente di specificare se più hit sulla stessa pagina vengono conteggiati come una o più visualizzazioni di pagina. </p> <p> <span class="uicontrol"> <span class="keyword"> Ad Hoc</span> </span>: Specifica <span class="keyword"> Ad Hoc</span> come unica origine di dati per il reporting. Questi dati provengono da richieste di immagini generate da pagine Web. </p> <p> <span class="uicontrol"> <span class="keyword"> Origini</span> dati </span>: Specifica se utilizzare i dati caricati da altre origini di Adobe  o da origini dati personalizzate. Questi dati diventano disponibili per i prodotti nel <span class="keyword"> Experience Cloud</span>. Per ulteriori informazioni, consulta <a href="https://docs.adobe.com/content/help/it-IT/analytics/import/data-sources/datasrc-home.html"  > Origini</a> dati. </p> <p> <span class="uicontrol"> Entrambi</span>: (Impostazione predefinita) Utilizza i dati provenienti da analisi <span class="keyword"></span> ad hoc e da altre origini dati. </p> <p>Nota: La modifica di queste opzioni può determinare discrepanze tra i dati di analisi <span class="keyword"> ad</span> hoc e i dati dei <span class="keyword"> marketing reports and analytics.</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Salva automaticamente </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Salvataggio automatico abilitato</span>: Abilita la funzionalità di salvataggio automatico. </p> <p> <span class="uicontrol"> Frequenza</span>progetto salvataggio automatico: Consente di regolare gli incrementi temporali della funzione di salvataggio automatico. Un salvataggio automatico del progetto viene creato solo in caso di arresto anomalo ad hoc. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Impostazioni grafico </p> </td> 
   <td colname="col2"> <p><b>Comprimi grafici per impostazione predefinita</b>: Fare clic su questo pulsante per visualizzare i rapporti senza un grafico nella sezione superiore. Una volta visualizzato il rapporto con questa opzione, potete estenderlo manualmente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Impostazioni tabella </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Mostra numeri</span>di riga: Attiva o disattiva la numerazione delle righe nella tabella del rapporto. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Scheda Classificati - Definizioni {#reference_FB9BADD7E3DA42C1BB2A02A6E9D5C1CF}

Configura la modalità di visualizzazione dei dati nelle colonne e seleziona le metriche predefinite per il traffico e i rapporti di conversione.

<!-- 

r_dsc_ranked_tab.xml

 -->

| Campo | Definizione |
|--- |--- |
| Impostazioni colonna | Configurare la modalità di visualizzazione dei dati delle celle nelle tabelle e nei grafici a barre nei grafici. |
| Seleziona metriche predefinite | Seleziona le metriche predefinite per i report Traffic (Traffico e Conversione), oltre alle metriche disponibili per tutti i report.    Includi predefinito specifico rapporto: Specifica se includere metriche predefinite durante la personalizzazione della visualizzazione. |

## Scheda Analisi sito - Definizioni {#reference_9DD37C8EF718409E990E149596282FF8}

Configura le metriche e altre impostazioni grafiche per il rapporto Analisi sito.

<!-- 

r_dsc_site_analysis_tab.xml

 -->

| Campo | Definizione |
|--- |--- |
| Metriche | Seleziona le metriche rappresentate da larghezza cilindro e altezza cilindro. Determinare quale metrica viene visualizzata utilizzando il colore e determinare i colori che rappresentano un valore basso e un valore alto per quella metrica. Puoi stabilire le metriche per gli assi X e Y e aggiungere qualsiasi altra metrica in cui desideri che appaia nel testo a comparsa del rapporto. Potete inoltre invertire una qualsiasi delle metriche selezionate per la visualizzazione. |
| Generali e avvisi | Abilitare e disabilitare alcuni elementi grafici del rapporto. Puoi configurare avvisi che vengono visualizzati nel rapporto quando le metriche associate alle pagine rappresentate dai cilindri passano un valore specifico. |

## Scheda Font e Impostazioni internazionali - Definizioni {#reference_5F2129B67CC44E5BA9EA7E30A35BFB49}

Specificate le impostazioni internazionali della lingua e il font predefinito. Per rendere effettive le modifiche a font e impostazioni internazionali, è necessario riavviare il sistema.

<!-- 

r_dsc_font_locale.xml

 -->

| Campo | Definizione |
|--- |--- |
| Selezionare le impostazioni internazionali | Consente di specificare la lingua da visualizzare nell&#39;interfaccia utente. |
| Selezionare un font | Consente di specificare un font da visualizzare. |
