---
description: Descrizioni dei campi per le impostazioni account generali della suite di rapporti in Amministratore.
title: Impostazioni account generali
feature: Strumenti di amministrazione
uuid: c1ab5c34-2c41-4d12-a706-0e760dff8a95
exl-id: f49babb2-8e26-4cc6-b264-b4d7be93f130
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 1%

---

# Impostazioni account generali

Descrizioni dei campi per le impostazioni account generali di una suite di rapporti in Amministratore.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL General Account Settings]**

Queste impostazioni contengono opzioni di modifica per le funzionalità di base della suite di rapporti, come nome e fuso orario.

| Opzione | Descrizione |
|--- |--- |
| Titolo sito | Identifica il tuo sito. Attribuisci a ciascuna suite di rapporti un titolo univoco del sito. |
| URL di base | Specifica il sito web principale della suite di rapporti. L&#39;URL di base non influisce sul filtro del referente. Utilizza invece i [filtri URL interni](/help/admin/admin/internal-url-filter-admin.md). |
| Fuso orario | Determina la data e l&#39;ora associate ai dati del report.  La modifica del fuso orario per una suite di rapporti live crea un picco o un intervallo nei dati del rapporto. Per ridurre al minimo l’impatto, l’Adobe consiglia di modificare i fusi orari nelle ore non di picco per evitare di distorcere i dati.  Ad esempio, se modifichi il fuso orario della suite di rapporti da Centrale a Pacifico alle 15:00, l’ora corrente della suite di rapporti diventa 1:00. Poiché il reporting ha già raccolto i dati per le 1:00 ore, i rapporti mostrano un picco di traffico tra le 13:00 e le 15:00.  In alternativa, se cambi il fuso orario della suite di rapporti da Centrale a Orientale alle 15:00, l&#39;ora corrente della suite di rapporti diventa le 16:00. I rapporti non visualizzano dati compresi tra le 15:00 e le 16:00 del giorno in cui cambia l’ora. |
| Pagina predefinita | Se il rapporto [!UICONTROL Most Popular Pages] contiene URL anziché nomi di pagina, questa impostazione impedisce a più URL di rappresentare la stessa pagina. Ad esempio, gli URL `https://example.com` e `https://example.com/index.html` sono in genere la stessa pagina. È possibile rimuovere i nomi di file predefiniti in modo che questi due URL vengano visualizzati entrambi come `https://example.com`.  Se lasciato vuoto, i seguenti nomi di file vengono rimossi dagli URL:  index.htm, index.html, index.cgi, index.asp, default.htm, default.html, default.cgi, default.asp, home.htm, home.html, home.cgi e home.asp.  Per disattivare completamente lo stripping dei nomi di file, immetti un valore che non è mai presente negli URL. |
| Sostituire l’ultimo ottetto degli indirizzi IP con 0 | La rimozione dell’ultimo ottetto viene eseguita prima di qualsiasi elaborazione sull’hit, incluso prima del filtro/esclusione IP, prima di controllare le regole bot, prima delle ricerche Geosegmentation, ecc. Di conseguenza, l’ultimo ottetto viene sostituito da 0 e le regole di esclusione IP devono essere aggiornate in modo che corrispondano a zero agli indirizzi IP alla fine. La corrispondenza * deve corrispondere a 0. Ad esempio, l’indirizzo IP 11.22.33.44 viene modificato in 11.22.33.0. I dati di segmentazione non saranno esattamente come quando viene utilizzato l’intero indirizzo IP. In particolare, l&#39;accuratezza delle città sarà più importante dell&#39;accuratezza del paese o della regione. Sono interessate sia le regole bot che le regole VISTA perché l’intero indirizzo IP non è disponibile. Inoltre, questa impostazione influisce su tutte le regole di elaborazione basate su IP, incluse le regole del canale di marketing e quelle basate sull’elaborazione delle suite di rapporti. <br> **Nota**: Questa impostazione è abilitata per impostazione predefinita per tutte le nuove suite di rapporti create nel datacenter di Londra dopo gennaio 2019, ma solo se le impostazioni per tali suite di rapporti vengono copiate da un modello elencato nell’Admin Console. Le suite di rapporti le cui impostazioni sono duplicate da altre suite di rapporti erediteranno tutte le impostazioni dalla suite di rapporti selezionata. |
| Offuscamento IP | Trasforma gli indirizzi IP in stringhe non riconoscibili, essenzialmente rimuovendoli dagli archivi di dati di Adobe. Quando IP Obfuscation è abilitato, gli indirizzi IP originali vengono persi definitivamente. <br> **Nota**: Gli indirizzi IP vengono offuscati ovunque in Analytics, inclusa la Data Warehouse. Tuttavia, l’impostazione IP in Target è controllata separatamente, pertanto questa impostazione non ha alcun impatto su Target.<br> Se l’offuscamento dell’IP è abilitato, tutte le operazioni di elaborazione necessarie, inclusi i filtri/esclusione IP, le regole bot e le ricerche per la geosegmentazione, vengono eseguite prima che l’indirizzo IP sia offuscato. Non è necessario modificare nulla quando si abilita l’offuscamento dell’IP.<ul><li>Selezionando **Disabilitato** l&#39;indirizzo IP viene lasciato nei dati.</li><li>Selezionando **Indirizzo IP offuscato** l&#39;IP viene modificato in due punti, seguiti da un valore con hash (ad esempio, `::1932023538`).</li><li>La selezione di **Rimuovi indirizzo IP** sostituisce l&#39;indirizzo IP con `::X.X.X.X` nei dati, dopo la ricerca geografica.</li></ul>**Nota**: Questa impostazione potrebbe richiedere modifiche alle  [regole bot personalizzate o alle esclusioni ](/help/admin/admin/bot-removal/bot-rules.md) IP [ ](/help/admin/admin/exclude-ip.md). |
| Archiviazione ID transazione | Consente di utilizzare le origini dati [ID transazione](/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md). |
| Abilita Data Warehouse | Abilita l’interfaccia utente Data Warehouse in Analytics > Strumenti > Data Warehouse. |
