---
description: Descrizioni dei campi per le impostazioni generali dell'account della suite di rapporti in Amministratore.
title: Impostazioni account generali
topic: Admin tools
uuid: c1ab5c34-2c41-4d12-a706-0e760dff8a95
translation-type: tm+mt
source-git-commit: d4ecb31e7a79546c97207772e9df3eb4d673c35f
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 1%

---


# Impostazioni account generali

Descrizioni dei campi per le impostazioni dell&#39;account generale di una suite di rapporti in Amministratore.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL General Account Settings]**

Queste impostazioni contengono opzioni di modifica per le funzionalità di base della suite di rapporti, come nome e fuso orario.

| Opzione | Descrizione |
|--- |--- |
| Titolo del sito | Identifica il sito. Date a ciascuna suite di rapporti un titolo univoco del sito. |
| URL di base | Specifica il sito Web principale della suite di rapporti. L&#39;URL di base non influisce sul filtro del referente. Utilizzate invece i filtri [URL interni](/help/admin/admin/internal-url-filter-admin.md). |
| Fuso orario | Determina la data e l&#39;ora associate ai dati del report.  Modificando il fuso orario per una suite per report live si crea un picco o uno spazio vuoto nei dati del report. Per ridurre al minimo l&#39;impatto,  Adobe consiglia di modificare i fusi orari nelle ore non di picco per evitare di distorcere i dati.  Ad esempio, se cambi il fuso orario della suite di rapporti da Centrale a Pacifico alle 15:00, l&#39;ora corrente della suite di rapporti diventa 1:00. Poiché il reporting ha già raccolto i dati per l&#39;ora 1:00, i report mostrano un picco di traffico tra le 1:00 e le 15:00.  In alternativa, se cambi il fuso orario della suite di rapporti da Centrale a Orientale alle 15:00, l&#39;ora corrente della suite di rapporti diventa le 16:00. I report non visualizzano dati compresi tra le 15:00 e le 16:00 del giorno in cui è avvenuto il cambiamento di ora. |
| Pagina predefinita | Se il rapporto [!UICONTROL Most Popular Pages] contiene URL invece che nomi di pagina, questa impostazione impedisce a più URL di rappresentare la stessa pagina. Ad esempio, gli URL `https://example.com` e `https://example.com/index.html` sono in genere la stessa pagina. Potete rimuovere i nomi file predefiniti in modo che entrambi questi due URL vengano visualizzati come `https://example.com`.  Se lasciato vuoto, i seguenti nomi file vengono rimossi dagli URL:  index.htm, index.html, index.cgi, index.asp, default.htm, default.html, default.cgi, default.asp, home.htm, home.html, home.cgi e home.asp.  Per disattivare completamente lo stripping dei nomi dei file, immettete un valore che non sia mai presente negli URL. |
| Sostituire l&#39;ultimo ottetto di indirizzi IP con 0 | La rimozione dell&#39;ultimo ottetto viene eseguita prima di qualsiasi elaborazione sull&#39;hit, incluso prima del filtraggio/esclusione IP, prima del controllo delle regole bot, prima delle ricerche Geosegmentazione, ecc. Di conseguenza, l&#39;ultimo ottetto viene sostituito con 0 e le regole di esclusione IP devono essere aggiornate in modo che corrispondano agli indirizzi IP con uno zero alla fine. La corrispondenza * deve corrispondere a 0. Ad esempio, l’indirizzo IP 11.22.33.44 viene modificato in 11.22.33.0. I dati di segmentazione geografica non saranno esattamente come quando viene utilizzato l&#39;intero indirizzo IP. Nello specifico, l&#39;accuratezza della città sarà più influenzata dall&#39;accuratezza di paese o regione. Le regole bot e VISTA sono influenzate dal fatto che l&#39;intero indirizzo IP non è disponibile. Inoltre, tutte le regole di elaborazione basate su IP, incluse le regole del canale di marketing e le regole di elaborazione delle suite di rapporti, sono influenzate da questa impostazione. <br> **Nota**: Questa impostazione è abilitata per impostazione predefinita per tutte le nuove suite di rapporti create nel centro dati londinese dopo gennaio 2019, ma solo se le impostazioni per tali suite di rapporti vengono copiate da un modello elencato nel Admin Console . Le suite di rapporti le cui impostazioni sono duplicate da altre suite di rapporti erediteranno tutte le impostazioni dalla suite di rapporti selezionata. |
| Obfuscamento IP | Trasforma gli indirizzi IP in stringhe non riconoscibili, essenzialmente rimuoverli dagli archivi di dati  Adobe. Quando l&#39;offuscamento IP è abilitato, gli indirizzi IP originali vengono persi in modo permanente. <br> **Nota**: Gli indirizzi IP sono oscurati ovunque in Analytics, inclusa la Data Warehouse. Tuttavia, l&#39;impostazione IP in Target è controllata separatamente, pertanto questa impostazione non ha alcun impatto su Target.<br> Se l&#39;offuscamento dell&#39;IP è attivato, tutte le operazioni di elaborazione necessarie, inclusi i filtri/esclusione IP, le regole bot e le ricerche di geosegmentazione vengono eseguite prima che l&#39;indirizzo IP venga oscurato. Non è necessario modificare nulla quando si abilita l&#39;offuscamento IP.<ul><li>Selezionando **Disabled** l&#39;indirizzo IP viene lasciato nei dati.</li><li>Selezionando **Indirizzo IP offuscato**, l&#39;IP viene modificato in due punti, seguiti da un valore con hash (ad es. `::1932023538`).</li><li>Selezionando **Rimuovi indirizzo IP** l&#39;indirizzo IP viene sostituito con `::X.X.X.X` nei dati, dopo la ricerca geografica.</li></ul>**Nota**: Questa impostazione potrebbe richiedere modifiche alle  [regole bot personalizzate ](/help/admin/admin/bot-removal/bot-rules.md) o alle esclusioni [ ](/help/admin/admin/exclude-ip.md)IP. |
| Archiviazione ID transazione | Consente di utilizzare le origini dati [ID transazione](/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md). |
| Attivare  Ad Hoc Analysis | Indica se la suite di rapporti in questione viene visualizzata come una suite di rapporti disponibile in  Ad Hoc Analysis. Utilizzate questa impostazione per limitare le suite di rapporti visualizzate come opzione per  Ad Hoc Analysis. Ad esempio, puoi disattivare  Ad Hoc Analysis per lo sviluppo e le suite di rapporti per la qualità. |
| Abilita Data Warehouse | Abilita l’interfaccia utente Data Warehouse in Analytics > Strumenti > Data Warehouse. |
