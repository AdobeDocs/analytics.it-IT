---
description: Modalità di ottimizzazione della distribuzione del generatore di report e un elenco di messaggi di errore che potrebbero verificarsi occasionalmente.
seo-description: Modalità di ottimizzazione della distribuzione del generatore di report e un elenco di messaggi di errore che potrebbero verificarsi occasionalmente.
seo-title: Risoluzione dei problemi e procedure ottimali per Generatore di report
solution: Analytics
title: Risoluzione dei problemi e procedure ottimali per Generatore di report
topic: Generatore di report
uuid: 36 a 08143-dc 78-40 f 5-9 ce 9-7 d 16980 aa 27 b
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Risoluzione dei problemi e procedure ottimali per Generatore di report

Modalità di ottimizzazione della distribuzione del generatore di report e un elenco di messaggi di errore che potrebbero verificarsi occasionalmente.

## Report Builder 5.0 users and opening 5.1 workbooks {#section_C29898775999453FABB5FB0E098415C8}

Adobe ha modificato il separatore tra dimensioni e classificazioni da un carattere carattere di sottolineatura (_) a ||. Questa modifica presenta implicazioni di compatibilità per un utente di Generatore di report 5.0 che apre una cartella di lavoro di Report Builder v5.1 con richieste di classificazione. Ogni volta che viene aperta una cartella di lavoro di una versione precedente alla 5.1, tutte le richieste di classificazione serializzate saranno convertite in questo formato.

Viene presentato un problema di compatibilità: Una volta convertito in v 5.1, se una cartella di lavoro è condivisa con un utente in Generatore di report v 5.0, l'utente non potrà riconoscere la richiesta di classificazione (in realtà sta cercando "_" ma v 5.1 serializzato "||").

Quando aprite una cartella di lavoro ARB v 5.1 con richiesta di classificazione, si verificherà il seguente effetto collaterale:

* Quando aprite la cartella di lavoro, viene visualizzato il seguente avviso: «Questa cartella di lavoro è stata salvata per ultimo tramite Generatore di report v 5.1. Questa versione ha introdotto alcune funzioni incompatibili con la versione di Generatore di report installata in questo computer. Si consiglia vivamente di effettuare l'aggiornamento alla versione più recente di Generatore di report prima di aggiornare questa cartella di lavoro. »»
* Se fai clic con il pulsante destro del mouse su una richiesta ARB con classificazione, i menu di scelta rapida del Generatore di report (modifica richiesta, Aggiungi richiesta dipendente…) non verranno visualizzati.
* Se esegui un aggiornamento All, facendo clic sul terzo pulsante o aggiornando un set di richieste dal modulo di gestione richieste, la richiesta di classificazione viene eseguita senza errori. Tuttavia, i valori di classificazione non verranno scritti.
* Potete comunque modificare la richiesta aprendo Request Manager, quindi passare dalla riga alla riga fino a raggiungere la richiesta corretta.
* Se modificate la richiesta e lasciate tutti i parametri invariati e quindi fate clic su Fine, la risposta verrà scritta correttamente. La modifica della richiesta risolve il problema quando i parametri di Layout risposta vengono nuovamente serializzati. È quindi disponibile una soluzione alternativa, ma si consiglia di risparmiare tempo.

## Authentication issues in Report Builder {#section_FD79104DF1414FE2B36591606C963DE6}

Il Generatore di report richiede l'autenticazione per creare richieste di dati dalle suite di rapporti. Sometimes there are issues logging in to report builder depending on your settings within [!DNL Analytics] or your network.

**Società di accesso non valida**

Questo errore si verifica maggiormente quando la società di accesso è immessa in modo errato oppure se sono presenti problemi di attività di rete. Effettuate le seguenti operazioni:

* Controllate l'ortografia della società di accesso per assicurarvi che non sia presente un errore ortografico o un errore.
* Accedi ad Analytics con la stessa società di accesso per assicurarti che sia corretta. Se non siete in grado di accedere a tali credenziali, contattate uno degli amministratori della vostra organizzazione per ottenere la corretta società di accesso.

**Firewall**

Generatore di report utilizza le porte 80 e 443. Assicuratevi che queste porte siano consentite tramite il firewall aziendale. Consultate anche gli indirizzi IP interni di Adobe per ulteriori esclusioni firewall.

## Recommendations for optimizing requests {#section_33EF919255BF46CD97105D8ACB43573F}

I fattori seguenti possono aumentare la complessità delle richieste e rallentare l'elaborazione:

**Fattori che possono rallentare le consegne**

* Sono stati pianificati troppi segnalibri, dashboard e cartelle di lavoro Generatore di report tra poche ore
* Troppi libri di lavoro di Generatore di report sono stati pianificati contemporaneamente. In tal caso, la coda API report viene registrata in background.

**Fattori che possono rallentare il runtime di una cartella di lavoro**

* Aumento significativo delle classificazioni.
* Aumento dell'intervallo di date della richiesta nel tempo.

   **Esempio**: Supponiamo di creare una richiesta con tendenze utilizzando l'impostazione Anno corrente, suddivise per granularità Giorno. Alla fine dell'anno, la richiesta restituirà più periodi rispetto a quella creata all'inizio dell'anno.

   `(January 1 - January 30 versus January 1 - December 31.)`

**Causa di errori di consegna della cartella di lavoro**

Formule Excel complesse in una cartella di lavoro, in particolare quelle che richiedono data e ora.

**Celle che restituiscono 0 s (nessun valore)**

Un apostrofo o una virgoletta singola nel nome del foglio Excel causerà la mancata restituzione di valori da parte del generatore di report. (Questa è una limitazione di Microsoft Excel).

**Prestazioni singole richieste**

