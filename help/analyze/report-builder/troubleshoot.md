---
description: Consente di ottimizzare la distribuzione del generatore di report e un elenco di messaggi di errore che possono verificarsi occasionalmente.
seo-description: Consente di ottimizzare la distribuzione del generatore di report e un elenco di messaggi di errore che possono verificarsi occasionalmente.
seo-title: Risoluzione dei problemi e Procedure consigliate per Report Builder
solution: Analytics
title: Risoluzione dei problemi e Procedure consigliate per Report Builder
topic: Generatore di report
uuid: 36a08143-dc78-40f5-9ce9-7d16980aa27b
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Risoluzione dei problemi e Procedure consigliate per Report Builder

Consente di ottimizzare la distribuzione del generatore di report e un elenco di messaggi di errore che possono verificarsi occasionalmente.

## Utenti di Generatore di report 5.0 e apertura di cartelle di lavoro 5.1 {#section_C29898775999453FABB5FB0E098415C8}

Adobe ha modificato il separatore tra dimensioni e classificazioni da carattere di sottolineatura (_) a|| Questa modifica presenta implicazioni di compatibilità per un utente di Generatore di report 5.0 che apre una cartella di lavoro di Report Builder v5.1 con richieste di classificazione. Ogni volta che una cartella di lavoro di una versione precedente alla v5.1 viene aperta, tutte le relative richieste di classificazione serializzate verranno convertite in questo formato.

Questo introduce un problema di compatibilità: Una volta convertita in v5.1, se una cartella di lavoro viene condivisa con un utente in Generatore di report v5.0, tale utente non sarà in grado di riconoscere la richiesta di classificazione (in realtà, cerca "_" ma v5.1 serializzato "|").

Si verificherà il seguente effetto collaterale all'apertura di una cartella di lavoro ARB v5.1 con richiesta di classificazione:

* Quando si apre la cartella di lavoro, viene visualizzato il seguente avviso: "L'ultima cartella di lavoro è stata salvata con Generatore di report v5.1. Questa versione ha introdotto alcune funzionalità incompatibili con la versione del Generatore di report installata nel computer. Prima di aggiornare la cartella di lavoro, si consiglia di effettuare l'aggiornamento alla versione più recente del Generatore di report."
* Se fai clic con il pulsante destro del mouse su una richiesta ARB con classificazione, i menu contestuali del Generatore di report (richiesta di modifica, aggiunta di richiesta dipendente...) non verranno visualizzati.
* Se si esegue un aggiornamento di tutti, facendo clic sul terzo pulsante o aggiornando un set di richieste dal modulo Request Manager, la richiesta di classificazione verrà eseguita senza errore. Tuttavia, i valori delle classificazioni non saranno scritti.
* È comunque possibile modificare la richiesta aprendo Request Manager, quindi passando da una riga all'altra fino a raggiungere la richiesta corretta.
* Se modificate la richiesta e lasciate tutti i parametri identici e fate clic su Fine, la risposta verrà scritta correttamente. La modifica della richiesta risolve il problema mano a mano che i parametri del layout di risposta vengono serializzati nuovamente. C'è una soluzione alternativa, anche se richiede tempo.

## Problemi di autenticazione nel Generatore di report {#section_FD79104DF1414FE2B36591606C963DE6}

Generatore di report richiede l'autenticazione per creare richieste di dati dalle suite di rapporti. A volte si verificano problemi durante l'accesso al generatore di report a seconda delle impostazioni all'interno [!DNL Analytics] o della rete.

**Società di accesso non valida**

Questo errore si verifica in genere quando la società di accesso viene immessa in modo non corretto o in presenza di problemi di attività di rete. Effettuate le seguenti operazioni:

* Per verificare che non sia presente un errore ortografico o uno spazio errato, controllate l’ortografia della società di accesso.
* Accedete ad Analytics con la stessa società di accesso per assicurarvi che sia corretta. Se non riuscite ad accedere con tali credenziali, contattate uno degli amministratori dell'organizzazione per ottenere la società di accesso corretta.

