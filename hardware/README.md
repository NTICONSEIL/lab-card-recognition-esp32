# L1 — Matériel et capture

## Nomenclature

| Élément | Rôle | Qté |
| --- | --- | --- |
| Carte ESP32-S3 avec caméra et 8 Mo de PSRAM (XIAO ESP32S3 Sense ou ESP32-S3-EYE, à arbitrer) | Capture et inférence embarquée (v2) | 2 |
| ESP32-CAM (OV2640) + adaptateur USB-série | Capture seule (v1) | 2 |
| Anneau de LED blanches | Éclairage constant | 2 |
| Écran OLED 0,96 pouce I2C | Affichage du nom | 2 |
| Module INA219 | Mesure de consommation | 1 |
| Bouton, câbles, platine d'essai | Déclenchement et montage | 1 lot |

## À produire

- [ ] Schéma de câblage de chaque version (`schemas/`)
- [ ] Support imprimé en 3D : source FreeCAD et STL (`support-3d/`), distance caméra–carte documentée
- [ ] Procédure de réglage de la mise au point de l'objectif
- [ ] Photo du montage final
