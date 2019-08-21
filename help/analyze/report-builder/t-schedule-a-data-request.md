---
description: Potete pianificare i rapporti in base all'ora e al formato di file definiti.
seo-description: Potete pianificare i rapporti in base all'ora e al formato di file definiti.
seo-title: Pianificazione di una richiesta dati
solution: Analytics
title: Pianificazione di una richiesta dati
topic: Generatore di report
uuid: f 6 d 8 c 90 f-e 185-4 d 60-8035-f 20 f 74 bfcd 89
translation-type: tm+mt
source-git-commit: 62937df0a763f6b9b34389d968c5641056b47aa8

---


# Pianificare una cartella di lavoro

Potete pianificare le cartelle di lavoro, specificare opzioni di consegna avanzate, specificare i destinatari e visualizzare la cronologia delle pianificazioni. Le opzioni di consegna avanzate consentono di configurare i documenti di lavoro che si desidera inviare a un determinato momento o a intervalli specifici. Potete anche specificare il formato di file in cui inviare la cartella di lavoro.

Ad esempio, potete pianificare la pubblicazione di cartelle di lavoro immediatamente o secondo una pianificazione periodica e specificare il formato di file in [!DNL Advanced Delivery Options]. Il limite di dimensione file è 5 MB per il caricamento di una cartella di lavoro.