**Firewall**

Generatore di report utilizza le porte 80 e 443. Assicurati che queste porte siano consentite attraverso il firewall aziendale. Per ulteriori esclusioni del firewall, consultate anche Indirizzi IP interni di Adobe.

## Raccomandazioni per l'ottimizzazione delle richieste {#section_33EF919255BF46CD97105D8ACB43573F}

I seguenti fattori possono aumentare la complessità delle richieste e rallentare l’elaborazione:

**Fattori che possono rallentare le consegne**

* Troppi segnalibri, dashboard e cartelle di lavoro di Generatore di report sono stati pianificati in poche ore
* Troppe cartelle di lavoro del Generatore di report sono state pianificate nello stesso momento. In questo caso, la coda dell'API del report viene retroregistrata.

**Fattori che possono rallentare il runtime della cartella di lavoro**

* Incremento significativo delle classificazioni.
* Incremento dell'intervallo di date della richiesta nel tempo.

   **Esempio**: Supponete di creare una richiesta con tendenze utilizzando l’impostazione Anno corrente, suddivisa per granularità Giorno. Alla fine dell'anno, la richiesta restituirà più periodi di quelli creati all'inizio dell'anno.

   `(January 1 - January 30 versus January 1 - December 31.)`

**Cause che causano errori di consegna della cartella di lavoro**

Formule Excel complesse in una cartella di lavoro, in particolare quelle che includono data e ora.

**Celle che restituiscono 0 (nessun valore)**

Un apostrofo o una citazione singola nel nome del foglio di Excel causerà la mancata restituzione di valori da parte del generatore di report. Limitazione di Microsoft Excel.

**Prestazioni singole richieste**

La velocità di elaborazione può essere influenzata dalle seguenti impostazioni:

| Impostazione | Prestazioni più rapide | Prestazioni più lente |
|--- |--- |--- |
| Suddivisioni e ordine di disaggregazione | Pochi | Molti |
|  | Esempio: Se si suddivide A per Z, il numero di elementi per A deve sempre essere minore del numero di elementi per Z. Se è il contrario, il tempo di richiesta può aumentare notevolmente. |
| Intervallo date | Piccola gamma | Ampia gamma |
| Filtro | Filtro specifico | Filtro più popolare |
| Granularity (Granularità) | Aggregato | Ogni ora<ul><li>Giornaliero</li><li>Settimanale</li><li>Mensile</li><li>Trimestrale</li><li>Annuale</li></ul> |
| Numero di voci | Piccolo set di dati | Set di dati grande |


**Tempo di programmazione**

Programmazione scaglionata su un periodo di 24 ore (vedere la tabella seguente). I segnalibri, le dashboard e le cartelle di lavoro del Generatore di report esistenti pianificate insieme potrebbero causare ritardi.

Programmare richieste più grandi e complesse nelle prime ore del mattino per consentire l'esecuzione di rilasci manuali e rinfrescanti durante la giornata lavorativa.

| Tempo di programmazione | 1:00 - 2.00 | 2 - 7.00 | 7 - 18:00 | 18 - Midnight |
|--- |--- |--- |--- |--- |
| Utilizzo di Generatore di report | Tranquillo | Molto occupato | Utilizzo lato client.<br>Volumi più elevati di utenti che aggiornano localmente e richiedono di inviarli immediatamente.<br>Inoltre, verificare se la coda API viene cancellata quando i libri di lavoro pianificati scadono. | Non occupato |

**Timeout**

Eventuali report pianificati scadono dopo quattro ore. Il sistema tenta di eseguire la programmazione tre volte di più, con la possibile conseguenza di un errore. (Generalmente, più grandi sono i dati impostati più lunghi sono i tempi di esecuzione.) Questi sono visibili in Generatore di [!DNL Analytics] report e Generatore di report:

