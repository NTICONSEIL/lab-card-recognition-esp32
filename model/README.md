# L3 — Modèle

## Choix à documenter (dans `docs/decisions/`)

- Classifieur unique à 33 sorties, ou deux têtes : hauteur (8) et couleur (4).
- Image entière, ou recadrage sur l'index du coin.
- Résolution d'entrée : plus grande pour la v1 (serveur), 96×96 environ pour la v2 (ESP32-S3).

## Évaluation

Toujours sur `dataset/splits/test.txt`, jamais sur la validation :

- taux de bonnes réponses global et par carte ;
- matrice de confusion 33 × 33 (surveiller cœur / carreau, pique / trèfle, 7 / 8, figures entre elles) ;
- pour la v2 : taille du modèle en Ko et perte de précision due à la quantification int8.

Les résultats sont consignés dans `results/` (un fichier par expérience, avec la date, le commit et les hyperparamètres).

## Livraison des modèles

Les poids ne sont pas commités : ils sont publiés en *release* GitHub, avec le numéro du commit qui les a produits.

## Installation

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```
