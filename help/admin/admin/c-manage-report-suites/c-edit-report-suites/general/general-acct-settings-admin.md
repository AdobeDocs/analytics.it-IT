---
description: Descrizioni dei campi per le impostazioni account generali della suite di rapporti in Amministratore.
title: Impostazioni account generali
feature: Admin Tools
uuid: c1ab5c34-2c41-4d12-a706-0e760dff8a95
exl-id: f49babb2-8e26-4cc6-b264-b4d7be93f130
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '685'
ht-degree: 85%

---

# Impostazioni account generali

Descrizioni dei campi per le impostazioni generali account di una suite di rapporti in Amministratore.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL General Account Settings]**

Queste impostazioni contengono opzioni di modifica per le funzionalità di base della suite di rapporti, come nome e fuso orario.


>[!BEGINSHADEBOX]

Consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Configurazione delle impostazioni account generali](https://video.tv.adobe.com/v/332330/?quality=12&learn=on){target="_blank"} per un video dimostrativo.

>[!ENDSHADEBOX]

| Opzione | Descrizione |
|--- |--- |
| Titolo sito | Identifica il tuo sito. Attribuisci a ciascuna suite di rapporti un titolo univoco del sito. |
| URL di base | Specifica il sito web principale della suite di rapporti. L&#39;URL di base non influisce sul filtro del referente. Utilizza, invece, [filtri URL interni](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md). |
| Fuso orario | Determina la data e l’ora associate ai dati del report.  La modifica del fuso orario per una suite di rapporti in tempo reale crea un picco o un intervallo nei dati del rapporto. Per ridurre al minimo l’impatto, Adobe consiglia di modificare i fusi orari nelle ore non di picco per evitare di distorcere i dati.  Ad esempio, se modifichi il fuso orario della suite di rapporti da Centrale a Pacifico alle 15:00, l’ora corrente della suite di rapporti diventa le 13:00. Poiché il reporting ha già raccolto i dati per le 13:00, i rapporti mostrano un picco di traffico tra le 13:00 e le 15:00.  In alternativa, se cambi il fuso orario della suite di rapporti da Centrale a Orientale alle 15:00, l’ora corrente della suite di rapporti diventa le 16:00. I rapporti non visualizzano dati compresi tra le 15:00 e le 16:00 del giorno in cui cambia l’ora. |
| Pagina predefinita | Se il report [!UICONTROL Most Popular Pages] contiene URL invece che nomi della pagnia, questa impostazione impedisce a più URL di rappresentare la stessa pagina. Ad esempio, gli URL `https://example.com` e `https://example.com/index.html` sono in genere la stessa pagina. È possibile rimuovere i nomi di file predefiniti in modo che questi due URL vengano visualizzati entrambi come `https://example.com`.  Se lasciato vuoto, i seguenti nomi di file vengono rimossi dagli URL: index.htm, index.html, index.cgi, index.asp, default.htm, default.html, default.cgi, default.asp, home.htm, home.html, home.cgi e home.asp.  Per disattivare completamente lo stripping dei nomi di file, immetti un valore che non è mai presente negli URL. |
| Sostituire l’ultimo ottetto degli indirizzi IP con 0 | Quando questa opzione è attivata, sostituisce l’ultimo ottetto degli indirizzi IP con uno zero. Ciò si verifica prima che i rapporti relativi alla geolocalizzazione vengano compilati e può quindi influire sulla precisione di tali rapporti. |
| Offuscamento IP | Trasforma gli indirizzi IP in stringhe non riconoscibili, essenzialmente rimuovendoli dagli archivi di dati di Adobe. Quando IP Obfuscation è abilitato, gli indirizzi IP originali vengono persi definitivamente. <br> **Nota**: gli indirizzi IP vengono offuscati ovunque in Analytics, inclusa la Data Warehouse. Tuttavia, l’impostazione IP in Target è controllata separatamente, pertanto questa impostazione non ha alcun impatto su Target.<br> Se l’offuscamento dell’IP è abilitato, tutte le operazioni di elaborazione necessarie, inclusi i filtri/esclusione IP, le regole bot e le ricerche per la geosegmentazione, vengono eseguite prima che l’indirizzo IP sia offuscato. Non è necessario modificare nulla quando si abilita l’offuscamento dell’IP.<ul><li>La selezione di **Disabilitato** lascia l’indirizzo IP nei dati.</li><li>La selezione di **Indirizzo IP offuscato** cambia l’IP in due punti seguiti da un valore con hash (ad esempio, `::1932023538`).</li><li>La verifica di **Rimuovi indirizzo IP** sostituisce l’indirizzo IP con `::X.X.X.X` nei dati, dopo la ricerca geografica.</li></ul>**Nota**: questa impostazione potrebbe richiedere modifiche alle [regole bot](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md) o [esclusioni IP](/help/admin/admin/exclude-ip.md) personalizzate.<br> **Nota**: ai dati raccolti tramite Web SDK può essere applicata l&#39;offuscamento dell&#39;IP all&#39;Edge Network tramite [configurazione del flusso di dati](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html#@advanced-options). Se l’offuscamento dell’IP viene applicato all’Edge Network, esso è già offuscato quando raggiunge Analytics. Questa offuscamento influisce sulle regole bot e sulle ricerche geografiche. |
| Archiviazione ID transazione | Consente di utilizzare [ID transazione](/help/import/data-sources/transactionid.md) origini dati. |
| Abilita Data Warehouse | Abilita l’interfaccia utente Data Warehouse in Analytics > Strumenti > Data Warehouse. |
| Opzione ZIP | Consente di specificare il codice postale anziché utilizzare qualsiasi prodotto dalla ricerca IP geografica. |
| Supporto di caratteri multibyte | Il supporto per caratteri multibyte memorizza i caratteri nella suite di rapporti utilizzando il formato UTF-8. Al momento della ricezione, il sistema converte i dati dal set di caratteri della pagina web al set di caratteri UTF-8, in modo da poter utilizzare qualsiasi lingua nei rapporti di marketing. Per modificare il supporto dei caratteri multibyte per una suite di rapporti esistente, contatta il team Adobe Account o l’Assistenza clienti. |
| Attivato | Specifica se la suite di rapporti è attivata o meno. |
| Valuta di base | Consente di specificare la [valuta](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/currencycode.html?lang=it) di base per questa suite di rapporti. |
| ID organizzazione | ID associato alla società di Experience Cloud con provisioning. Questo ID è una stringa alfanumerica composta da 24 caratteri, seguita da (e che deve includere) @AdobeOrg. |
