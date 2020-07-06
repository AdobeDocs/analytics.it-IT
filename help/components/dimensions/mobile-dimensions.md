---
title: Dimensioni mobili
description: Dimensioni basate sulla stringa agente utente del dispositivo.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '892'
ht-degree: 0%

---


# Dimensioni mobili

*Questa pagina fa riferimento alle proprietà dei dispositivi mobili che accedono al sito Web. Se desiderate tenere traccia dei dispositivi su un’app mobile, consultate[Implementazione  Analytics per dispositivi](/help/implement/mobile-device-sdk.md)mobili nella guida per l’utente Implementazione.*

Le dimensioni per dispositivi mobili forniscono informazioni approfondite sulle proprietà dei dispositivi mobili che visitano il sito. Potete usare queste dimensioni per comprendere meglio quali funzioni supporta un dispositivo mobile.

## Compilare queste dimensioni con i dati

Queste dimensioni fanno riferimento a regole di ricerca interne ad Adobe. Il valore di ricerca si basa sull’intestazione `User-Agent` HTTP inviata con l’hit. Adobe collabora con [DeviceAtlas](https://deviceatlas.com/) per mantenere le ricerche tra agente utente e dimensioni mobili. Se utilizzi una libreria AppMeasurement (ad esempio tramite  lancio di un Adobe Experience Platform), tutte le dimensioni del dispositivo mobile non sono disponibili.

## Descrizioni delle dimensioni mobili

>[!NOTE]
>
>I valori delle dimensioni etichettati `"None"` sono dispositivi non mobili. Se desiderate un rapporto che includa solo dispositivi mobili, trascinate la dimensione &quot;Dispositivo mobile&quot; nell’area di segmento del quadro di Workspace.

* **Supporto** audio per dispositivi mobili: Determina i formati di file che il dispositivo può riprodurre. I valori di esempio includono `"MP3"`, `"AAC"`e `"MIDI Monophonic"`. I valori in questa dimensione non si escludono a vicenda; un singolo hit può attribuire più valori di dimensione.
* **Mobile**: Se l&#39;agente utente contiene un dispositivo specifico per il vettore, quest&#39;ultimo è un valore di dimensione. I valori di esempio includono `"Reliance Jio"`, `"Airtel"`, `"Vodafone"`e `"Verizon"`.
* **Profondità** colore mobile: Profondità colore del dispositivo mobile, in bit.
* **Supporto** dei cookie per dispositivi mobili: Determina se il dispositivo mobile supporta i cookie. Questo rapporto non viene indicato se il browser accetta i cookie. I valori delle dimensioni includono `"Supported"`, `"Not supported"`e `"Unknown"`.
* **Dispositivo** mobile: Il dispositivo mobile utilizzato dal visitatore.
* **Numero** dispositivo mobile: Determina se il dispositivo mobile trasmette il proprio numero. I valori delle dimensioni includono `"Supported"`, `"Not supported"`e `"Unknown"`.
* **Tipo** di dispositivo mobile: Tipo di dispositivo mobile. I valori di esempio includono `"Mobile phone"`, `"Tablet"`, `"Media player"`e `"Gaming console"`.
* **DRM** mobile: Il tipo di DRM supportato dal dispositivo mobile. I valori di esempio includono `"DRM OMA forward"`, `"DRM OMA combined delivery"`e `"DRM OMA separate delivery"`.
* **Supporto** per immagini per dispositivi mobili: I tipi di immagini supportati da un dispositivo mobile. I valori di esempio includono `"PNG"`, `"JPEG"`e `"GIF 87"`. I valori in questa dimensione non si escludono a vicenda; un singolo hit può attribuire più valori di dimensione.
* **Mobile Information Services**: Tipi di servizi di notizie supportati dal dispositivo. I dispositivi recenti in genere non segnalano queste informazioni.
* **VM** Java mobile: Le versioni di Java supportate dal dispositivo.
* **Decorazione** della posta mobile: Determina se il dispositivo supporta la funzionalità Decomail, una volta nota sui dispositivi giapponesi.
* **Produttore** mobile: Raggruppa i dispositivi mobili in base al produttore. I valori di esempio includono `"Apple"`, `"Samsung"`, `"Huawei"`e `"Motorola"`.
* **Lunghezza** massima segnalibro mobile: Il numero massimo di byte supportati dal dispositivo mobile negli URL con segnalibro. I dispositivi recenti in genere non hanno un limite.
* **Lunghezza** massima URL browser mobile: Il numero massimo di byte supportati dal dispositivo mobile negli URL. I dispositivi recenti in genere non hanno un limite.
* **Lunghezza** e-mail massima per dispositivi mobili: Il numero massimo di byte supportati dal dispositivo mobile in un&#39;e-mail. I dispositivi recenti in genere non hanno un limite.
* **Protocolli** di rete mobile: Tipi di protocollo supportati dal dispositivo quando si accede a Internet. I valori di esempio includono `"EDGE"`, `"GPRS"`, `"UMTS"`e `"LTE"`.
* **Sistema operativo mobile (obsoleto)**: Utilizzare invece la dimensione del sistema [](operating-systems.md) operativo.
* **Push mobile per parlare**: Determina se il dispositivo supporta la tecnologia PTT (Push to talk), che consente al dispositivo mobile di comportarsi in modo simile alla radio bidirezionale. I dispositivi recenti in genere non segnalano questa funzione.
* **Altezza** schermo mobile: Altezza dello schermo, in pixel. Tenete presente che gli iPhone segnalano sempre `"480"` a causa dell&#39;impossibilità di determinare la versione del dispositivo iPhone. Consultate la sezione di seguito per determinare la versione del dispositivo iPhone.
* **Dimensioni** schermo mobile: Dimensioni intere del dispositivo mobile, in pixel. Le dimensioni dello schermo riportate non indicano l&#39;orientamento del dispositivo. Indipendentemente dall&#39;orientamento dello schermo, ogni dispositivo ha una risoluzione fissa dello schermo nel rapporto. Questa dimensione è basata sulla ricerca che determina quale orientamento è più probabile. Potete visualizzare dimensioni come `"768x1024"` e `"1024x768"` nello stesso rapporto con ciascuna dimensione che rappresenta uno o più dispositivi diversi.
* **Larghezza** schermo mobile: Larghezza dello schermo, in pixel.
* **Supporto** per video mobile: Formati di file video e codec supportati dal dispositivo mobile. Esistono diversi valori di dimensione per diversi codec di file MP4 e 3GPP. I valori in questa dimensione non si escludono a vicenda; un singolo hit può attribuire più valori di dimensione.

## Separazione di iPhone per modello o versione

I dispositivi mobili riportano la versione del firmware nella stringa agente utente, non nella versione del dispositivo. Ad esempio, un iPhone di generazione corrente contiene un agente utente identico all’iPhone di ultima generazione se utilizza la stessa versione firmware. Poiché non è possibile determinare la versione di un dispositivo iPhone utilizzando JavaScript, tutti gli iPhone appartengono allo stesso bucket. Le dimensioni per dispositivi mobili sono strettamente basate su ricerche che fanno riferimento all&#39;agente utente, pertanto tutti gli iPhone segnalano una dimensione dello schermo mobile pari a `320 x 480`.

Se desiderate raccogliere la versione per dispositivi iPhone, vi sono due modi per aggirare questo limite.

* **Utilizzate l&#39;SDK** iOS: L’SDK per dispositivi mobili contiene dimensioni che espongono la versione del dispositivo per l’utilizzo nei report. Questo metodo è più ideale per le app mobili che per i siti Web.
* **Utilizzare altre variabili disponibili tramite JavaScript**: Alcune variabili, come `screen.height` e `screen.width`, possono essere utilizzate per identificare la versione del dispositivo. Ad esempio, potete utilizzare il seguente frammento di codice sul vostro sito:

   ```js
   if (navigator.userAgent.indexOf('iPhone') > -1) {
     s.eVarXX = screen.width + "x" + screen.height;
     }
   ```

   Questo blocco di codice rileva prima se il dispositivo è un iPhone. In caso affermativo, il codice utilizza JavaScript per inserire la risoluzione dello schermo in una eVar. Questo metodo consente di rilevare approssimativamente la versione del dispositivo se le risoluzioni dello schermo sono univoche.
