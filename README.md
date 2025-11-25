# 🍕 Guida di Setup Completa: Tracker pizza (ALL-IN-ONE) v2

[![Import Blueprint](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2FGiorgio866%2FTrackerpizza%2Fmain%2FTrackerpizza.yaml)

> **Blueprint per Home Assistant:** Tracciamento automatico e completo delle consegne con calcolo preciso dei tempi di viaggio/sosta e reportistica avanzata.

---

## 1. 🛠️ Preparazione: Aiutanti (Helper) Necessari

Prima di usare il Blueprint, è **obbligatorio** creare tutti i seguenti Aiutanti. Andate su **Impostazioni** > **Dispositivi e Servizi** > **Aiutanti**.

| Tipo di Aiutante | Nome Suggerito | ID Entità Risultante | Scopo |
| :--- | :--- | :--- | :--- |
| **Data e Ora (Solo Ora)** | Orario Partenza Panda | `input_datetime.orario_partenza_panda` | Memorizza l'ora di uscita dalla pizzeria. |
| **Data e Ora (Solo Ora)** | Orario Arrivo Consegna | `input_datetime.orario_arrivo_consegna` | Memorizza l'ora in cui il veicolo si ferma dal cliente. |
| **Interruttore (Boolean)** | Consegna in Corso Panda | `input_boolean.consegna_in_corso_panda` | Flag (memoria) per indicare che il veicolo è fermo in consegna. |
| **Contatore** | Consegne Giornaliere Panda | `counter.consegne_giornaliere_panda` | Contatore delle consegne effettuate oggi. |
| **Contatore** | Consegne Settimanali Panda | `counter.consegne_settimanali_panda` | Contatore totale per il report settimanale. |

---

## 2. 🗺️ Entità Base e Servizi Richiesti

Assicuratevi che queste integrazioni e sensori siano attivi e funzionanti.

| Entità Richiesta | Tipo di Entità | Esempio ID | Descrizione |
| :--- | :--- | :--- | :--- |
| **Tracciatore Veicolo** | `device_tracker` | `device_tracker.panda` | Il sensore GPS del telefono nella Panda. |
| **Sensore Indirizzo** | `sensor` | `sensor.panda_geocoded_location` | Sensore dell'App Companion che fornisce l'indirizzo testuale. |
| **Sensore Traffico** | `sensor` | `sensor.waze_travel_time` | Integrazione Waze configurata per calcolare il tempo di rientro in pizzeria. |
| **Zona Pizzeria** | `zone` | `zone.pizzeria` | Zona creata con la posizione della sede. |
| **Target Alexa** | `notify` | `notify.echo_show_di_giorgia_annuncio` | Entità di notifica dei dispositivi Alexa per gli annunci vocali. |
| **Servizio Mobile** | `notify` | `notify.mobile_app_panda` | Servizio di notifica del telefono (usato per accendere/spegnere il GPS ad alta precisione). |
| **Chat ID Telegram** | `Text` | `341280357` | Il vostro ID Chat per ricevere le notifiche. |

---

## 3. 🚀 Configurazione dell'Automazione (Blueprint)

1.  Cliccate sul badge **"Import Blueprint"** in cima a questo file (o importate manualmente con il link Raw).
2.  Andate su **Impostazioni** > **Automazioni e Scene** e cliccate su **+ Crea Automazione**.
3.  Selezionate il Blueprint **"Tracker pizza (ALL-IN-ONE) v2)"**.
4.  **Compilate tutti i campi** collegando ogni `input` al corrispettivo Helper o Entità creato nel punto 1 e 2.
    * *Suggerimento:* Scegliete l'ID `input_datetime.orario_partenza_panda` per il campo **Helper Orario Partenza**, e così via per tutti gli altri helper.
5.  Date un nome all'Automazione (es. "Gestione Logistica Panda").
6.  Cliccate su **SALVA**.

Il sistema è ora attivo e funzionante!
