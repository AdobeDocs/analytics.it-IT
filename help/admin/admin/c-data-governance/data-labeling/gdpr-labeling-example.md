---
description: Mostra esempi su come etichettare i dati per i dati relativi agli hit, le richieste di accesso, le richieste di eliminazione
title: Esempi di etichettatura
feature: Data Governance
role: Admin
exl-id: 9bea8636-c79c-4998-8952-7c66d31226e3
source-git-commit: 48f1974a0c379a4e619d9a04ae80e43cce9527c1
workflow-type: tm+mt
source-wordcount: '932'
ht-degree: 74%

---

# Esempi di etichettatura

## Dati hit di esempio {#hit}

Supponi di avere i dati seguenti:

* La prima riga contiene le etichette per ogni variabile.
* La seconda riga è il nome della variabile. Se ha un’etichetta ID, contiene lo spazio dei nomi assegnato tra parentesi.
* I dati dei risultati partono dalla terza riga.

| Etichette | I2 <br> ID-PERSON <br> DEL-PERSON <br> ACC-PERSON | I2 <br> ID-DEVICE <br> DEL-DEVICE <br> ACC-ALL | I2 <br> DEL-PERSON <br> ACC-PERSON | I2 <br> DEL-DEVICE <br> DEL-PERSON <br> ACC-ALL | I2 <br> ID-DEVICE <br> DEL-DEVICE <br> ACC-ALL |
|---|---|---|---|---|---|
| **Nome variable** <br> **(Namespace)** | **MyProp1** <br> **(utente)** | **ID visitatore** <br> **(AAID)** | **MyEvar1** | **MyEvar2** | **MyEvar3** <br> **(xyz)** |
| Dati dei risultati | Mary | 77 | A | M | X |
| | Mary | 88 | B | N | Y |
| | Mary | 99 | C | O | Z |
| | John | 77 | D | P | W |
| | John | 88 | E | N | U |
| | John | 44 | F | Q | V |
| | John | 55 | G | R | X |
| | Alice | 66 | A | N | Z |

## Richiesta di accesso di esempio {#access}

Inviando una richiesta di accesso, si riceveranno due file che è possibile restituire all&#39;interessato. Un file è un file CSV contenente una riga per ogni hit ricevuto per l’interessato e una colonna per ogni variabile con l’etichetta di accesso appropriata. L’altro file è un file HTML di riepilogo che elenca ciascuna variabile, seguito da tutti i valori univoci visualizzati per tale variabile per l’interessato e dal numero di volte in cui è stato visualizzato ogni valore univoco.

Ad esempio, il file di riepilogo contiene i valori indicati nella tabella seguente. Una richiesta può restituire solo un file di dispositivo, solo un file di persona o entrambi. Due file di riepilogo vengono restituiti solo se viene utilizzato un ID persona e `expandIds` è true.

<table>
  <tr>
    <th colspan="2" style="text-align:center">Valori API</th>
    <th rowspan="2">Riepilogo<br/>tipo di file<br/>restituito</th>
    <th colspan="5" style="text-align:center">Dati in un file di accesso di riepilogo</th>
  </tr>
  <tr>
    <th>Namespace/ID</th>
    <th>expandIDs</th>
    <th>MyProp1</th>
    <th>Visitor ID</th>
    <th>MyEvar1</th>
    <th>MyEvar2</th>
    <th>MyEvar3</th>
  </tr>
  <tr>
    <td>AAID=77</td>
    <td>false</td>
    <td>dispositivo</td>
    <td>assente</td>
    <td>77</td>
    <td>assente</td>
    <td>M, P</td>
    <td>X, W</td>
  </tr>
  <tr>
    <td>AAID=77</td>
    <td>true</td>
    <td>dispositivo</td>
    <td>assente</td>
    <td>77</td>
    <td>assente</td>
    <td>M, P</td>
    <td>X, W</td>
  </tr>
  <tr>
    <td>user=Mary</td>
    <td>false</td>
    <td>persona</td>
    <td>Mary</td>
    <td>77, 88, 99</td>
    <td>A, B, C</td>
    <td>M, N, O</td>
    <td>X, Y, Z</td>
  </tr>
  <tr>
    <td rowspan="2">user=Mary</td>
    <td rowspan="2">true</td>
    <td>persona</td>
    <td>Mary</td>
    <td>77, 88, 99</td>
    <td>A, B, C</td>
    <td>M, N, O</td>
    <td>X, Y, Z</td>
  </tr>
  <tr>
    <td>dispositivo</td>
    <td>assente</td>
    <td>77, 88</td>
    <td>A, B, C</td>
    <td>N, P</td>
    <td>U, W</td>
  </tr>
  <tr>
    <td rowspan="2">user=Mary<br>AAID=66</td>
    <td rowspan="2">true</td>
    <td>persona</td>
    <td>Mary</td>
    <td>77, 88, 99</td>
    <td>A, B, C</td>
    <td>M, N, O</td>
    <td>X, Y, Z</td>
  </tr>
  <tr>
    <td>dispositivo</td>
    <td>assente</td>
    <td>66, 77, 88</td>
    <td>A, B, C</td>
    <td>N, P</td>
    <td>U, W, Z</td>
  </tr>
  <tr>
    <td>xyz=X</td>
    <td>false</td>
    <td>dispositivo</td>
    <td>assente</td>
    <td>55, 77</td>
    <td>assente</td>
    <td>M, R</td>
    <td>X</td>
  </tr>
  <tr>
    <td>xyz=X</td>
    <td>true</td>
    <td>dispositivo</td>
    <td>assente</td>
    <td>55, 77</td>
    <td>assente</td>
    <td>M, P, R</td>
    <td>W, X</td>
  </tr>
