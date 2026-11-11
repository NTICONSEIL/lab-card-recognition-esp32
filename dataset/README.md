# L2 — Jeu de données

Les images sont prises avec la caméra du boîtier lui-même, sur le support définitif. Elles ne sont pas versionnées dans Git.

**Emplacement des images** : à renseigner (espace partagé du lab).

## Classes

33 classes : les 32 cartes + `pas_de_carte`.

Nommage des dossiers : `<hauteur>_<couleur>`, par exemple `dame_coeur`, `7_pique`, `as_trefle`.

- Hauteurs : `7`, `8`, `9`, `10`, `valet`, `dame`, `roi`, `as`
- Couleurs : `pique`, `coeur`, `carreau`, `trefle`

## Protocole de prise de vue

- Au moins 50 images par classe, avec au moins deux jeux de cartes de marques différentes.
- Variations : rotation de ±15°, carte à l'endroit et retournée, trois niveaux d'éclairage, léger décalage sur le support.
- Résolution et format de capture identiques à ceux du firmware.

## Découpage

- 70 % entraînement, 15 % validation, 15 % test.
- Le jeu de test est **figé à la fin de la phase 2** et inclut un jeu de cartes jamais vu à l'entraînement.
- La liste des fichiers de chaque ensemble est versionnée dans `splits/` pour que tout le monde évalue sur les mêmes images.

## À produire

- [ ] Script de capture en série depuis l'ESP32 (`scripts/capture.py`)
- [ ] Script de découpage reproductible avec graine fixe (`scripts/split.py`)
- [ ] Fichiers `splits/train.txt`, `splits/val.txt`, `splits/test.txt`
- [ ] Statistiques : nombre d'images par classe et par jeu de cartes
