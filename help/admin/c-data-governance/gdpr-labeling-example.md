---
description: nulle
seo-description: nulle
seo-title: Esempi di etichettatura
title: Esempi di etichettatura
uuid: a 9 a 5 b 937-dbde -4 f 0 f-a 171-005 ef 4 c 79 df 9
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Esempi di etichettatura

## Dati di esempio dei risultati {#section_94DE6BC0026F46D7AD7061C5625C8D52}

Supponi di avere i dati seguenti:

* La prima riga contiene le etichette per ogni variabile.
* La seconda riga è il nome della variabile. Se ha un’etichetta ID, contiene lo spazio dei nomi assegnato tra parentesi.
* I dati dei risultati partono dalla terza riga.

<!-- Meike, I converted html tables for fix elusive validation error. Bob -->

| Etichette | I2<br>ID-PERSONCAN@-@ PERSONACC<br><br>-PERSON | I2<br>ID-DEVICE<br>DEL-DEVICE<br>ACC-ALL | I2<br>DEL-PERSON<br>ACC-PERSON | I2<br>DEL-DEVICE<br>DEL-PERSON<br>ACC-ALL | I2<br>ID-DEVICE<br>DEL-DEVICE<br>ACC-ALL |
|:---:|:---:|:---:|:---:|:---:|:---:|
| Variable Name<br>(Namespace) | MyProp1<br>(user) | Visitor ID<br>(AAID) | MyEvar1 | MyEvar2 | MyEvar3<br>(xyz) |
| Dati dei risultati | Mary | 77 | A | M | X |
| Mary | 88 | B | N | Y |
| Mary | 99 | C | O | Z |
| John | 77 | D | P | W |
| John | 88 | E | N | U |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | Z |


## Richiesta di accesso di esempio {#section_BDA817FD2415420DAAC835825484BA9D}

Se si invia una richiesta di accesso, il file di riepilogo conterrà i valori indicati nella tabella seguente. Una richiesta può restituire solo un file di dispositivo, solo un file di persona o entrambi. Due file di riepilogo vengono restituiti solo se viene usato un ID persona ed expandIDs è true.

| Valori API | Tipo di file restituito | Dati in un file di accesso di riepilogo |
|--- |--- |--- |
| Namespace/ID | expandIDs |  | MyProp1 | Visitor ID | MyEvar1 | MyEvar2 | MyEvar3 |
| AAID=77 | false | dispositivo | Variabile assente | 77 | Variabile assente | M, P | X, W |
| AAID=77 | true | dispositivo | 77 | M, P | X, W |
| user=Mary | false | persona | Mary | 77, 88, 99 | A, B, C | M, N, O | X, Y, Z |
| user=Mary | true | persona | Mary | 77, 88, 99 | A, B, C | M, N, O | X, Y, Z |
| dispositivo | assente | 77, 88 | assente | N, P | U, W |
| user=Mary AAID=66 | true | persona | Mary | 77, 88, 99 | A, B, C | M, N, O | X, Y, Z |
| dispositivo | assente | 66, 77, 88 | assente | N, P | U, W, Z |
| xyz=X | false | dispositivo | assente | 55, 77 | assente | M, R | X |
| xyz=X | true | dispositivo | assente | 55, 77 | assente | M, P, R | W, X |

Si noti che le impostazioni di expandIDs non cambiano nell’output quando viene usato un ID cookie.

## Richiesta di cancellazione di esempio {#section_6C75F70F5D574BE7AA540981E8B7EA26}

Se la richiesta di cancellazione usa i valori dell’API nella prima riga della tabella, la tabella dei risultati verrà aggiornata e apparirà come la seguente:

| AAID=77 il valore di expandIDs non conta |
|--- |
| MyProp1 | AAID | MyEvar1 | MyEvar2 | MyEvar3 |
| Mary | 42 | A | GDPR-7398 | GDPR-9152 |
| Mary | 88 | B | N | Y |
| Mary | 99 | C | O | Z |
| John | 42 | D | GDPR-1866 | GDPR-8216 |
| John | 88 | E | N | U |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

>[!NOTE]
>
>Vengono influenzate solo le celle sulle righe contenenti AAID = 77 e un'etichetta Dell-DEVICE.

| user = Mary expanddids = false |
|--- |
| MyProp1 | AAID | MyEvar1 | MyEvar2 | MyEvar3 |
| GDPR-0523 | 77 | GDPR-1866 | GDPR-3681 | X |
| GDPR-0523 | 88 | GDPR-2178 | GDPR-1975 | Y |
| GDPR-0523 | 99 | GDPR-9045 | GDPR-2864 | Z |
| John | 77 | D | P | W |
| John | 88 | E | N | U |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

>[!NOTE]
>
>Vengono influenzate solo le celle sulle righe contenenti user = Mary e un'etichetta Dell-PERSON. In pratica, la variabile contenente A_ID probabilmente è una proprietà o un’eVar e il valore di sostituzione è una stringa che inizia con “GDPR-” seguito da un numero a caso (GUID), invece di un diverso valore numerico casuale.

| user=Mary expandIDs=true |
|--- |
| MyProp1 | AAID | MyEvar1 | MyEvar2 | MyEvar3 |
| GDPR-5782 | 09 | GDPR-0859 | GDPR-8183 | GDPR-9152 |
| GDPR-5782 | 16 | GDPR-6104 | GDPR-2911 | GDPR-6821 |
| GDPR-5782 | 83 | GDPR-2714 | GDPR-0219 | GDPR-4395 |
| John | 09 | D | GDPR-8454 | GDPR-8216 |
| John | 16 | E | GDPR-2911 | GDPR-2930 |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

Tenete presente quanto segue:

* Sono interessate le celle nelle righe contenenti user=Mary e un’etichetta DEL-DEVICE o DEL-PERSON, nonché le celle con un’etichetta DEL-DEVICE nelle righe contenenti qualsiasi ID visitatore che si è verificato in una riga contenente user=Mary.
* MyEvar2 nella quarta e nella quinta riga viene aggiornato perché queste righe contengono gli stessi valori ID visitatore di quelli nella prima e nella seconda riga, pertanto l’espansione dell’ID li include per le cancellazioni a livello di dispositivo.
* I valori di MyEvar2 nella seconda e nella quinta riga corrispondono prima e dopo la cancellazione, ma dopo la cancellazione non corrisponde più il valore N che si trova nell’ultima riga, perché quella riga non è stata aggiornata come parte della richiesta di cancellazione.
* MyEvar3 si comporta in modo molto diverso rispetto alla versione senza l’espansione dell’ID, in quanto senza l’espansione dell’ID, nessun ID-DEVICES corrisponde. Ora AAID corrisponde alle prime cinque righe.
