# Deskbot ESPHome Starter

Dieses Repository enthält einen praxisnahen ESPHome-Startpunkt für einen kleinen Desktop-Roboter auf Basis des **Waveshare ESP32-S3-Touch-AMOLED-1.75**.

## Enthalten

- `deskbot.yaml`: vollständige ESPHome-Konfiguration mit
  - animierten Augen
  - Idle-Bewegung und Blinzeln
  - Touch-Interaktion für „Streicheln“
  - emotionalen Zuständen
  - Home-Assistant-steuerbarer Nachricht und Stimmung
  - einfacher Seiten-Navigation per Wischgeste
  - Stoppuhr- und Countdown-Seite
- `secrets.example.yaml`: Beispiel für die benötigten Secrets

## Hinweise

- Das Display nutzt laut Waveshare/ESPHome-Devices **CO5300**, **466x466**, Touch über **CST9217**.
- Achtung: Die aktuelle Stable-Version in dieser Container-Umgebung (`ESPHome 2025.7.5`) kennt das Modell `CO5300` noch nicht; dafür ist voraussichtlich eine neuere ESPHome-Version nötig.
- Für den Touch ist aktuell ein externer ESPHome-Component-Eintrag für `cst9217` nötig.
- Die Reaktion auf Erschütterungen ist im YAML bereits als State-Logik vorgesehen; für echte IMU-Events ist zusätzlich ein QMI8658-External-Component sinnvoll.
- Die Konfiguration ist als solide Basis gedacht und sollte im eigenen Home-Assistant-/ESPHome-Setup weiter angepasst werden.

## Schnellstart

1. `secrets.example.yaml` nach `secrets.yaml` kopieren.
2. WLAN/API-Daten eintragen.
3. `deskbot.yaml` in ESPHome importieren.
4. Kompilieren, flashen, feinjustieren.

## Home Assistant Entities

Nach dem Flashen stehen u. a. diese Entitäten zur Verfügung:

- `text.deskbot_face_message`
- `select.deskbot_emotion`
- `button.deskbot_startle`
- `button.deskbot_laugh`
- `button.deskbot_stopwatch_toggle`
- `button.deskbot_stopwatch_reset`
- `button.deskbot_countdown_start`
- `button.deskbot_countdown_stop`
- `number.deskbot_countdown_minutes`

## Geplante sinnvolle Erweiterungen

- QMI8658-Anbindung für echte Schock-/Neigungs-Erkennung
- Audio-Ausgabe für Kichern über Lautsprecher/Ringtone/RTTTL
- zusätzliche „Apps“ auf weiteren Seiten
- Home-Assistant-Automationen für Benachrichtigungen und Stimmungen
