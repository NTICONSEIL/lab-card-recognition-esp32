# 0001 — Livrer deux architectures, v1 déportée puis v2 embarquée

Statut : acceptée · 11 novembre 2026

## Contexte

L'inférence embarquée sur ESP32-S3 est la plus démonstrative, mais aussi la plus risquée (mémoire, précision après quantification). Une équipe qui n'aurait que cette voie pourrait arriver en soutenance sans démonstrateur fonctionnel.

## Décision

- La v1 (image envoyée à un serveur d'inférence) doit fonctionner de bout en bout à la fin de la phase 3.
- La v2 (modèle int8 sur ESP32-S3) est développée ensuite, avec le même jeu de données et le même jeu de test.
- Les deux versions sont comparées sur la précision, la latence, la consommation et la confidentialité.

## Conséquences

- Une démonstration est garantie à mi-parcours.
- Le jeu de test doit être figé avant la phase 3 pour que la comparaison soit honnête.

## Modèle pour les prochaines décisions

Copier ce fichier en `NNNN-sujet.md` : contexte, décision, conséquences, statut.
