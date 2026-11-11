# Reconnaissance de cartes à jouer par vision embarquée

Projet transversal du lab — NTInstitute

Un boîtier à base d'ESP32 et de caméra photographie une carte d'un jeu de 32 cartes et annonce son nom (« Dame de cœur »). Le projet livre deux versions de la même chaîne et les compare :

- **v1 — inférence déportée** : l'ESP32-CAM envoie l'image à un serveur d'inférence (API FastAPI en Docker), qui renvoie le nom et un indice de confiance.
- **v2 — inférence embarquée** : un modèle quantifié int8 tourne sur un ESP32-S3 ; seul le résultat circule sur le réseau (MQTT).

Cahier des charges : [document de travail](https://claude.ai/artifact/DAgcwRuo1hY291it4vsapB) · résumé dans [`docs/cahier-des-charges.md`](docs/cahier-des-charges.md)

## Objectifs

1. Reconnaître les 32 cartes (7, 8, 9, 10, Valet, Dame, Roi, As × pique, cœur, carreau, trèfle) avec au moins 95 % de bonnes réponses dans les conditions du boîtier.
2. Comparer les deux architectures : précision, latence, consommation, confidentialité.
3. Livrer un démonstrateur reproductible par les promotions suivantes.

## Organisation du dépôt

| Dossier | Contenu | Lot |
| --- | --- | --- |
| [`hardware/`](hardware/) | Schémas de câblage, nomenclature, fichiers 3D du support | L1 |
| [`dataset/`](dataset/) | Protocole de prise de vue, scripts de capture et d'annotation (les images ne sont pas versionnées ici) | L2 |
| [`model/`](model/) | Entraînement, évaluation, quantification, matrice de confusion | L3 |
| [`firmware/v1-esp32cam/`](firmware/v1-esp32cam/) | Capture et envoi de l'image (v1) | L4 |
| [`firmware/v2-esp32s3/`](firmware/v2-esp32s3/) | Capture, inférence embarquée, publication MQTT (v2) | L4 |
| [`server/`](server/) | API d'inférence FastAPI (v1) | L5 |
| [`platform/`](platform/) | Pile Docker Compose : Mosquitto, Node-RED, InfluxDB, Grafana | L5 / L6 |
| [`docs/`](docs/) | Cahier des charges, décisions d'architecture, comptes rendus, rapport comparatif | Tous |

## Planning

| Phase | Semaines | Jalon de sortie |
| --- | --- | --- |
| 1. Cadrage | 1 et 2 | Images nettes depuis le support |
| 2. Données | 3 et 4 | Jeu de test figé |
| 3. v1 déportée | 5 et 6 | **v1 de bout en bout** |
| 4. v2 embarquée | 7 et 8 | v2 sur ESP32-S3 |
| 5. Mesures | 9 et 10 | Démo validée, rapport, soutenance |

Chaque phase correspond à un *milestone* GitHub ; chaque tâche est une *issue* rattachée à un lot (label `L1` à `L6`).

## Démarrage rapide

```bash
git clone https://github.com/NTICONSEIL/lab-card-recognition-esp32.git
cd lab-card-recognition-esp32
cp platform/.env.example platform/.env   # renseigner les mots de passe, jamais commités
docker compose -f platform/docker-compose.yml up -d
```

Les instructions propres à chaque brique sont dans le README de son dossier.

## Contribuer

Lire [`CONTRIBUTING.md`](CONTRIBUTING.md) : une branche par issue, une pull request relue par un membre d'un autre lot, aucun identifiant dans le code.

## Licence

Code sous licence MIT (voir [`LICENSE`](LICENSE)). Licence du jeu de données à décider (voir les points à arbitrer du cahier des charges).
