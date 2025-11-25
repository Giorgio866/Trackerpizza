# 🍕 Tracker pizza (ALL-IN-ONE) v2

[![Import Blueprint](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2FGiorgio866%2FTrackerpizza%2Fmain%2FTrackerpizza.yaml)

> **Blueprint per Home Assistant: Tracciamento Completo delle Consegne.**
> Questa versione è stata creata per garantire una sintassi YAML pulita e l'importazione diretta. Gestisce il ciclo completo della consegna, inclusi calcoli di tempo, notifiche e reportistica.

---

## ✨ Funzionalità

* **Tracciamento Preciso:** Usa l'ora di partenza e l'ora di sosta (arrivo) per calcolare la durata esatta del viaggio.
* **Calcolo Sosta:** Misura il tempo di sosta dal cliente.
* **Notifiche Alexa:** Annuncia l'indirizzo di consegna e il tempo di rientro stimato (tramite Waze).
* **Reportistica:** Incrementa contatori giornalieri e settimanali.
* **Gestione Turno:** Attiva/Disattiva il GPS ad alta precisione del telefono durante l'orario di lavoro (18:00 - 23:30).
* **Report Settimanale:** Invia un riepilogo ogni Domenica sera.

---

## 🛠️ Prerequisiti (Da Creare in Home Assistant)

Assicurati che tutti i seguenti Aiutanti (Helper) siano configurati prima di importare il Blueprint.

### 1. Entità Base

| Entità | Tipo | Nome Suggerito | Scopo |
| :--- | :--- | :--- | :--- |
| **Tracker** | `device_tracker` | `device_tracker.panda` | Posizione del veicolo. |
| **Zona** | `zone` | `zone.pizzeria` | Zona della sede/pizzeria. |
| **Sensore Indirizzo**| `sensor` | `sensor.panda_geocoded_location` | Sensore dell'App HA che fornisce l'indirizzo. |
| **Sensore Traffico**| `sensor` | `sensor.waze_travel_time` | Tempo stimato di rientro (integrazione Waze). |

### 2. Aiutanti (Helper)

Questi helper devono essere creati sotto **Impostazioni** > **Dispositivi e Servizi** > **Aiutanti**.

| Tipo di Helper | Nome Suggerito | Descrizione |
| :--- | :--- | :--- |
| **Data e Ora (Solo Ora)** | `input_datetime.panda_orario_partenza` | Salva l'ora di uscita dalla pizzeria. |
| **Data e Ora (Solo Ora)** | `input_datetime.panda_orario_arrivo` | Salva l'ora di arrivo (sosta) dal cliente. |
| **Interruttore** | `input_boolean.panda_in_consegna` | Stato di memoria: indica che l'auto è ferma per consegna. |
| **Contatore** | `counter.contatore_consegne_panda` | Contatore delle consegne del giorno. |
| **Contatore** | `counter.panda_consegne_settimanali` | Contatore delle consegne della settimana. |

---

## 🚀 Importazione Finale

1.  **Assicurati che il file `Trackerpizza.yaml` sia stato salvato** e committato sul tuo repository GitHub **`Trackerpizza`**.
2.  Clicca sul badge **"Import Blueprint"** qui sopra.
3.  Se l'importazione automatica fallisce, usa l'URL Raw pulito manualmente:
    `https://raw.githubusercontent.com/Giorgio866/Trackerpizza/main/Trackerpizza.yaml`

Fammi sapere se con questo nuovo file e nome riesci a importare il Blueprint in Home Assistant!
