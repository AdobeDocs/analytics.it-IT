---
description: Descrizioni dei campi per le impostazioni account generali della suite di rapporti in Amministratore.
title: Impostazioni account generali
feature: Admin Tools
uuid: c1ab5c34-2c41-4d12-a706-0e760dff8a95
exl-id: f49babb2-8e26-4cc6-b264-b4d7be93f130
source-git-commit: dc9cd6bb45af0c992c37ffe20ea22eab67789ec5
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 100%

---

# Impostazioni account generali

Descrizioni dei campi per le impostazioni generali account di una suite di rapporti in Amministratore.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL General Account Settings]**

Queste impostazioni contengono opzioni di modifica per le funzionalità di base della suite di rapporti, come nome e fuso orario.

Ecco un video sulla configurazione delle impostazioni generali dell’account:

>[!VIDEO](https://video.tv.adobe.com/v/332330/?quality=12)

| Opzione | Descrizione |
|--- |--- |
| Titolo sito | Identifica il tuo sito. Attribuisci a ciascuna suite di rapporti un titolo univoco del sito. |
| URL di base | Specifica il sito web principale della suite di rapporti. L&#39;URL di base non influisce sul filtro del referente. Utilizza, invece, [filtri URL interni](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md). |
| Fuso orario | Determina la data e l’ora associate ai dati del report.  La modifica del fuso orario per una suite di rapporti in tempo reale crea un picco o un intervallo nei dati del rapporto. Per ridurre al minimo l’impatto, Adobe consiglia di modificare i fusi orari nelle ore non di picco per evitare di distorcere i dati.  Ad esempio, se modifichi il fuso orario della suite di rapporti da Centrale a Pacifico alle 15:00, l’ora corrente della suite di rapporti diventa le 13:00. Poiché il reporting ha già raccolto i dati per le 13:00, i rapporti mostrano un picco di traffico tra le 13:00 e le 15:00.  In alternativa, se cambi il fuso orario della suite di rapporti da Centrale a Orientale alle 15:00, l’ora corrente della suite di rapporti diventa le 16:00. I rapporti non visualizzano dati compresi tra le 15:00 e le 16:00 del giorno in cui cambia l’ora. |
| Pagina predefinita | Se il report [!UICONTROL Most Popular Pages] contiene URL invece che nomi della pagnia, questa impostazione impedisce a più URL di rappresentare la stessa pagina. Ad esempio, gli URL `https://example.com` e `https://example.com/index.html` sono in genere la stessa pagina. È possibile rimuovere i nomi di file predefiniti in modo che questi due URL vengano visualizzati entrambi come `https://example.com`.  Se lasciato vuoto, i seguenti nomi di file vengono rimossi dagli URL: index.htm, index.html, index.cgi, index.asp, default.htm, default.html, default.cgi, default.asp, home.htm, home.html, home.cgi e home.asp.  Per disattivare completamente lo stripping dei nomi di file, immetti un valore che non è mai presente negli URL. |
| Sostituire l’ultimo ottetto degli indirizzi IP con 0 | La rimozione dell’ultimo ottetto viene eseguita prima di qualsiasi elaborazione sull’hit, incluso prima del filtro/esclusione IP, prima di controllare le regole bot, prima delle ricerche Geosegmentation, ecc. Di conseguenza, l’ultimo ottetto viene sostituito da 0 e le regole di esclusione IP devono essere aggiornate in modo che corrispondano agli indirizzi IP con uno zero alla fine. La corrispondenza * deve corrispondere a 0. Ad esempio, l’indirizzo IP 11.22.33.44 viene modificato in 11.22.33.0. I dati di geosegmentazione non saranno esattamente come quando viene utilizzato l’intero indirizzo IP. In particolare, l’accuratezza delle città sarà più importante dell’accuratezza del paese o della regione. Sono interessate sia le regole bot che le regole VISTA perché l’intero indirizzo IP non è disponibile. Inoltre, questa impostazione influisce su tutte le regole di elaborazione basate su IP, incluse le regole del canale di marketing e quelle basate sull’elaborazione delle suite di rapporti. <br> **Nota**: questa impostazione è attivata per impostazione predefinita per ogni nuova suite di rapporti creata nel datacenter di Londra dopo gennaio 2019, ma solo se le impostazioni per tali suite di rapporti sono copiate da un modello elencato in Admin Console. Le suite di rapporti le cui impostazioni sono duplicate da altre suite di rapporti ereditano tutte le impostazioni dalla suite di rapporti selezionata. |
| Offuscamento IP | Trasforma gli indirizzi IP in stringhe non riconoscibili, essenzialmente rimuovendoli dagli archivi di dati di Adobe. Quando IP Obfuscation è abilitato, gli indirizzi IP originali vengono persi definitivamente. <br> **Nota**: gli indirizzi IP vengono offuscati ovunque in Analytics, inclusa la Data Warehouse. Tuttavia, l’impostazione IP in Target è controllata separatamente, pertanto questa impostazione non ha alcun impatto su Target.<br> Se l’offuscamento dell’IP è abilitato, tutte le operazioni di elaborazione necessarie, inclusi i filtri/esclusione IP, le regole bot e le ricerche per la geosegmentazione, vengono eseguite prima che l’indirizzo IP sia offuscato. Non è necessario modificare nulla quando si abilita l’offuscamento dell’IP.<ul><li>La selezione di **Disabilitato** lascia l’indirizzo IP nei dati.</li><li>La selezione di **Indirizzo IP offuscato** cambia l’IP in due punti seguiti da un valore con hash (ad esempio, `::1932023538`).</li><li>La verifica di **Rimuovi indirizzo IP** sostituisce l’indirizzo IP con `::X.X.X.X` nei dati, dopo la ricerca geografica.</li></ul>**Nota**: questa impostazione potrebbe richiedere modifiche alle [regole bot](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md) o [Esclusioni IP](/help/admin/admin/exclude-ip.md) personalizzate. |
| Archiviazione ID transazione | Consente di utilizzare [ID transazione](/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md) origini dati. |
| Abilita Data Warehouse | Abilita l’interfaccia utente Data Warehouse in Analytics > Strumenti > Data Warehouse. |
| Opzione ZIP | Consente di specificare il codice postale anziché utilizzare qualsiasi prodotto dalla ricerca IP geografica. |
| Supporto di caratteri multibyte | Il supporto per caratteri multibyte memorizza i caratteri nella suite di rapporti utilizzando il formato UTF-8. Al momento della ricezione, il sistema converte i dati dal set di caratteri della pagina web al set di caratteri UTF-8, in modo da poter utilizzare qualsiasi lingua nei rapporti di marketing. Per modificare il supporto dei caratteri multibyte per una suite di rapporti esistente, contatta il tuo Account Manager o l’Assistenza clienti. |
| Attivato | Specifica se la suite di rapporti è attivata o meno. |
| Valuta di base | Consente di specificare la [valuta](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/currencycode.html?lang=it) di base per questa suite di rapporti. |
| ID organizzazione | ID associato alla società di Experience Cloud con provisioning. Questo ID è una stringa alfanumerica composta da 24 caratteri, seguita da (e che deve includere) @AdobeOrg. |