* [!DNL Analytics]: **[!UICONTROL Favorites]** &gt; **[!UICONTROL Scheduled Reports]**

* Generatore di report: Fare clic **[!UICONTROL Management]** nella [!UICONTROL Add-ins] scheda in Excel.

## Descrizioni dei messaggi di errore {#section_3DF3A1EEDAD149CB941BEABEF948A4A5}

Elenco di messaggi di errore che possono verificarsi occasionalmente durante l'utilizzo di Generatore di report.

> [!NOTE] Si tratta solo di una selezione di messaggi di errore e non di un elenco completo. Per ulteriori informazioni sulla risoluzione degli errori, contattare l'amministratore.

**Questa funzione può essere applicata solo a una cartella di lavoro aperta.**

Se in Excel non sono aperte cartelle di lavoro (documenti foglio di calcolo) e si fa clic su una delle icone nella barra degli strumenti del generatore di report, viene visualizzato questo messaggio. Inoltre, la barra degli strumenti viene disattivata fino all’apertura di un foglio di calcolo. Tuttavia, è possibile fare clic sull'icona della guida in linea mentre la barra degli strumenti è ancora attivata senza causare questo errore.

**Prima di attivare l’[!UICONTROL Request Wizard]opzione è necessario uscire dall’applicazione[!UICONTROL Request Manager].**

Anche se il collegamento [!UICONTROL Request Manager] e il collegamento [!UICONTROL Request Wizard] sono funzionalmente, non è possibile iniziare a lavorare con il [!UICONTROL Request Manager] sistema prima di completare o annullare le azioni eseguite nel [!UICONTROL Request Wizard].

**Nessuna richiesta associata a questo intervallo.**

Questo messaggio di errore si verifica se si fa clic sul [!UICONTROL From Sheet] pulsante nel [!UICONTROL Request Manager] caso in cui una cella del foglio di calcolo non contenga richieste.

Per identificare le celle del foglio di calcolo contenenti richieste, fate clic su singole richieste elencate nella tabella nella [!UICONTROL Request Manager]. Se una richiesta è associata alle celle, le celle vengono evidenziate quando la richiesta viene selezionata nella tabella.

**L'intervallo selezionato non è valido. Selezionare un altro intervallo.**

Se è selezionata una cella del foglio di calcolo a cui è già stata associata una richiesta, si verifica questo errore. Eliminare la richiesta mappata alle celle o scegliere un altro intervallo di celle da mappare.

Per eliminare le celle, è importante individuare le celle contenenti richieste ed eliminare la richiesta prima di eliminare le celle (rimuovere righe o colonne).

**Uscire dalla cella Excel con lo stato attivo prima di utilizzare questa funzione.**

Se siete in modalità *di* modifica in una cella Excel e fate clic su una delle icone Generatore di report, viene visualizzato questo messaggio di errore. La modalità di modifica in una cella Excel indica che la cella è selezionata e il cursore viene visualizzato all'interno della cella. In una cella di Excel è inoltre attiva la modalità di modifica quando si digita direttamente nella [!UICONTROL Formula] barra o nella [!UICONTROL Name Box] parte superiore di Excel.

**L'intervallo selezionato interseca l'intervallo di un'altra richiesta. Modifica la selezione.**

Se avete già mappato un set di celle al foglio di calcolo, questo errore viene visualizzato.

Un modo per determinare quali celle vengono mappate prima di aggiungere nuove richieste consiste nel chiudere [!UICONTROL Request Wizard] e aprire il [!UICONTROL Request Manager]. Quindi, selezionate gli elementi elencati nella tabella di riepilogo delle richieste uno per uno. Ogni volta che selezionate una richiesta nell’elenco, vengono evidenziate le celle corrispondenti contenenti le mappature delle richieste nel foglio di calcolo.

Questo è uno dei motivi per cui è consigliabile contrassegnare le celle con le informazioni di evidenziazione, riga o colonna o uno stile di formattazione prima di mappare più celle su più aree.
