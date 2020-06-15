---
description: 'null'
title: Esempi di etichettatura
uuid: a9a5b937-dbde-4f0f-a171-005ef4c79df9
translation-type: ht
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Esempi di etichettatura

## Dati di esempio dei risultati

Supponi di avere i dati seguenti:

* La prima riga contiene le etichette per ogni variabile.
* La seconda riga è il nome della variabile. Se ha un’etichetta ID, contiene lo spazio dei nomi assegnato tra parentesi.
* I dati dei risultati partono dalla terza riga.

| Etichette | I2<br>ID-PERSON<br>DEL-PERSON<br>ACC-PERSON | I2<br>ID-DEVICE<br>DEL-DEVICE<br>ACC-ALL | I2<br>DEL-PERSON<br>ACC-PERSON | I2<br>DEL-DEVICE<br>DEL-PERSON<br>ACC-ALL | I2<br>ID-DEVICE<br>DEL-DEVICE<br>ACC-ALL |
|---|---|---|---|---|---|
| **Nome variabile **<br>**(Namespace)** | **MyProp1 **<br>**(utente)** | **ID visitatore **<br>**(AAID)** | **MyEvar1** | **MyEvar2** | **MyEvar3 **<br>**(xyz)** |
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

| Valori API | Valori API | Tipo di file restituito | Dati in un file di accesso di riepilogo<br> | Dati in un file di accesso di riepilogo<br> | Dati in un file di accesso di riepilogo<br> | Dati in un file di accesso di riepilogo<br> | Dati in un file di accesso di riepilogo<br> |
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
| Mary | 42 | A | Privacy-7398 | Privacy-9152 |
| Mary | 88 | B | N | Y |
| Mary | 99 | C | O | Z |
| John | 42 | D | Privacy-1866 | Privacy-8216 |
| John | 88 | E | N | U |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

>[!NOTE] Sono interessate solo le celle nelle righe contenenti AAID = 77 e un’etichetta DEL-DEVICE.

| user=Mary<br>expandIDs=false | user=Mary<br>expandIDs=false | user=Mary<br>expandIDs=false | user=Mary<br>expandIDs=false | user=Mary<br>expandIDs=false |
|--- |---|---|---|---|
| **MyProp1** | **AAID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| Privacy-0523 | 77 | Privacy-1866 | Privacy-3681 | X |
| Privacy-0523 | 88 | Privacy-2178 | Privacy-1975 | Y |
| Privacy-0523 | 99 | Privacy-9045 | Privacy-2864 | Z |
| John | 77 | D | P | W |
| John | 88 | E | N | U |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

>[!NOTE] sono interessate solo le celle nelle righe contenenti user=Mary e un’etichetta DEL-PERSON. In pratica, la variabile contenente A_ID probabilmente è una proprietà o un’eVar e il valore di sostituzione è una stringa che inizia con “Privacy-” seguito da un numero a caso (GUID), invece di un diverso valore numerico casuale.

| user=Mary<br>expandIDs=true | user=Mary<br>expandIDs=true | user=Mary<br>expandIDs=true | user=Mary<br>expandIDs=true | user=Mary<br>expandIDs=true |
|--- |---|---|---|---|
| **MyProp1** | **AAID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| Privacy-5782 | 09 | Privacy-0859 | Privacy-8183 | Privacy-9152 |
| Privacy-5782 | 16 | Privacy-6104 | Privacy-2911 | Privacy-6821 |
| Privacy-5782 | 83 | Privacy-2714 | Privacy-0219 | Privacy-4395 |
| John | 09 | D | Privacy-8454 | Privacy-8216 |
| John | 16 | E | Privacy-2911 | Privacy-2930 |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

Tieni presente quanto segue:

* Sono interessate le celle nelle righe contenenti `user=Mary` e un’etichetta `DEL-DEVICE` o `DEL-PERSON`, nonché le celle con un’etichetta `DEL-DEVICE` nelle righe contenenti qualsiasi ID visitatore che si è verificato in una riga contenente `user=Mary`.
* `MyEvar2` nella quarta e nella quinta riga viene aggiornato perché queste righe contengono gli stessi valori ID visitatore di quelli nella prima e nella seconda riga, pertanto l’espansione dell’ID li include per le cancellazioni a livello di dispositivo.
* I valori di `MyEvar2` nella seconda e nella quinta riga corrispondono prima e dopo la cancellazione, ma dopo la cancellazione non corrisponde più il valore N che si trova nell’ultima riga, perché quella riga non è stata aggiornata come parte della richiesta di cancellazione.
* `MyEvar3` si comporta in modo molto diverso rispetto alla versione senza l’espansione dell’ID, in quanto senza l’espansione dell’ID, nessun corrisponde `ID-DEVICES`. Ora `AAID` corrisponde alle prime cinque righe.
