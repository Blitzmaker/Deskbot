# ESPHome Projekt: Robot Eyes für Waveshare ESP32-S3 Touch AMOLED 1.75

Dieses Projekt zeigt animierte Roboter-Augen auf dem AMOLED-Display und erlaubt Interaktionen über den Touchscreen.

## Features

- Ruhige Augenbewegung im Idle
- Zufällige spontane Emotionen (Freude / Aufregung)
- Blinzeln in zufälligen Intervallen
- Touch-Interaktion:
  - Links tippen → Freude
  - Rechts tippen → Aufregung
  - Mitte tippen → Blinzeln
- Home-Assistant-Integration über:
  - `button` Entitäten (`Emotion Freude`, `Emotion Aufregung`, `Zur Ruhe`)
  - `select` Entität (`Augenmodus`)

## Dateien

- `robot_eyes.yaml`: Hauptkonfiguration für ESPHome

## Wichtige Hinweise zu Pins

Die Display-/Touch-Pins können je nach Board-Revision variieren. In `robot_eyes.yaml` sind sinnvolle Startwerte hinterlegt, die du mit dem Waveshare-Wiki gegenprüfen solltest:

- Touch I2C: `touch_sda_pin`, `touch_scl_pin`
- Touch IRQ/Reset: `touch_int_pin`, `touch_rst_pin`
- Display QSPI: `cs_pin`, `reset_pin`

## Nutzung

1. Datei in dein ESPHome-Projekt übernehmen.
2. WLAN/Secrets ergänzen.
3. Pins gemäß Wiki anpassen.
4. Flashen:

```bash
esphome run robot_eyes.yaml
```

Danach erscheint das Gerät in Home Assistant (via ESPHome API), und du kannst die Emotionen auch per Automation setzen.
