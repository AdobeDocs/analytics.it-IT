---
description: Le regole bot personalizzate consentono di filtrare le condizioni basate sul traffico definite dall'utente.
seo-description: Le regole bot personalizzate consentono di filtrare le condizioni basate sul traffico definite dall'utente.
seo-title: Creare una regola bot personalizzata
solution: Analytics
subtopic: Regole bot
title: Creare una regola bot personalizzata
topic: Strumenti di amministrazione
uuid: abbc 5 c 7 e -912 f -4660-a 02 b -0431 a 740 ec 70
translation-type: tm+mt
source-git-commit: 4a627e268994d0152a19fb44e9bc06ea7ebc64c6

---


# Creare una regola bot personalizzata

Le regole bot personalizzate consentono di filtrare le condizioni basate sul traffico definite dall'utente.

Le regole bot personalizzate vengono definite utilizzando i seguenti tipi di condizione:

* Agente utente
* Indirizzo IP
* Intervallo IP

Per una singola regola è possibile definire più condizioni. Più condizioni sono associate a "OR". Ad esempio, se fornisci un valore per Agente utente e Indirizzo IP, il traffico viene considerato traffico bot se una condizione è soddisfatta.

## Agente utente

Una condizione Agente utente verifica il valore dell'agente utente per verificare se essa **[!UICONTROL starts with]** o **[!UICONTROL contains]** la stringa specificata. Se **[!UICONTROL contains]** è selezionata, la sottostringa viene rilevata se si verifica ovunque nell'agente utente.

I valori facoltativi possono essere inclusi **[!UICONTROL does not contain]** nell'elenco per definire valori che l'agente utente non deve contenere per una corrispondenza vincente. È possibile specificare più valori includendo un valore per linea. Se l'agente utente soddisfa i criteri specificati nella stringa di corrispondenza, ma contiene anche una stringa sull'elenco non viene considerato come corrispondenza.

**[!UICONTROL contains]** Il campo è limitato a 100 caratteri. L'elenco non contiene un massimo di 255 caratteri meno un carattere separatore per ogni nuova riga. (Corrisponde al numero di stringhe - 1. Se si specifica 4 *non contiene* stringhe, sono necessari 3 caratteri di separazione. Tutte le corrispondenze stringa non sono sensibili alle maiuscole/minuscole.

## Indirizzo IP (comprese le corrispondenze con caratteri jolly)

Corrisponde a un indirizzo IP o a più indirizzi nello stesso blocco utilizzando caratteri jolly (*). Inserite i valori numerici dell'indirizzo IP che desiderate corrispondere. Sostituite * per tutti i valori che desiderate corrispondere utilizzando un carattere jolly. Nell'elenco seguente sono riportati alcuni esempi di stringa di corrispondenza indirizzo IP:

```
10.10.10.1
10.10.10.*
```

## Intervallo indirizzi IP

Fornite gli intervalli di inizio e fine degli indirizzi IP per la corrispondenza. Sostituite * per tutti i valori che desiderate corrispondere utilizzando un carattere jolly.

## Definire una regola bot personalizzata

1. Vai a **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]**, seleziona una o più suite di rapporti e fai clic **[!UICONTROL General]** su &gt; **[!UICONTROL Bot Rules]**.
1. Fare clic **[!UICONTROL Add Rule]** e definire una o più condizioni di corrispondenza.
1. Fai clic su **[!UICONTROL Save]**. La modifica dovrebbe diventare effettiva entro 30 minuti.

>[!Note]
>L'interfaccia utente consente di definire manualmente 500 regole. Una volta raggiunto tale limite, le regole devono essere gestite in gruppo tramite le opzioni Importa file ed Esporta regole bot.
