---
description: Descrizioni dei campi per le impostazioni account generali della suite di rapporti in Amministratore.
title: Impostazioni account generali
feature: Admin Tools
uuid: c1ab5c34-2c41-4d12-a706-0e760dff8a95
exl-id: f49babb2-8e26-4cc6-b264-b4d7be93f130
TQID: 'https://experienceleague.adobe.com/1HGpY4lstZB6baXYggrD4xni1SWbYTDLa2fqYw11yd4'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 1ed4ab984231b7c72580c5ae505b1a16c0330c2f
workflow-type: tm+mt
source-wordcount: 663
ht-degree: 66%

---

# Impostazioni account generali

Descrizioni dei campi per le impostazioni generali account di una suite di rapporti in Amministratore.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL General Account Settings]**

Queste impostazioni contengono opzioni di modifica per le funzionalità di base della suite di rapporti, come nome e fuso orario.


>[!BEGINSHADEBOX]

Consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Configurazione delle impostazioni account generali](https://experienceleague.adobe.com/it/docs/analytics-learn/tutorials/administration/manage-report-suites/configuring-general-account-settings){target="_blank"} per un video dimostrativo.

>[!ENDSHADEBOX]

| Opzione | Descrizione |
|--- |--- |
| Titolo sito | Identifica il tuo sito. Attribuisci a ciascuna suite di rapporti un titolo univoco del sito. |
| URL di base | Specifica il sito web principale della suite di rapporti. L&#39;URL di base non influisce sul filtro del referente. Utilizza, invece, [filtri URL interni](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md). |
| Fuso orario | Determina la data e l’ora associate ai dati del report. Se il fuso orario selezionato osserva l’ora legale, i dati orari vengono automaticamente regolati in modo da riflettere tale situazione. La modifica del fuso orario per una suite di rapporti in tempo reale crea un picco o un intervallo nei dati del rapporto. Adobe consiglia di apportare questa modifica durante le ore non di picco per ridurre al minimo l’impatto. |
| Pagina predefinita | Se il report [!UICONTROL Most Popular Pages] contiene URL invece che nomi della pagnia, questa impostazione impedisce a più URL di rappresentare la stessa pagina. Ad esempio, gli URL `https://example.com` e `https://example.com/index.html` sono in genere la stessa pagina. È possibile rimuovere i nomi di file predefiniti in modo che questi due URL vengano visualizzati entrambi come `https://example.com`.  Se lasciato vuoto, i seguenti nomi di file vengono rimossi dagli URL: index.htm, index.html, index.cgi, index.asp, default.htm, default.html, default.cgi, default.asp, home.htm, home.html, home.cgi e home.asp.  Per disattivare completamente lo stripping dei nomi di file, immetti un valore che non è mai presente negli URL. |
| Sostituire l’ultimo ottetto degli indirizzi IP con 0 | Quando questa opzione è attivata, sostituisce l’ultimo ottetto degli indirizzi IP con uno zero. Ciò si verifica prima che i rapporti relativi alla geolocalizzazione vengano compilati e può quindi influire sulla precisione di tali rapporti. |
| Offuscamento IP | Trasforma gli indirizzi IP in stringhe non riconoscibili, essenzialmente rimuovendoli dagli archivi di dati di Adobe. Quando IP Obfuscation è abilitato, gli indirizzi IP originali vengono persi definitivamente. <br> **Nota**: gli indirizzi IP vengono offuscati ovunque in Analytics, inclusa la Data Warehouse. Tuttavia, l&#39;impostazione IP in Target è controllata separatamente, pertanto questa impostazione non ha alcun impatto su Target.<br> Se l’offuscamento dell’IP è abilitato, tutte le operazioni di elaborazione necessarie, inclusi i filtri/esclusione IP, le regole bot e le ricerche per la geosegmentazione, vengono eseguite prima che l’indirizzo IP sia offuscato. Non è necessario modificare nulla quando si abilita l’offuscamento dell’IP.<ul><li>La selezione di **Disabilitato** lascia l’indirizzo IP nei dati.</li><li>La selezione di **Indirizzo IP offuscato** cambia l’IP in due punti seguiti da un valore con hash (ad esempio, `::1932023538`).</li><li>La verifica di **Rimuovi indirizzo IP** sostituisce l&#39;indirizzo IP con `::X.X.X.X` nei dati, dopo la ricerca geografica.<br/>Questa opzione è selezionata per impostazione predefinita per le nuove suite di rapporti.</li></ul>**Nota**: questa impostazione potrebbe richiedere modifiche alle [regole bot](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md) o [esclusioni IP](/help/admin/tools/exclude-ip.md) personalizzate.<br> **Nota**: ai dati raccolti tramite Web SDK può essere applicata l&#39;offuscamento dell&#39;IP in Edge Network tramite [configurazione del flusso di dati](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=it#@advanced-options). Se l’offuscamento dell’IP viene applicato in Edge Network, esso risulta già offuscato quando questo raggiunge Analytics. Questa offuscamento influisce sulle regole bot e sulle ricerche geografiche. |
| Archiviazione ID transazione | Consente di utilizzare [ID transazione](/help/import/data-sources/transactionid.md) origini dati. |
| Abilita Data Warehouse | Abilita l’interfaccia utente Data Warehouse in Analytics > Strumenti > Data Warehouse. |
| Opzione ZIP | Consente di specificare il codice postale anziché utilizzare qualsiasi prodotto dalla ricerca IP geografica. |
| Supporto di caratteri multibyte | Il supporto per caratteri multibyte memorizza i caratteri nella suite di rapporti utilizzando il formato UTF-8. Al momento della ricezione, il sistema converte i dati dal set di caratteri della pagina web al set di caratteri UTF-8, in modo da poter utilizzare qualsiasi lingua nei rapporti di marketing. Per modificare il supporto dei caratteri multibyte per una suite di rapporti esistente, contatta il team Adobe Account o l’Assistenza clienti. |
| Attivato | Specifica se la suite di rapporti è attivata o meno. |
| Valuta di base | Consente di specificare la [valuta](/help/implement/vars/config-vars/currencycode.md) di base per questa suite di rapporti. |
| ID organizzazione | L&#39;ID associato all&#39;azienda con provisioning CX Enterprise. Questo ID è una stringa alfanumerica composta da 24 caratteri, seguita da (e che deve includere) @AdobeOrg. |