</table>

Si noti che l&#39;impostazione per `expandIDs` non fa alcuna differenza nell&#39;output quando viene utilizzato un ID cookie.

## Esempio di richieste di eliminazione {#delete}

Se la richiesta di cancellazione usa i valori dell’API nella prima riga della tabella, la tabella dei risultati verrà aggiornata e apparirà come la seguente:

<table>
  <tr>
    <th colspan="5" style="text-align:center">AAID=77 <br>(il valore expandIDs non conta)</th>
  </tr>
  <tr>
    <th>MyProp1</th>
    <th>AAID</th>
    <th>MyEvar1</th>
    <th>MyEvar2</th>
    <th>MyEvar3</th>
  </tr>
  <tr>
    <td>Mary</td>
    <td>42</td>
    <td>A</td>
    <td>Privacy-7398</td>
    <td>Privacy-9152</td>
  </tr>
  <tr>
    <td>Mary</td>
    <td>88</td>
    <td>B</td>
    <td>N</td>
    <td>Y</td>
  </tr>
  <tr>
    <td>Mary</td>
    <td>99</td>
    <td>C</td>
    <td>O</td>
    <td>Z</td>
  </tr>
  <tr>
    <td>John</td>
    <td>42</td>
    <td>D</td>
    <td>Privacy-1866</td>
    <td>Privacy-8216</td>
  </tr>
  <tr>
    <td>John</td>
    <td>88</td>
    <td>E</td>
    <td>N</td>
    <td>U</td>
  </tr>
  <tr>
    <td>John</td>
    <td>44</td>
    <td>F</td>
    <td>Q</td>
    <td>V</td>
  </tr>
  <tr>
    <td>John</td>
    <td>55</td>
    <td>G</td>
    <td>R</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Alice</td>
    <td>66</td>
    <td>A</td>
    <td>N</td>
    <td>Z</td>
  </tr>
</table>

>[!NOTE]
>
>Sono interessate solo le colonne nelle righe contenenti `AAID=77` e un&#39;etichetta `DEL-DEVICE`.

<table>
  <tr>
    <th colspan="5" style="text-align:center">user=Mary <br> expandIDs=false</th>
  </tr>
  <tr>
    <th>MyProp1</th>
    <th>AAID</th>
    <th>MyEvar1</th>
    <th>MyEvar2</th>
    <th>MyEvar3</th>
  </tr>
  <tr>
    <td>Privacy-0523</td>
    <td>77</td>
    <td>Privacy-1866</td>
    <td>Privacy-3681</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Privacy-0523</td>
    <td>88</td>
    <td>Privacy-2178</td>
    <td>Privacy-1975</td>
    <td>Y</td>
  </tr>
  <tr>
    <td>Privacy-0523</td>
    <td>99</td>
    <td>Privacy-9045</td>
    <td>Privacy-2864</td>
    <td>Z</td>
  </tr>
  <tr>
    <td>John</td>
    <td>77</td>
    <td>D</td>
    <td>P</td>
    <td>W</td>
  </tr>
  <tr>
    <td>John</td>
    <td>88</td>
    <td>E</td>
    <td>N</td>
    <td>U</td>
  </tr>
  <tr>
    <td>John</td>
    <td>44</td>
    <td>F</td>
    <td>Q</td>
    <td>V</td>
  </tr>
  <tr>
    <td>John</td>
    <td>55</td>
    <td>G</td>
    <td>R</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Alice</td>
    <td>66</td>
    <td>A</td>
    <td>N</td>
    <td>Z</td>
  </tr>
