---
description: Opzioni di calendario diverse dal modello gregoriano. Le opzioni includono i modelli di calendario 4-4-5, 4-5-4 e 5-4-4, tutti utilizzati come standard per il settore retail. Inoltre, il reporting offre un’opzione per un calendario completamente personalizzabile che puoi impostare autonomamente.
title: Personalizza calendario
feature: Admin Tools
exl-id: 2196c7b7-7183-43a8-bb91-5a1e479819d4
source-git-commit: 2c0aef13bdb88b0a7aa9f100c72c21f66a14c8dd
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 1%

---

# Personalizza calendario

Opzioni di calendario diverse dal modello gregoriano. Le opzioni includono i modelli di calendario 4-4-5, 4-5-4 e 5-4-4, tutti utilizzati come standard per il settore retail. Inoltre, il reporting offre un’opzione per un calendario completamente personalizzabile che puoi impostare autonomamente.

**[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > Seleziona suite di rapporti > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Customize Calendar]**

>[!CAUTION]
>
>La modifica del calendario modifica il modo in cui i dati vengono elaborati (ovvero la definizione di visitatori univoci settimanali e mensili). Quando la definizione di settimane e mesi di un calendario cambia, i dati storici non vengono modificati. Questa impostazione ha effetto anche sui segmenti basati su intervalli di date.

È possibile utilizzare il calendario per definire il primo giorno della settimana e dell&#39;anno oppure utilizzare un diverso stile di calendario per la vendita al dettaglio. I formati calendario vengono utilizzati per vari scopi, tra cui il confronto delle vendite e la standardizzazione delle previsioni, l&#39;analisi dei costi del ciclo paghe o la regolamentazione del conteggio delle scorte fisiche. Ad esempio, il settore del commercio al dettaglio utilizza il calendario contabile 4-5-4 per supportare l&#39;attività particolare della stagione di vendita nel settore del commercio al dettaglio. Di seguito sono descritti tutti i formati del calendario.

## Personalizzare le descrizioni del calendario {#section_B0D224DACB914A378902A4E0E1234889}

| Calendario | Descrizione |
|--- |--- |
| Calendario gregoriano | Utilizza il formato calendario tradizionale (da gennaio a dicembre, con 30 o 31 giorni e un numero variabile di settimane in ogni mese). |
| Calendario gregoriano modificato | Utilizza il Calendario gregoriano tradizionale ma ti consente di selezionare il primo mese dell&#39;anno e il primo giorno della settimana. |
| Calendario Retail 4-5-4 | Scomposizione mensile per numero di settimane nel mese. Ciò significa che gennaio ha quattro settimane, e così via. La Federazione nazionale del commercio al dettaglio utilizza il formato calendario 4-5-4. |
| Calendario personalizzato | Offre tre formati in base al numero di settimane in ogni mese. Il numero di settimane in ogni mese dipende dal primo giorno dell’anno selezionato.  Un anno ha 52 settimane. Dividetelo in 4 quarti e ottenete 13 settimane al trimestre. Ma ci sono 3 mesi in un trimestre. 13 non è divisibile per tre quindi si finisce per mettere la settimana extra in uno dei mesi in modo che è sempre coerente.<ul><li>5/4/4 significa che il primo mese del trimestre ha la settimana supplementare. 4/5/4 significa che il secondo mese ha la settimana supplementare, ecc. Nel calendario 5-4-4, la 53a settimana viene aggiunta all&#39;ultimo trimestre dell&#39;anno.</li><li>4-5-4:Gennaio ha quattro settimane, Febbraio ha cinque settimane, Marzo ha quattro settimane, e così via.</li><li>4-4-5: Gennaio ha quattro settimane, Febbraio ha quattro settimane, Marzo ha cinque settimane, e così via.</li><li>5-4-4: Gennaio ha cinque settimane, Febbraio ha quattro settimane, Marzo ha quattro settimane, e così via.</li></ul> |

>[!NOTE]
>Queste opzioni del calendario sono supportate in tutti gli strumenti di Adobe Analytics (Analysis Workspace, Reports &amp; Analytics, Report Builder, Activity Map), eccetto Data Warehouse. La Data Warehouse supporta completamente solo il calendario gregoriano. Quando si sceglie un calendario non gregoriano, la Data Warehouse utilizzerà l&#39;intervallo di date previsto del calendario non gregoriano, tuttavia le suddivisioni giorno/settimana/mese all&#39;interno delle righe del rapporto potrebbero non essere quelle previste da un calendario non gregoriano.
