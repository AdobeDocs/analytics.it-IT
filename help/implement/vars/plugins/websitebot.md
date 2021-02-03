---
title: websiteBot
description: Identificare dinamicamente i bot utilizzando il movimento del mouse.
translation-type: tm+mt
source-git-commit: 7c130a1b79c9ab1b60773f51f1679249bfa338be
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 1%

---


#  plug-in di Adobe: websiteBot

>[!IMPORTANT]
>
>Questo plug-in è fornito da  Adobe Consulting come una cortesia per aiutarvi a ottenere più valore da  Adobe Analytics. &#39;Assistenza clienti di Adobe non fornisce supporto con questo plug-in, inclusa l&#39;installazione o la risoluzione dei problemi. Se avete bisogno di aiuto con questo plug-in, contattate l&#39;Account Manager della vostra azienda. Possono organizzare una riunione con un consulente per assistenza.

Il plug-in `websiteBot` consente di identificare dinamicamente se i visitatori del desktop sono bot. Puoi utilizzare questi dati per ottenere una maggiore precisione in tutti i tipi di reporting, il che ti offre un modo migliore per misurare il traffico legittimo del sito.

Questo plug-in esegue due verifiche:

* In primo luogo, determina se il dispositivo è un desktop o un dispositivo mobile che utilizza la variabile `navigator.UserAgent`. I dispositivi mobili vengono ignorati.
* Se si tratta di un dispositivo desktop, aggiunge un listener di eventi per il movimento del mouse.

Se l&#39;agente utente si trova su un desktop e non viene rilevato alcun movimento del mouse, il plug-in imposta la variabile `websiteBot` su `true`. Se l&#39;agente utente è un dispositivo mobile o se viene rilevato un movimento del mouse, il plug-in imposta la variabile `websiteBot` su `false`.

## Prerequisiti

 Adobe consiglia quanto segue prima di utilizzare questo plug-in:

* **Configurare  impostazioni** eVar: Configurate un eVar  nelle variabili  [Conversion (Conversione) ](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) nelle impostazioni della suite Report. Impostare la scadenza su **&quot;Visitor&quot;** e l&#39;allocazione su **&quot;Original Value (First)&quot;**.
* **Raccogliere l’agente utente in una variabile** separata: Raccogliere la stringa agente utente in una variabile separata per monitorare l&#39;efficacia di questo plug-in. Impostate un eVar  su `navigator.UserAgent` per ogni hit per raccogliere i dati.

## Installare il plug-in utilizzando l&#39;editor di codice personalizzato Launch

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
1. Fate clic sulla proprietà desiderata.
1. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante [!UICONTROL Configure] sotto l&#39;estensione Adobe Analytics .
1. Espandere il [!UICONTROL Configure tracking using custom code] Accordion, che mostra il pulsante [!UICONTROL Open Editor].
1. Aprite l’editor di codice personalizzato e incollate il codice plug-in fornito di seguito nella finestra di modifica.
1. Salvate e pubblicate le modifiche all&#39;estensione Analytics.

## Installare il plug-in utilizzando AppMeasurement