La velocità di elaborazione può essere modificata dalle seguenti impostazioni:

| Impostazione | Prestazioni più veloci | Prestazioni lente |
|--- |--- |--- |
| Suddivisioni e ordine di suddivisione | Pochi | Molti |
|  | Esempio: Se si suddivide A per Z, il numero di elementi per A deve essere sempre minore del numero di elementi per Z. Se questa situazione è opposta, il tempo di richiesta può aumentare in modo significativo. |
| Intervallo date | Intervallo piccolo | Ampia gamma |
| Filtro | Filtro specifico | Filtro più popolare |
| Granularity (Granularità) | Aggregato | Orario<ul><li>Giornaliero</li><li>Settimanale</li><li>Mensile</li><li>Trimestrale</li><li>Annuale</li></ul> |
| Numero di voci | Set di dati piccolo | Set di dati grande |


**Pianificazione della pianificazione**

Pianificazione di Stagger su 24 ore (vedete la tabella seguente). I segnalibri, le dashboard e i libri di lavoro di Generatore di report esistenti pianificati insieme possono causare ritardi.

Programmate richieste più grandi e più complesse all'inizio della mattina per consentire l'esecuzione di macchie manuali e la relativa aggiornamento durante il giorno lavorativo.

| Tempo di pianificazione | dalle 1 alle 2. | dalle 2 alle 7. | dalle 7 alle 6. | 6 PM - Mezzanotte |
|--- |--- |--- |--- |--- |
| Utilizzo del Generatore di report | Silenzioso | Molto occupato | Utilizzo sul lato client.<br>Più grandi quantità di utenti che si aggiornano localmente e richiedono "Invia immediatamente".<br>Inoltre, verificate che la coda API venga cancellata in caso di timeout dei documenti di lavoro pianificati. | Non occupato |

**Timeout**

Qualsiasi rapporto pianificato scade dopo quattro ore. La pianificazione dei tentativi del sistema è stata pianificata tre ulteriori volte, generando potenzialmente un errore. (Generalmente, più grande è il set di dati più tempo necessario per eseguire.) These can be seen in [!DNL Analytics] reporting and Report Builder:

* [!DNL Analytics]: **[!UICONTROL Favorites]** &gt; **[!UICONTROL Scheduled Reports]**

* Report Builder: Click **[!UICONTROL Management]** in the [!UICONTROL Add-ins] tab in Excel.

## Error message descriptions {#section_3DF3A1EEDAD149CB941BEABEF948A4A5}

Elenco di messaggi di errore che possono verificarsi talvolta durante l'utilizzo di Generatore di report.

>[!NOTE]
>
>Si tratta solo di una selezione di messaggi di errore e non di un elenco completo. Per ulteriori informazioni sulla risoluzione degli errori, contattate l'amministratore.

**Questa funzione può essere applicata solo a una cartella di lavoro aperta.**

Se in Excel non sono aperti documenti di lavoro (documenti fogli di calcolo) e fate clic su una delle icone nella barra degli strumenti del generatore di report, viene visualizzato questo messaggio. Inoltre, la barra degli strumenti diventa disattivata finché non si apre un foglio di calcolo. Tuttavia, potete fare clic sull'icona della guida online mentre la barra degli strumenti è ancora abilitata senza che questo sia stato risolto.

**Prima di attivare[!UICONTROL Request Wizard]l'[!UICONTROL Request Manager]evento dovete uscire.**

While the [!UICONTROL Request Manager] and the [!UICONTROL Request Wizard] are linked functionally, it is not possible to start working with the [!UICONTROL Request Manager] before completing or cancelling actions taken in the [!UICONTROL Request Wizard].

**Non esiste una richiesta associata a questo intervallo.**

This error message occurs if you click on the [!UICONTROL From Sheet] button in the [!UICONTROL Request Manager] when a cell of the spreadsheet contains no requests.

To identify which cells in the spreadsheet contain requests, click individual requests listed in the table in the [!UICONTROL Request Manager]. Se una richiesta è associata a celle, le celle risulteranno evidenziate quando la richiesta viene selezionata nella tabella.

**L'intervallo selezionato non è valido. Please select another Range.**

Se una cella del foglio di calcolo è selezionata e vi è già una richiesta mappata su di essa, si verifica l'errore. Eliminate la richiesta mappata sulle celle o scegliete un'altra serie di celle da mappare.

Quando si desidera eliminare le celle, è importante individuare le celle contenenti richieste ed eliminare la richiesta prima di eliminare le celle (rimuovere righe o colonne).

**Prima di usare questa funzione, uscite dalla cella Excel con lo stato attivo.**

If you are in *edit mode* in an Excel cell and click one of the Report Builder icons, this error message appears. La modalità Modifica in una cella Excel indica che la cella è selezionata e che il cursore viene visualizzato all'interno della cella. You are also in edit mode in an Excel cell when you type directly into the [!UICONTROL Formula] bar or into the [!UICONTROL Name Box] at the top of Excel.

**L'intervallo selezionato interseca l'intervallo di un'altra richiesta. Please change your selection.**

Se avete già mappato un set di celle sul foglio di calcolo, viene visualizzato questo errore.

One way to determine which cells are mapped before adding new requests is to close the [!UICONTROL Request Wizard] and open the [!UICONTROL Request Manager]. Quindi, selezionate una volta per volta gli elementi elencati nella tabella di riepilogo della richiesta. Ogni volta che selezionate una richiesta nell'elenco, vengono evidenziate le celle corrispondenti contenenti mappature di richiesta nel foglio di calcolo.

Questo è uno dei motivi per cui è opportuno considerare le celle con evidenziazione, informazioni di riga o colonna o uno stile di formattazione prima di mappare più celle in più aree.