Inoltre, dopo aver creato una pianificazione di cartelle di lavoro in Generatore di report, potete visualizzare e modificare la pianificazione in **[!UICONTROL Analytics]** &gt; **[!UICONTROL Reports]**. (consultate [Pianificazione dei report e distribuzione](/help/analyze/reports-analytics/scheduling.md) nell'Aiuto di Reporting e analisi.)

>[!NOTE]
>
>Per pianificare una cartella di lavoro, è necessario installare Excel 2007 o il pacchetto di compatibilità installato. Potete disporre di un massimo di 10 cartelle di lavoro pianificate per Licenza Generatore di report. Tuttavia, potete aumentare questo numero sottraendo da altre licenze. A questo scopo, accedete **[!UICONTROL Admin]** a &gt; **[!UICONTROL Company Settings]** &gt; **[!UICONTROL Report Builder Reports]**. Una cartella di lavoro che è stata pianificata (o caricata nella Libreria di Workcartelle) e non è stata toccata (aggiornata, sostituita) in più di 28 mesi verrà eliminata.

>[!NOTE]
>
>Il «Tempo di consegna»/«Ora del giorno» immesso dall'utente specifica l'ora in cui la cartella di lavoro deve iniziare elaborazione, non l'ora in cui verrà effettivamente consegnata. La data e l'ora effettive in cui la cartella di lavoro verrà distribuita dipende principalmente dal tempo necessario per l'elaborazione (i documenti di lavoro complessi e di grandi dimensioni richiedono più tempo rispetto alle cartelle di lavoro più semplici). Ad esempio, se una cartella di lavoro impiega 15 minuti da elaborare, il tempo di consegna effettivo sarà almeno 15 minuti oltre il «Tempo di consegna»/«Ora del giorno» specificato originariamente.
>Inoltre, esistono molti altri fattori che possono aumentare ulteriormente il ritardo prima della distribuzione della cartella di lavoro:
>
> * **L'esecuzione contemporanea di numerose pianificazioni dello stesso tipo** può sovraccaricare il sistema. Il sistema Pianificazione consente solo alcuni (5-10) cartelle di lavoro di qualsiasi tipo da eseguire simultaneamente; pertanto, quando tutte le versioni di un determinato tipo sono pianificate contemporaneamente, alcuni dovranno attendere in linea per il termine di altri documenti di lavoro prima di iniziare l'elaborazione. Questo problema può essere mitigato pianificando le cartelle di lavoro della società in tempi rapidizzati durante il giorno o l'ora, anziché simultaneamente.
> * A parte il tipo di cartella di lavoro, le cartelle di lavoro saranno anche in linea se l'azienda ha **più di 15-20 di qualsiasi tipo di cartella di lavoro pianificata contemporaneamente (per tutti i tipi di cartelle)**. Questa operazione può essere mitigata rendendo difficoltosa la pianificazione temporale, evitando che venga eseguita contemporaneamente.
> * **I problemi nei servizi** a valle richiesti dal programma di pianificazione possono influire anche sulla distribuzione delle cartelle di lavoro. Ad esempio, se utilizzate indipendentemente le API per eseguire le cartelle di lavoro e compilare la coda delle richieste API, i vostri documenti di lavoro pianificati potrebbero venire distribuiti lentamente mentre siete competitivi per quella risorsa.
> * **La latenza della suite di rapporti** (un ritardo nella raccolta dati) può anche ritardare alcune cartelle di lavoro pianificate.


**Pianificazione di una cartella di lavoro**

1. Generate e salvate una cartella di lavoro.
1. Nella barra degli strumenti di Generatore di report, fate clic **[!UICONTROL Schedule]** su.

   [!UICONTROL Scheduled Reports] La scheda riepiloga tutte le attività create, oltre al numero di operazioni rimanenti.
1. Nella **[!UICONTROL Scheduled Reports]** scheda, fate clic **[!UICONTROL New]** su.
1. Viene visualizzata la procedura guidata di base della pianificazione:

   ![](assets/simple-schedule-wizard.png)

1. In [!UICONTROL Basic Scheduling Wizard], configurate le seguenti opzioni:

* **Selezionate Report**: Nome della cartella di lavoro. Per i nuovi documenti di lavoro pianificati, questo campo viene compilato con il nome del cartella di lavoro attivo.

<table id="table_6D5B1B832EB0451293F1902E2A1D1068"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Seleziona Rapporto </p> </td> 
   <td colname="col2"> <p>Nome del rapporto. Per i nuovi rapporti pianificati, questo campo viene compilato con il nome del cartella di lavoro attivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Seleziona </p> </td> 
   <td colname="col2"> <p>Visualizza la <span class="wintitle"> pagina Seleziona rapporto</span> . Potete selezionare un rapporto dal server (dove vengono archiviate tutte le cartelle di lavoro precedentemente pianificate) o dal computer locale. Se selezionate una cartella di lavoro dall'unità locale in <span class="filepath"> formato. xls</span> , il file converte il file in <span class="filepath"> .xlsx</span>. Come parte di tale conversione, il file viene aperto in Excel e reso attivo. Se la cartella di lavoro selezionata per il rapporto pianificata ha lo stesso nome file della cartella di lavoro attualmente aperta in Excel, il sistema seleziona il file locale anziché quello caricato in precedenza. Se selezionate un rapporto dall'archivio di pianificazione, viene creata una copia della cartella di lavoro sul server, con il nome file aggiornato con 1. Il rapporto appena creato utilizza la cartella di lavoro copiata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Personalizza </p> </td> 
   <td colname="col2"> <p>Consente di personalizzare il formato della data. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A </p> </td> 
   <td colname="col2"> <p>Se applicabile, visualizza la rubrica di Outlook. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Invia a: E-mail </p> </td> 
   <td colname="col2"> <p>Destinatario e-mail della cartella di lavoro. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Invia a: Elenco pubblicazione </p> </td> 
   <td colname="col2"> <p>Visualizza un elenco degli elenchi di distribuzione disponibili per questa società. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Power BI </p> </td> 
   <td colname="col2"> <p>Per ulteriori informazioni, consultate <a href="../../analyze/report-builder/c-publish-power-bi/integration-power-bi.md#section_BA137EA92A46483F83BB5C1C40FBA002" format="dita" scope="local"> Pubblicare la cartella di lavoro su Microsoft Power BI</a> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Oggetto </p> </td> 
   <td colname="col2"> <p>Descrizione definita dall'utente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pianificazione </p> </td> 
   <td colname="col2"> <p> Consente di specificare quando inviare la cartella di lavoro. (immediatamente, su base giornaliera, giornaliera, settimanale, mensile e annuale). </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Fate clic per **[!UICONTROL Advanced Delivery Options]** configurare i file e le opzioni di pubblicazione:

<table id="table_1BA8A5600DE94A33B83B096E69CE15F3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Scheda Pianificazione</b> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ora di consegna </p> </td> 
   <td colname="col2"> <p>Consente di pianificare la cartella di lavoro immediatamente o per un momento successivo. L'ora del giorno è relativa al fuso orario specificato nel computer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pattern di ricorrenza </p> </td> 
   <td colname="col2"> <p>Invia la cartella di lavoro in base alle selezioni. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Intervallo di ricorrenza </p> </td> 
   <td colname="col2"> <p>Consente di specificare quando avviare e interrompere la ricezione della cartella di lavoro. </p> <p> <p>Nota: La pianificazione di una cartella di lavoro il primo giorno di qualsiasi periodo (settimana, mese, trimestre o anno) restituisce dati solo per il primo giorno. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>scheda Opzioni</b> file </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Formato file </p> </td> 
   <td colname="col2"> <p>Consente di selezionare un formato di consegna Excel 2007 (<span class="filepath"> .xlsx</span>) o 2003 (<span class="filepath"> . xls</span>) <span class="filepath"> .pdf</span><span class="filepath"> . csv</span><span class="filepath"> . mht</span><span class="filepath"> .txt</span>e<span class="filepath"> .xml</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Destinazione file </p> </td> 
   <td colname="col2"> <p> Specifica e-mail o FTP. Le opzioni della pagina variano a seconda della selezione. Per l'FTP, dovrai accertarti che l'host sia disponibile all'esterno. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Elenco pubblicazione </p> </td> 
   <td colname="col2"> <p> Se inviate la cartella di lavoro pianificata a più elenchi di pubblicazione, la cartella di lavoro viene eseguita una volta per ogni elenco. Le suite di rapporti variabili vengono sostituite dalla suite di rapporti assegnata all'elenco di pubblicazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lingua contenuto file </p> </td> 
   <td colname="col2"> <p>Specifica la lingua da utilizzare per la lettera di copertina. È possibile selezionare Cinese (Semplificato o Tradizionale), Tedesco, Francese, Giapponese, Coreano, Portoghese o Spagnolo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>scheda Opzioni</b> pubblicazione </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pubblicazione su Power BI </p> </td> 
   <td colname="col2"> 
    <ul id="ul_40697E4FB2CE4F34B857FBF153D6D6D5"> 
     <li id="li_023E4750814D415EBC899269C9EA5D46"><a href="../../analyze/report-builder/c-publish-power-bi/integration-power-bi.md#section_BA137EA92A46483F83BB5C1C40FBA002" format="dita" scope="local"> Pubblicare la cartella di lavoro su Power BI</a> </li> 
     <li id="li_9B684BE22AF94ABC903405EE83951A80"><a href="../../analyze/report-builder/c-publish-power-bi/integration-power-bi.md#section_E48148793E794169B766C73995897B9F" format="dita" scope="local"> Pubblica tutte le richieste di Generatore di report come datasets Power BI</a> </li> 
     <li id="li_7B0BD285BC1749D1B2C65759CA97877B"><a href="../../analyze/report-builder/c-publish-power-bi/integration-power-bi.md#section_6F8422B90D3F4F7EB5D4C97BFFA807AD" format="dita" scope="local"> Pubblica tutte le tabelle formattate come datasets Power BI</a> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Etichettate questo report Power BI come </p> </td> 
   <td colname="col2"> <p>Dettagli etichettatura </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Fate clic **[!UICONTROL OK]** su, quindi fate clic **[!UICONTROL Exit]** su.

   Generatore di report visualizza la cartella di lavoro pianificata in Task Manager [pianificata](../../analyze/report-builder/r-arb-scheduled-reports.md#section_69306B8D833F4DF7BBFA53753B0E6C31).

