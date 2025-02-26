---
description: Opzioni di calendario diverse dal modello gregoriano. Le opzioni includono i modelli di calendario 4-4-5, 4-5-4 e 5-4-4, tutti utilizzati come standard per il settore della vendita al dettaglio. Il reporting offre anche un calendario completamente personalizzabile che puoi impostare autonomamente.
title: Personalizza calendario
feature: Admin Tools
exl-id: 2196c7b7-7183-43a8-bb91-5a1e479819d4
role: Admin
source-git-commit: d5bbba7518529befabb8815ac657336326562fd1
workflow-type: tm+mt
source-wordcount: '553'
ht-degree: 94%

---

# Personalizza calendario

Opzioni di calendario diverse dal modello gregoriano. Le opzioni includono i modelli di calendario 4-4-5, 4-5-4 e 5-4-4, tutti utilizzati come standard per il settore della vendita al dettaglio. Inoltre, il reporting offre un’opzione per un calendario completamente personalizzabile che puoi impostare autonomamente.

**[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > Seleziona suite di rapporti > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Customize Calendar]**

>[!CAUTION]
>
>La modifica del calendario cambia il modo in cui i dati vengono elaborati (ovvero la definizione di visitatori univoci settimanali e mensili). Quando la definizione di settimane e mesi di un calendario cambia, i dati storici non vengono modificati. Questa impostazione ha effetto anche sui segmenti basati su intervalli di date.

Puoi utilizzare il calendario per definire il primo giorno della settimana e dell’anno oppure utilizzare un diverso stile di calendario per la vendita al dettaglio. I formati del calendario vengono utilizzati per vari scopi, tra cui il confronto delle vendite e la standardizzazione delle previsioni, l’analisi dei costi per paghe e contributi o la regolamentazione del conteggio delle scorte a magazzino. Ad esempio, il settore del commercio al dettaglio utilizza il calendario contabile 4-5-4 per supportare l’attività della stagione di vendita specifica per il commercio al dettaglio. Di seguito sono descritti tutti i formati del calendario.

## Personalizzare le descrizioni del calendario {#section_B0D224DACB914A378902A4E0E1234889}

| Calendario | Descrizione |
|--- |--- |
| Calendario gregoriano | Utilizza il formato tradizionale del calendario (da gennaio a dicembre, con 30 o 31 giorni e un numero variabile di settimane in ogni mese). |
| Calendario gregoriano modificato | Utilizza il calendario gregoriano tradizionale ma consente di selezionare il primo mese dell’anno e il primo giorno della settimana. |
| Calendario 4-5-4 per vendita al dettaglio | Raggruppa ogni mese in base al numero di settimane nel mese. Ciò significa che gennaio ha quattro settimane e così via. La Federazione nazionale del commercio al dettaglio utilizza il formato di calendario 4-5-4. |
| Calendario personalizzato | Offre tre formati in base al numero di settimane in ogni mese. Il numero di settimane in ogni mese dipende dal primo giorno dell’anno selezionato.  Un anno ha 52 settimane. Dividilo in 4 trimestri e ottieni 13 settimane al trimestre. Ma ci sono 3 mesi in un trimestre. 13 non è divisibile per tre quindi la settimana extra viene inserita in uno dei mesi in modo da mantenere la coerenza.<ul><li>5-4-4 significa che il primo mese del trimestre contiene una settimana supplementare. 4-5-4 significa che il secondo mese contiene la settimana supplementare e così via. Nel calendario 5-4-4, la 53a settimana viene aggiunta all’ultimo trimestre dell’anno.</li><li>4-5-4:gennaio ha quattro settimane, febbraio ha cinque settimane, marzo ha quattro settimane e così via.</li><li>4-4-5: Gennaio ha quattro settimane, Febbraio ha quattro settimane, Marzo ha cinque settimane, e così via.</li><li>5-4-4: gennaio ha cinque settimane, febbraio ha quattro settimane, marzo ha quattro settimane e così via.</li></ul> |

>[!NOTE]
>Queste opzioni del calendario sono supportate in tutti gli strumenti di Adobe Analytics (Analysis Workspace, Report Builder, Activity Map) eccetto Data Warehouse. Data Warehouse supporta completamente solo il calendario gregoriano. Quando si sceglie un calendario non gregoriano, Data Warehouse utilizza l’intervallo di date previsto del calendario non gregoriano, tuttavia è possibile che i raggruppamenti di giorni/settimane/mesi all’interno delle righe del rapporto non siano quelli previsti da un calendario non gregoriano.
