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
source-git-commit: 93d6c7698216b3064f5417dbcfb33184efc2c132

---


# Creare una regola bot personalizzata

Le regole bot personalizzate consentono di filtrare le condizioni basate sul traffico definite dall'utente.

Le regole bot personalizzate vengono definite utilizzando i seguenti tipi di condizione:

* Agente utente
* Indirizzo IP
* Intervallo IP

Per una singola regola è possibile definire più condizioni. Più condizioni sono associate a "OR". Ad esempio, se fornisci un valore per Agente utente e Indirizzo IP, il traffico viene considerato traffico bot se una condizione è soddisfatta.

## Agente utente

A User Agent condition checks the user agent value to see if it **[!UICONTROL starts with]** or **[!UICONTROL contains]** the specified string. If **[!UICONTROL contains]** is selected, the substring is matched if it occurs anywhere in the user agent.

Optional values can be included in the **[!UICONTROL does not contain]** list to define values that the user agent must not contain for a successful match. È possibile specificare più valori includendo un valore per linea. Se l'agente utente soddisfa i criteri specificati nella stringa di corrispondenza, ma contiene anche una stringa sull'elenco non viene considerato come corrispondenza.

**[!UICONTROL contains]** Il campo è limitato a 100 caratteri. L'elenco non contiene un massimo di 255 caratteri meno un carattere separatore per ogni nuova riga. (Corrisponde al numero di stringhe - 1. If you specify 4 *does not contain* strings, 3 separator characters are required.) Tutte le corrispondenze stringa non sono sensibili alle maiuscole/minuscole.

## Indirizzo IP (comprese le corrispondenze con caratteri jolly)

Corrisponde a un indirizzo IP o a più indirizzi nello stesso blocco utilizzando caratteri jolly (*). Inserite i valori numerici dell'indirizzo IP che desiderate corrispondere. Sostituite * per tutti i valori che desiderate corrispondere utilizzando un carattere jolly. Nell'elenco seguente sono riportati alcuni esempi di stringa di corrispondenza indirizzo IP:

```
10.10.10.1
10.10.10.*
```

## Intervallo indirizzi IP

Fornite gli intervalli di inizio e fine degli indirizzi IP per la corrispondenza. Sostituite * per tutti i valori che desiderate corrispondere utilizzando un carattere jolly.

## Definire una regola bot personalizzata

1. Go to **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]**, select one or more report suites and click **[!UICONTROL General]** &gt; **[!UICONTROL Bot Rules]**.
1. Click **[!UICONTROL Add Rule]** and define one or more match conditions.
1. Fai clic su **[!UICONTROL Save]**. La modifica dovrebbe diventare effettiva entro 30 minuti.

>[!Note]
>L'interfaccia utente consente di definire manualmente 500 regole. Una volta raggiunto tale limite, le regole devono essere gestite in gruppo tramite le opzioni Importa file ed Esporta regole bot.
