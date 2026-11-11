# Cahier des charges — résumé

Version validée le 11 novembre 2026. Document de travail complet : https://claude.ai/artifact/DAgcwRuo1hY291it4vsapB

## Périmètre

Une carte à la fois, posée face visible sur un support fixe. La reconnaissance d'une main entière ou d'une carte tenue à la main reste une extension.

**Fonctionnalités** : détection de la carte et capture, reconnaissance avec indice de confiance (« carte non reconnue » sous un seuil), affichage sur écran OLED et tableau de bord web, historique horodaté.

## Livrables

| Livrable | Échéance |
| --- | --- |
| Dossier de conception | Fin de la phase 1 |
| Jeu de données annoté et découpé | Fin de la phase 2 |
| Démonstrateur v1 (inférence déportée) | Fin de la phase 3 |
| Démonstrateur v2 (inférence embarquée sur ESP32-S3) | Fin de la phase 4 |
| Rapport comparatif v1 / v2 | Fin de la phase 5 |
| Dépôt Git reproductible | Continu |
| Soutenance avec démonstration en direct | Fin de la phase 5 |

## Lots de travail

| Lot | Contenu |
| --- | --- |
| L1. Matériel et capture | Carte, caméra, alimentation, éclairage, support 3D, mise au point |
| L2. Jeu de données | Prise de vue, annotation, augmentation, découpage |
| L3. Modèle | Entraînement, décomposition des classes, quantification, évaluation |
| L4. Embarqué | Firmware v1 et v2, mesures de latence et de consommation |
| L5. Communication et plateforme | HTTP / MQTT, serveur d'inférence, tableau de bord |
| L6. Sécurité | Authentification de l'objet, TLS, gestion des secrets |

## Critères de réussite

- Au moins 95 % de bonnes réponses sur le jeu de test figé, qui inclut un jeu de cartes jamais vu à l'entraînement.
- Latence de bout en bout, consommation par reconnaissance et taille du modèle mesurées pour les deux versions.