Copiate e incollate il seguente codice in qualsiasi punto del file AppMeasurement dopo la creazione dell&#39;istanza dell&#39;oggetto di tracciamento di Analytics (utilizzando [`s_gi`](../functions/s-gi.md)). Mantenendo i commenti e i numeri di versione del codice nell’implementazione,  Adobe può risolvere eventuali problemi.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: websiteBot BETA v0.1 */
websiteBot=true;if(!/(android|bb\d+|meego).+mobile|avantgo|bada\/|blackberry|blazer|compal|elaine|fennec|hiptop|iemobile|ip(hone|od)|ipad|iris|kindle|Android|Silk|lge |maemo|midp|mmp|netfront|opera m(ob|in)i|palm( os)?|phone|p(ixi|re)\/|plucker|pocket|psp|series(4|6)0|symbian|treo|up\.(browser|link)|vodafone|wap|windows (ce|phone)|xda|xiino/i.test(navigator.userAgent)||/1207|6310|6590|3gso|4thp|50[1-6]i|770s|802s|a wa|abac|ac(er|oo|s\-)|ai(ko|rn)|al(av|ca|co)|amoi|an(ex|ny|yw)|aptu|ar(ch|go)|as(te|us)|attw|au(di|\-m|r |s )|avan|be(ck|ll|nq)|bi(lb|rd)|bl(ac|az)|br(e|v)w|bumb|bw\-(n|u)|c55\/|capi|ccwa|cdm\-|cell|chtm|cldc|cmd\-|co(mp|nd)|craw|da(it|ll|ng)|dbte|dc\-s|devi|dica|dmob|do(c|p)o|ds(12|\-d)|el(49|ai)|em(l2|ul)|er(ic|k0)|esl8|ez([4-7]0|os|wa|ze)|fetc|fly(\-|_)|g1 u|g560|gene|gf\-5|g\-mo|go(\.w|od)|gr(ad|un)|haie|hcit|hd\-(m|p|t)|hei\-|hi(pt|ta)|hp( i|ip)|hs\-c|ht(c(\-| |_|a|g|p|s|t)|tp)|hu(aw|tc)|i\-(20|go|ma)|i230|iac( |\-|\/)|ibro|idea|ig01|ikom|im1k|inno|ipaq|iris|ja(t|v)a|jbro|jemu|jigs|kddi|keji|kgt( |\/)|klon|kpt |kwc\-|kyo(c|k)|le(no|xi)|lg( g|\/(k|l|u)|50|54|\-[a-w])|libw|lynx|m1\-w|m3ga|m50\/|ma(te|ui|xo)|mc(01|21|ca)|m\-cr|me(rc|ri)|mi(o8|oa|ts)|mmef|mo(01|02|bi|de|do|t(\-| |o|v)|zz)|mt(50|p1|v )|mwbp|mywa|n10[0-2]|n20[2-3]|n30(0|2)|n50(0|2|5)|n7(0(0|1)|10)|ne((c|m)\-|on|tf|wf|wg|wt)|nok(6|i)|nzph|o2im|op(ti|wv)|oran|owg1|p800|pan(a|d|t)|pdxg|pg(13|\-([1-8]|c))|phil|pire|pl(ay|uc)|pn\-2|po(ck|rt|se)|prox|psio|pt\-g|qa\-a|qc(07|12|21|32|60|\-[2-7]|i\-)|qtek|r380|r600|raks|rim9|ro(ve|zo)|s55\/|sa(ge|ma|mm|ms|ny|va)|sc(01|h\-|oo|p\-)|sdk\/|se(c(\-|0|1)|47|mc|nd|ri)|sgh\-|shar|sie(\-|m)|sk\-0|sl(45|id)|sm(al|ar|b3|it|t5)|so(ft|ny)|sp(01|h\-|v\-|v )|sy(01|mb)|t2(18|50)|t6(00|10|18)|ta(gt|lk)|tcl\-|tdg\-|tel(i|m)|tim\-|t\-mo|to(pl|sh)|ts(70|m\-|m3|m5)|tx\-9|up(\.b|g1|si)|utst|v400|v750|veri|vi(rg|te)|vk(40|5[0-3]|\-v)|vm40|voda|vulc|vx(52|53|60|61|70|80|81|83|85|98)|w3c(\-| )|webc|whit|wi(g |nc|nw)|wmlb|wonu|x700|yas\-|your|zeto|zte\-/i.test(navigator.userAgent.substr(0,4))){document.addEventListener('mousemove',function detectMouseMove(){document.removeEventListener('mousemove',detectMouseMove,false);websiteBot=false;})}else websiteBot=false;
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

La variabile `websiteBot` è un valore booleano. Restituisce `true` se il plug-in rileva un bot; altrimenti restituisce `false`.

## Esempi

```js
// Set eVar1 to detect bots. Dimension items in reporting are "true" or "false"
s.eVar1 = websiteBot;

// Use a ternary operator to set eVar values
s.eVar1 = websiteBot ? "Bot detected" : "Not a bot";
```

## Cronologia versioni

### 0.1 (19 gennaio 2021)

* Versione beta.