</table>

>[!NOTE]
>
>Sono interessati solo i celcolumnsl nelle righe contenenti `user=Mary` e un&#39;etichetta `DEL-PERSON`. Inoltre, in pratica, la variabile contenente `A_ID` probabilmente è una prop o un eVar. Il valore sostitutivo sarà una stringa che inizia con `Privacy-`, seguita da un numero casuale (GUID), anziché sostituire il valore numerico con un diverso valore numerico casuale.

<table>
  <tr>
    <th colspan="5" style="text-align:center">user=Mary <br> expandIDs=true</th>
  </tr>
  <tr>
    <th>MyProp1</th>
    <th>AAID</th>
    <th>MyEvar1</th>
    <th>MyEvar2</th>
    <th>MyEvar3</th>
  </tr>
  <tr>
    <td>Privacy-5782</td>
    <td>09</td>
    <td>Privacy-0859</td>
    <td>Privacy-8183</td>
    <td>Privacy-9152</td>
  </tr>
  <tr>
    <td>Privacy-5782</td>
    <td>16</td>
    <td>Privacy-6104</td>
    <td>Privacy-2911</td>
    <td>Privacy-6821</td>
  </tr>
  <tr>
    <td>Privacy-5782</td>
    <td>83</td>
    <td>Privacy-2714</td>
    <td>Privacy-0219</td>
    <td>Privacy-4395</td>
  </tr>
  <tr>
    <td>John</td>
    <td>09</td>
    <td>D</td>
    <td>Privacy-8454</td>
    <td>Privacy-8216</td>
  </tr>
  <tr>
    <td>John</td>
    <td>16</td>
    <td>E</td>
    <td>Privacy-2911</td>
    <td>Privacy-2930</td>
  </tr>
  <tr>
    <td>John</td>
    <td>44</td>
    <td>F</td>
    <td>Q</td>
    <td>V</td>
  </tr>
  <tr>
    <td>John</td>
    <td>55</td>
    <td>G</td>
    <td>R</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Alice</td>
    <td>66</td>
    <td>A</td>
    <td>N</td>
    <td>Z</td>
  </tr>
</table>

Tieni presente quanto segue:

* Sono interessate solo le celle nelle righe contenenti `user=Mary` e un’etichetta `DEL-PERSON`.
* A causa dell’espansione dell’ID, sono interessate le celle nelle righe contenenti `AAID=77`, `AAID=88` o `AAID=99` (valori AAID nelle righe contenenti `user=Mary`) e un’etichetta `DEL-DEVICE`. Questo include le celle con un’etichetta `DEL-DEVICE` nelle righe in cui `user=Mary`. Questo causa l’oscuramento delle celle nelle righe 4 e 5 (nonché nelle righe 1-3) con le etichette `DEL-DEVICE` (AAID, MyEvar2 e MyEvar3).
* L’impostazione expandIDs non si estende alla chiamata per includere i valori presenti in MyEvar3 (`X`, `Y` e `Z`), che ha un’etichetta ID-DEVICE, quando `user=Mary`. ExpandIDs si estende solo per includere l’ID visitatore (AAID in questo esempio, ma anche ECID) nelle righe in cui `user=Mary`. Così le ultime due righe, che contengono i valori MyEvar3 `X` e `Z`, non sono interessate.
* `MyEvar2` nella quarta e nella quinta riga vengono aggiornate perché queste righe contengono gli stessi valori ID visitatore (`77` e `88`) di quelli nella prima e nella seconda riga. Di conseguenza, l’espansione dell’ID li include per le cancellazioni a livello di dispositivo.
* I valori di `MyEvar2` nella seconda e nella quinta riga corrispondono prima e dopo l’eliminazione. Tuttavia, dopo l’eliminazione non corrispondono più al valore `N` che si trova nell’ultima riga, perché tale riga non è stata aggiornata come parte della richiesta di eliminazione.
* `MyEvar3` si comporta in modo molto diverso rispetto alla versione senza l’espansione dell’ID, in quanto senza l’espansione dell’ID, nessun corrisponde `ID-DEVICES`. Ora `AAID` corrisponde alle prime cinque righe.
