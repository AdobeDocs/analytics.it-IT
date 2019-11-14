---
description: Le variabili di pagina popolano direttamente un report, ad esempio pageName, List Props, List Variables e così via.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variabili di pagina
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 45642bdbe18627caa20b1def6443f1e596a41f52

---


# visitorNamespace

La variabile viene utilizzata per identificare il dominio con cui sono impostati i cookie.

<!-- 

visitorNamespace.xml

 -->

Se *`visitorNamespace`* viene utilizzato nel file JavaScript, non eliminarlo o modificarlo. Se *`visitorNamespace`* vengono apportate modifiche, tutti i visitatori segnalati in Analytics possono diventare nuovi visitatori. La cronologia del visitatore viene disconnessa dal traffico corrente e futuro. Non modificate questa variabile senza l'approvazione di un rappresentante Adobe.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | ns | N/D | "" |

Analytics utilizza un cookie per identificare in modo univoco i visitatori del sito. Se non *`visitorNamespace`* viene utilizzato, il cookie è associato a 2o7.net. Se *`visitorNamespace`* viene utilizzato, il cookie è associato a un sottodominio di 2o7.net. Tutti i visitatori del sito devono avere i loro cookie associati allo stesso dominio o sottodominio.

Il motivo per utilizzare la *`visitorNamespace`* variabile è di evitare il sovraccarico del limite di cookie di un browser. Internet Explorer impone un limite di 20 cookie per dominio. Utilizzando la *`visitorNamespace`* variabile, i cookie di Analytics di altre società non entrano in conflitto con i cookie dei visitatori.

**Sintassi e valori** possibili {#section_EE247FE371784CA4B6058182181F3EA1}

Il valore di *`visitorNamespace`* deve essere fornito da Adobe ed è una stringa di caratteri ASCII che non contengono virgole, punti, spazi o caratteri speciali.

```js
s.visitorNamespace="company_specific_value"
```

**Identificazione dei visitatori tra le suite** di rapporti {#section_7AC5A97FC8C045DD8850245A62BB09F4}

Se non specificate un `visitorNamespace`, ogni suite di rapporti della società riceve il cookie dell’ID visitatore personalizzato scritto come `s_vi_[random string]`. Se specifichi `visitorNamespace`, lo stesso `s_vi` cookie verrà utilizzato per tutte le suite di rapporti che inviano i dati a quelle specificate `trackingServer`. Se avete implementato i tag per più suite, accertatevi di specificare lo spazio nomi visitatore in modo che lo stesso cookie venga utilizzato da ogni suite di rapporti.

**Esempi** {#section_89A95852AB9446E794AD3283B8800B09}

```js
s.visitorNamespace="company_name"
```

```js
s.visitorNamespace="Adobe"
```

**Impostazioni** di configurazione {#section_1128A2531ECC43DFA6749ECC21F050A2}

Nessuno
