---
description: Tabella di ricerca per determinare il tipo di hit in base al valore page_event.
keywords: Feed dati;pagina;evento;page_event;post_page_event
title: Ricerca eventi pagina
feature: Data Feeds
exl-id: ef0467df-b94b-4cec-b312-96d8f42c23b0
source-git-commit: 4daa5c8bdbcb483f23a3b8f75dde9eeb48516db8
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 7%

---

# Ricerca eventi pagina

Tabella di ricerca per determinare il tipo di hit in base al valore page_event.

| Tipo di hit | `page_event` valore | `post_page_event` valore |
| --- | --- | --- |
| Visualizzazioni pagina | 0: tutte le chiamate di visualizzazione pagina e `trackState` chiamate da SDK per dispositivi mobili | Stesso valore di `page_event` |
| Tracciamento dei collegamenti | 10: Collegamenti personalizzati e `trackAction` chiamate negli SDK per dispositivi mobili<br>11: Collegamenti di download<br>12: Collegamenti di uscita | 100: Collegamenti personalizzati e `trackAction` chiamate negli SDK per dispositivi mobili<br>101: Collegamenti di download<br>102: Collegamenti di uscita |
| Video su Milestone | 31: Avvio file multimediale<br>32: Aggiornamenti multimediali (nessuna altra elaborazione variabile)<br>33: Aggiornamenti multimediali (con altre variabili) | 76: Avvio file multimediale<br>77: Aggiornamenti multimediali (nessuna altra elaborazione variabile)<br>78: Aggiornamenti multimediali (con altre variabili) |
| Video Heartbeat | 50: avvio del flusso multimediale (non Primetime)<br>51: chiusura del flusso multimediale (non Primetime)<br>52: scrubbing del flusso multimediale (non Primetime)<br>53: Flusso multimediale keep alive (non Primetime)<br>54: Avvio annuncio flusso multimediale (non Primetime)<br>55: Chiusura annuncio flusso multimediale (non Primetime)<br>56: Scrubbing di annunci di flusso multimediale (non Primetime)<br>60: avvio del flusso multimediale Primetime<br>61: chiusura del flusso multimediale Primetime<br>62: scrubbing del flusso multimediale Primetime<br>63: Primetime media stream keep alive<br>64: Avvio annuncio flusso multimediale Primetime<br>65: chiusura annuncio flusso multimediale Primetime<br>66: Scrubbing degli annunci per streaming multimediale Primetime | Stesso valore di `page_event` |
| Sondaggio | 40: qualsiasi chiamata generata dal sondaggio | 80: qualsiasi chiamata generata dal sondaggio |
| Analytics for Target | 70: hit include i dati dell’attività di Target | Stesso valore di `page_event` |
