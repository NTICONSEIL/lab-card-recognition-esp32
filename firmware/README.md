# L4 — Firmware

| Dossier | Carte | Rôle |
| --- | --- | --- |
| [`v1-esp32cam/`](v1-esp32cam/) | ESP32-CAM (OV2640) | Capture, envoi de l'image au serveur, affichage du résultat |
| [`v2-esp32s3/`](v2-esp32s3/) | ESP32-S3 + caméra | Capture, inférence embarquée, publication MQTT, affichage |

## Secrets

Chaque firmware lit ses paramètres dans `secrets.h`, ignoré par Git. Copier `secrets.example.h` en `secrets.h` et le remplir localement.

## Mesures à fournir

Pour chaque version : latence de la pose de la carte à l'affichage du nom, consommation moyenne par reconnaissance (module INA219), mémoire utilisée.
