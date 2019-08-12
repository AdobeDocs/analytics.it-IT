---
description: nulle
seo-description: nulle
seo-title: Esempi di etichettatura
title: Esempi di etichettatura
uuid: a 9 a 5 b 937-dbde -4 f 0 f-a 171-005 ef 4 c 79 df 9
translation-type: tm+mt
source-git-commit: edafa9ca8dc34bd1f3af8c56b4f23c4a983aa677

---


# Esempi di etichettatura

## Dati di esempio dei risultati

Supponi di avere i dati seguenti:

* La prima riga contiene le etichette per ogni variabile.
* La seconda riga è il nome della variabile. Se ha un’etichetta ID, contiene lo spazio dei nomi assegnato tra parentesi.
* I dati dei risultati partono dalla terza riga.

| Etichette | I2<br>ID-PERSONCAN@-@ PERSONACC<br><br>-PERSON | I 2<br>ID-DEVICECAN@-@ DEVICEACC<br><br>-ALL | I 2<br>DI-PERSONACC<br>-PERSON | I 2<br>CAN@-@ DEVICEDELL<br>-PERSONACC<br>-ALL | I 2<br>ID-DEVICECAN@-@ DEVICEACC<br><br>-ALL |
|---|---|---|---|---|---|
| **Nome variabile**<br>**(spazio nomi)** | **Myprop 1**<br>**(utente)** | **ID visitatore**<br>**(AAID)** | **MyEvar1** | **MyEvar2** | **MyEvar3**<br>**(xyz)** |
| Dati dei risultati | Mary | 77 | A | M | X |
|  | Mary | 88 | B | N | Y |
|  | Mary | 99 | C | O | Z |
|  | John | 77 | D | P | W |
|  | John | 88 | E | N | U |
|  | John | 44 | F | Q | V |
|  | John | 55 | G | R | X |
|  | Alice | 66 | A | N | Z |

## Richiesta di accesso di esempio

Se si invia una richiesta di accesso, il file di riepilogo conterrà i valori indicati nella tabella seguente. Una richiesta può restituire solo un file di dispositivo, solo un file di persona o entrambi. Due file di riepilogo vengono restituiti solo se viene usato un ID persona ed expandIDs è true.

| Valori API | Valori API | Tipo di file restituito | Data in <br>Summary Access File | Data in <br>Summary Access File | Data in <br>Summary Access File | Data in <br>Summary Access File | Data in <br>Summary Access File |
|--- |--- |--- |---|---|---|---|---|
| **Namespace/ID** | **expandIDs** |  | **MyProp1** | **Visitor ID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| AAID=77 | false | dispositivo | Variabile assente | 77 | Variabile assente | M, P | X, W |
| AAID=77 | true | dispositivo | Variabile assente | 77 | Variabile assente | M, P | X, W |
| user=Mary | false | persona | Mary | 77, 88, 99 | A, B, C | M, N, O | X, Y, Z |
| user=Mary | true | persona | Mary | 77, 88, 99 | A, B, C | M, N, O | X, Y, Z |
| user=Mary | true | dispositivo | assente | 77, 88 | assente | N, P | U, W |
| user=Mary AAID=66 | true | persona | Mary | 77, 88, 99 | A, B, C | M, N, O | X, Y, Z |
| user=Mary AAID=66 | true | dispositivo | assente | 66, 77, 88 | assente | N, P | U, W, Z |
| xyz=X | false | dispositivo | assente | 55, 77 | assente | M, R | X |
| xyz=X | true | dispositivo | assente | 55, 77 | assente | M, P, R | W, X |

Si noti che le impostazioni di expandIDs non cambiano nell’output quando viene usato un ID cookie.

## Richiesta di cancellazione di esempio

Se la richiesta di cancellazione usa i valori dell’API nella prima riga della tabella, la tabella dei risultati verrà aggiornata e apparirà come la seguente:

| AAID=77 expandIDs value<br>does not matter | AAID=77 expandIDs value<br>does not matter | AAID=77 expandIDs value<br>does not matter | AAID=77 expandIDs value<br>does not matter | AAID=77 expandIDs value<br>does not matter |
|---|---|---|---|---|
| **MyProp1** | **AAID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| Mary | 42 | A | GDPR-7398 | GDPR-9152 |
| Mary | 88 | B | N | Y |
| Mary | 99 | C | O | Z |
| John | 42 | D | GDPR-1866 | GDPR-8216 |
| John | 88 | E | N | U |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

>[!NOTE] Vengono influenzate solo le celle sulle righe contenenti AAID = 77 e un'etichetta Dell-DEVICE.

| user = maryexpanddids<br>= false | user = maryexpanddids<br>= false | user = maryexpanddids<br>= false | user = maryexpanddids<br>= false | user = maryexpanddids<br>= false |
|--- |---|---|---|---|
| **MyProp1** | **AAID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| GDPR-0523 | 77 | GDPR-1866 | GDPR-3681 | X |
| GDPR-0523 | 88 | GDPR-2178 | GDPR-1975 | Y |
| GDPR-0523 | 99 | GDPR-9045 | GDPR-2864 | Z |
| John | 77 | D | P | W |
| John | 88 | E | N | U |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

>[!NOTE] Vengono influenzate solo le celle sulle righe contenenti user = Mary e un'etichetta Dell-PERSON. In pratica, la variabile contenente A_ID probabilmente è una proprietà o un’eVar e il valore di sostituzione è una stringa che inizia con “GDPR-” seguito da un numero a caso (GUID), invece di un diverso valore numerico casuale.

| user=Mary<br>expandIDs=true | user = maryexpanddids<br>= true | user = maryexpanddids<br>= true | user = maryexpanddids<br>= true | user = maryexpanddids<br>= true |
|--- |---|---|---|---|
| **MyProp1** | **AAID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| GDPR-5782 | 09 | GDPR-0859 | GDPR-8183 | GDPR-9152 |
| GDPR-5782 | 16 | GDPR-6104 | GDPR-2911 | GDPR-6821 |
| GDPR-5782 | 83 | GDPR-2714 | GDPR-0219 | GDPR-4395 |
| John | 09 | D | GDPR-8454 | GDPR-8216 |
| John | 16 | E | GDPR-2911 | GDPR-2930 |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

Tenete presente quanto segue:

* Cells on rows containing `user=Mary` and a `DEL-DEVICE` or `DEL-PERSON` label are impacted, as well as cells with a `DEL-DEVICE` label on rows containing any Visitor ID that occurred on a row containing `user=Mary`.
* `MyEvar2` nella quarta e nella quinta riga viene aggiornato perché queste righe contengono gli stessi valori ID visitatore di quelli nella prima e nella seconda riga, pertanto l’espansione dell’ID li include per le cancellazioni a livello di dispositivo.
* The values of `MyEvar2` in rows two and five match both before and after the delete, but after the delete no longer matches the value N that occurs in the last row, because that row was not updated as part of the delete request.
* `MyEvar3` si comporta in modo molto diverso rispetto alla versione senza l’espansione dell’ID, in quanto senza l’espansione dell’ID, nessun corrisponde. `ID-DEVICES` `AAID` Ora corrisponde alle prime cinque righe.
