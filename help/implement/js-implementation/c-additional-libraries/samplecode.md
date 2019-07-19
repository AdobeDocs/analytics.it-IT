---
description: Esempi per illustrare l'utilizzo di un tag immagine generato dal server in una pagina di esempio HTML.
keywords: Implementazione di Analytics; variabili
seo-description: Esempi per illustrare l'utilizzo di un tag immagine generato dal server in una pagina di esempio HTML.
seo-title: Codice di esempio
solution: Analytics
title: Codice di esempio
topic: Sviluppatore e implementazione
uuid: 47 e 5 e 82 c-cfb 2-4912-919 b -720 b 2 ee 852 ba
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Codice di esempio

Esempi per illustrare l'utilizzo di un tag immagine generato dal server in una pagina di esempio HTML.

Nella tabella seguente sono visualizzati i valori utilizzati nell'esempio.

| Variabile | Valore |
|---|---|
| pageName | Conferma ordine |
| URL corrente | https://www.somesite.com/cart/confirmation.asp |
| events | purchase, event 1 |
| c1 | Registrati |
| purchaseID | 0123456 |
| products | Libri; Nome libro; 1; 19.95 |
| state | CA |
| zip | 90210 |
| una # | 123456 |

## Example 1 {#section_91D91CE318AE43F0ADDF6005607E83C7}

Nell'esempio seguente viene visualizzato un tag immagine lato server. Il numero casuale evidenziato impedisce la memorizzazione nella cache dell'immagine.

```
<html> 
<head> 
</head> 
<body> 
Order Confirmation<br> 
Thanks for your order #0123456. 
<img src="https://102.112.207.net/b/ss/suite1,suite2/1/G.4--NS 
<codeph outputclass="syntax">
  /123456?pageName=Order%20 Confirmation&events=purchase%2Cevent1&c1=Registered&purchaseID=0123456&products=Books%3BBook%20Name%3B1%3B19.95&state=CA&zip=90210&g=https%3A//www.somesite.com/cart/confirmation.asp" width="1" height="1" border="0" /> 
 </body> 
 </html> 
  
</codeph outputclass="syntax">
```

## Example 2 {#section_726D12029583428BA853043F988ED1B8}

L'esempio seguente mostra un tag immagine javascript minimo.

```
<html> 
<head> 
</head> 
<body> 
Order Confirmation<br> 
Thanks for your order #0123456. 
<script language="javascript"><!— 
s.s_date = new Date(); 
s.s_rdm = s.s_date.getTime(); 
s.s_desturl="<img width=\"1\" height=\"1\" 
src=\"https://102.112.207.net/b/ss/suite1,suite2/1/G.4--NS/" + s.s_rdm + 
"?pageName=Order%20Confirmation&events=purchase%2Cevent1&c1=Registered 
&purchaseID=0123456&products=Books%3BBook%20Name%3B1%3B19.95&state=CA&zip=90210&g=http 
s%3A//www.somesite.com/cart/confirmation.asp\">"; 
document.write(s.s_desturl); 
//--></script> 
</body> 
</html> 
```

